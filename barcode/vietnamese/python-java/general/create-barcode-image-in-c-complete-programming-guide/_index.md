---
category: general
date: 2026-08-09
description: Tạo hình ảnh mã vạch trong C# với hướng dẫn từng bước này. Tìm hiểu cách
  tạo mã vạch, điều chỉnh độ cao mã vạch tính bằng pixel và tạo nhiều mã vạch một
  cách hiệu quả.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: vi
lastmod: 2026-08-09
og_description: Tạo hình ảnh mã vạch trong C# nhanh chóng. Theo dõi hướng dẫn này
  để học cách tạo mã vạch, đặt chiều cao mã vạch tính bằng pixel và tạo nhiều mã vạch.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn đầy đủ cho nhà phát triển
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Tạo hình ảnh mã vạch trong C# – hướng dẫn lập trình toàn diện
url: /vi/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch trong C# – hướng dẫn lập trình đầy đủ

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn **cách tạo mã vạch** bằng thư viện Aspose.BarCode. Bạn sẽ thấy cách điều chỉnh **độ cao mã vạch tính bằng pixel**, lưu ảnh, và tạo **nhiều mã vạch** mà không cần sao chép lại mã.

Bài tutorial bao gồm mọi thứ từ cài đặt gói đến tùy chỉnh kích thước, vì vậy bạn có thể sao chép‑dán một ví dụ đã sẵn sàng chạy vào dự án của mình ngay hôm nay.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào)  
* Gói NuGet `Aspose.BarCode` – cài đặt bằng  

```bash
dotnet add package Aspose.BarCode
```

Không cần bất kỳ phụ thuộc bổ sung nào.

## Cách tạo hình ảnh mã vạch với BarcodeGenerator C#

Lớp cốt lõi để tạo hình ảnh mã vạch là `BarcodeGenerator`. Nó bao gồm loại mã hoá, chuỗi dữ liệu, và tất cả các tham số render.

### Bước 1: Xác định thư mục đầu ra

Chọn một thư mục nơi các tệp PNG được tạo sẽ được lưu. Sử dụng đường dẫn tuyệt đối giúp tránh các vấn đề về quyền truy cập.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Tại sao?** Tạo thư mục bằng chương trình đảm bảo các lệnh `Save` tiếp theo sẽ thành công ngay cả trên máy mới.

### Bước 2: Khởi tạo barcode generator

Đối với mã DataBar Omnidirectional, truyền `EncodeTypes.DatabarOmniDirectional` và chuỗi dữ liệu GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Lưu ý:** Đối tượng `BarcodeGenerator` có thể tái sử dụng; bạn có thể thay đổi các tham số giữa các lần lưu để **tạo nhiều mã vạch** từ cùng một dữ liệu.

### Bước 3: Đặt các tham số chung cho mã vạch

Các điều chỉnh hình ảnh phổ biến nhất là X‑dimension (độ rộng mô-đun) và chiều cao thanh. Cả hai đều được biểu thị bằng pixel.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Tại sao phải đặt X‑dimension?** X‑dimension nhỏ hơn tạo độ phân giải cao hơn, điều này quan trọng khi hình ảnh sẽ được in hoặc hiển thị trên màn hình DPI cao.

### Bước 4: Lưu hình ảnh mã vạch đầu tiên

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Tệp `DatabarBarHeight30Pixels.png` bây giờ chứa một mã DataBar Omnidirectional có chiều cao 30 pixel.

### Bước 5: Điều chỉnh chiều cao mã vạch tính bằng pixel

Thay đổi chiều cao không cần tạo một thể hiện `BarcodeGenerator` mới—chỉ cần sửa tham số.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Bước 6: Lưu hình ảnh mã vạch thứ hai

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Bây giờ bạn có hai tệp PNG với **chiều cao mã vạch tính bằng pixel** khác nhau, minh họa cách dễ dàng **tạo hình ảnh mã vạch** đa dạng.

## Đặt chiều cao mã vạch tính bằng pixel một cách động

Thường bạn cần một loạt mã vạch với chiều cao phù hợp với các thành phần UI hoặc nhãn in. Phương thức trợ giúp dưới đây trừu tượng hoá việc thay đổi chiều cao:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Bạn có thể gọi `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` để **tạo hình ảnh mã vạch** với chiều cao 45 pixel trong một dòng lệnh.

## Tạo nhiều mã vạch trong vòng lặp

Khi bạn có một tập hợp các định danh sản phẩm, vòng lặp `foreach` loại bỏ việc lặp lại mã. Ví dụ này cho thấy cách **tạo nhiều mã vạch** từ một mảng GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Vòng lặp tạo ra ba tệp PNG, mỗi tệp có một **giá trị chiều cao mã vạch tính bằng pixel** riêng. Vì phương thức trợ giúp `SaveBarcodeWithHeight` đã bao gói việc thay đổi chiều cao, vòng lặp chính vẫn gọn gàng và tập trung vào dữ liệu.

### Kết quả mong đợi

Sau khi chạy toàn bộ mẫu, thư mục `Barcodes` sẽ chứa:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Mở bất kỳ tệp PNG nào sẽ hiển thị một mã DataBar Omnidirectional sắc nét, có thể quét bằng các ứng dụng di động tiêu chuẩn.

## Những lỗi thường gặp và mẹo chuyên nghiệp

| Vấn đề | Tại sao xảy ra | Cách tránh |
|-------|----------------|------------|
| **EncodeTypes sai** | Sử dụng loại 1D cho DataBar sẽ tạo ra hình ảnh không đọc được. | Luôn chọn `EncodeTypes.DatabarOmniDirectional` (hoặc biến thể DataBar khác) cho payload GS1‑128. |
| **X‑dimension không đủ** | X‑dimension quá thấp có thể làm cho các thanh mỏng biến mất trên màn hình độ phân giải thấp. | Giữ `XDimension.Pixels` ≥ 2 cho hiển thị trên màn hình; tăng lên 3‑4 cho in ấn. |
| **Lỗi đường dẫn tệp** | Đường dẫn tương đối có thể trỏ tới thư mục không mong muốn. | Sử dụng `Path.Combine` và `Environment.CurrentDirectory` để xây dựng đường dẫn tuyệt đối. |
| **Ghi đè ảnh** | Sử dụng cùng một tên tệp trong vòng lặp sẽ ghi đè kết quả trước đó. | Bao gồm các định danh duy nhất (ví dụ: GTIN hoặc timestamp) trong tên tệp. |
| **Thiếu gói NuGet** | Mã biên dịch nhưng ném `FileNotFoundException` lúc chạy. | Kiểm tra `Aspose.BarCode` đã được cài đặt và dự án đã tham chiếu tới nó. |

## Ví dụ hoàn chỉnh hoạt động

Dưới đây là chương trình đầy đủ mà bạn có thể sao chép vào một ứng dụng console. Nó bao gồm tất cả các bước, phương thức trợ giúp, và xử lý lỗi.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Chạy chương trình này


## Bạn Nên Học Gì Tiếp Theo?


Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo chiều cao tùy chỉnh cho mã vạch – Mã vạch một chiều](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Tạo hình ảnh mã vạch C# – Ví dụ GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Tạo hình ảnh mã vạch DotCode – hàng & cột (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}