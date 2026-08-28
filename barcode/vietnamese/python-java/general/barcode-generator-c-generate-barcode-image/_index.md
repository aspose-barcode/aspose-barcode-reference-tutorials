---
category: general
date: 2026-08-03
description: Hướng dẫn tạo mã vạch C# cho thấy cách tạo hình ảnh mã vạch bằng Aspose.BarCode,
  thiết lập cột và hàng, và lưu các tệp PNG cho DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: vi
lastmod: 2026-08-03
og_description: Hướng dẫn tạo mã vạch C# giải thích cách tạo hình ảnh mã vạch bằng
  Aspose.BarCode, cấu hình các cột và hàng của DataBar Expanded Stacked, và lưu các
  tệp PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Trình tạo mã vạch C# – hướng dẫn từng bước để tạo hình ảnh mã vạch
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Trình tạo mã vạch C# – tạo hình ảnh mã vạch
url: /vi/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trình tạo mã vạch C# – tạo hình ảnh mã vạch

Nếu bạn cần một trình tạo mã vạch C# có thể tạo hình ảnh mã vạch cho DataBar Expanded Stacked, hướng dẫn này sẽ đưa bạn qua toàn bộ quá trình. Bạn sẽ học cách cấu hình cài đặt cột và hàng, lưu kết quả dưới dạng PNG, và điều chỉnh mã cho các loại mã vạch khác.

Tạo hình ảnh mã vạch một cách lập trình loại bỏ các bước thủ công và đảm bảo tính nhất quán trên các hoá đơn, nhãn vận chuyển và hệ thống tồn kho. Bài hướng dẫn này bao gồm mọi thứ bạn cần, từ thiết lập dự án đến mã nguồn đầy đủ, để bạn có thể chạy ví dụ ngay lập tức.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn đã được cài đặt  
* Một IDE như Visual Studio 2022 (bất kỳ trình chỉnh sửa nào hỗ trợ C# đều hoạt động)  
* Một giấy phép cho **Aspose.BarCode for .NET** – phiên bản dùng thử miễn phí hoạt động cho việc kiểm tra  
* Hiểu biết cơ bản về cú pháp C#  

Nếu bất kỳ mục nào trong số này còn thiếu, hãy cài đặt .NET SDK từ dotnet.microsoft.com và lấy gói Aspose.BarCode NuGet bằng:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Tạo dự án trình tạo mã vạch C# project

Tạo một ứng dụng console mới và thêm các chỉ thị `using` cần thiết:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

Lớp `BarcodeGenerator` là lõi của API trình tạo mã vạch C#. Nó nhận loại symbology và văn bản cần mã hoá.

## Bước 2: Tạo mã vạch DataBar Expanded Stacked và đặt số cột

Ví dụ đầu tiên tạo một mã vạch với bốn cột. Điều chỉnh thuộc tính `Columns` sẽ thay đổi mật độ hiển thị của symbology DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Tại sao điều này quan trọng:** Số cột ảnh hưởng đến lượng dữ liệu có thể lưu trữ trong không gian nhỏ gọn. Đặt giá trị thành 4 sẽ tạo ra một mã vạch rộng hơn nhưng vẫn có thể đọc được bởi hầu hết các máy quét.

## Bước 3: Tạo mã vạch với số hàng tùy chỉnh

Ví dụ thứ hai cho thấy cách kiểm soát bố cục dọc bằng cách đặt thuộc tính `Rows`. Cấu hình ba hàng hữu ích khi bạn cần một mã vạch cao hơn cho không gian ngang hạn chế.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Tại sao điều này quan trọng:** Điều chỉnh số hàng cho phép bạn đặt mã vạch vào một cột hẹp trong khi vẫn duy trì khả năng đọc. Trình tạo mã vạch C# tự động tính lại kích thước module để đáp ứng tiêu chuẩn.

## Bước 4: Ví dụ đầy đủ, có thể chạy

Dưới đây là một chương trình tự chứa kết hợp các bước trước. Sao chép mã vào `Program.cs`, thay thế `YOUR_DIRECTORY` bằng đường dẫn thư mục hiện có, và chạy ứng dụng.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Kết quả mong đợi

Khi bạn chạy chương trình, hai tệp PNG sẽ xuất hiện trong thư mục đích:

* **DatabarCols4.png** – một mã vạch DataBar Expanded Stacked với bốn cột  
* **DatabarRows3.png** – cùng dữ liệu được mã hoá trong ba hàng  

Mở các hình ảnh bằng bất kỳ trình xem ảnh nào; chúng hiển thị mã vạch sắc nét, có thể quét được, sẵn sàng để in hoặc nhúng vào PDF.

## Cách tạo hình ảnh mã vạch với kích thước tùy chỉnh

Nếu bạn cần kích thước ảnh cụ thể, hãy điều chỉnh các thuộc tính `ImageHeight` và `ImageWidth` trước khi gọi `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Thay đổi kích thước không ảnh hưởng đến dữ liệu đã mã hoá; nó chỉ thay đổi tỉ lệ hiển thị. Kỹ thuật này hữu ích khi tích hợp mã vạch vào các thành phần UI có ràng buộc bố cục cố định.

## Những lỗi thường gặp và mẹo chuyên nghiệp

* **Path separators:** Sử dụng chuỗi nguyên (`@"C:\Path\file.png"`) hoặc `Path.Combine` để tránh các vấn đề ký tự escape trên Windows.  
* **License enforcement:** Nếu không có giấy phép hợp lệ, các hình ảnh được tạo sẽ chứa watermark. Áp dụng giấy phép của bạn sớm trong ứng dụng:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Encoding limits:** DataBar Expanded Stacked hỗ trợ tối đa 74 ký tự số. Vượt quá giới hạn này sẽ gây ra ngoại lệ. Kiểm tra độ dài đầu vào trước khi tạo trình tạo.  
* **Performance:** Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất cho nhiều lần lưu giảm việc cấp phát bộ nhớ. Chỉ thay đổi các thuộc tính `Rows` hoặc `Columns` giữa các lần lưu nếu văn bản đã mã hoá vẫn giữ nguyên.

## Các bước tiếp theo

Bây giờ bạn đã có thể tạo hình ảnh mã vạch với trình tạo mã vạch C#, hãy cân nhắc khám phá:

* **Different symbologies** – thử `EncodeTypes.QR`, `EncodeTypes.Code128`, hoặc `EncodeTypes.Pdf417`.  
* **Color customization** – đặt `Parameters.Barcode.ForeColor` và `BackColor` để phù hợp với thương hiệu.  
* **Embedding in PDFs** – kết hợp PNG đã tạo với Aspose.PDF để tạo tài liệu có thể in.  

Các phần mở rộng này cho phép bạn xây dựng một giải pháp mã vạch đầy đủ tính năng cho các ứng dụng quản lý tồn kho, logistics hoặc bán lẻ.

---

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động cùng giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo hình ảnh mã vạch – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Tạo hình ảnh mã vạch DotCode – hàng & cột (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}