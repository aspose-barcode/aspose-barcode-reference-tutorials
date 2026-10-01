---
category: general
date: 2026-08-06
description: Cách thiết lập mã vạch bằng Aspose.BarCode trong C#. Tìm hiểu cách thay
  đổi ký tự macro và tạo hình ảnh mã vạch C# với mã từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to change macro
- barcode generator c#
- create barcode image c#
language: vi
lastmod: 2026-08-06
og_description: Cách thiết lập mã vạch với Aspose.BarCode trong C#. Hướng dẫn này
  cho thấy cách thay đổi ký tự macro và tạo nhanh hình ảnh mã vạch C#.
og_image_alt: Screenshot of a MicroPDF417 barcode generated with C# code
og_title: Cách thiết lập mã vạch trong C# – Hướng dẫn Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set barcode using Aspose.BarCode in C#. Learn how to change
    macro characters and create barcode image C# with step‑by‑step code.
  headline: How to set barcode in C# – complete Aspose.BarCode guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách thiết lập mã vạch trong C# – hướng dẫn đầy đủ Aspose.BarCode
url: /vi/net/one-dimensional-barcode-types/how-to-set-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập mã vạch trong C# – hướng dẫn đầy đủ Aspose.BarCode

Nếu bạn cần **cách thiết lập mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn các bước chính xác bằng cách sử dụng Aspose.BarCode. Bạn sẽ thấy cách thay đổi ký tự macro, điều chỉnh các tham số trực quan, và **tạo file ảnh mã vạch C#** có thể lưu trực tiếp vào đĩa.

Hướng dẫn bao gồm mọi thứ từ cài đặt thư viện đến tạo hai mã vạch MicroPDF417 với các giá trị macro khác nhau. Không cần tài liệu bên ngoài—bạn có thể sao chép mã, chạy nó, và kiểm tra kết quả PNG ngay lập tức.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 hoặc mới hơn (ví dụ sử dụng dự án console)
* Visual Studio 2022 hoặc bất kỳ IDE C# nào
* Giấy phép Aspose.BarCode đang hoạt động (bản dùng thử miễn phí cũng đủ cho việc thử nghiệm)
* Kiến thức cơ bản về cú pháp C#

Bạn cũng sẽ cần gói NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Cách thiết lập các tham số mã vạch – bước 1: tạo generator

Hành động đầu tiên là khởi tạo một `BarcodeGenerator` với ký hiệu và dữ liệu mong muốn. Sử dụng `EncodeTypes.MicroPdf417` cho Aspose.BarCode biết tạo ra một biến thể PDF417 gọn nhẹ.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 1: Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, // symbology
                "12345ABC");             // data to encode
```

**Tại sao điều này quan trọng:** `BarcodeGenerator` là đối tượng trung tâm; tất cả các cài đặt sau này sẽ sửa đổi thuộc tính `Parameters` của nó. Chọn đúng `EncodeTypes` đảm bảo mã vạch tuân theo tiêu chuẩn MicroPDF417.

## Cách thay đổi ký tự macro – bước 2: điều chỉnh các tham số trực quan

Ký tự macro là các mã điều khiển tùy chọn cho phép bạn nối nhiều ký hiệu PDF417 lại với nhau. Ví dụ chuyển đổi giữa `Macro05` và `Macro06`. Bạn cũng thiết lập độ rộng mô-đun (`XDimension`) và số cột để kiểm soát kích thước mã vạch.

```csharp
            // Step 2: Adjust visual parameters – set the X‑dimension (module width) and number of columns
            generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width in pixels
            generator.Parameters.Barcode.Pdf417.Columns = 4;           // number of data columns

            // Encode the first macro character (Macro05) and save the image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro05;
            generator.Save("MicroPdf417_Macro05.png", BarCodeImageFormat.Png);
```

**Tại sao bạn thay đổi macro:** Ký tự macro thông báo cho máy quét rằng mã vạch này là một phần của tập dữ liệu lớn hơn. Việc chuyển đổi nó minh họa cách cùng một dữ liệu có thể được liên kết với các định danh macro khác nhau.

## Cách thiết lập mã vạch – bước 3: tạo mã vạch thứ hai với macro khác

Bây giờ chúng ta tái sử dụng cùng một thể hiện `generator`, chỉ thay đổi giá trị macro. Điều này tránh việc tạo lại đối tượng và chứng minh rằng **cách thiết lập mã vạch** có thể thực hiện tại thời gian chạy.

```csharp
            // Step 3: Switch to the second macro character (Macro06) and save the new image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro06;
            generator.Save("MicroPdf417_Macro06.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ tạo hai file PNG trong thư mục dự án:

* `MicroPdf417_Macro05.png` – mã vạch với Macro05
* `MicroPdf417_Macro06.png` – mã vạch với Macro06

Cả hai hình ảnh đều hiển thị một ký hiệu MicroPDF417 gọn nhẹ mã hoá `12345ABC`. Bạn có thể mở các file PNG bằng bất kỳ trình xem ảnh nào để kiểm tra chất lượng hình ảnh.

## Các thực hành tốt nhất khi sử dụng Barcode generator C#

* **Tái sử dụng generator:** Thay đổi `Parameters` trên một thể hiện hiện có hiệu quả hơn so với việc tạo generator mới cho mỗi mã vạch.
* **Đặt X‑dimension sớm:** Độ rộng mô-đun ảnh hưởng đến kích thước tổng thể của hình ảnh; hãy điều chỉnh trước khi lưu.
* **Xác thực việc sử dụng macro:** Không phải tất cả máy quét đều hỗ trợ ký tự macro. Hãy thử nghiệm với phần cứng mục tiêu nếu bạn dự định sử dụng chúng trong môi trường sản xuất.
* **Giải phóng tài nguyên:** `BarcodeGenerator` triển khai `IDisposable`. Trong dịch vụ chạy lâu, hãy bọc nó trong khối `using` hoặc gọi `Dispose()` khi hoàn thành.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "12345ABC"))
{
    // configure parameters...
}
```

## Tạo ảnh mã vạch C# – mẹo khắc phục sự cố

| Triệu chứng                         | Nguyên nhân có thể                                 | Cách khắc phục                                 |
|-------------------------------------|----------------------------------------------------|-----------------------------------------------|
| File PNG trống                      | `XDimension` được đặt thành 0 hoặc giá trị quá cao | Sử dụng độ rộng pixel hợp lý (1‑5)            |
| Mã vạch không đọc được bởi máy quét | Ký tự macro không phù hợp với máy quét             | Kiểm tra tài liệu máy quét; sử dụng `MacroNone` nếu không cần |
| Ngoại lệ `ArgumentOutOfRangeException` | Số cột vượt ngoài phạm vi cho phép (1‑30)          | Giữ `Columns` trong khoảng từ 1 đến 30        |

## Kết luận

Bây giờ bạn đã biết **cách thiết lập thuộc tính mã vạch**, **cách thay đổi ký tự macro**, và cách **tạo file ảnh mã vạch C#** bằng Aspose.BarCode. Ví dụ đầy đủ, có thể chạy được này minh họa quy trình toàn bộ từ việc tạo generator đến xuất ảnh.

Tiếp theo, khám phá các ký hiệu khác (`EncodeTypes.QR`, `EncodeTypes.Code128`) hoặc nhúng mã vạch trực tiếp vào PDF bằng Aspose.PDF. Cả hai chủ đề đều thuộc hệ sinh thái rộng hơn **barcode generator c#** và có thể được thêm vào dự án này với ít thay đổi mã.

Chúc lập trình vui vẻ, và hãy thoải mái thử nghiệm với các giá trị macro, kích thước và định dạng đầu ra khác nhau!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh, hoạt động kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo vùng yên tĩnh cho mã vạch Code 16K bằng Aspose.BarCode cho .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cách tạo dotcode với văn bản mã mở rộng bằng Aspose.BarCode cho .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Cách đặt viền cho tùy chỉnh mã vạch ITF-14](/barcode/english/net/itf-14-barcode-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}