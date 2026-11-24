---
category: general
date: 2026-11-23
description: Tìm hiểu cách sử dụng BarCodeReader trong C# để đọc mã vạch từ hình ảnh,
  bao gồm giải mã Macro PDF417, với ví dụ mã đầy đủ và giải thích rõ ràng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: vi
lastmod: 2026-11-23
og_description: Cách sử dụng BarCodeReader trong C# để đọc mã vạch từ hình ảnh. Hãy
  làm theo hướng dẫn từng bước này để giải mã Macro PDF417 và các định dạng khác với
  mã sẵn sàng chạy.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Cách sử dụng BarCodeReader trong C# – đọc mã vạch từ hình ảnh nhanh chóng
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Cách sử dụng BarCodeReader trong C# để đọc mã vạch từ hình ảnh
url: /vi/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng BarCodeReader trong C# để đọc mã vạch từ hình ảnh

Nếu bạn cần **cách sử dụng BarCodeReader** để quét mã vạch nhanh, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Dù bạn đang xây dựng hệ thống điểm bán hàng hay tự động hoá việc nhập tài liệu, bạn sẽ học cách đọc mã vạch từ các dự án C# chỉ với vài dòng code.

Trong tutorial này, bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, giải mã mã Macro PDF417, trích xuất các thuộc tính mở rộng và in thông tin hữu ích ra console. Không cần tài liệu bên ngoài – mọi thứ bạn cần đều có ở đây.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 (hoặc mới hơn) được cài đặt – code nhắm tới phiên bản LTS mới nhất.
* Tham chiếu tới gói NuGet **Aspose.BarCode** (hoặc bất kỳ gói tương thích nào) cung cấp `BarCodeReader`.
* Một file ảnh chứa mã Macro PDF417 (ví dụ sử dụng `ExtPDF417Meta.png`).

> **Mẹo chuyên nghiệp:** Nếu bạn dùng Visual Studio, thêm gói bằng lệnh `dotnet add package Aspose.BarCode` hoặc qua giao diện NuGet Package Manager.

## Bước 1: Tạo một thể hiện BarCodeReader

Điều đầu tiên bạn làm khi làm việc với thư viện mã vạch là khởi tạo một reader trỏ tới ảnh nguồn và chỉ định cho API loại mã vạch cần tìm.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Tại sao bước này quan trọng:*  
`BarCodeReader` mở ảnh, cấp phát bộ nhớ native và chuẩn bị các thuật toán giải mã cho `DecodeType` đã chỉ định. Khi giới hạn loại thành `MacroPdf417`, bạn giảm tải CPU và cải thiện độ chính xác phát hiện.

## Bước 2: Đọc tất cả các mã vạch có trong ảnh

Một ảnh duy nhất có thể chứa nhiều mã vạch, đặc biệt khi làm việc với dữ liệu được mã hoá macro. Phương thức `ReadBarCodes` trả về một enumerable các đối tượng `BarCodeResult`, mỗi đối tượng đại diện cho một mã được phát hiện.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Tại sao bước này quan trọng:*  
Duyệt qua collection đảm bảo bạn nắm bắt mọi trường hợp, điều này rất cần thiết cho các kịch bản xử lý hàng loạt hoặc khi một tài liệu nhúng nhiều mã.

## Bước 3: Truy cập các thuộc tính mở rộng của Macro PDF417

Macro PDF417 lưu trữ siêu dữ liệu bổ sung như định danh tệp, số đoạn và tổng số đoạn. Những giá trị này được mở ra qua thuộc tính `Extended.Pdf417` của `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Tại sao bước này quan trọng:*  
Các trường mở rộng cho phép bạn tái tạo tài liệu đa đoạn hoặc xác thực rằng tất cả các phần thuộc về cùng một nguồn. Bỏ qua bước này sẽ chỉ nhận được văn bản thô, mất đi ngữ cảnh quan trọng.

## Bước 4: Xuất ra thông tin hữu ích nhất

Cuối cùng, ghi dữ liệu ra console (hoặc bất kỳ logger nào) để bạn có thể kiểm tra hoạt động đọc. Ví dụ in ra loại mã, văn bản đã giải mã và một số trường macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Kết quả console dự kiến**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Lưu ý:** Nếu ảnh không chứa mã Macro PDF417, `ReadBarCodes()` sẽ trả về một collection rỗng và vòng lặp không thực thi. Luôn kiểm tra kết quả rỗng trong code production.

## Đọc mã vạch từ ảnh trong C# – xử lý các kịch bản thường gặp

### 1. Giải mã nhiều định dạng mã vạch

Nếu bạn cần phát hiện hơn một định dạng, truyền một cờ `DecodeType` kết hợp:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Quản lý ảnh lớn

Ảnh lớn có thể gây tiêu tốn bộ nhớ cao. Hạ độ phân giải ảnh trước khi truyền cho reader:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Xử lý lỗi

Bao bọc logic đọc trong khối try‑catch để phát hiện các lỗi giải mã:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Ví dụ hoàn chỉnh

Dưới đây là chương trình đầy đủ mà bạn có thể sao chép, dán và chạy. Nó bao gồm tất cả các bước, các chỉ thị `using` cần thiết và một khung xử lý lỗi đơn giản.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Chạy chương trình** sẽ in mỗi mã Macro PDF417 được phát hiện cùng các trường mở rộng, hoặc thông báo rằng không tìm thấy mã nào.

## Kết luận

Bây giờ bạn đã biết **cách sử dụng BarCodeReader** để đọc mã vạch từ các ứng dụng C# dựa trên hình ảnh, bao gồm việc trích xuất siêu dữ liệu Macro PDF417. Giải pháp bao gồm khởi tạo, lặp qua kết quả, truy cập thuộc tính mở rộng và các mẹo thực tế để xử lý đa định dạng, ảnh lớn và lỗi.

Tiếp theo, bạn có thể khám phá:

* **Đọc QR code** – thay `DecodeType.MacroPdf417` bằng `DecodeType.QR`.
* **Lưu dữ liệu đã giải mã** vào cơ sở dữ liệu hoặc file JSON để xử lý tiếp theo.
* **Tích hợp với ASP.NET Core** để nhận ảnh tải lên qua API web.

Hãy thoải mái thử nghiệm với các loại mã vạch và nguồn ảnh khác nhau. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ cùng các giải thích chi tiết từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}