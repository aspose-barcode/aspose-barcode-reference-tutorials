---
category: general
date: 2026-07-15
description: tạo mã vạch đa hướng trong C# nhanh chóng với Aspose.BarCode – tìm hiểu
  cách tạo mã vạch C# với chiều cao thanh và kích thước X có thể điều chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: vi
lastmod: 2026-07-15
og_description: Tạo mã vạch đa hướng trong C# với Aspose.BarCode. Nắm vững cách tạo
  mã vạch C# bằng cách điều chỉnh XDimension và BarHeight để đạt kết quả hoàn hảo.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Tạo mã vạch đa hướng trong C# – Hướng dẫn lập trình chi tiết
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Tạo mã vạch đa hướng trong C# – Hướng dẫn từng bước
url: /vi/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# tạo mã vạch omni-directional trong C# – Hướng dẫn từng bước

Bạn đã bao giờ tự hỏi làm thế nào để tạo một mã vạch C# tuân thủ chuẩn GS1 DataBar Omni‑Directional? Bạn không phải là người duy nhất. Trong hướng dẫn này, chúng ta sẽ **tạo mã vạch omni-directional** từ đầu, điều chỉnh X‑dimension và thay đổi chiều cao thanh—tất cả đều sử dụng thư viện Aspose.BarCode.

Chúng ta sẽ đi qua một kịch bản thực tế: bạn cần một mã vạch nhỏ gọn, mật độ cao cho nhãn bán lẻ, và muốn kiểm soát hoàn toàn kích thước hiển thị của nó. Khi kết thúc, bạn sẽ có hai tệp PNG—một với chiều cao thanh 30 px và một nữa với 60 px—sẵn sàng đưa vào bất kỳ quy trình in nào.

## Yêu cầu trước

- .NET 6 (hoặc bất kỳ runtime .NET gần đây nào) đã được cài đặt trên máy của bạn.  
- Visual Studio 2022 hoặc VS Code—IDE yêu thích của bạn đều được.  
- Gói NuGet miễn phí Aspose.BarCode cho .NET (`Aspose.BarCode`).

Không cần bất kỳ phụ thuộc nào khác. Nếu bạn chưa từng dùng NuGet, chỉ cần mở Package Manager Console và chạy:

```powershell
Install-Package Aspose.BarCode
```

## tạo mã vạch omni-directional – Hiểu các nguyên tắc cơ bản

Biểu tượng **GS1 DataBar Omni‑Directional** được thiết kế để quét ở bất kỳ hướng nào, làm cho nó trở nên hoàn hảo cho nhãn cạnh kệ. Khi bạn gọi `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, thư viện sẽ thực hiện các công việc nặng: mã hoá dữ liệu, áp dụng các quy tắc biểu tượng và chuẩn bị một hình ảnh raster.

> **Mẹo chuyên nghiệp:** Luôn bao bọc dữ liệu thô trong định dạng Application Identifier (AI) phù hợp, ví dụ `"(01)12345678901231"` cho GTIN‑14. Điều này cho máy quét biết các chữ số đại diện cho gì.

## Bước 1 – Thiết lập Barcode Generator (cách tạo barcode c#)

Đầu tiên chúng ta tạo đối tượng generator. Đây là nền tảng của **cách tạo barcode c#** với Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Giá trị enum `EncodeTypes.DatabarOmniDirectional` cho engine biết biểu tượng nào sẽ được sử dụng. Tham số thứ hai là chuỗi dữ liệu thô, đã được bao bọc trong GTIN AI.

## Bước 2 – Điều chỉnh X‑Dimension (barcode XDimension)

**barcode XDimension** kiểm soát độ rộng của thanh nhỏ nhất. Giá trị 2 px là sự cân bằng tốt giữa khả năng đọc và độ gọn cho hầu hết các máy in nhãn.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nếu bạn cần hình ảnh mịn hơn hoặc thô hơn, chỉ cần thay đổi số. Nhớ rằng: X‑dimension là đơn vị cơ bản; tất cả các độ rộng thanh khác đều là bội số của giá trị này.

## Bước 3 – Tạo hình ảnh đầu tiên với chiều cao thanh 30 px (barcode BarHeight)

Bây giờ chúng ta đặt **barcode BarHeight** thành 30 px và lưu hình ảnh. Điều này tạo ra một mã vạch kích thước vừa phải, phù hợp với nhãn tiêu chuẩn.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Phương thức `Save` ghi tệp PNG ra đĩa. Bạn có thể thay `BarCodeImageFormat.Jpeg` nếu muốn xuất ra JPEG.

## Bước 4 – Tăng chiều cao thanh lên 60 px cho nhãn lớn hơn (barcode BarHeight)

Đôi khi cần một mã vạch lớn hơn—có thể cho nhãn kệ đặt xa hơn máy quét. Hãy tăng gấp đôi chiều cao.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Lưu ý chúng ta **không** cần tạo lại generator; chỉ cần điều chỉnh tham số và sử dụng lại cùng một đối tượng. Điều này tiết kiệm bộ nhớ và giữ cho mã gọn gàng.

## Bước 5 – Lưu hình ảnh thứ hai (cách tạo barcode c#)

Cuối cùng, chúng ta lưu PNG thứ hai. Bây giờ bạn có hai tệp chỉ khác nhau ở chiều cao thanh.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Kết quả mong đợi

- `DatabarBarHeight30Pixels.png` – mã vạch omni‑directional cao 30 px.  
- `DatabarBarHeight60Pixels.png` – cùng dữ liệu, nhưng với mã vạch cao 60 px.

Mở các tệp trong bất kỳ trình xem ảnh nào; bạn sẽ thấy các thanh sắc nét, có thể quét được và tuân thủ chuẩn GS1 DataBar Omni‑Directional.

## Câu hỏi thường gặp & Trường hợp đặc biệt

### Nếu tôi cần X‑dimension khác thì sao?

Chỉ cần gán một giá trị mới trước khi gọi `Save`. Đối với in siêu mật độ, bạn có thể giảm xuống 1 px, nhưng hãy thử nghiệm với máy quét của bạn trước—một số thiết bị gặp khó khăn với các thanh dưới 2 px.

### Tôi có thể thêm văn bản đọc được cho người dưới mã vạch không?

Có. Đặt `barcodeGenerator.Parameters.Barcode.CodeText` thành một chuỗi và tùy chọn điều chỉnh `barcodeGenerator.Parameters.Barcode.CodeLocation` thành `BarCodeTextLocation.Below`. Điều này hữu ích cho môi trường bán lẻ nơi GTIN số phải hiển thị.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### PNG có phải là định dạng tốt nhất cho việc in không?

PNG là định dạng không mất dữ liệu, giữ được các cạnh sắc nét cần thiết cho máy quét mã vạch. Nếu hệ thống downstream của bạn yêu cầu định dạng khác (TIFF, BMP), chỉ cần thay đổi enum `BarCodeImageFormat`.

## Ví dụ hoàn chỉnh (tạo mã vạch omni-directional)

Dưới đây là chương trình hoàn chỉnh, sẵn sàng chạy. Sao chép‑dán vào một dự án console mới và nhấn **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Chạy chương trình, kiểm tra thư mục output, và bạn sẽ thấy hai tệp PNG đúng như mô tả.

## Tóm tắt

Chúng tôi đã trình bày mã **cách tạo barcode C#** tạo **mã vạch omni-directional** bằng Aspose.BarCode. Bằng cách điều chỉnh **barcode XDimension** và **barcode BarHeight**, bạn có được kiểm soát chi tiết kích thước hiển thị mà không làm giảm độ tin cậy khi quét.

## Tiếp theo là gì?

- Thử nghiệm các cài đặt khác của **GS1 DataBar Omni-Directional** như `Color` hoặc `Margin`.  
- Kết hợp nhiều mã vạch trên một canvas duy nhất bằng `Graphics` cho các thiết kế nhãn phức tạp.  
- Tích hợp generator vào một web API để nền tảng thương mại điện tử của bạn có thể tạo mã vạch theo yêu cầu.

Có cách tiếp cận nào bạn muốn chia sẻ? Để lại bình luận, và chúng ta sẽ tiếp tục thảo luận. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo Barcode – Cấu hình Code 39 với Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Cách tạo vùng yên tĩnh (Quiet Zone) cho ITF-14 bằng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cách tạo vùng yên tĩnh cho Code 16K bằng Aspose.BarCode cho .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}