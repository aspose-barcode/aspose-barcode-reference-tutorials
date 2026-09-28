---
category: general
date: 2026-08-19
description: Tạo tệp PNG databar trong C# với Aspose.BarCode. Tìm hiểu cách tạo hình
  ảnh databar, cấu hình các tham số databar và lưu đầu ra PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: vi
lastmod: 2026-08-19
og_description: Tạo các tệp PNG databar trong C# bằng Aspose.BarCode. Hướng dẫn này
  sẽ chỉ cho bạn cách tạo hình ảnh databar, cấu hình các tham số databar như kích
  thước X và tỷ lệ khung hình, và lưu các tệp PNG chất lượng cao để in hoặc sử dụng
  trên web.
og_image_alt: create databar PNG example
og_title: Tạo hình ảnh PNG dạng databar trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Cách tạo hình ảnh PNG dạng databar bằng C# và Aspose.BarCode
url: /vi/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh databar PNG với C# và Aspose.BarCode

Nếu bạn cần **tạo databar PNG** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một ví dụ đầy đủ, có thể chạy được, tạo ra các mã DataBar xếp chồng omnidirectional, cấu hình các tham số chính, và lưu hai tệp PNG với tỷ lệ khung hình khác nhau.

Việc tạo hình ảnh DataBar không chỉ đơn giản là gọi một phương thức duy nhất. Bạn cũng phải **cấu hình các tham số databar** như X‑dimension (độ rộng mô-đun) và tỷ lệ khung hình để đáp ứng các yêu cầu in ấn hoặc quét. Khi kết thúc tutorial này, bạn sẽ hiểu **cách tạo đồ họa databar** hoạt động đáng tin cậy trong các tình huống thực tế.

## Yêu cầu trước

- .NET 6.0 trở lên (mã cũng hoạt động với .NET Framework 4.7+)
- Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
- Giấy phép hợp lệ cho **Aspose.BarCode for .NET** (phiên bản dùng thử miễn phí hoạt động để thử nghiệm)
- Kiến thức cơ bản về cú pháp C#

> **Mẹo chuyên nghiệp:** Nếu bạn chưa có giấy phép, bạn có thể yêu cầu một khóa đánh giá tạm thời từ cổng thông tin Aspose. API hoạt động như bình thường; chỉ có watermark thay đổi.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở dự án của bạn trong Visual Studio, nhấp chuột phải vào solution và chọn **Manage NuGet Packages**. Tìm kiếm `Aspose.BarCode` và cài đặt phiên bản ổn định mới nhất.

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm assembly `Aspose.BarCode` vào dự án của bạn và cho phép sử dụng lớp `BarcodeGenerator`.

## Bước 2: Khởi tạo trình tạo mã vạch cho DataBar xếp chồng omnidirectional

Constructor của `BarcodeGenerator` nhận hai đối số: loại mã vạch và chuỗi dữ liệu thô. Đối với DataBar xếp chồng omnidirectional, bạn sử dụng `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Tại sao điều này quan trọng:** Hằng số `EncodeTypes.DatabarStackedOmniDirectional` thông báo cho thư viện tạo ra một mã vạch có thể đọc được từ bất kỳ hướng nào, rất phù hợp cho nhãn kệ bán lẻ.

## Bước 3: Cấu hình X‑dimension (độ rộng mô-đun) bằng pixel

X‑dimension kiểm soát kích thước của phần tử thanh nhỏ nhất. Đặt giá trị bằng pixel cho phép bạn kiểm soát chính xác kích thước hình ảnh cuối cùng.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Giá trị **2 pixel** là sự cân bằng tốt giữa khả năng đọc và độ gọn cho hầu hết các máy in nhãn. Điều chỉnh giá trị này nếu bạn cần mô-đun lớn hơn hoặc nhỏ hơn.

## Bước 4: Đặt tỷ lệ khung hình đầu tiên và lưu PNG

Tỷ lệ khung hình ảnh hưởng đến chiều cao của DataBar xếp chồng. Tỷ lệ **15** tạo ra một mã vạch tương đối ngắn, trong khi **30** làm nó cao hơn.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Phương thức `Save` ghi mã vạch đã tạo ra vào tệp PNG. PNG là định dạng không mất dữ liệu, giữ được các cạnh sắc nét cần thiết cho máy quét mã vạch.

## Bước 5: Thay đổi tỷ lệ khung hình và lưu PNG thứ hai

Bạn có thể tái sử dụng cùng một đối tượng `BarcodeGenerator` để tạo các biến thể chỉ bằng cách thay đổi tỷ lệ khung hình.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Bây giờ bạn có hai tệp PNG—`DatabarAspectRatio15.png` và `DatabarAspectRatio30.png`—mỗi tệp có mật độ hình ảnh khác nhau.

## Bước 6: Kiểm tra kết quả

Mở các tệp PNG đã tạo trong bất kỳ trình xem ảnh nào. Bạn sẽ thấy một mã DataBar sạch sẽ, độ tương phản cao. Quét các hình ảnh bằng ứng dụng quét mã vạch trên điện thoại thông minh xác nhận rằng cả hai tỷ lệ khung hình đều giải mã được giá trị GTIN gốc `12345678901231`.

![create databar PNG example](databar_example.png)

*Hình ảnh trên hiển thị hai tệp PNG cạnh nhau. Hình bên trái sử dụng tỷ lệ 15, hình bên phải sử dụng tỷ lệ 30.*

## Các biến thể phổ biến và trường hợp biên

| Scenario | What to change | Reason |
|----------|----------------|--------|
| **Dữ liệu khác** | Thay thế chuỗi `(01)12345678901231` bằng bất kỳ GS1 Application Identifier và dữ liệu hợp lệ nào | Cho phép bạn mã hoá ID sản phẩm, số serial, v.v. |
| **Độ phân giải cao hơn** | Tăng `XDimension.Pixels` lên 3 hoặc 4 | Cần thiết khi mã vạch sẽ được in ở kích thước lớn hoặc quét từ khoảng cách xa. |
| **Các loại DataBar khác** | Sử dụng `EncodeTypes.DatabarStacked` hoặc `EncodeTypes.DatabarExpanded` | Chọn loại phù hợp nhất với bố cục nhãn của bạn. |
| **Nền trong suốt** | Truyền `BarCodeImageFormat.Png` cùng với `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Hữu ích khi đặt mã vạch lên nhãn màu. |

> **Cẩn thận:** Đặt X‑dimension quá nhỏ (< 1 pixel) có thể tạo ra mã vạch bị mờ sau

## Bạn nên học gì tiếp theo?

Các tutorial sau đây bao quát các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, có hướng dẫn từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo và điều chỉnh chiều cao mã vạch One-Dimensional Databar bằng Aspose.BarCode cho .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Tạo mã One-Dimensional Databar GS1 Encoding với Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Tạo mã Databar Aspose.BarCode bằng .NET API – Cấu hình hàng & cột](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}