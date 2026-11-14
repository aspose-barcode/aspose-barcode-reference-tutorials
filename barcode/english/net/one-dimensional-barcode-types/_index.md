---
title: Generate One-Dimensional Barcodes with Aspose.BarCode .NET
linktitle: One-Dimensional Barcode Types
second_title: Aspose.BarCode .NET API
description: Learn how to generate barcode in .NET with Aspose.BarCode, how to adjust height, handle errors, configure wide narrow ratio, and work with barcode aspect ratio.
weight: 25
url: /net/one-dimensional-barcode-types/
date: 2026-02-22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# One-Dimensional Barcode Types

## Introduction

Are you eager to learn **how to generate barcode** images in .NET using one‑dimensional barcode types? In this comprehensive tutorial we’ll walk through the most popular 1‑D symbologies, show you how to adjust height, handle errors, and fine‑tune the wide‑narrow ratio—all with the **Aspose.BarCode .NET** library. Let’s embark on this exciting journey into barcode customization!

## Quick Answers
- **What library should I use?** Aspose.BarCode for .NET  
- **Can I adjust barcode height?** Yes – use the `BarHeight` property  
- **How do I handle generation errors?** Wrap the code in a try‑catch block and inspect `BarCodeException`  
- **What is the wide‑narrow ratio?** It controls the relative width of wide vs. narrow bars in 1‑D codes  
- **Is Aspose.BarCode .NET compatible with .NET 6?** Absolutely, it supports .NET Framework 4.5+ and .NET Core/5/6+

## What is “how to generate barcode” in .NET?
Generating a barcode means creating a visual representation of data that scanners can read. With Aspose.BarCode you can produce PNG, JPEG, SVG, or PDF outputs directly from your C# or VB.NET code, without any external dependencies.

## Why use Aspose.BarCode .NET?
- **Full‑featured API** – supports over 40 one‑dimensional and two‑dimensional symbologies.  
- **No external services** – everything runs locally, guaranteeing data privacy.  
- **Fine‑grained control** – adjust size, aspect ratio, colors, and error handling programmatically.  

## The power of one-Dimensional barcodes

One‑dimensional barcodes are the foundation of data encoding, providing a simple and efficient way to store information. These barcodes are commonly used for tasks like inventory management, retail, and shipping. In this tutorial series, we'll focus on the most popular one‑dimensional barcode types and how to configure them.

## How to Generate Barcode: Code 128 Configuration

First up, let's dive into **Code 128**. This versatile barcode type can encode various data, making it a favorite among developers. With Aspose.BarCode, you'll find a seamless integration process. Follow our step‑by‑step guide to get started.

```csharp
using Aspose.BarCode.Generation;

var generator = new BarcodeGenerator(EncodeTypes.Code128, "123456789");
generator.Parameters.Barcode.XDimension = 0.8; // narrow bar width
generator.Parameters.Barcode.BarHeight = 50;
generator.Save("code128.png", BarCodeImageFormat.Png);
```

## How to Generate Barcode: Code 39 Configuration

If you need to generate **Code 39** barcodes, Aspose.BarCode has you covered. This barcode type is widely used in various applications, from industrial to healthcare. Developers can count on our step‑by‑step guide for a smooth setup.

## How to Generate Barcode: Code 93 Configuration

Now, let's move on to **Code 93**. With Aspose.BarCode for .NET, you can create these barcodes effortlessly. Our step‑by‑step guide will ensure you're on the right track.

## How to Adjust Height of One‑Dimensional Barcodes

Barcode customization is a breeze with Aspose.BarCode. Learn **how to adjust height** of one‑dimensional barcodes, ensuring precision in your designs. Your barcodes will be tailor‑made to meet your specific requirements.

## Databar and GS1 Encoding

Are you looking to create Databar GS1 encoded barcodes? Aspose.BarCode simplifies the process. Our step‑by‑step guide guarantees a straightforward experience.

## Dynamic row and column configuration

For dynamic one‑dimensional DataBar barcodes, our guide on row and column configuration will be your best companion. Aspose.BarCode ensures that customization is within reach.

## How to Handle Errors While Generating Barcodes

Even the most experienced developers face challenges. Learn **how to handle errors** effectively while generating one‑dimensional barcodes. Aspose.BarCode is your go‑to solution for error‑tolerant barcode creation.

## Wide‑Narrow ratio configuration

We'll explore the **wide‑narrow ratio** configuration for one‑dimensional barcodes. Customize your barcodes easily and efficiently with the guidance of Aspose.BarCode.

## Barcode aspect ratio customization

Understanding the **barcode aspect ratio** helps you create legible, scanner‑friendly images. This section shows you how to tweak aspect ratios for optimal readability.

## One-Dimensional barcode types tutorials
### [One-Dimensional code 128 configuration]({{< relref "one-dimensional-code-128-configuration/_index.md" >}})
Learn how to generate one-dimensional Code 128 barcodes in .NET using Aspose.BarCode. Follow our step-by-step guide for seamless barcode integration.
### [One-Dimensional code 39 configuration]({{< relref "one-dimensional-code-39-configuration/_index.md" >}})
Learn how to generate one-dimensional Code 39 barcodes in .NET with Aspose.BarCode. Step-by-step guide for developers.
### [One-Dimensional code 93 configuration]({{< relref "one-dimensional-code-93-configuration/_index.md" >}})
Learn how to create Code 93 barcodes with Aspose.BarCode for .NET. Step-by-step guide for barcode generation.
### [One-Dimensional barcode height adjustment]({{< relref "one-dimensional-barcode-height-adjustment/_index.md" >}})
Learn how to adjust the height of one-dimensional barcodes in .NET with Aspose.BarCode for precise customization. Create perfect barcodes effortlessly!
### [One-Dimensional databar 2D component configuration]({{< relref "one-dimensional-databar-2d-component-configuration/_index.md" >}})
Generate One-Dimensional Databar 2D barcodes with Aspose.BarCode for .NET. Follow our step-by-step guide for configuration and customization. Start creating unique barcodes today!
### [One-Dimensional databar aspect ratio customization]({{< relref "one-dimensional-databar-aspect-ratio-customization/_index.md" >}})
Learn how to customize One-Dimensional DataBar aspect ratios in .NET using Aspose.BarCode. Enhance barcode precision and design.
### [One-Dimensional databar barcode height adjustment]({{< relref "one-dimensional-databar-barcode-height-adjustment/_index.md" >}})
Learn how to adjust One-Dimensional Databar barcode height with Aspose.BarCode for .NET. Create custom barcodes in a few simple steps. Explore the power of barcode customization.
### [One-Dimensional databar GS1 encoding]({{< relref "one-dimensional-databar-gs1-encoding/_index.md" >}})
Learn to create Databar GS1 encoded barcodes in .NET using Aspose.BarCode. Generate barcodes with ease. Follow our step-by-step guide.
### [One-Dimensional databar row and column configuration]({{< relref "one-dimensional-databar-row-column-configuration/_index.md" >}})
Generate dynamic one-dimensional DataBar barcodes with row and column configuration in .NET using Aspose.BarCode for .NET. Customization made easy!
### [One-Dimensional filled bars configuration]({{< relref "one-dimensional-filled-bars-configuration/_index.md" >}})
Earn how to generate barcodes in .NET with Aspose.BarCode for .NET. This comprehensive tutorial covers everything from importing namespaces to creating one-dimensional barcodes. 
### [One-Dimensional barcode exception handling]({{< relref "one-dimensional-barcode-exception-handling/_index.md" >}})
Learn how to handle exceptions while generating one-dimensional barcodes using Aspose.BarCode for .NET. This step-by-step guide ensures error-tolerant barcode solutions. Get started now!
### [One-Dimensional wide-Narrow ratio configuration]({{< relref "one-dimensional-wide-narrow-ratio-configuration/_index.md" >}})
Generate customized barcodes easily with Aspose.BarCode for .NET. Step-by-step guide for one-dimensional wide-narrow ratio configuration.
### [How to set barcode in C# – complete Aspose.BarCode guide]({{< relref "how-to-set-barcode-in-c-complete-aspose-barcode-guide/_index.md" >}})
Learn how to set up barcode generation in C# using Aspose.BarCode with a complete step‑by‑step guide.
### [Read barcode from image – C# barcode reader example]({{< relref "read-barcode-from-image-c-barcode-reader-example/_index.md" >}})
Learn how to read barcodes from images in C# using Aspose.BarCode .NET with a step‑by‑step example.
### [Read barcode from image in C# – BarCodeReader tutorial]({{< relref "read-barcode-from-image-in-c-barcodereader-tutorial/_index.md" >}})
Learn how to read barcodes from images in C# using Aspose.BarCodeReader. Follow our step‑by‑step guide for easy implementation.
### [How to read barcode images in C# – full example guide]({{< relref "how-to-read-barcode-images-in-c-full-example-guide/_index.md" >}})
Full example guide on reading barcode images in C# using Aspose.BarCode, covering setup, decoding, and error handling.
### [Read barcode from image in C# – BarCodeReader tutorial]({{< relref "read-barcode-from-image-in-c-barcodereader-tutorial/_index.md" >}})
Learn how to read barcodes from images in C# using Aspose.BarCodeReader. Follow our step‑by‑step guide for easy implementation.
### [How to read barcode from image in C# using Aspose.BarCode]({{< relref "how-to-read-barcode-from-image-in-c-using-aspose-barcode/_index.md" >}})
Learn how to read barcodes from images in C# using Aspose.BarCode with a step‑by‑step guide.
### [How to read barcodes from image using C# – step‑by‑step guide]({{< relref "how-to-read-barcodes-from-image-using-c-step-by-step-guide/_index.md" >}})
Step‑by‑step guide to reading barcodes from images in C# with Aspose.BarCode, covering setup, decoding, and error handling.
### [Generate barcode from text using Aspose.BarCode – C# Guide]({{< relref "generate-barcode-from-text-using-aspose-barcode-c-guide/_index.md" >}})
Learn how to generate a barcode from text in C# using Aspose.BarCode. Follow our step‑by‑step guide for quick implementation.
### [How to generate barcode with custom text using Aspose.BarCode for .NET]({{< relref "how-to-generate-barcode-with-custom-text-using-aspose-barcod/_index.md" >}})
Learn how to generate barcodes with custom text in .NET using Aspose.BarCode. Step‑by‑step guide for developers.
### [How to Generate Barcode in C# – Complete Programming Guide]({{< relref "how-to-generate-barcode-in-c-complete-programming-guide/_index.md" >}})
Comprehensive guide to generating barcodes in C# using Aspose.BarCode, covering setup, encoding options, and customization.
### [How to generate a barcode with special characters in C#]({{< relref "how-to-generate-a-barcode-with-special-characters-in-c/_index.md" >}})
Learn how to generate barcodes with special characters in C# using Aspose.BarCode, with clear step‑by‑step instructions.
### [How to set barcode parameters in C# using Aspose.Barcode]({{< relref "how-to-set-barcode-parameters-in-c-using-aspose-barcode/_index.md" >}})
### [How to generate barcode with Aspose in C#]({{< relref "how-to-generate-barcode-with-aspose-in-c/_index.md" >}})
Learn how to generate barcodes in C# using Aspose.BarCode with a step‑by‑step guide.
### [How to save barcode as an image using Aspose.BarCode for .NET]({{< relref "how-to-save-barcode-as-an-image-using-aspose-barcode-for-net/_index.md" >}})
Learn how to save generated barcodes as image files using Aspose.BarCode for .NET, with step‑by‑step instructions.

## Frequently asked questions

**Q: Can I generate barcodes in formats other than PNG?**  
A: Yes, Aspose.BarCode supports JPEG, SVG, PDF, and BMP outputs.

**Q: How do I change the barcode's foreground and background colors?**  
A: Use the `ForeColor` and `BackColor` properties of the `BarCodeGenerator` object.

**Q: What should I do if the generated barcode is not scannable?**  
A: Verify the `BarHeight`, `XDimension`, and `WideNarrowRatio` settings, and ensure the image resolution is at least 300 dpi.

**Q: Is there a limit to the data length for Code 128?**  
A: Code 128 can encode up to 48 characters in a single barcode, but you can split longer data into multiple barcodes if needed.

**Q: Does Aspose.BarCode .NET require a license for development?**  
A: A free temporary license is available for evaluation; a full license is required for production use.

## Conclusion

In this tutorial series, we've delved into the world of one‑dimensional barcode types, focusing on their configuration and customization. With **Aspose.BarCode for .NET**, the process is made simple, ensuring that you can create barcodes tailored to your needs. Whether you're a seasoned developer or just starting, these tutorials will empower you to harness the power of one‑dimensional barcodes in your .NET projects. Get started now and unleash the potential of barcode technology!

With this article, you'll not only gain knowledge about various one‑dimensional barcode types but also have the confidence to implement them in your projects. Happy coding!

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}