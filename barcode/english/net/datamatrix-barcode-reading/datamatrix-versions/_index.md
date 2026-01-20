---
title: Generate DataMatrix barcodes with datamatrix error correction
linktitle: DataMatrix Versions
second_title: Aspose.BarCode .NET API
description: Learn how to generate DataMatrix barcodes with datamatrix error correction in .NET using Aspose.BarCode. Find out how to generate barcode quickly.
weight: 12
url: /net/datamatrix-barcode-reading/datamatrix-versions/
date: 2026-01-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate DataMatrix barcodes with datamatrix error correction using Aspose.BarCode for .NET

If you're looking for a reliable solution to generate DataMatrix barcodes in your .NET applications, Aspose.BarCode for .NET is the way to go. In this step‑by‑step guide, we'll walk you through **how to generate barcode** with full support for **datamatrix error correction**, so you can create robust, scannable symbols for a variety of business scenarios.

## Quick Answers
- **What library supports datamatrix error correction?** Aspose.BarCode for .NET
- **Which ECC level gives the strongest protection?** Ecc140 (offers higher redundancy)
- **How many lines of code are needed?** Less than 20 lines for a basic barcode
- **Can I customize rows and columns?** Yes – set the DataMatrix version manually
- **Is a license required for production?** Yes, a commercial license is needed

## datamatrix error correction Overview
DataMatrix error correction (ECC) adds redundant data to the symbol, allowing scanners to recover the original information even if part of the barcode is damaged. Aspose.BarCode lets you choose between ECC200, ECC140, and other levels, giving you control over the balance between symbol size and resilience.

## Prerequisites

Before we dive into the code, make sure you have the following prerequisites in place:
- A development environment with .NET support.
- A copy of Aspose.BarCode for .NET, which you can download from [this link](https://releases.aspose.com/barcode/net/).
- Basic knowledge of C# and the .NET framework.

Now, let's explore the DataMatrix versions and how to generate them using Aspose.BarCode for .NET.

## Import Namespaces

In any C# project, it's essential to import the necessary namespaces. In the case of Aspose.BarCode, you'll need to include the following:

```csharp
using Aspose.BarCode.Generation;
```

This namespace provides access to the `BarcodeGenerator` class, which is crucial for generating barcodes.

Now, let's break down the example into multiple steps.

## Step 1: Set Up Your Directory Path

Begin by defining the directory path where you want to save the generated DataMatrix barcodes.

```csharp
string path = "Your Directory Path";
```

Replace `"Your Directory Path"` with the actual path where you want to save the barcode images.

## Step 2: Initialize the Barcode Generator

Create an instance of the `BarcodeGenerator` class and specify the barcode type as `DataMatrix`. You can also provide the data that you want to encode within the barcode.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Code for generating barcodes goes here
}
```

## Step 3: Configure Barcode Properties for datamatrix error correction

You can customize various properties of the DataMatrix barcode, such as its dimensions and ECC (Error Correction Code) type. Here's an example of setting the X‑dimension to 4 pixels and choosing ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Step 4: Set DataMatrix Version and Save

You can specify the DataMatrix version by setting the number of rows and columns. After configuring the version, save the barcode image.

For example, to create a DataMatrix barcode with 22 rows and 22 columns using ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Similarly, you can generate a barcode with different parameters by changing the version and ECC type as needed.

## Step 5: Repeat for Other Versions

You can repeat Step 4 for other DataMatrix versions. For example, to create a barcode with 12 rows and 64 columns using ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Step 6: Switch ECC Types

If you want to change the ECC type to Ecc140, you can do so by updating the ECC property:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Step 7: Generate Barcodes with Different Versions and ECC

Repeat Step 4 for other DataMatrix versions and ECC types, saving each barcode with a unique file name.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Now that you've learned how to generate DataMatrix barcodes using Aspose.BarCode for .NET, you can easily integrate this functionality into your .NET applications.

## Conclusion

Aspose.BarCode for .NET simplifies the process of generating DataMatrix barcodes in your .NET applications. With this step‑by‑step guide, you can create barcodes with different versions and ECC types, offering flexibility and customization to meet your specific needs.

If you have any questions or need assistance, don't hesitate to visit the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) or check out the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) for support.

## FAQ's

### Q1: What is ECC in DataMatrix barcodes?

A1: ECC (Error Correction Code) is a vital component of DataMatrix barcodes that helps ensure data integrity. Different ECC levels provide varying degrees of error correction.

### Q2: Can I generate DataMatrix barcodes with custom dimensions using Aspose.BarCode for .NET?

A2: Yes, you can customize the dimensions of DataMatrix barcodes by setting the number of rows and columns as demonstrated in the tutorial.

### Q3: Where can I download Aspose.BarCode for .NET?

A3: You can download Aspose.BarCode for .NET from [this link](https://releases.aspose.com/barcode/net/).

### Q4: Is there a free trial available for Aspose.BarCode for .NET?

A4: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).

### Q5: How can I obtain a temporary license for Aspose.BarCode for .NET?

A5: To get a temporary license for Aspose.BarCode for .NET, visit [this link](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Does the library support .NET Core and .NET 5/6?**  
A: Yes, Aspose.BarCode for .NET is fully compatible with .NET Framework, .NET Core, .NET 5, and .NET 6.

**Q: How do I choose the right ECC level for my use case?**  
A: Use ECC200 for a good balance of size and protection; switch to ECC140 when you need higher resilience against damage.

**Q: Can I generate barcodes in formats other than PNG?**  
A: Absolutely—BarCodeImageFormat supports JPEG, BMP, GIF, and more.

**Q: What if I need to generate many barcodes in a loop?**  
A: Create a single `BarcodeGenerator` instance, update the data and version inside the loop, and call `Save` for each iteration to improve performance.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}