---
id: cancellation
url: conversion/java/cancellation
title: Cancellation
linkTitle: Cancellation
weight: 6
description: "Cancel document conversions using cancellation tokens in GroupDocs.Conversion for Java."
keywords: Cancel conversion, conversion timeout, CancellationToken, CancellationTokenSource
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
draft: true
---

<!-- Publication gate: the local 26.10 source exposes CancellationToken and
CancellationTokenSource, but the installed Maven 26.10 JAR does not expose
these public class names. Compile and run these examples against the release
artifact after correcting API obfuscation before removing draft: true. -->

GroupDocs.Conversion for Java provides a cancellation signal that you can pass to a conversion. Use it to request cancellation from another thread or after a timeout.

Create a `com.groupdocs.conversion.CancellationTokenSource`, pass its `getToken()` result to `convert`, and call `cancel()` to request cancellation. Catch `java.util.concurrent.CancellationException` to handle the result.

Cancellation is cooperative. Requesting cancellation does not forcibly interrupt an operation already running. The conversion call can return before that operation finishes, and output already written is not rolled back. Use a separate output path for each conversion and do not immediately reuse its resources after cancellation.

## Set a conversion timeout

Java's `CancellationTokenSource` does not provide a `CancelAfter` method. Schedule `cancel()` using `ScheduledExecutorService` instead. Cancel the scheduled task when conversion finishes and shut down the scheduler.

```java
import com.groupdocs.conversion.CancellationTokenSource;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.util.concurrent.CancellationException;
import java.util.concurrent.Executors;
import java.util.concurrent.ScheduledExecutorService;
import java.util.concurrent.ScheduledFuture;
import java.util.concurrent.TimeUnit;

public class ConvertWithTimeout {
    public static void main(String[] args) {
        CancellationTokenSource cancellation = new CancellationTokenSource();
        ScheduledExecutorService scheduler = Executors.newSingleThreadScheduledExecutor();
        ScheduledFuture<?> timeout = scheduler.schedule(cancellation::cancel, 60, TimeUnit.SECONDS);

        try (Converter converter = new Converter("sample.dwg")) {
            converter.convert("converted.pdf", new PdfConvertOptions(), cancellation.getToken());
        } catch (CancellationException e) {
            System.out.println("Conversion was cancelled or timed out.");
        } finally {
            timeout.cancel(false);
            scheduler.shutdownNow();
        }
    }
}
```

The timeout requests cancellation after 60 seconds; it is not a hard deadline for stopping all work. Reuse of a cancelled token immediately cancels another conversion. Create a new token source for each independent operation.

## Request cancellation manually

Keep the token source accessible to the code handling a user action. The following example simulates that action by requesting cancellation after ten seconds while conversion runs on another thread.

```java
import com.groupdocs.conversion.CancellationTokenSource;
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.util.concurrent.CancellationException;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class CancelConversionManually {
    public static void main(String[] args) throws Exception {
        CancellationTokenSource cancellation = new CancellationTokenSource();
        ExecutorService worker = Executors.newSingleThreadExecutor();
        try {
            Future<?> conversion = worker.submit(() -> {
                try (Converter converter = new Converter("large-document.dwg")) {
                    converter.convert("converted.pdf", new PdfConvertOptions(), cancellation.getToken());
                } catch (CancellationException e) {
                    System.out.println("Conversion was cancelled by the user.");
                }
            });

            Thread.sleep(10000);
            cancellation.cancel();
            conversion.get();
        } finally {
            cancellation.cancel();
            worker.shutdown();
        }
    }
}
```

Calling `cancel()` is thread-safe and does not wait for the conversion to finish. Unlike a .NET token source, the Java token source does not require disposal.

## Use fluent syntax

The final `convert` call of the fluent chain also accepts a cancellation token:

```java
import com.groupdocs.conversion.CancellationTokenSource;
import com.groupdocs.conversion.fluent.FluentConverter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import java.util.concurrent.CancellationException;
import java.util.concurrent.Executors;
import java.util.concurrent.ScheduledExecutorService;
import java.util.concurrent.ScheduledFuture;
import java.util.concurrent.TimeUnit;

public class CancelFluentConversion {
    public static void main(String[] args) {
        CancellationTokenSource cancellation = new CancellationTokenSource();
        ScheduledExecutorService scheduler = Executors.newSingleThreadScheduledExecutor();
        ScheduledFuture<?> timeout = scheduler.schedule(cancellation::cancel, 60, TimeUnit.SECONDS);
        try {
            FluentConverter.load("sample.dwg")
                    .convertTo("converted.pdf")
                    .withOptions(new PdfConvertOptions())
                    .convert(cancellation.getToken());
        } catch (CancellationException e) {
            System.out.println("Conversion was cancelled or timed out.");
        } finally {
            timeout.cancel(false);
            scheduler.shutdownNow();
        }
    }
}
```
