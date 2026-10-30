---
category: general
date: 2026-10-28
description: Tạo hình ảnh mã vạch trong C# và tìm hiểu cách điều chỉnh chiều cao bằng
  API BarcodeGenerator. Hướng dẫn từng bước để tùy chỉnh chiều cao mã vạch và thay
  đổi chiều cao các thanh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: vi
lastmod: 2026-10-28
og_description: Tạo hình ảnh mã vạch trong C# và ngay lập tức xem cách điều chỉnh
  chiều cao. Theo dõi ví dụ đầy đủ này để đặt chiều cao mã vạch tùy chỉnh với BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Tạo hình ảnh mã vạch với chiều cao tùy chỉnh trong C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Tạo hình ảnh mã vạch với chiều cao tùy chỉnh trong C#
url: /vi/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch với chiều cao tùy chỉnh trong C#

Nếu bạn cần **tạo hình ảnh mã vạch** và kiểm soát kích thước của nó, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Sử dụng thư viện Aspose.BarCode .NET, bạn có thể tạo mã GS1‑Databar Omni‑Directional, sau đó **cách điều chỉnh chiều cao** để đáp ứng bất kỳ yêu cầu bố cục nào.

Bạn sẽ đi qua một chương trình hoàn chỉnh, có thể chạy được, minh họa **c# barcode generator**, giải thích từng thuộc tính bạn thiết lập, và hiển thị hai kết quả khác nhau — một với chiều cao thanh 30 pixel và một với chiều cao thanh 60 pixel. Khi kết thúc, bạn sẽ có thể **thay đổi chiều cao mã vạch** một cách lập trình cho bất kỳ loại mã vạch nào được thư viện hỗ trợ.

## Yêu cầu trước

- .NET 6.0 SDK hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
- Visual Studio 2022 hoặc bất kỳ trình soạn thảo nào có thể biên dịch dự án C#
- Gói NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Kiến thức cơ bản về cú pháp C#

> **Mẹo chuyên nghiệp:** Nếu bạn đang sử dụng pipeline CI, hãy thêm gói NuGet vào file `csproj` của bạn để quá trình build tự động khôi phục nó.

## Bước 1: Thiết lập dự án và nhập các namespace

Tạo một dự án console mới và thêm các câu lệnh `using` cần thiết. Các namespace này cung cấp cho bạn quyền truy cập vào `BarcodeGenerator`, `EncodeTypes`, và các trợ giúp định dạng ảnh.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Tại sao lại quan trọng:** Nhập đúng các namespace ngăn ngừa lỗi biên dịch và giúp API hiện ra trong IntelliSense.

## Bước 2: Khởi tạo **c# barcode generator** cho mã GS1‑Databar Omni‑Directional

Constructor nhận hai đối số: loại mã vạch (`EncodeTypes.DatabarOmniDirectional`) và chuỗi dữ liệu. Chuỗi dữ liệu phải tuân theo định dạng GS1 Application Identifier, ví dụ `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Giải thích:** Đối tượng `BarcodeGenerator` là điểm khởi đầu cho mọi cài đặt liên quan đến mã vạch. Khi có instance này, bạn có thể tinh chỉnh kích thước, màu sắc và định dạng xuất ra.

## Bước 3: Định nghĩa X‑dimension chung (độ rộng pixel của thanh hẹp nhất)

X‑dimension 2 pixel là điểm khởi đầu tốt cho hầu hết các trường hợp hiển thị trên màn hình.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tại sao phải đặt X‑dimension?** Nó kiểm soát tổng chiều rộng của mã vạch. Giữ giá trị này nhất quán giúp việc thay đổi chiều cao thanh không làm mất cân đối hình ảnh.

## Bước 4: **Tạo hình ảnh mã vạch** với chiều cao thanh 30 pixel

Bây giờ chúng ta cấu hình chiều cao thanh, lưu ảnh đầu tiên, sau đó thay đổi chiều cao cho ảnh thứ hai.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Kết quả:** Bạn sẽ có một file PNG trong đó mỗi thanh dọc có chiều cao 30 pixel. X‑dimension vẫn là 2 pixel, vì vậy tổng chiều rộng không thay đổi.

## Bước 5: **Cách điều chỉnh chiều cao** – thay đổi chiều cao thanh thành 60 pixel

Để minh họa **chiều cao mã vạch tùy chỉnh**, chỉ cần gán một giá trị mới cho cùng một thuộc tính và lưu lại.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Điểm mấu chốt:** Thuộc tính `BarHeight` có thể thay đổi; bạn không cần tạo lại instance `BarcodeGenerator`. Điều này giúp tạo nhiều kích thước trong vòng lặp hoặc quy trình batch một cách hiệu quả.

## Bước 6: Kiểm tra kết quả

Chạy chương trình console (`dotnet run`). Sau khi thực thi, bạn sẽ thấy hai file PNG trong thư mục output của dự án:

- `DatabarBarHeight30Pixels.png` – thanh ngắn (30 px)
- `DatabarBarHeight60Pixels.png` – thanh dài (60 px)

Cả hai ảnh đều chứa cùng một dữ liệu đã mã hoá, nhưng chiều cao hiển thị khác nhau, hữu ích khi tích hợp mã vạch vào biểu mẫu, nhãn sản phẩm, hoặc các thành phần UI có không gian khác nhau.

![Tạo hình ảnh mã vạch với chiều cao tùy chỉnh](barcode-example.png){.align-center width="600" alt="Tạo hình ảnh mã vạch với chiều cao tùy chỉnh"}

> **Mẹo:** Mở các file PNG bằng bất kỳ trình xem ảnh nào. Mã vạch cao hơn sẽ đúng gấp đôi chiều cao dọc so với mã vạch ngắn, trong khi khoảng cách ngang vẫn giữ nguyên.

## Bước 7: Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Cài đặt đề xuất |
|-----------|-----------------|
| **In trên máy in nhãn độ phân giải cao** | Sử dụng X‑dimension lớn hơn (ví dụ 4 px) và tăng `BarHeight` tỷ lệ. |
| **Hiển thị trên màn hình DPI thấp** | Giữ `XDimension` ở 1 px và `BarHeight` trong khoảng 20‑40 px để dễ đọc. |
| **Tạo QR code hoặc mã vạch 2‑D** | Thuộc tính `BarHeight` bị bỏ qua; dùng `EncodeTypes.QR` và điều chỉnh `ImageHeight` thay thế. |
| **Tạo batch nhiều chiều cao** | Lặp qua một mảng các giá trị chiều cao và gọi `Save` trong vòng lặp; không cần tạo lại generator mỗi lần. |

### Xử lý chiều cao không hợp lệ

Thư viện sẽ ném `ArgumentOutOfRangeException` nếu bạn đặt `BarHeight` thành giá trị không dương. Hãy bảo vệ bằng một kiểm tra đơn giản:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Toàn bộ mã nguồn (sẵn sàng sao chép)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Tại sao cách này hoạt động:** Tất cả các cài đặt cần thiết (`EncodeTypes`, `XDimension`, `BarHeight`) được áp dụng trước mỗi lần gọi `Save`. Cùng một instance `BarcodeGenerator` được tái sử dụng, vừa tiết kiệm bộ nhớ vừa dễ đọc.

## Kết luận

Bây giờ bạn đã biết cách **tạo hình ảnh mã vạch** trong C# và chính xác **thay đổi chiều cao mã vạch** bằng API `BarcodeGenerator`. Bằng cách điều chỉnh `BarHeight.Pixels` bạn đạt được **chiều cao mã vạch tùy chỉnh** mà không cần xây dựng lại generator, làm cho giải pháp này lý tưởng cho việc tạo nhãn động, render UI, hoặc các pipeline xử lý batch.

Tiếp theo, khám phá các chủ đề liên quan như **cách điều chỉnh chiều rộng**, **thêm văn bản có thể đọc được**, hoặc **xuất ra SVG cho việc sử dụng trên web có thể mở rộng**. Mô hình giống nhau — đặt thuộc tính, gọi `Save` — áp dụng cho các kịch bản đó, giúp bạn mở rộng ví dụ này một cách tự tin.

## Bạn Nên Học Gì Tiếp Theo?


Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ và giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example – create Planet and RM4SCC barcodes with custom height](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [How to create rm4scc barcode and control its height in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}