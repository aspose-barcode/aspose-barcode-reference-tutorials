---
category: general
date: 2026-10-08
description: Tìm hiểu cách tạo hình ảnh mã vạch trong C# và khám phá cách điều chỉnh
  tỷ lệ khung hình cho các mã vạch DataBar xếp chồng đa hướng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: vi
lastmod: 2026-10-08
og_description: Tạo hình ảnh mã vạch trong C# và học cách điều chỉnh tỷ lệ khung hình
  cho các mã vạch DataBar xếp chồng đa hướng với mẫu mã hoàn chỉnh.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách tạo ảnh mã vạch và điều chỉnh tỷ lệ khung hình trong C#
url: /vi/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch và điều chỉnh tỷ lệ khung hình trong C#

Nếu bạn cần **tạo hình ảnh mã vạch** một cách lập trình, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy chính xác **cách điều chỉnh tỷ lệ khung hình** cho mã vạch DataBar stacked omni‑directional, một yêu cầu thường xuất hiện trong các ứng dụng bán lẻ và logistics.

Trong tutorial này bạn sẽ học cách:
* Khởi tạo một Aspose.BarCode `BarcodeGenerator` cho ký hiệu DataBar stacked omni‑directional.  
* Đặt X‑dimension (độ rộng mô-đun) tính bằng pixel để kiểm soát độ dày của các thanh.  
* Áp dụng hai tỷ lệ khung hình khác nhau và lưu mỗi kết quả dưới dạng tệp PNG.  
* Xác minh đầu ra và hiểu tại sao tỷ lệ khung hình lại quan trọng.

Không cần công cụ bên ngoài—chỉ cần thư viện Aspose.BarCode cho .NET và môi trường phát triển .NET 6 (hoặc mới hơn).

## Cách tạo hình ảnh mã vạch với Aspose.BarCode

Bước đầu tiên là khởi tạo generator với ký hiệu và chuỗi dữ liệu mong muốn. Enum `EncodeTypes.DatabarStackedOmniDirectional` cho Aspose.BarCode biết tạo mã vạch DataBar stacked omni‑directional, thường được sử dụng cho các ứng dụng GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Tại sao điều này quan trọng:** Đối tượng `BarcodeGenerator` là điểm khởi đầu cho tất cả các nhiệm vụ tạo mã vạch. Bằng cách chỉ định ký hiệu và dữ liệu thô ngay từ đầu, bạn đảm bảo rằng hình ảnh được tạo tuân thủ tiêu chuẩn GS1.

## Đặt X‑dimension (độ rộng mô-đun)

X‑dimension xác định độ rộng của thanh mảnh nhất (mô-đun). X‑dimension lớn hơn tạo ra mã vạch dày hơn, có thể hữu ích cho các máy in độ phân giải thấp.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao điều này quan trọng:** Điều chỉnh X‑dimension là một phần của quá trình tinh chỉnh hình ảnh. Nó không ảnh hưởng tới dữ liệu đã mã hoá, nhưng nó ảnh hưởng tới độ tin cậy khi quét trên các thiết bị khác nhau.

## Cách điều chỉnh tỷ lệ khung hình – phiên bản đầu tiên (15)

Tỷ lệ khung hình kiểm soát mối quan hệ chiều cao‑với‑chiều rộng của mã vạch DataBar. Thuộc tính `DataBar.AspectRatio` chấp nhận các giá trị nguyên; số lớn hơn tạo ra các thanh cao hơn.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Tại sao điều này quan trọng:** Tỷ lệ khung hình 15 là mặc định phổ biến cho các máy quét bán lẻ. PNG kết quả (`DatabarAspectRatio15.png`) sẽ có hình dáng cao hơn, có thể cải thiện khả năng quét thành công trên các thiết bị cầm tay.

## Cách điều chỉnh tỷ lệ khung hình – phiên bản thứ hai (30)

Bạn có thể cần một mã vạch cao hơn cho các định dạng nhãn cụ thể. Thay đổi tỷ lệ khung hình đơn giản chỉ cần gán một giá trị nguyên mới trước khi gọi `Save` lần nữa.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao điều này quan trọng:** Bằng cách minh họa **cách điều chỉnh tỷ lệ khung hình**, bạn có thể tạo nhiều hình ảnh mã vạch từ cùng một nguồn dữ liệu mà không cần tạo lại generator. Điều này giảm việc sử dụng bộ nhớ và tăng tốc xử lý hàng loạt.

### Kết quả mong đợi

Sau khi chạy chương trình, bạn sẽ tìm thấy hai tệp PNG trong thư mục thực thi:

| Tên tệp                     | Tỷ lệ khung hình | Mô tả hình ảnh |
|-----------------------------|------------------|----------------|
| `DatabarAspectRatio15.png`  | 15               | Chiều cao tiêu chuẩn, phù hợp cho hầu hết các máy quét điểm bán hàng. |
| `DatabarAspectRatio30.png`  | 30               | Các thanh cao hơn, hữu ích cho nhãn lớn hoặc máy in độ phân giải thấp. |

Cả hai hình ảnh đều chứa cùng một GTIN đã mã hoá `(01)12345678901231`, nhưng tỉ lệ hình ảnh khác nhau tùy theo tỷ lệ khung hình bạn đã đặt.

## Các câu hỏi thường gặp và xử lý các trường hợp đặc biệt

### Nếu tôi cần một X‑dimension khác?

Bạn có thể thay đổi `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` thành bất kỳ số nguyên nào lớn hơn không. Đối với đầu ra độ phân giải rất cao (ví dụ, 300 dpi), giá trị 3‑4 pixel thường cho kết quả rõ nét hơn.

### Làm sao chọn tỷ lệ khung hình phù hợp?

Tỷ lệ tối ưu phụ thuộc vào môi trường quét:
* **Nhãn thấp** – sử dụng tỷ lệ nhỏ hơn (ví dụ, 10‑15) để giữ mã vạch gọn gàng.  
* **Container vận chuyển lớn** – tỷ lệ cao hơn (ví dụ, 25‑35) cải thiện khả năng đọc từ xa.  
* **Yêu cầu quy định** – một số tiêu chuẩn yêu cầu chiều cao tối thiểu; hãy tham khảo tài liệu GS1 để biết số liệu chính xác.

### Tôi có thể tạo các định dạng mã vạch khác bằng cùng một đoạn code không?

Có. Thay `EncodeTypes.DatabarStackedOmniDirectional` bằng bất kỳ giá trị `EncodeTypes` nào khác (ví dụ, `EncodeTypes.Code128`). Phần còn lại của code—X‑dimension, aspect ratio (nếu áp dụng), và lưu—vẫn giữ nguyên.

### Nếu tôi cần tạo hình ảnh ở định dạng khác thì sao?

`BarCodeImageFormat` hỗ trợ PNG, JPEG, BMP, GIF và TIFF. Chỉ cần thay đổi đối số thứ hai của `Save`, ví dụ:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Mẹo chuyên nghiệp: tái sử dụng generator cho xử lý hàng loạt

Khi bạn cần tạo hàng chục mã vạch với cùng thiết lập hình ảnh, hãy khởi tạo generator một lần, chỉ cập nhật thuộc tính `CodeText`, và gọi `Save` liên tục. Điều này tránh việc tốn kém khi liên tục cấp phát bộ nhớ đệm nội bộ.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Kết luận

Bây giờ bạn đã biết cách **tạo hình ảnh mã vạch** trong C# bằng Aspose.BarCode và chính xác **cách điều chỉnh tỷ lệ khung hình** cho các ký hiệu DataBar stacked omni‑directional. Bằng cách kiểm soát X‑dimension và aspect ratio, bạn có thể tạo ra các mã vạch đáp ứng mọi yêu cầu quét hoặc bố cục đồng thời giữ cho việc triển khai đơn giản và dễ bảo trì.

### Các bước tiếp theo

* Khám phá các ký hiệu khác như **Code128** hoặc **QR Code** bằng cách thay đổi giá trị `EncodeTypes`.  
* Kết hợp việc tạo mã vạch với tạo PDF (ví dụ, sử dụng Aspose.PDF) để nhúng mã vạch trực tiếp vào hoá đơn.  
* Thử nghiệm việc lựa chọn tỷ lệ khung hình động dựa trên kích thước nhãn—điều này mở rộng mẫu **cách điều chỉnh tỷ lệ khung hình** thành một công cụ thiết kế nhãn đầy đủ tính năng.

Hãy tự do tùy chỉnh mẫu, chia sẻ kết quả của bạn, hoặc đặt câu hỏi tiếp theo trong phần bình luận. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động cùng các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các phương pháp triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch databar stacked trong C# với Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Cách tạo hình ảnh mã vạch với Aspose.Barcode trong C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Cách Điều Chỉnh Kích Thước Mã Vạch – Tỷ Lệ Khung Hình Codablock F với Aspose.BarCode cho .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}