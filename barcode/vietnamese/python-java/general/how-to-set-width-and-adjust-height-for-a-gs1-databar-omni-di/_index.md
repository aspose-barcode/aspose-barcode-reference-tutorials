---
category: general
date: 2026-09-29
description: Cách đặt chiều rộng của mã vạch GS1 DataBar Omni‑Directional và cách
  thay đổi chiều cao bằng C#. Thực hiện theo hướng dẫn từng bước kèm mã nguồn đầy
  đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: vi
lastmod: 2026-09-29
og_description: Cách đặt chiều rộng cho mã vạch GS1 DataBar Omni‑Directional và cách
  thay đổi chiều cao trong C#. Tìm hiểu các lời gọi API chính xác và xem một ví dụ
  hoàn chỉnh có thể chạy được.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Cách thiết lập chiều rộng của mã vạch GS1 DataBar – Hướng dẫn C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Cách thiết lập chiều rộng và điều chỉnh chiều cao cho mã vạch GS1 DataBar Omni‑Directional
  trong C#
url: /vi/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt chiều rộng và điều chỉnh chiều cao cho mã vạch GS1 DataBar Omni‑Directional trong C#

Việc đặt chiều rộng cho mã vạch GS1 DataBar Omni‑Directional là một nhiệm vụ thường gặp khi bạn cần kích thước chính xác cho thiết bị quét. Trong hướng dẫn này, bạn cũng sẽ học **cách thay đổi chiều cao** để mã vạch phù hợp hoàn hảo với bố cục của bạn. Hướng dẫn sẽ đưa bạn qua toàn bộ quy trình, từ thiết lập dự án đến một mẫu mã có thể chạy được đầy đủ.

Chúng tôi sẽ đề cập tới:

* Gói NuGet cần thiết và phiên bản .NET.
* Tại sao X‑dimension (độ rộng mô-đun) quan trọng đối với khả năng đọc mã vạch.
* Các lời gọi API chính xác để **cách đặt chiều rộng** và **cách thay đổi chiều cao**.
* Xử lý các trường hợp đặc biệt như độ rộng mô-đun tối thiểu và render độ phân giải cao.
* Một ví dụ hoàn chỉnh, sao chép‑dán, tạo ra hai tệp PNG với chiều cao vạch khác nhau.

## Yêu cầu trước

| Yêu cầu | Lý do |
|------------|--------|
| .NET 6.0 SDK hoặc mới hơn | Ví dụ sử dụng các tính năng hiện đại của C# và chạy trên Windows, Linux hoặc macOS. |
| Visual Studio 2022 (hoặc bất kỳ IDE C# nào) | Cung cấp IntelliSense cho API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Chứa `BarcodeGenerator`, `EncodeTypes`, và hỗ trợ định dạng ảnh. Cài đặt bằng `dotnet add package Aspose.Barcode`. |
| Quyền ghi vào thư mục sẽ lưu các tệp PNG | Trình tạo ghi các ảnh đầu ra vào đĩa. |

## Cách đặt chiều rộng cho mã vạch

Bước **cách đặt chiều rộng** được thực hiện bằng cách cấu hình thuộc tính `XDimension` của các tham số mã vạch. `XDimension` đại diện cho độ rộng mô-đun (vạch hoặc khoảng trống nhỏ nhất) tính bằng pixel, point hoặc milimet. Đặt đúng giá trị sẽ đảm bảo mã vạch đáp ứng các thông số kỹ thuật của máy quét.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Tại sao X‑dimension quan trọng

* **Scanner tolerance** – Hầu hết các máy quét yêu cầu độ rộng mô-đun tối thiểu; giá trị quá nhỏ có thể gây lỗi đọc.
* **Print resolution** – Khi in ở 300 dpi, một mô-đun 2 px tương đương ~0.17 mm, nằm trong khoảng khuyến nghị cho GS1 DataBar.
* **Image size** – Giá trị X‑dimension lớn hơn làm tăng tổng chiều rộng của mã vạch, có thể ảnh hưởng đến các ràng buộc bố cục.

### Mẹo để thiết lập chiều rộng đáng tin cậy

* **Never set XDimension below 1 px** – Thư viện sẽ giới hạn giá trị, nhưng mã vạch tạo ra có thể không đọc được.
* **Match the target DPI** – Nếu bạn render sang định dạng độ phân giải cao (ví dụ, TIFF ở 600 dpi), tăng XDimension một cách tỷ lệ.
* **Test with a real scanner** – Sau khi thay đổi chiều rộng, hãy xác thực mã vạch trên thiết bị sẽ đọc nó.

## Cách thay đổi chiều cao của mã vạch

Khi chiều rộng đã được xác định, bạn có thể kiểm soát kích thước theo chiều dọc bằng thuộc tính `BarHeight`. Đoạn mã dưới đây minh họa **cách thay đổi chiều cao** từ 30 px lên 60 px và lưu hai hình ảnh riêng biệt.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Hiểu về chiều cao vạch

* **Visual balance** – Các vạch cao hơn cải thiện khả năng đọc trên nền có độ tương phản thấp nhưng tăng kích thước dọc của hình ảnh.
* **Regulatory limits** – Một số tiêu chuẩn (ví dụ, nhãn bán lẻ) quy định chiều cao vạch tối đa; hãy điều chỉnh cho phù hợp.
* **Aspect ratio** – Thay đổi chiều cao không ảnh hưởng đến độ rộng mô-đun; bạn có thể tinh chỉnh cả hai một cách độc lập.

### Xử lý các trường hợp đặc biệt khi điều chỉnh chiều cao

| Tình huống | Cách tiếp cận đề xuất |
|-----------|----------------------|
| Height < 10 px | Tăng lên ít nhất 10 px; các vạch quá ngắn có thể bị máy quét bỏ qua. |
| Very tall bars (≥ 100 px) | Xác minh rằng phương tiện đầu ra (giấy, nhãn) có thể chứa không gian bổ sung. |
| Need proportional scaling | Tính `BarHeight = XDimension * desiredRatio` để duy trì tính nhất quán về hình ảnh. |

## Ví dụ đầy đủ, có thể chạy

Dưới đây là chương trình hoàn chỉnh kết hợp các bước **cách đặt chiều rộng** và **cách thay đổi chiều cao**. Sao chép mã vào một dự án console mới, khôi phục gói NuGet Aspose.Barcode, và chạy nó. Hai tệp PNG sẽ xuất hiện trong thư mục `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo ra hai tệp PNG:

* `DatabarBarHeight30Pixels.png` – mã vạch cao 30 px, mô-đun rộng 2 px.
* `DatabarBarHeight60Pixels.png` – cùng mã vạch nhưng chiều cao gấp đôi.

Mở bất kỳ hình ảnh nào trong trình xem; bạn sẽ thấy một biểu tượng GS1 DataBar Omni‑Directional sạch sẽ, sẵn sàng để quét.

## Các câu hỏi thường gặp được trả lời

| Câu hỏi | Trả lời |
|----------|--------|
| *Tôi có thể sử dụng milimet thay vì pixel không?* | Có. Đặt `generator.Parameters.Barcode.XDimension.Millimeters` và `BarHeight.Millimeters`. Thư viện sẽ chuyển đổi sang pixel của thiết bị dựa trên DPI của ảnh. |
| *Nếu tôi cần một loại mã vạch khác thì sao?* | Thay thế `EncodeTypes.DatabarOmniDirectional` bằng bất kỳ giá trị `EncodeTypes` nào khác (ví dụ, `EncodeTypes.QR`). Các thuộc tính chiều rộng và chiều cao hoạt động tương tự. |
| *Có cách nào tạo SVG thay vì PNG không?* | Sử dụng `BarCodeImageFormat.Svg` trong lời gọi `Save`. Các cài đặt chiều rộng/chiều cao vẫn áp dụng. |
| *Tôi có cần gọi `generator.Dispose()` không?* | `BarcodeGenerator` triển khai `IDisposable`. Trong ứng dụng console bạn có thể bọc nó trong khối `using`, nhưng đối với các ví dụ ngắn hạn thì không bắt buộc. |

## Kết luận

Bây giờ bạn đã biết **cách đặt chiều rộng** cho mã vạch GS1 DataBar Omni‑Directional và **cách thay đổi chiều cao** bằng API Aspose.Barcode trong C#. Ví dụ đầy đủ minh họa cách tạo generator, cấu hình `XDimension` và `BarHeight`, và lưu các tệp PNG với các kích thước dọc khác nhau.  

Từ đây bạn có thể:

* Thử nghiệm các `EncodeTypes` khác (ví dụ, QR, Code128).
* Render sang các định dạng độ phân giải cao như TIFF để in.
* Tích hợp generator vào một web API trả về mã vạch ngay lập tức.

Chúc lập trình vui vẻ, và hy vọng các mã vạch của bạn luôn được quét sạch sẽ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách thay đổi chiều cao mã vạch trong C# – Hướng dẫn đầy đủ](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Ví dụ trình tạo mã vạch trong C# – đặt chiều rộng và chiều cao](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Cách sử dụng trình tạo mã vạch C# để tạo mã vạch DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}