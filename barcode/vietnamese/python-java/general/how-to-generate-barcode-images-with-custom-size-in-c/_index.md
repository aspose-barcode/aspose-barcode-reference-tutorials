---
category: general
date: 2026-08-22
description: Cách tạo mã vạch nhanh chóng và học cách thay đổi kích thước mã vạch
  khi xuất hình ảnh mã vạch dưới dạng PNG bằng Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: vi
lastmod: 2026-08-22
og_description: Cách tạo mã vạch trong C# và dễ dàng thay đổi kích thước mã vạch trước
  khi xuất hình ảnh mã vạch dưới dạng PNG. Hãy theo dõi hướng dẫn đầy đủ này.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Cách tạo hình ảnh mã vạch với kích thước tùy chỉnh trong C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách tạo hình ảnh mã vạch với kích thước tùy chỉnh trong C#
url: /vi/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch với kích thước tùy chỉnh trong C#

Nếu bạn cần **cách tạo mã vạch** cho tự động hoá bưu chính, theo dõi tồn kho, hoặc vé sự kiện, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy trong C#. Bạn cũng sẽ học **cách thay đổi kích thước mã vạch** và **xuất tệp hình ảnh mã vạch** ở định dạng PNG mà không rời khỏi IDE của mình.

Chúng tôi sẽ sử dụng thư viện Aspose.BarCode vì nó hỗ trợ ký hiệu OneCode, cho phép bạn kiểm soát kích thước từng pixel, và xử lý việc xuất ảnh chỉ với một lời gọi phương thức. Khi kết thúc hướng dẫn, bạn sẽ có bốn tệp PNG—mỗi tệp đại diện cho một mã vạch OneCode với số chữ số khác nhau.

## Yêu cầu trước

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
- Visual Studio 2022 (hoặc bất kỳ trình chỉnh sửa C# nào bạn thích)
- Tham chiếu NuGet tới **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Kiến thức cơ bản về cú pháp C#

> **Mẹo chuyên nghiệp:** Nếu bạn đang đánh giá thư viện, Aspose cung cấp bản dùng thử miễn phí 30 ngày bao gồm tất cả các tính năng mã vạch.

## Bước 1: Thiết lập dự án console tối thiểu

Tạo một ứng dụng console mới và thêm gói Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Tệp `Program.cs` được tạo sẽ chứa toàn bộ logic tạo mã vạch.

## Bước 2: Cách tạo mã vạch – tạo phương thức tái sử dụng

Dưới đây là một phương thức tự chứa nhận chuỗi dữ liệu, tên tệp mong muốn và các tham số kích thước tùy chọn. Phương thức này minh họa mẫu cốt lõi **cách tạo mã vạch**.

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
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Tại sao phương thức này quan trọng

- **Đóng gói:** Tất cả các cài đặt liên quan đến kích thước đều nằm trong một nơi, giúp gọi phương thức với các kích thước khác nhau một cách đơn giản.
- **Tái sử dụng:** Bạn có thể tái sử dụng cùng một phương thức cho bất kỳ độ dài chuỗi OneCode nào, điều này quan trọng vì OneCode chỉ chấp nhận 20‑31 chữ số.
- **Rõ ràng:** Các chú thích có biểu tượng cảm xúc hướng dẫn người đọc qua ba giai đoạn logic—khởi tạo, thay đổi kích thước và xuất.

## Bước 3: Thay đổi kích thước mã vạch cho các yêu cầu khác nhau

Đôi khi máy quét yêu cầu một mã vạch cao hơn, hoặc bố cục in yêu cầu mô-đun hẹp hơn. Thuộc tính `XDimension.Pixels` kiểm soát chiều rộng của một mô-đun mã vạch, trong khi `BarHeight.Pixels` đặt chiều cao tổng thể.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Các điểm quan trọng khi bạn thay đổi kích thước:**

- **Kích thước X tối thiểu:** 1 pixel về mặt kỹ thuật cho phép, nhưng hầu hết máy quét cần ít nhất 2 pixel để đọc đáng tin cậy.
- **Chiều cao tối đa:** Không có giới hạn cứng, nhưng các mã vạch rất cao có thể vượt quá khu vực in trên nhãn tiêu chuẩn.
- **Tỷ lệ khung hình:** Giữ tỷ lệ chiều cao‑so‑với‑chiều rộng mô-đun cân bằng (≈12‑15 × chiều rộng mô-đun) để tránh biến dạng.

## Bước 4: Xuất hình ảnh mã vạch sang các định dạng khác (tùy chọn)

Phương thức `Save` chấp nhận một số giá trị `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Nếu bạn cần định dạng vector không mất dữ liệu, bạn có thể xuất sang `Svg` thay thế.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Xuất dưới dạng PNG là lựa chọn phổ biến nhất vì nó giữ được các cạnh sắc nét và được hỗ trợ rộng rãi bởi trình duyệt web và quy trình in ấn.

## Kết quả mong đợi

Chạy chương trình sẽ tạo ra bốn tệp PNG trong thư mục dự án:

- `PostalOneCodeBarcode20Digits.png` – Mã vạch OneCode 20 chữ số
- `PostalOneCodeBarcode25Digits.png` – Mã vạch OneCode 25 chữ số
- `PostalOneCodeBarcode29Digits.png` – Mã vạch OneCode 29 chữ số
- `PostalOneCodeBarcode31Digits.png` – Mã vạch OneCode 31 chữ số

Mỗi hình ảnh sẽ trông tương tự như hình placeholder dưới đây (đồ họa thực tế phụ thuộc vào dữ liệu số bạn cung cấp).

![Ví dụ cách tạo mã vạch](https://example.com/placeholder.png "Ví dụ cách tạo mã vạch")

*Văn bản alt của hình ảnh bao gồm từ khóa chính để hỗ trợ truy cập và SEO.*

## Các câu hỏi thường gặp và trường hợp đặc biệt

| Câu hỏi | Câu trả lời |
|----------|--------|
| **Nếu chuỗi dữ liệu ngắn hơn 20 chữ số thì sao?** | OneCode yêu cầu tối thiểu 20 chữ số. Hãy bổ sung các số 0 ở đầu chuỗi hoặc sử dụng ký hiệu khác (ví dụ, Code128). |
| **Tôi có thể tạo mã vạch trong môi trường đa luồng không?** | Có. `BarcodeGenerator` không an toàn với đa luồng, vì vậy hãy tạo một đối tượng generator riêng cho mỗi luồng. |
| **Làm thế nào để đặt màu nền?** | Sử dụng `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` trước khi gọi `Save`. |
| **Có cách nào để nhúng hình ảnh trực tiếp vào trang HTML không?** | Lưu hình ảnh vào một `MemoryStream`, chuyển sang Base64, và nhúng bằng `<img src="data:image/png;base64,..." />`. |

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch** dưới dạng hình ảnh trong C# với Aspose.BarCode, cách **thay đổi kích thước mã vạch** bằng việc điều chỉnh X‑dimension và chiều cao thanh, và cách **xuất tệp hình ảnh mã vạch** ở định dạng PNG (hoặc các định dạng khác). Phương thức tái sử dụng `GenerateOneCode` cho phép bạn tạo bất kỳ mã vạch OneCode nào từ 20 đến 31 chữ số chỉ với một dòng lệnh.

Từ đây bạn có thể:

- Thử nghiệm các ký hiệu khác (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Tích hợp generator vào một web API trả về hình ảnh mã vạch theo yêu cầu.
- Kết hợp đầu ra PNG với thư viện PDF để nhúng mã vạch vào nhãn vận chuyển.

Chúc lập trình vui vẻ, và hãy thoải mái chia sẻ các biến thể của bạn trong phần bình luận!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh, hoạt động với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Tạo Mã DataMatrix Bằng Aspose.BarCode cho .NET – Hướng Dẫn Từng Bước](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cách tạo mã Aztec với tỷ lệ khung hình tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cách Tạo và Điều Chỉnh Chiều Cao Mã Vạch One-Dimensional Databar bằng Aspose.BarCode cho .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}