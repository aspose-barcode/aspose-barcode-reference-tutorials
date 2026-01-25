---
title: Create Barcode PNG using Aspose.BarCode for .NET – DataMatrix Bytes
linktitle: DataMatrix Encoding Mode (Bytes)
second_title: Aspose.BarCode .NET API
description: Learn how to create barcode PNG files with Aspose.BarCode for .NET by encoding DataMatrix in Bytes mode. Follow this barcode generation guide for easy implementation.
weight: 15
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
date: 2026-01-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Barcode PNG – DataMatrix Encoding in Bytes with Aspose.BarCode for .NET

In this tutorial you’ll learn **how to create barcode PNG** images using Aspose.BarCode for .NET. We’ll walk through the complete **barcode generation guide** for DataMatrix — specifically the Bytes encoding mode—so you can generate, display, and read DataMatrix barcodes in your .NET applications.

## Quick Answers
- **What does “create barcode PNG” mean?** It refers to generating a raster PNG image that contains a barcode.
- **Which library is best for this?** Aspose.BarCode for .NET provides a full‑featured API for barcode creation and recognition.
- **Do I need a license?** A free trial works for development; a commercial license is required for production.
- **Can I read the barcode back?** Yes, the same library includes a BarCodeReader to **read DataMatrix barcode** data.
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## How to create barcode PNG with Aspose.BarCode for .NET
Below you’ll find everything you need—from prerequisites to a step‑by‑step code walkthrough—that will let you **generate a PNG barcode**, set display text, and verify the result with the built‑in reader.

## Prerequisites

Before we dive into the encoding process, you'll need to have the following prerequisites in place:

1. Aspose.BarCode for .NET: To get started, you must have the Aspose.BarCode for .NET library installed. You can download it from [here](https://releases.aspose.com/barcode/net/).

2. Your Development Environment: Make sure you have a development environment set up, including Visual Studio or any other IDE of your choice.

3. Basic Knowledge of C#: This tutorial assumes you have a basic understanding of C# programming.

With these prerequisites in place, you're ready to start encoding data in the DataMatrix format using Bytes mode.

## Import Namespaces

To use Aspose.BarCode for .NET, you'll need to import the necessary namespaces into your C# code. Add the following lines to the top of your code file:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Now, let's break down the process of encoding data in the DataMatrix format using Bytes mode into multiple steps.

## Step 1: Initialize the BarcodeGenerator

Create a BarcodeGenerator object, specifying the EncodeType as DataMatrix, and the data you want to encode. You can replace `"Your Directory Path"` with the actual path where you want to save the barcode image.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## Step 2: Set DataMatrix Encode Mode to Bytes

Set the DataMatrix encoding mode to Bytes using the following code:

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

## Step 3: Set Display Text

You can set the display text for your barcode. In this example, we've set it to "Bytes mode."

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

## Step 4: Save the Barcode Image

Save the generated barcode image to the specified path. In this case, it's saved as "DataMatrixEncodeModeBytes.png."

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

## Step 5: Try to Recognize

Now, let's attempt to recognize the encoded DataMatrix barcode. We'll use the BarCodeReader to do this.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

## Step 6: Iterate and Display Results

Iterate through the results and display the encoded data.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

With these steps, you've successfully **created a barcode PNG** in DataMatrix Bytes mode with Aspose.BarCode for .NET. This powerful library simplifies barcode generation and recognition, making it an essential tool for developers.

Now, you're ready to integrate barcode encoding and decoding into your .NET applications with ease, thanks to Aspose.BarCode.

## Conclusion

In this tutorial, we've explored how to use Aspose.BarCode for .NET to **create barcode PNG** files in the DataMatrix format using Bytes mode. By following these simple steps, you can enhance your applications with robust barcode generation and recognition capabilities. If you run into any issues, the Aspose.BarCode community is ready to help.

If you have any questions or face any issues, don't hesitate to seek assistance from the Aspose.BarCode community at [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

## FAQ's

### Q1: What is DataMatrix encoding mode?

A1: DataMatrix encoding mode is a method used to encode data into a 2D barcode format. It provides various encoding options, including Bytes mode, which is suitable for encoding binary data.

### Q2: How can I get a free trial of Aspose.BarCode for .NET?

A2: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.BarCode for .NET?

A3: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).

### Q4: Is Aspose.BarCode for .NET suitable for commercial use?

A4: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase a license from [here](https://purchase.aspose.com/buy).

### Q5: Can I use a temporary license for Aspose.BarCode for .NET?

A5: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from [here](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: How do I **read DataMatrix barcode** after creating it?**  
A: Use the `BarCodeReader` class with `DecodeType.DataMatrix` as shown in Step 5 and Step 6 of the code example.

**Q: Can I change the size of the generated PNG?**  
A: Yes, adjust `gen.Parameters.Barcode.XDimension.Pixels` or set `ImageWidth` and `ImageHeight` parameters before calling `Save`.

**Q: What if I need to encode text instead of bytes?**  
A: Switch the encode mode to `DataMatrixEncodeMode.Text` and provide the string you want to encode.

**Q: Is there a way to hide the human‑readable text on the barcode?**  
A: Set `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = false` to hide the display text.

**Q: Does Aspose.BarCode support .NET Core?**  
A: Absolutely— the library works with .NET Core, .NET 5, .NET 6, and later versions.

---

**Last Updated:** 2026-01-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}