---
category: general
date: 2026-07-18
description: Tạo mã vạch PDF417 nhanh chóng bằng C#. Tìm hiểu cách tạo mã vạch, thiết
  lập các tham số và lưu file ảnh – bao gồm xử lý AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: vi
lastmod: 2026-07-18
og_description: Tạo mã vạch PDF417 trong C# với hướng dẫn chi tiết. Khám phá cách
  tạo mã vạch, điều chỉnh cài đặt và lưu hình ảnh đồng thời xử lý AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Tạo mã vạch PDF417 trong C# – Nhanh, Linh hoạt, Ví dụ đầy đủ mã
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Tạo mã vạch PDF417 trong C# – Hướng dẫn chi tiết từng bước
url: /vi/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Vạch PDF417 trong C# – Hướng Dẫn Chi Tiết Từng Bước

Bạn đã bao giờ cần **create pdf417 barcode** nhưng không chắc thư viện hoặc cài đặt nào nên chọn? Bạn không phải là người duy nhất—nhiều nhà phát triển gặp khó khăn này khi lần đầu làm việc với GS1‑Micro‑PDF417. Tin tốt là chỉ với vài dòng C# bạn có thể tạo một mã vạch được định dạng hoàn hảo, điều chỉnh giao diện và lưu hình ảnh trực tiếp vào đĩa.

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **how to generate barcode** bằng thư viện Aspose.BarCode, chỉ ra **how to set parameters** như X‑dimension và số cột, và trình bày **how to save image** cho cả hai biến thể AI 10 và AI 21. Khi kết thúc, bạn sẽ có một đoạn mã có thể tái sử dụng và chèn vào bất kỳ dự án .NET nào.

## Yêu cầu trước

- .NET 6+ hoặc .NET Framework 4.7.2 (bất kỳ runtime mới nào cũng hoạt động)
- Visual Studio 2022 hoặc trình chỉnh sửa C# yêu thích của bạn
- Gói NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Một thư mục có quyền ghi trên đĩa nơi các tệp PNG sẽ được lưu

Chỉ vậy—không cần công cụ bổ sung, không cấu hình phức tạp. Sẵn sàng? Hãy bắt đầu.

## Bước 1: Tạo Mã Vạch PDF417 với Định Dạng GS1‑Micro

Điều đầu tiên chúng ta làm là tạo đối tượng **create pdf417 barcode** và cung cấp dữ liệu AI ban đầu. Trong GS1‑Micro‑PDF417, AI 10 (số lô) thường là điểm bắt đầu, vì vậy chúng ta sẽ mã hoá nó ngay lập tức.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Why this matters:** `EncodeTypes.GS1MicroPdf417` cho thư viện biết tuân theo chuẩn GS1‑Micro, tự động thêm tiền tố cho các dấu ngoặc AI. Nếu bỏ qua, bạn sẽ nhận được một PDF417 chung có thể không thể quét được trong môi trường bán lẻ.

## Bước 2: Cách Đặt Tham Số cho Mã Vạch

Bây giờ chúng ta đã có một thể hiện mã vạch, chúng ta cần tinh chỉnh các đặc tính hình ảnh của nó. Đây là nơi **how to set parameters** đóng vai trò. Chúng ta sẽ điều chỉnh ba cài đặt phổ biến:

1. **X‑dimension** – điều khiển độ rộng của thanh nhỏ nhất (tính bằng pixel)
2. **Column count** – ảnh hưởng đến hình dạng tổng thể; ít cột hơn = mã vạch cao hơn
3. **IsLinked** – bật mô-đun liên kết tùy chọn để gắn mã vạch với chuỗi dữ liệu

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Pro tip:** Nếu bạn nhắm tới việc quét trên thiết bị di động, tăng X‑dimension lên 3‑4 pixel; các mô-đun lớn hơn sẽ chịu được camera độ phân giải thấp tốt hơn.

## Bước 3: Cách Lưu Hình Ảnh – Phiên Bản Đầu Tiên (AI 10)

Khi trình tạo đã được cấu hình, cuối cùng chúng ta có thể **how to save image**. Phương thức `Save` ghi mã vạch vào tệp theo định dạng bạn chỉ định. Ở đây chúng ta dùng PNG vì nó giữ được các cạnh sắc nét mà không có hiện tượng nén.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Tại thời điểm này, bạn sẽ thấy một tệp có tên `GS1MicroPdf417_AI10.png` trong thư mục `outputDir` của bạn. Mở nó bằng bất kỳ trình xem ảnh nào—bạn sẽ thấy một PDF417 sạch sẽ, độ tương phản cao, sẵn sàng để in.

## Bước 4: Chuyển Sang AI Khác (AI 21) và Lưu Lại Lại

Thường bạn cần mã hoá một định danh ứng dụng khác, chẳng hạn AI 21 (số sê-ri). Thay đổi thuộc tính `CodeText` là tất cả những gì cần thiết. Điều này minh họa việc xử lý **barcode ai 10** và **barcode ai 21** trong một lần.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **What if you need more AIs?** Chỉ cần nối chúng trong cùng một chuỗi, ví dụ `"(10)ABCD(21)12345(240)XYZ"`. Thư viện sẽ tự động phân tích các dấu ngoặc.

## Ví Dụ Hoàn Chỉnh Hoạt Động

Kết hợp tất cả lại, đây là một chương trình tự chứa mà bạn có thể sao chép và dán vào một ứng dụng console:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Expected output:** Hai tệp PNG xuất hiện trong `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` và `GS1MicroPdf417_AI21.png`. Cả hai đều chứa một PDF417 có thể quét; tệp đầu tiên mã hoá AI 10, tệp thứ hai AI 21.

## Những Sai Lầm Thường Gặp & Cách Tránh

- **Missing folder permissions:** Nếu `Save` ném ra `UnauthorizedAccessException`, hãy kiểm tra lại đường dẫn tồn tại và ứng dụng của bạn có quyền ghi.
- **Incorrect AI formatting:** Quên dấu ngoặc (`(10)`) sẽ khiến mã vạch được xử lý như dữ liệu thường, làm mất tính hợp lệ GS1.
- **Too small X‑dimension:** Các thanh mỏng hơn 1 pixel có thể biến mất khi ảnh được thay đổi kích thước. Đặt ít nhất 2 pixel cho hiển thị trên màn hình.

## Các Bước Tiếp Theo & Chủ Đề Liên Quan

Bây giờ bạn đã biết **how to generate barcode**, **how to set parameters**, và **how to save image**, bạn có thể muốn khám phá:

- [Cách Tạo Mã Vạch – Compact PDF417 với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách Tạo Vùng Yên Tĩnh cho Mã Vạch ITF-14 Sử Dụng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cách Tạo Mã Vạch Aztec với Sửa Lỗi trong .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}