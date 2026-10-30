---
category: general
date: 2026-10-28
description: Tạo hình ảnh mã vạch trong C# nhanh chóng. Tìm hiểu cách sử dụng trình
  tạo mã vạch C#, cách đặt kích thước pixel và cách thay đổi tỷ lệ khung hình cho
  DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: vi
lastmod: 2026-10-28
og_description: Tạo hình ảnh mã vạch trong C# bằng Trình tạo Mã vạch. Tham khảo hướng
  dẫn này để đặt kích thước pixel, thay đổi tỷ lệ khung hình và tạo mã vạch DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn từng bước
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Cách tạo ảnh mã vạch bằng C# sử dụng Barcode Generator
url: /vi/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch với C# sử dụng Barcode Generator

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được sử dụng thư viện Barcode Generator C# để tạo mã DataBar stacked omnidirectional, thiết lập kích thước pixel và thay đổi tỷ lệ khung hình.

Tạo mã vạch bằng chương trình loại bỏ nhu cầu sử dụng công cụ bên ngoài và cho phép bạn nhúng hình ảnh trực tiếp vào PDF, báo cáo hoặc các điều khiển UI. Trong các bước dưới đây, chúng tôi cũng sẽ đề cập đến **cách thiết lập kích thước pixel** và **cách thay đổi tỷ lệ khung hình**, hai yêu cầu phổ biến khi bạn cần một mã vạch sắc nét, được tỷ lệ đúng.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Một IDE tương thích C# (Visual Studio, Rider, hoặc VS Code)  
* Gói NuGet `BarcodeGenerator` (ví dụ: `GroupDocs.Barcode` hoặc `Aspose.Barcode`) đã được cài đặt trong dự án của bạn  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package GroupDocs.Barcode
```

> **Mẹo chuyên nghiệp:** Kiểm tra phiên bản gói phù hợp với framework mục tiêu của bạn để tránh các lỗi không tương thích thời gian chạy.

## Tạo hình ảnh mã vạch với Barcode Generator C#

Bước đầu tiên là khởi tạo trình tạo với loại mã vạch và dữ liệu mong muốn. Ví dụ dưới đây tạo một mã **DataBar stacked omnidirectional**, lý tưởng cho các kịch bản quét bán lẻ.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **Khởi tạo `BarcodeGenerator`** – Hàm khởi tạo nhận một loại ký hiệu mã vạch (`EncodeTypes.DatabarStackedOmniDirectional`) và chuỗi dữ liệu thô. Việc chọn đúng ký hiệu đảm bảo máy quét có thể đọc được mã.  
* **Thiết lập `XDimension.Pixels`** – Thuộc tính này kiểm soát độ rộng của phần tử thanh nhỏ nhất. Giá trị `2` tạo ra một hình ảnh chi tiết mịn mà vẫn đọc được trên hầu hết các màn hình. Tăng giá trị lên nếu bạn cần mã vạch lớn hơn cho máy in độ phân giải thấp.  
* **Cấu hình `AspectRatio`** – Dòng DataBar hỗ trợ một số tỷ lệ khung hình ảnh hưởng đến mối quan hệ chiều cao‑chiều rộng. Các giá trị `15` và `30` là phổ biến; `15` tạo ra mã vạch ngắn hơn, trong khi `30` tạo ra mã vạch cao hơn.  
* **Phương thức `Save`** – Lưu mã vạch đã tạo vào một tệp PNG. Bạn có thể thay `BarCodeImageFormat.Png` bằng `Jpeg` hoặc `Bmp` nếu hệ thống downstream của bạn yêu cầu định dạng khác.  

## Cách thiết lập kích thước pixel cho các ngữ cảnh render khác nhau

Kích thước pixel quyết định mật độ hình ảnh của mã vạch. Nếu mã vạch sẽ được hiển thị trên màn hình DPI cao, bạn có thể tăng kích thước pixel lên `3` hoặc `4`. Ngược lại, đối với máy in nhiệt độ phân giải thấp, kích thước pixel nhỏ hơn (ví dụ, `1`) sẽ giảm lượng mực sử dụng.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Trường hợp đặc biệt:** Đặt kích thước pixel quá thấp (< 1) sẽ gây ra `ArgumentOutOfRangeException`. Luôn kiểm tra giá trị trước khi gán.

## Cách thay đổi tỷ lệ khung hình mà không cần tạo lại trình tạo

Thay đổi tỷ lệ khung hình là một cập nhật thuộc tính đơn giản; bạn **không** cần tạo lại thể hiện `BarcodeGenerator`. Điều này tiết kiệm bộ nhớ và cải thiện hiệu suất khi bạn cần nhiều hình ảnh với các hình dạng khác nhau.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Nếu bạn cần hơn hai tỷ lệ, bạn có thể lặp qua một mảng:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Kết quả mong đợi

Chạy chương trình sẽ tạo ra hai tệp PNG (hoặc nhiều hơn nếu bạn dùng vòng lặp). Mở chúng trong bất kỳ trình xem ảnh nào; bạn sẽ thấy một mã DataBar sạch sẽ:

* **DatabarAspectRatio15.png** – mã vạch ngắn, rộng phù hợp cho không gian nhãn hẹp.  
* **DatabarAspectRatio30.png** – mã vạch cao hơn giúp cải thiện độ tin cậy khi quét bằng máy quét góc.

Cả hai hình ảnh đều có cùng kích thước pixel (2 px mỗi mô-đun) nhưng chỉ khác nhau về chiều cao, minh họa **cách thay đổi tỷ lệ khung hình** trong khi giữ các tham số khác không đổi.

## Những lỗi thường gặp và cách tránh

| Triệu chứng | Nguyên nhân | Cách khắc phục |
|------------|-------------|----------------|
| Mã vạch xuất hiện mờ | `XDimension.Pixels` được đặt quá thấp cho độ phân giải đầu ra | Tăng kích thước pixel lên ít nhất `2` cho hiển thị trên màn hình, `3` cho in |
| Máy quét không thể đọc mã | `EncodeTypes` không phù hợp với định dạng dữ liệu | Kiểm tra dữ liệu GTIN‑14 có khớp với ký hiệu đã chọn không |
| `ArgumentOutOfRangeException` khi thay đổi tỷ lệ khung hình | Giá trị tỷ lệ không được thư viện hỗ trợ (phạm vi hợp lệ: 15‑30) | Chỉ sử dụng các giá trị được tài liệu của thư viện liệt kê, hoặc bắt ngoại lệ và chuyển về giá trị mặc định |
| Không tìm thấy tệp sau khi `Save` | Đường dẫn tương đối trỏ tới thư mục không tồn tại | Sử dụng đường dẫn tuyệt đối hoặc đảm bảo gọi `Directory.CreateDirectory` trước |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Các bước tiếp theo – mở rộng quy trình mã vạch

Bây giờ bạn đã có thể **tạo hình ảnh mã vạch**, bạn có thể muốn:

* **Nhúng PNG vào PDF** bằng thư viện như `PdfSharp` hoặc `iTextSharp`.  
* **Tạo các ký hiệu khác** (QR, Code128, PDF417) bằng cách thay đổi enum `EncodeTypes`.  
* **Áp dụng chuyển đổi màu** bằng cách truy cập `barcode.Parameters.Barcode.Image.Color`.  
* **Phục vụ hình ảnh qua endpoint ASP.NET Core** để tạo hình ảnh ngay lập tức trong các ứng dụng web.

Mỗi chủ đề này dựa trên các khái niệm cốt lõi đã được đề cập trong hướng dẫn, chẳng hạn như việc sử dụng **barcode generator c#**, kiểm soát kích thước pixel và thao tác tỷ lệ khung hình.

## Kết luận

Bạn giờ đã biết cách **tạo hình ảnh mã vạch** trong C# với Barcode Generator, cách thiết lập kích thước pixel, cách thay đổi tỷ lệ khung hình, và cách tạo mã DataBar một cách hiệu quả. Ví dụ hoàn chỉnh, có thể chạy được có thể sao chép vào bất kỳ dự án .NET nào, điều chỉnh cho các ký hiệu khác và mở rộng để phù hợp với quy trình thực tế.

Hãy thoải mái thử nghiệm với các giá trị `XDimension` khác nhau, tỷ lệ khung hình và định dạng đầu ra. Nếu gặp vấn đề, hãy xem lại bảng “Những lỗi thường gặp” hoặc tham khảo tài liệu chính thức của thư viện để biết các tùy chọn cấu hình sâu hơn. Chúc bạn lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch và điều chỉnh tỷ lệ khung hình trong C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Cách tạo bộ mã vạch kích thước tùy chỉnh và lưu hình ảnh trong C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Cách sử dụng barcode generator C# để tạo mã DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}