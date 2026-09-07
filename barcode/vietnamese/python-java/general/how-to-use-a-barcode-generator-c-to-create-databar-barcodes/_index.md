---
category: general
date: 2026-09-07
description: hướng dẫn tạo mã vạch C# cho thấy cách tạo file PNG mã vạch và tạo mã
  DataBar với số hàng và cột có thể tùy chỉnh
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: vi
lastmod: 2026-09-07
og_description: 'Hướng dẫn tạo mã vạch C#: học cách tạo file PNG mã vạch và tạo mã
  DataBar với hàng và cột tùy chỉnh chỉ trong vài phút.'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: Trình tạo mã vạch C# – tạo mã vạch DataBar và hình ảnh PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Cách sử dụng trình tạo mã vạch C# để tạo mã vạch DataBar
url: /vi/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng barcode generator C# để tạo mã vạch DataBar

Nếu bạn cần một **barcode generator C#** để tạo các mã vạch chất lượng cao, hướng dẫn này sẽ chỉ cho bạn cách **generate barcode PNG** và **create DataBar barcodes** với các hàng và cột tùy chỉnh. Dù bạn đang xây dựng hệ thống quản lý tồn kho bán lẻ hay nền tảng bán vé, các bước dưới đây cho phép bạn tạo một mã vạch DataBar Expanded Stacked trong một ví dụ duy nhất, tự chứa.

Trong tutorial này bạn sẽ học:

* Cách khởi tạo `BarcodeGenerator` cho ký hiệu DataBar Expanded Stacked.  
* Cách điều chỉnh cài đặt cột và hàng để đáp ứng các tiêu chuẩn ISO / GS1.  
* Cách lưu kết quả dưới dạng ảnh PNG có thể nhúng vào trang web hoặc in lên nhãn.  

Không cần dịch vụ bên ngoài—chỉ cần thư viện Aspose.BarCode cho .NET (hoặc bất kỳ thư viện tương thích nào có cùng API). Mã chạy trên .NET 6+ và hoạt động trong Visual Studio, Rider, hoặc bất kỳ IDE nào hỗ trợ C#.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6 SDK hoặc phiên bản mới hơn được cài đặt.  
* Tham chiếu tới gói NuGet `Aspose.BarCode` (hoặc thư viện tương đương cung cấp `BarcodeGenerator`, `EncodeTypes`, và `BarCodeImageFormat`).  
* Kiến thức cơ bản về cú pháp C# và cấu trúc dự án.  

Bạn có thể thêm gói bằng dòng lệnh:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Initialize the barcode generator C# for DataBar Expanded Stacked

Bước đầu tiên là tạo một thể hiện `BarcodeGenerator` nhắm tới ký hiệu **DataBar Expanded Stacked**. Đối tượng này chứa tất cả các tham số render, bao gồm cả văn bản cần mã hoá.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Tại sao lại quan trọng:** Giá trị enum `EncodeTypes.DatabarExpandedStacked` cho thư viện biết chuẩn mã vạch nào sẽ được áp dụng. Sử dụng enum đúng đảm bảo hình ảnh tạo ra tuân thủ các quy chuẩn GS1 DataBar.

## Step 2: Configure the number of columns (default rows are used)

DataBar Expanded Stacked có thể được chia thành nhiều cột. Điều chỉnh số cột sẽ thay đổi mật độ hiển thị và giúp vừa các chuỗi dữ liệu dài trong không gian hạn chế.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Mẹo:** Số cột mặc định là 1. Đặt thành 4 sẽ tạo bốn cột xếp chồng, lý tưởng cho các chuỗi số dài hơn đồng thời giữ chiều cao mã vạch ở mức vừa phải.

## Step 3: Generate barcode PNG with the column setting applied

Bây giờ lưu mã vạch dưới dạng ảnh PNG. PNG giữ được các cạnh sắc nét cần thiết cho máy quét và hoạt động tốt trên cả web và in ấn.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Tệp `DatabarCols4.png` chứa một **barcode PNG** mà bạn có thể nhúng trực tiếp vào HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Step 4: Create a separate generator instance for row configuration

Nếu bạn muốn kiểm soát số hàng thay vì số cột, hãy khởi tạo một `BarcodeGenerator` mới. Việc tái sử dụng cùng một thể hiện sau khi thay đổi một kích thước có thể gây ra các lỗi bố cục không mong muốn, vì vậy một đối tượng mới là cách an toàn nhất.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: Set the number of rows (default columns are used)

Số hàng ảnh hưởng đến việc xếp chồng dọc của các mô-đun mã vạch. Tăng số hàng có thể làm mã vạch cao hơn, điều này có thể cần thiết cho một số kích thước nhãn nhất định.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Tại sao hàng khác cột:** Cột chia mã vạch theo chiều ngang, trong khi hàng mở rộng nó theo chiều dọc. Chọn hướng phù hợp nhất với bố cục nhãn của bạn.

## Step 6: Generate barcode PNG with the row setting applied

Cuối cùng, lưu mã vạch đã điều chỉnh hàng dưới dạng tệp PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Bạn hiện có hai tệp PNG riêng biệt:

* `DatabarCols4.png` – 4 cột, 1 hàng.  
* `DatabarRows3.png` – 1 cột, 3 hàng.

Cả hai hình ảnh đều sẵn sàng để sử dụng ngay trong ứng dụng, báo cáo hoặc nhãn in.

## How to generate barcode PNG files in C# with custom dimensions

Mẫu được trình bày ở trên có thể tái sử dụng cho bất kỳ biến thể DataBar nào hoặc các ký hiệu khác mà thư viện hỗ trợ. Dưới đây là một mẫu ngắn gọn bạn có thể sao chép‑dán vào một lớp tiện ích:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Gọi phương thức như sau:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Các trường hợp góc cạnh cần lưu ý**

* **Độ dài dữ liệu** – DataBar Expanded Stacked có thể mã hoá tối đa 74 ký tự số. Vượt quá giới hạn này sẽ ném ra ngoại lệ. Hãy kiểm tra độ dài đầu vào trước khi gọi generator.  
* **Kích thước không hợp lệ** – Thư viện giới hạn cột từ 1‑4 và hàng từ 1‑3 cho ký hiệu này. Cung cấp giá trị ngoài phạm vi sẽ bị bỏ qua hoặc gây lỗi.  
* **DPI ảnh** – Nếu bạn cần độ phân giải cao hơn cho việc in, hãy đặt `generator.Parameters.ImageResolution` trước khi lưu.

## Expected output

Khi mở `DatabarCols4.png` hoặc `DatabarRows3.png` bạn sẽ thấy một mã vạch DataBar rõ ràng, độ tương phản cao. Quét hình ảnh bằng máy quét tương thích GS1 sẽ trả về văn bản gốc `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Alt text: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#*

## Conclusion

Tutorial này đã chứng minh cách một **barcode generator C#** có thể được dùng để **create DataBar barcodes** và **generate barcode PNG** với các cài đặt hàng và cột tùy chỉnh. Bằng cách thực hiện sáu bước—khởi tạo generator, cấu hình cột hoặc hàng, và lưu dưới dạng PNG—bạn sẽ có được các hình ảnh sẵn sàng cho sản xuất, phù hợp cho hệ thống quản lý tồn kho, bán vé, hoặc bất kỳ kịch bản nào yêu cầu render mã vạch đáng tin cậy.

Tiếp theo, bạn có thể khám phá:

* Thêm màu hoặc ảnh nền vào PNG (vẫn tương thích với hầu hết máy quét).  
* Sử dụng các ký hiệu khác như QR, Code 128, hoặc PDF417 qua cùng một API `BarcodeGenerator`.  
* Nhúng PNG đã tạo trực tiếp vào các view ASP.NET Core MVC hoặc thành phần Blazor.

Hãy tự do thử nghiệm với các chuỗi dữ liệu, kích thước và định dạng ảnh khác nhau (ví dụ: JPEG, BMP). Mẫu tương tự áp dụng cho mọi trường hợp, biến **barcode generator C#** thành công cụ đa năng trong hộp công cụ của bất kỳ nhà phát triển .NET nào. Chúc bạn lập trình vui!

## What Should You Learn Next?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã nguồn đầy đủ cùng giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}