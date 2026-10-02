---
category: general
date: 2026-09-16
description: Tìm hiểu cách thiết lập cột mã vạch trong C# bằng BarcodeGenerator và
  cũng thiết lập hàng mã vạch cho các mã vạch DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: vi
lastmod: 2026-09-16
og_description: Thiết lập các cột mã vạch trong C# nhanh chóng. Hướng dẫn này cho
  bạn cách cấu hình cột, hàng và định dạng hình ảnh với BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Thiết lập các cột và hàng mã vạch trong C# – hướng dẫn đầy đủ BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách thiết lập cột và hàng mã vạch với C# BarcodeGenerator
url: /vi/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập cột và hàng cho mã vạch bằng C# BarcodeGenerator

Nếu bạn cần thiết lập cột cho mã vạch trong một ứng dụng C#, hướng dẫn này sẽ chỉ cho bạn các bước chính xác cần thực hiện. Bạn sẽ thấy cách cấu hình cả cột và hàng cho mã vạch DataBar Expanded Stacked, sau đó lưu kết quả dưới dạng ảnh PNG.

Việc tạo mã vạch bằng chương trình giúp bạn tránh công việc thiết kế thủ công và đảm bảo tính nhất quán trên các báo cáo, hoá đơn và nhãn sản phẩm. Ví dụ dưới đây bao gồm toàn bộ quy trình, từ cài đặt thư viện đến tạo hai ảnh—một với số cột tùy chỉnh và một với số hàng tùy chỉnh.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt.  
* Tham chiếu tới gói NuGet **Aspose.BarCode for .NET**. Cài đặt bằng cách:

```bash
dotnet add package Aspose.BarCode
```

* Quyền ghi vào thư mục nơi các tệp PNG được tạo sẽ được lưu.

Các yêu cầu này đảm bảo mã có thể biên dịch và chạy mà không cần cấu hình bổ sung.

## Cách thiết lập cột cho mã vạch trong C#

Bước quan trọng đầu tiên là tạo một thể hiện `BarcodeGenerator` cho ký hiệu **DataBar Expanded Stacked** và gán số cột mong muốn.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao cách này hoạt động:**  
`EncodeTypes.DatabarExpandedStacked` cho thư viện biết ký hiệu nào cần hiển thị. Việc đặt `Parameters.Barcode.DataBar.Columns` thay đổi bố cục mô-đun nội bộ, ảnh hưởng trực tiếp đến chiều rộng hiển thị của mã vạch. Phương thức `Save` ghi ảnh ra đĩa ở định dạng `BarCodeImageFormat` đã yêu cầu.

### Kết quả mong đợi
Mở `C:\Barcodes\DatabarCols4.png` bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy một mã vạch DataBar Expanded Stacked rộng hơn so với mặc định vì nó sử dụng bốn cột.

## Cách thiết lập hàng cho mã vạch trong C#

Sau khi đã lưu ảnh dựa trên cột, bạn có thể muốn một mã vạch thay đổi chiều cao bằng cách điều chỉnh hàng. Quy trình tương tự như cấu hình cột nhưng sử dụng thuộc tính `Rows` thay vì.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao cách này hoạt động:**  
Khởi tạo lại trình tạo đảm bảo cài đặt cột trước đó không can thiệp vào cấu hình hàng. Thay đổi `Parameters.Barcode.DataBar.Rows` sẽ điều chỉnh chiều cao của mã vạch, tạo ra ảnh cao hơn khi số hàng vượt quá mặc định.

### Kết quả mong đợi
Mở `C:\Barcodes\DatabarRows3.png`. Mã vạch sẽ xuất hiện cao hơn, phản ánh cấu hình ba hàng.

## Ví dụ toàn diện từ đầu đến cuối

Dưới đây là một chương trình duy nhất tạo cả hai ảnh trong một lần thực thi. Giữ mã trong một tệp cho thấy cách bạn có thể chuyển đổi giữa cấu hình cột và hàng mà không cần khởi động lại ứng dụng.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Chạy chương trình sẽ tạo ra hai tệp PNG:

* **DatabarCols4.png** – mã vạch với bốn cột.  
* **DatabarRows3.png** – mã vạch với ba hàng.

Cả hai tệp đều sử dụng **định dạng ảnh mã vạch** PNG, giữ được các cạnh sắc nét và hỗ trợ nén không mất dữ liệu—lý tưởng cho việc in ấn và hiển thị kỹ thuật số.

## Câu hỏi thường gặp và mẹo

| Question | Answer |
|----------|--------|
| *Tôi có thể dùng JPEG thay vì PNG không?* | Có. Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`. JPEG có kích thước nhỏ hơn nhưng sẽ tạo ra các artefact nén, có thể ảnh hưởng đến độ tin cậy của máy quét. |
| *Số cột hoặc hàng tối đa là bao nhiêu?* | Thư viện sẽ kiểm tra các giá trị dựa trên tiêu chuẩn DataBar. Các giá trị nằm ngoài phạm vi cho phép sẽ ném ra `ArgumentException`. Kiểm tra tài liệu Aspose.BarCode để biết giới hạn chính xác. |
| *Tôi có cần giải phóng `BarcodeGenerator` không?* | Lớp này triển khai `IDisposable`. Đặt trình tạo trong khối `using` nếu bạn tạo nhiều thể hiện trong vòng lặp để giải phóng tài nguyên không quản lý kịp thời. |
| *Làm sao thay đổi kích thước mã vạch mà không thay đổi cột/hàng?* | Sử dụng `barcodeGenerator.Parameters.Image.Width` và `Height` để phóng to/thu nhỏ ảnh đầu ra trong khi giữ nguyên bố cục mô-đun. |

**Mẹo chuyên nghiệp:** Khi tạo mã vạch cho việc in ấn độ phân giải cao, tăng kích thước ảnh đầu ra (`Width`/`Height`) thay vì tăng số cột hoặc hàng. Cách này duy trì kích thước mô-đun chuẩn của ký hiệu đồng thời cung cấp ảnh sắc nét hơn.

## Kết luận

Bây giờ bạn đã biết cách thiết lập cột và hàng cho mã vạch trong C# bằng lớp **BarcodeGenerator**. Hướng dẫn đã bao gồm việc khởi tạo trình tạo, cấu hình số cột và hàng, lưu mã vạch ở định dạng PNG, và xử lý các biến thể thường gặp như thay đổi định dạng ảnh và giải phóng tài nguyên.

Tiếp theo, hãy khám phá các chủ đề liên quan như **tùy chỉnh màu sắc mã vạch**, **thêm văn bản có thể đọc được**, và **nhúng mã vạch vào tài liệu PDF**. Tất cả các mở rộng này dựa trên cùng một mẫu cấu hình đã được trình bày ở đây, cho phép bạn tạo các giải pháp mã vạch đầy đủ tính năng cho bất kỳ ứng dụng .NET nào.

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật đã được minh họa trong bài viết này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ và giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Ví dụ Trình tạo Mã vạch trong C# – Thiết lập Cột, Hàng & Xuất ảnh](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Hướng dẫn mã vạch databar expanded stacked – cách tạo và định kích thước trong C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Ví dụ Trình tạo Mã vạch trong C# – thiết lập chiều rộng và chiều cao](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}