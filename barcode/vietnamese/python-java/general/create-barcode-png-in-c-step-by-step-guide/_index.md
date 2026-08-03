---
category: general
date: 2026-08-03
description: Tạo mã vạch PNG trong C# và tìm hiểu cách thay đổi tỷ lệ khung hình cho
  hình ảnh DataBar. Theo dõi ví dụ đầy đủ này kèm mã và mẹo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: vi
lastmod: 2026-08-03
og_description: Tạo mã vạch PNG bằng C# và xem cách thay đổi tỷ lệ khung hình cho
  các mã vạch DataBar. Hướng dẫn này cung cấp cho bạn mã sẵn sàng chạy và các mẹo
  thực tế.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Tạo mã vạch PNG trong C# – ví dụ đầy đủ với kiểm soát tỷ lệ khung hình
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Tạo mã vạch PNG trong C# – hướng dẫn từng bước
url: /vi/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo file PNG mã vạch trong C# – hướng dẫn chi tiết

Nếu bạn cần **tạo file PNG mã vạch** trong C#, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ tạo một mã DataBar đa hướng xếp chồng, lưu nó dưới dạng file PNG, và học **cách thay đổi tỷ lệ khung hình** để phù hợp với các môi trường quét khác nhau.

Hướng dẫn bao gồm mọi thứ bạn cần: các gói cần thiết, một chương trình hoàn chỉnh, có thể chạy ngay, và giải thích lý do mỗi thiết lập quan trọng. Khi hoàn thành, bạn sẽ có hai file PNG—một với tỷ lệ khung hình 15 và một với 30—sẵn sàng để thử nghiệm hoặc sử dụng trong môi trường sản xuất.

## Các điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có:

- .NET 6.0 SDK hoặc phiên bản mới hơn
- Visual Studio 2022 (hoặc bất kỳ IDE C# nào)
- Tham chiếu NuGet tới **Aspose.BarCode** (thư viện cung cấp `BarcodeGenerator`)
- Quyền ghi vào thư mục sẽ lưu các file PNG

Bạn có thể thêm gói Aspose.BarCode bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Thiết lập dự án và nhập không gian tên

Tạo một ứng dụng console mới và nhập các không gian tên cần thiết cho việc tạo mã vạch và I/O file.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Tại sao lại quan trọng:** Nhập `Aspose.BarCode.Generation` cho phép bạn truy cập `BarcodeGenerator`. Giữ mã trong `Main` giúp ví dụ tự chứa và dễ chạy.

## Bước 2: Tạo trình tạo mã vạch cho DataBar đa hướng xếp chồng

Khởi tạo `BarcodeGenerator` với kiểu `EncodeTypes.DatabarStackedOmniDirectional` và một chuỗi dữ liệu mẫu GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Tại sao lại quan trọng:** Kiểu mã đã chọn tạo ra một DataBar mật độ cao, có thể được đọc bởi hầu hết các máy quét hiện đại. Chuỗi dữ liệu tuân theo định dạng GS1 Application Identifier (01), thường dùng cho các mã sản phẩm.

## Bước 3: Định nghĩa kích thước X (độ rộng mô-đun) bằng pixel

Đặt độ rộng mô-đun để kiểm soát kích thước tổng thể của mã vạch mà không ảnh hưởng đến khả năng đọc.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao lại quan trọng:** Kích thước X = 2 pixel tạo ra một mã vạch vừa đủ lớn để máy quét nhận dạng, vừa không quá lớn so với không gian nhãn thường.

## Bước 4: Lưu PNG đầu tiên với tỷ lệ khung hình 15

Điều chỉnh tỷ lệ khung hình của DataBar, sau đó lưu ảnh dưới dạng file PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Tại sao lại quan trọng:** Tỷ lệ khung hình kiểm soát mối quan hệ chiều cao‑so‑với‑chiều rộng của DataBar xếp chồng. Giá trị 15 là mặc định phổ biến, cân bằng giữa khả năng đọc và chiều cao nhãn.

## Bước 5: Thay đổi tỷ lệ khung hình thành 30 và lưu PNG thứ hai

Sửa đổi cùng một đối tượng `generator` để sử dụng tỷ lệ khung hình lớn hơn, rồi lưu ảnh thứ hai.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Tại sao lại quan trọng:** Tăng tỷ lệ khung hình kéo dài mã vạch theo chiều dọc, có thể cải thiện độ tin cậy khi quét trên các thiết bị độ phân giải thấp hoặc khi nhãn được in trên vật liệu hẹp.

## Kết quả mong đợi

Chạy chương trình sẽ tạo ra hai file PNG:

| Tệp                                 | Tỷ lệ khung hình | Kích thước xấp xỉ (pixel) |
|-------------------------------------|------------------|---------------------------|
| `DatabarAspectRatio15.png`          | 15               | 200 × 300 (rộng × cao)     |
| `DatabarAspectRatio30.png`          | 30               | 200 × 600 (rộng × cao)     |

Cả hai ảnh đều chứa một mã DataBar rõ ràng, có thể quét được, mã hoá định danh GS1 `(01)12345678901231`.

## Câu hỏi thường gặp và các trường hợp đặc biệt

### Làm sao thay đổi các thuộc tính hiển thị khác?

Bạn có thể điều chỉnh màu nền, màu nền phụ, hoặc thêm văn bản có thể đọc được qua đối tượng `generator.Parameters.Barcode`. Ví dụ:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Nếu tôi muốn dùng định dạng ảnh khác thì sao?

Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy nhu cầu. PNG vẫn là lựa chọn tốt nhất cho ảnh mã vạch không mất dữ liệu.

### Tỷ lệ khung hình có ảnh hưởng đến tốc độ quét không?

Tỷ lệ khung hình cao hơn làm tăng chiều cao của mã vạch, có thể cải thiện độ tin cậy khi quét trên các thiết bị gặp khó khăn với các ký hiệu xếp chồng ngắn. Tuy nhiên, mã vạch quá cao có thể không vừa trên các nhãn nhỏ, vì vậy hãy thử nghiệm với phần cứng mục tiêu của bạn.

### Tôi có thể tạo nhiều mã vạch trong một vòng lặp không?

Có. Tạo một đối tượng `BarcodeGenerator` mới cho mỗi chuỗi dữ liệu hoặc tái sử dụng cùng một đối tượng bằng cách cập nhật `CodeText` và `DataBar.AspectRatio`. Cách này giảm tải việc cấp phát đối tượng.

## Mẹo chuyên nghiệp

- **Tái sử dụng trình tạo**: Chỉ thay đổi `CodeText` hoặc `AspectRatio` mà không tạo lại đối tượng, giúp tăng tốc xử lý hàng loạt.
- **Xác thực đầu ra**: Dùng máy quét cầm tay hoặc ứng dụng di động để kiểm tra PNG tạo ra đọc đúng trước khi đưa vào sản xuất.
- **Đặt tên file**: Bao gồm tỷ lệ khung hình trong tên file (như ví dụ) để dễ theo dõi các biến thể trong quá trình thử nghiệm.

## Kết luận

Bây giờ bạn đã biết cách **tạo file PNG mã vạch** trong C# và **thay đổi tỷ lệ khung hình** cho các ký hiệu DataBar đa hướng xếp chồng. Ví dụ hoàn chỉnh minh họa việc khởi tạo, thiết lập kích thước X, điều chỉnh tỷ lệ khung hình và lưu ảnh—tất cả trong một chương trình có thể chạy ngay.

Từ đây, bạn có thể khám phá thêm các loại mã vạch khác, thử nghiệm màu sắc, hoặc tích hợp trình tạo vào hệ thống báo cáo hay quản lý tồn kho lớn hơn. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong bài viết này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ, kèm giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}