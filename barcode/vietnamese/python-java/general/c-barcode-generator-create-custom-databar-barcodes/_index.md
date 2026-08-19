---
category: general
date: 2026-08-19
description: Hướng dẫn tạo mã vạch bằng C# cho thấy cách tạo mã vạch DataBar Expanded
  Stacked, tùy chỉnh kích thước mã vạch và cấu hình hàng và cột.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: vi
lastmod: 2026-08-19
og_description: Hướng dẫn tạo mã vạch C# dạy bạn cách tạo mã vạch DataBar, tùy chỉnh
  kích thước và cấu hình hàng và cột để có đầu ra chính xác.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Trình tạo mã vạch C# – hướng dẫn chi tiết từng bước cho mã vạch DataBar
  tùy chỉnh
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Trình tạo mã vạch C#: tạo mã vạch DataBar tùy chỉnh'
url: /vi/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trình tạo mã vạch C#: tạo mã DataBar tùy chỉnh

Nếu bạn cần một **c# barcode generator** có thể tạo các ký hiệu DataBar Expanded Stacked, hướng dẫn này sẽ chỉ cho bạn cách tạo hình ảnh mã vạch với các hàng và cột tùy chỉnh. Bạn sẽ học cách cấu hình các tham số databar, điều chỉnh kích thước mã vạch và lưu kết quả dưới dạng tệp PNG.

Việc tạo mã vạch bằng chương trình loại bỏ các bước thiết kế thủ công và đảm bảo đầu ra nhất quán trên mọi nền tảng. Trong tutorial này bạn sẽ:

* Cài đặt và tham chiếu thư viện Aspose.BarCode cho .NET (hoặc bất kỳ gói nào tương thích).
* Tạo một trình tạo mã vạch cho ký hiệu DataBar Expanded Stacked.
* **Cách tạo hình ảnh mã vạch** với cài đặt cột và hàng cụ thể.
* **Tùy chỉnh kích thước mã vạch** bằng cách kiểm soát các hàng và cột DataBar.
* **Cấu hình các tham số databar** như văn bản, định dạng và chất lượng hình ảnh.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt.
* Môi trường phát triển C# (Visual Studio, VS Code, Rider, v.v.).
* Gói NuGet `Aspose.BarCode` (hoặc một thư viện tương đương cung cấp `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat`).

Thêm gói bằng .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Sử dụng trình tạo mã vạch C# để tạo mã DataBar

Các phần sau sẽ hướng dẫn bạn qua từng bước. Mục tiêu chính là **c# barcode generator** API, nhưng cùng một mẫu có thể áp dụng cho các thư viện mã vạch khác có các thuộc tính tương tự.

### Bước 1: Khởi tạo trình tạo mã vạch với văn bản mẫu

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Tại sao cần bước này?*  
`BarcodeGenerator` là điểm vào cho mọi tác vụ tạo mã vạch. Cung cấp enum `EncodeTypes.DatabarExpandedStacked` cho thư viện biết sẽ sử dụng ký hiệu nào, trong khi đối số văn bản sẽ trở thành giá trị có thể đọc được được mã hoá trong ký hiệu.

### Bước 2: Đặt số cột (số hàng mặc định được sử dụng)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Tại sao cần bước này?*  
Các ký hiệu DataBar Expanded Stacked bao gồm các phần tử tuyến tính xếp chồng. Điều chỉnh thuộc tính `Columns` thay đổi mật độ theo chiều ngang, cho phép bạn chứa chuỗi dữ liệu dài hơn mà không tăng chiều cao tổng thể. Điều này trực tiếp **tùy chỉnh kích thước mã vạch**.

### Bước 3: Lưu hình ảnh mã vạch sử dụng bốn cột

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Bạn sẽ thấy gì:*  
Hình ảnh `DatabarCols4.png` được lưu hiển thị một mã vạch DataBar rộng hơn mặc định vì nó chứa bốn cột. Bạn có thể mở tệp trong bất kỳ trình xem ảnh nào để xác nhận đầu ra.

### Bước 4: Khởi tạo lại trình tạo cho cấu hình mới

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Tại sao phải khởi tạo lại?*  
Thay đổi thuộc tính `Rows` trong khi giữ lại cài đặt cột trước đó có thể tạo ra một sự kết hợp không mong muốn. Bắt đầu với một thể hiện mới đảm bảo chỉ có tham số dự định (`Rows`) ảnh hưởng đến hình ảnh tiếp theo.

### Bước 5: Đặt số hàng (số cột mặc định được sử dụng)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Tại sao cần bước này?*  
Thuộc tính `Rows` kiểm soát việc xếp chồng theo chiều dọc. Tăng số hàng làm cho mã vạch cao hơn, hữu ích khi không gian ngang hạn chế nhưng không gian dọc phong phú. Đây là một cách khác để **tùy chỉnh kích thước mã vạch**.

### Bước 6: Lưu hình ảnh mã vạch sử dụng ba hàng

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Kết quả:*  
`DatabarRows3.png` cho thấy một mã vạch cao hơn với ba hàng xếp chồng, minh họa cách **cấu hình các tham số databar** ảnh hưởng đến giao diện trực quan.

## Ví dụ đầy đủ có thể chạy

Dưới đây là một chương trình hoàn chỉnh mà bạn có thể sao chép, dán và chạy. Nó bao gồm tất cả các import, xử lý lỗi và chú thích để dễ hiểu.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo hai tệp PNG:

* `DatabarCols4.png` – một mã vạch DataBar rộng với bốn cột.
* `DatabarRows3.png` – một mã vạch DataBar cao với ba hàng.

Mở các hình ảnh để xác nhận rằng kích thước mã vạch khớp với các tham số đã cấu hình.

## Các câu hỏi thường gặp và xử lý trường hợp đặc biệt

| Câu hỏi | Trả lời |
|----------|--------|
| *Nếu tôi cần cả hàng **và** cột tùy chỉnh thì sao?* | Đặt `Rows` **và** `Columns` trên cùng một thể hiện `BarcodeGenerator` trước khi gọi `Save`. Thư viện sẽ kết hợp cả hai giá trị để tạo ra lưới kích thước yêu cầu. |
| *Tôi có thể thay đổi định dạng ảnh không?* | Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp` hoặc `Gif` tùy theo quy trình làm việc của bạn. |
| *Điều gì xảy ra khi văn bản dài hơn khả năng chứa của ký hiệu?* | Trình tạo sẽ ném ra `ArgumentException`. Hãy rút ngắn văn bản hoặc tăng `Columns`/`Rows` để cung cấp dung lượng lớn hơn. |
| *Có cách nào để đặt DPI hoặc độ phân giải ảnh không?* | Sử dụng `generator.Parameters.ImageResolution` để chỉ định DPI mong muốn trước khi lưu. Điều này còn **tùy chỉnh kích thước mã vạch** cho việc in độ phân giải cao. |
| *Thư viện có hỗ trợ các biến thể DataBar khác không?* | Có. Thay `EncodeTypes.DatabarExpandedStacked` bằng `DatabarExpanded`, `DatabarLimited`, v.v., trong khi vẫn giữ cấu trúc tham số giống nhau. |

## Mẹo để tạo mã vạch đáng tin cậy

* **Mẹo chuyên nghiệp:** Luôn kiểm tra hình ảnh đã tạo bằng máy quét hoặc ứng dụng di động trước khi đưa vào sản xuất.  
* **Cẩn thận với:** Thư mục đầu ra rỗng hoặc không tồn tại—`Save` sẽ ném ra ngoại lệ nếu đường dẫn không tồn tại. Tạo thư mục bằng mã nếu cần.  
* **Lưu ý về hiệu năng:** Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất và chỉ thay đổi `Rows` hoặc `Columns` có thể giảm chi phí tạo đối tượng khi tạo nhiều mã vạch trong vòng lặp.

## Kết luận

Bây giờ bạn đã biết cách sử dụng **c# barcode generator** để **tạo hình ảnh mã vạch databar**, **tùy chỉnh kích thước mã vạch**, và **cấu hình các tham số databar** như hàng và cột. Bằng cách điều chỉnh các thiết lập này, bạn có thể đưa mã vạch vào bất kỳ bố cục nào mà vẫn duy trì độ tin cậy khi quét.

Tiếp theo, hãy khám phá các chủ đề liên quan như **cách tạo mã vạch** dưới dạng PDF, nhúng mã vạch vào báo cáo, hoặc chuyển sang các ký hiệu khác (QR, Code‑128, v.v.). Thử nghiệm với các giá trị `Rows`, `Columns` và độ phân giải ảnh khác nhau để tìm cấu hình tối ưu cho trường hợp sử dụng cụ thể của bạn.

---


## Bạn Nên Học Gì Tiếp Theo?


Các tutorial dưới đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động cùng các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}