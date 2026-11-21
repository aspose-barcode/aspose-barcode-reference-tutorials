---
category: general
date: 2026-11-20
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# bằng BarcodeGenerator. Hướng
  dẫn từng bước này bao gồm X‑Dimension, cài đặt cột và xuất PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: vi
lastmod: 2026-11-20
og_description: Tạo mã vạch PDF417 trong C# nhanh chóng. Thực hiện theo hướng dẫn
  này để thiết lập kích thước, cột và xuất mã vạch dưới dạng hình ảnh PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Tạo mã vạch PDF417 bằng C# – hướng dẫn chi tiết từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Cách tạo mã vạch PDF417 trong C# với BarcodeGenerator
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với BarcodeGenerator

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, thiết lập X‑Dimension, chọn số cột và lưu kết quả dưới dạng ảnh PNG.

Việc tạo mã vạch PDF417 thường được sử dụng khi bạn phải mã hoá một lượng lớn dữ liệu—như giấy phép lái xe, thẻ lên máy bay, hoặc hồ sơ tồn kho—vào một hình ảnh máy đọc được gọn gàng. Trong tutorial này chúng ta sử dụng lớp **BarcodeGenerator** từ thư viện Aspose.BarCode, nhưng các khái niệm cũng áp dụng cho bất kỳ thư viện nào hỗ trợ PDF417.

Khi kết thúc bài viết này, bạn sẽ có thể:

* Khởi tạo một `BarcodeGenerator` để mã hoá PDF417.  
* Điều chỉnh kích thước mô-đun bằng **set XDimension pixels**.  
* Kiểm soát bố cục bằng cách **configure PDF417 columns**.  
* **Lưu mã vạch dưới dạng PNG** để sử dụng trong trang web, ứng dụng di động hoặc tài liệu in.  

> **Prerequisites**  
> * .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+).  
> * Tham chiếu tới gói NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Kiến thức cơ bản về C# và Visual Studio (hoặc bất kỳ IDE nào bạn thích).

---

## Cách tạo mã vạch PDF417 trong C#

Cốt lõi của giải pháp là một quy trình ngắn gồm bốn bước. Mỗi bước được gói trong một phương thức riêng để bạn có thể tái sử dụng logic trong các dự án lớn hơn.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Tại sao bốn bước này lại quan trọng

1. **Initialize the generator** – `BarcodeGenerator` liên kết loại symbology đã chọn (`EncodeTypes.Pdf417`) với dữ liệu bạn muốn mã hoá. Không có đối tượng này, bạn không thể truy cập bất kỳ cấu hình nào khác.  
2. **Set X‑Dimension** – PDF417 được xây dựng từ các mô-đun hình chữ nhật nhỏ. Thay đổi `XDimension.Pixels` cho phép bạn kiểm soát mật độ hình ảnh của mã vạch, điều này rất quan trọng để đọc được trên các màn hình hoặc máy in độ phân giải thấp.  
3. **Configure columns** – PDF417 có thể sắp xếp các codeword trong một số lượng cột thay đổi. Ít cột hơn sẽ tạo ra mã vạch cao hơn, trong khi nhiều cột hơn sẽ làm nó phẳng hơn. Điều chỉnh điều này để phù hợp với không gian nơi hình ảnh sẽ được đặt.  
4. **Save as PNG** – PNG là định dạng không mất dữ liệu, giữ lại các cạnh sắc nét cần thiết cho việc quét chính xác. Bạn cũng có thể chọn JPEG hoặc BMP, nhưng PNG là lựa chọn an toàn nhất theo mặc định.

---

## Cấu hình kích thước mã vạch (X‑Dimension)

Bước **set XDimension pixels** ảnh hưởng trực tiếp đến cách máy quét diễn giải mã vạch. Nếu mô-đun quá nhỏ, camera chất lượng thấp có thể bỏ lỡ các thanh riêng lẻ; nếu quá lớn, mã vạch có thể trở nên không cần thiết quá to.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Kiểm tra hình ảnh đã tạo ở kích thước in dự định. Đối với in độ mật cao (300 dpi trở lên), giá trị `1` hoặc `2` hoạt động tốt. Đối với hiển thị trên màn hình ở 96 dpi, `2`–`3` cho hình ảnh rõ ràng.

---

## Đặt số cột PDF417

Bước **configure PDF417 columns** cho phép bạn quyết định hình dạng của mã vạch.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Khi nào nên thay đổi số cột

| Cột | Hình dạng kết quả | Trường hợp sử dụng điển hình |
|-----|-------------------|------------------------------|
| 1–3 | Cao, hẹp          | Nhãn có chiều rộng hạn chế |
| 4–9 | Cân bằng          | Quét đa mục đích |
| 10+ | Rộng, ngắn        | Biển hiệu lớn hoặc đồ họa web |

Nếu dung lượng dữ liệu của bạn vượt quá khả năng mặc định, thư viện sẽ tự động thêm các hàng bổ sung, nhưng bạn vẫn có thể ảnh hưởng đến tỷ lệ khung hình bằng cách điều chỉnh số cột.

---

## Xuất mã vạch ra PNG

Lưu mã vạch dưới dạng ảnh PNG rất đơn giản:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Why PNG?**  
* Nén không mất dữ liệu giữ lại các cạnh sắc nét cần cho máy đọc mã vạch.  
* PNG hỗ trợ trong suốt, hữu ích nếu bạn muốn đặt mã vạch lên nền màu sau này.

Nếu bạn cần định dạng khác, thay thế `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp` hoặc `Svg`—API sẽ tự động xử lý chuyển đổi.

---

## Những lỗi thường gặp và cách khắc phục

| Vấn đề | Nguyên nhân có thể | Cách khắc phục |
|--------|--------------------|----------------|
| Mã vạch xuất hiện mờ | X‑Dimension quá nhỏ so với độ phân giải đầu ra | Tăng `XDimension.Pixels` lên 3 hoặc 4. |
| Máy quét không đọc được mã | Các ký tự Unicode không được phông chữ đã chọn hỗ trợ | Đảm bảo phông chữ của thư viện hỗ trợ các ký tự, hoặc thay thế bằng các ký tự ASCII tương đương. |
| Không tạo được file đầu ra | Đường dẫn không hợp lệ hoặc thiếu quyền ghi | Sử dụng đường dẫn tuyệt đối và kiểm tra quyền ghi thư mục. |
| Quá nhiều hàng, mã vạch trở nên cao | Số cột quá thấp so với độ dài dữ liệu | Tăng `Pdf417.Columns` lên số cao hơn (ví dụ: 6). |

---

## Tóm tắt ví dụ làm việc đầy đủ

Dưới đây là **chương trình hoàn chỉnh** bạn có thể sao chép‑dán vào một dự án console mới. Không cần mã bổ sung nào ngoài các câu lệnh `using` và gói Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Expected output:** Một tệp có tên `Pdf417Basic.png` chứa một mã vạch PDF417 rõ ràng mã hoá chuỗi `Åspóse.Barcóde©`. Khi mở, hình ảnh sẽ hiển thị một loạt các thanh hình chữ nhật xếp chồng với phía trái có mật độ cao hơn (do bố trí ba cột).

---

## Kết luận

Bạn giờ đã biết cách **tạo mã vạch PDF417** trong C# bằng lớp `BarcodeGenerator`. Tutorial đã bao gồm việc khởi tạo generator, **set XDimension pixels**, **configure PDF417 columns**, và **save barcode as PNG**—những bước thiết yếu cho bất kỳ quy trình làm việc mã vạch sẵn sàng sản xuất nào.

Từ đây bạn có thể:

* Thử nghiệm các `EncodeTypes` khác nhau (ví dụ: QR, Code128).  
* Thêm mức độ sửa lỗi qua `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Render mã vạch trực tiếp tới một `MemoryStream` cho các API web.  

Hãy tự do điều chỉnh mã cho dự án của mình, và chia sẻ kết quả trong phần bình luận hoặc trên Stack Overflow bằng thẻ `#pdf417`. Chúc bạn lập trình vui!

## Bạn nên học gì tiếp theo?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate PDF417 barcode as PNG in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}