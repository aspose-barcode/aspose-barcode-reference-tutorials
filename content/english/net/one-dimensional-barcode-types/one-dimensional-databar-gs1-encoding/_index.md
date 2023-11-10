---
title: One-Dimensional Databar GS1 Encoding
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
description: Learn to create Databar GS1 encoded barcodes in .NET using Aspose.BarCode. Generate barcodes with ease. Follow our step-by-step guide.
type: docs
weight: 18
url: /net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

In this tutorial, we will walk you through the process of creating one-dimensional Databar GS1 encoded barcodes using the Aspose.BarCode for .NET library. Whether you're looking to generate barcodes with GS1 encoding or without it, we've got you covered. This step-by-step guide will help you understand the prerequisites, import namespaces, and demonstrate each example to create Databar GS1 encoded barcodes with ease.

## Prerequisites

Before we dive into the code, make sure you have the following prerequisites in place:

1. Aspose.BarCode for .NET: You should have Aspose.BarCode for .NET installed. If you haven't already, you can download it from [here](https://releases.aspose.com/barcode/net/).

2. Your Directory Path: Replace `"Your Directory Path"` in the code examples with the actual path where you want to save the generated barcode images.

Now that you have the necessary prerequisites ready, let's proceed to the coding part.

## Importing Namespaces

To get started, you need to import the relevant namespaces for Aspose.BarCode. Add the following lines of code at the beginning of your .NET project:

```csharp
using Aspose.BarCode;
using System;
```

## Step 1: Initialize the Barcode Generator

The first step is to initialize the BarcodeGenerator object with the desired encoding type. In this case, we are using Databar Expanded encoding. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Step 2: Generate a Barcode with GS1 Encoding

Now, we will set the codetext with GS1Encoding check and save the generated barcode image. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Step 3: Generate a Variable Encoding Barcode

In this step, we will generate a barcode with variable codetext without GS1Encoding check.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Step 4: Handle Exception for GS1 Encoding Check

If you try to generate a barcode with variable codetext with GS1Encoding check enabled, it will throw an exception. Here's how you can handle it:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Now you have successfully created one-dimensional Databar GS1 encoded barcodes with Aspose.BarCode for .NET. You can further explore and customize your barcode generation based on your specific requirements.

## Conclusion

In this tutorial, we've covered the process of generating one-dimensional Databar GS1 encoded barcodes using Aspose.BarCode for .NET. We discussed the prerequisites, imported the necessary namespaces, and provided step-by-step guidance for creating both GS1 encoded and variable encoding barcodes.

With Aspose.BarCode for .NET, barcode generation becomes a seamless task, offering flexibility and control over your barcode creation needs. If you encounter any issues or have questions, don't hesitate to visit the [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) or seek help on the [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

## Frequently Asked Questions

### 1. What is GS1 encoding in barcodes?
GS1 encoding is a standard used in barcoding to ensure proper data structure and identification. It's commonly used for items in retail, healthcare, and logistics to facilitate accurate tracking and information exchange.

### 2. Can I customize the appearance of the generated barcodes?
Yes, you can customize the appearance of the barcodes generated with Aspose.BarCode for .NET. You have control over various parameters like size, color, and style.

### 3. Where can I find additional resources and documentation for Aspose.BarCode?
You can find comprehensive documentation and examples at [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). It's a valuable resource for learning and troubleshooting.

### 4. Is there a trial version available for Aspose.BarCode?
Yes, you can get a free trial version of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).

### 5. How can I purchase a license for Aspose.BarCode for .NET?
To purchase a license for Aspose.BarCode for .NET, visit the [purchase page](https://purchase.aspose.com/buy) on the Aspose website.

