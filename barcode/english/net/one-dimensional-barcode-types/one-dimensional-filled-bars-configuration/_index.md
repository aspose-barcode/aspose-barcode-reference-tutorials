---
title: How to Generate Barcode: One-Dimensional Filled Bars
linktitle: One-Dimensional Filled Bars Configuration
second_title: Aspose.BarCode .NET API
description: Learn how to generate barcode images in PNG format with Aspose.BarCode for .NET. This barcode generator tutorial covers creating a Code128 barcode, configuring filled bars, and saving barcode PNG files.
weight: 20
url: /net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/
date: 2026-02-28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Generate Barcode: One-Dimensional Filled Bars

Are you looking to generate professional and customizable barcodes in your .NET applications? If you’re wondering **how to generate barcode** images quickly and reliably, Aspose.BarCode for .NET has you covered. This tutorial walks you through everything from importing the required namespaces to creating one‑dimensional filled bars, saving them as **barcode image png** files, and customizing the output. Let’s dive in!

## Quick Answers
- **What does “filled bars” mean?** Filled bars are solid‑filled modules that give the barcode a bold appearance.  
- **Which barcode type is used in this example?** Code128, a high‑density linear symbology.  
- **Can I save the result as PNG?** Yes – the tutorial shows how to **save barcode png** files.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **What .NET versions are supported?** Any version that supports .NET Framework or .NET Core compatible with Aspose.BarCode.

## What is “how to generate barcode” with Aspose.BarCode?
Aspose.BarCode for .NET provides a simple API that lets you programmatically create a wide range of linear and 2‑D barcodes. By configuring properties such as **XDimension**, **FilledBars**, and image format, you can tailor the output to meet packaging, inventory, or labeling requirements.

## Why use Aspose.BarCode for .NET?
- **Full control** over barcode appearance (size, colors, filled/empty bars).  
- **No external dependencies** – everything runs locally in your application.  
- **Supports over 50 symbologies**, including Code128, QR, DataMatrix, and more.  
- **Easy to integrate** with existing .NET projects, whether you target .NET Framework or .NET Core.

## Prerequisites

Before we start, make sure you have the following:

1. **Visual Studio** – any recent edition (Community, Professional, or Enterprise).  
2. **Aspose.BarCode for .NET** – download it from the official site **[here](https://releases.aspose.com/barcode/net/)**.  
3. **.NET Framework or .NET Core** – a compatible runtime installed on your development machine.

Now that the environment is ready, let’s move on to the code.

## Importing Namespaces

To begin using the library, add the required `using` directive at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
```

This import gives you access to the `BarcodeGenerator` class and all related configuration objects.

## How to Generate Barcode with Filled Bars

Below is a step‑by‑step guide that shows exactly **how to generate barcode** images with filled and empty bars.

### Step 1: Define the Output Folder
Choose a folder where the generated PNG files will be stored. Replace `"Your Directory Path"` with an actual path on your machine.

```csharp
string path = "Your Directory Path";
```

> **Pro tip:** Use `Path.Combine` to build platform‑independent paths.

### Step 2: Create a BarcodeGenerator Instance
Instantiate `BarcodeGenerator` with the desired symbology (`EncodeTypes.Code128`) and the data you want to encode (`"ASPOSE"`).

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

### Step 3: Configure Filled Bars
Set the X‑dimension (the width of a single bar) and decide whether the bars should be filled. The following configuration creates solid bars.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.FilledBars = true;
```

### Step 4: Generate and Save the Images
Save the barcode with filled bars, then switch the `FilledBars` flag to `false` and save the empty‑bar version. Both files are saved as **barcode image png** files.

```csharp
gen.Save($"{path}BarsFilledCode128.png", BarCodeImageFormat.Png);
gen.Parameters.Barcode.FilledBars = false;
gen.Save($"{path}BarsEmptyCode128.png", BarCodeImageFormat.Png);
```

When you run the code, you’ll end up with two PNG files:
- `BarsFilledCode128.png` – solid, bold bars.  
- `BarsEmptyCode128.png` – standard, non‑filled bars.

## Common Issues & Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **File not found** | Invalid `path` value. | Verify the directory exists or create it with `Directory.CreateDirectory(path)`. |
| **License exception** | Running without a valid license in production. | Apply your Aspose license using `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Incorrect image format** | Using an unsupported format. | Ensure you use `BarCodeImageFormat.Png` (or another supported enum value). |

## Frequently Asked Questions

### What barcode formats are supported by Aspose.BarCode for .NET?
Aspose.BarCode for .NET supports over 50 linear and 2‑D formats, including Code128, QR Code, DataMatrix, PDF417, and more. See the full list in the documentation **[here](https://reference.aspose.com/barcode/net/)**.

### Can I customize the appearance of the generated barcodes?
Absolutely. You can modify size, colors, margins, text placement, and even apply background images. All options are available through the `Parameters` object.

### Is there a free trial available for Aspose.BarCode for .NET?
Yes – you can download a fully functional trial **[here](https://releases.aspose.com/)**.

### Where can I get support for Aspose.BarCode for .NET?
The official support forum is a great place to ask questions and share experiences: **[here](https://forum.aspose.com/c/barcode/13)**.

### Can I purchase a temporary license for Aspose.BarCode for .NET?
A temporary license is available for short‑term projects. Grab one **[this link](https://purchase.aspose.com/temporary-license/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

---