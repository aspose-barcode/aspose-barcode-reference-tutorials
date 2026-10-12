---
category: general
date: 2026-10-12
description: Cách thiết lập chiều cao mã vạch và tạo mã DataBar trong C# bằng Aspose.BarCode.
  Thực hiện theo hướng dẫn từng bước với mã hoàn chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: vi
lastmod: 2026-10-12
og_description: Cách đặt chiều cao mã vạch trong C# và tạo mã vạch DataBar bằng Aspose.BarCode.
  Tìm hiểu toàn bộ mã, lý do mỗi bước quan trọng, và cách thay đổi chiều cao mã vạch.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Cách đặt chiều cao mã vạch và tạo mã DataBar trong C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách đặt chiều cao mã vạch, tạo mã DataBar trong C#
url: /vi/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt chiều cao mã vạch, tạo mã DataBar trong C#

Nếu bạn cần **cách đặt mã vạch** dimensions programmatically, this guide shows you the exact steps. You’ll learn how to generate a DataBar Omni‑directional barcode, adjust its height, and save both versions as PNG files.

Changing a barcode’s bar height is a common requirement when you integrate barcodes into receipts, product labels, or mobile screens. The example below uses the Aspose.BarCode library, which supports the full range of GS1 DataBar symbologies.

## Những gì bạn sẽ đạt được

* **cách đặt mã vạch** chiều cao cho một DataBar Omni‑directional barcode  
* **tạo mã vạch c#** code that creates two images with different heights  
* understand **cách tạo databar** symbols and why the bar height matters  
* apply **thay đổi chiều cao mã vạch** logic without recreating the generator  

No external tools are required beyond the Aspose.BarCode NuGet package and a .NET 6+ runtime.

## Yêu cầu trước

* .NET 6 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ C# editor nào)  
* Aspose.BarCode for .NET – install via `dotnet add package Aspose.BarCode`  

> **Mẹo chuyên nghiệp:** Use the free trial license from Aspose if you don’t have a commercial key; the API works the same way.

## Bước 1: Cài đặt gói Aspose.BarCode

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `Aspose.BarCode` namespace, which contains the `BarcodeGenerator` class we’ll use to **tạo mã vạch c#** images.

## Bước 2: Tạo trình tạo mã DataBar

The first concrete action for **cách đặt mã vạch** parameters is to instantiate `BarcodeGenerator` with the desired symbology and data string.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` produces a compact, omnidirectional DataBar that can be scanned from any angle—ideal for small labels.

## Bước 3: Đặt các tham số chung cho mã vạch (bao gồm chiều cao thanh ban đầu)

Now we answer **cách đặt mã vạch** X‑dimension and bar height before saving the first image.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

The X‑dimension controls the overall width of each bar; a 2‑pixel setting yields a readable, sharp image on most screens. The **thay đổi chiều cao mã vạch** step later will reuse the same generator, saving time and memory.

## Bước 4: Lưu hình ảnh mã vạch đầu tiên (chiều cao 30‑pixel)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

The file `DatabarHeight30.png` now contains a DataBar barcode with a 30‑pixel bar height.

## Bước 5: Chỉ thay đổi chiều cao thanh lên 60 pixel

To demonstrate **thay đổi chiều cao mã vạch**, we modify just the `BarHeight` property. All other settings remain unchanged, which is the most efficient way to produce multiple sizes from a single generator.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Bước 6: Lưu hình ảnh mã vạch thứ hai (chiều cao 60‑pixel)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

You now have two PNG files, each with a different bar height but identical data and X‑dimension.

## Ví dụ đầy đủ, có thể chạy được

Below is the complete program you can copy‑paste into a new console application (`dotnet new console`) and run immediately.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Kết quả mong đợi

Running the program produces two files in the executable’s working directory:

* `DatabarHeight30.png` – một DataBar barcode with 30‑pixel tall bars.  
* `DatabarHeight60.png` – the same barcode, but each bar is twice as tall.

Both images can be opened in any image viewer or embedded directly into PDFs, HTML pages, or printed labels.

## Tại sao việc điều chỉnh chiều cao thanh lại quan trọng

* **Độ tin cậy khi quét:** Some scanners struggle with very short bars on low‑resolution media; increasing the height improves detection.  
* **Ràng buộc thiết kế:** A mobile app may need a compact barcode (30 px) while a printed receipt may require a larger one (60 px).  
* **Tuân thủ quy định:** Certain industries mandate a minimum bar height for GS1 DataBar symbols.

By reusing the same `BarcodeGenerator` instance, you avoid the overhead of re‑parsing the data string, which is especially beneficial in high‑throughput environments.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh đề xuất |
|-----------|-------------------|
| Cần một X‑dimension khác | Change `XDimension.Pixels` before the first `Save`. |
| Muốn một kiểu mã khác (ví dụ, DataBar Stacked) | Use `EncodeTypes.DatabarStacked` when constructing `BarcodeGenerator`. |
| Phải nhúng mã vạch vào PDF | Use `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` and add the stream to a PDF library. |
| Chạy trên .NET Framework 4.6 | The same code works; just reference the appropriate Aspose.BarCode assembly. |

## Mẹo chuyên nghiệp để tạo mã vạch đáng tin cậy

* **Lưu trữ bộ tạo** when you generate many barcodes with the same data but different sizes.  
* **

## Bạn nên học gì tiếp theo?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Cách tạo và điều chỉnh chiều cao mã vạch cho Databar một chiều bằng Aspose.BarCode cho .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cách tạo hình ảnh PNG Databar với C# và Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Cách tạo mã vạch với kích thước tùy chỉnh và lưu hình ảnh trong C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}