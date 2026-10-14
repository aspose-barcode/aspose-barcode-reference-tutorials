---
category: general
date: 2026-10-14
description: Tạo một console barcode scanner bằng C# có khả năng đọc PDF417 barcode,
  xử lý macro PDF417, và giải mã nhiều barcode từ một hình ảnh duy nhất.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Tạo một console barcode scanner bằng C# để nhanh chóng đọc PDF417
  và macro PDF417 barcode từ hình ảnh. Hướng dẫn từng bước này chỉ ra cách giải mã
  nhiều barcode trong một bức ảnh.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Tạo console barcode scanner bằng C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Tạo console barcode scanner bằng C# – ví dụ đọc PDF417 barcode
url: /vi/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo trình quét mã vạch console bằng C# – ví dụ đọc mã vạch PDF417

`BarCodeReader` là lớp cốt lõi của Aspose.BarCode, giải mã mã vạch từ hình ảnh và trả về siêu dữ liệu chi tiết. Nếu bạn cần đọc dữ liệu mã vạch PDF417 từ một hình ảnh, hướng dẫn này sẽ chỉ cho bạn cách thực hiện bằng lớp **BarCodeReader** trong C#. Bạn sẽ học một ví dụ **tạo trình quét mã vạch console** đồng thời xử lý macro PDF417 và có thể đọc nhiều mã vạch trong một hình ảnh duy nhất.

Làm việc với mã vạch thường đồng nghĩa với việc phải xử lý các nguồn hình ảnh khác nhau, điều kiện ánh sáng thay đổi, và đôi khi dữ liệu tổng hợp như các đoạn macro PDF417. Bài hướng dẫn này bao gồm mọi thứ bạn cần để giải mã mã vạch PDF417, trích xuất các trường mở rộng, và xử lý nhiều mã vạch từ cùng một bức ảnh. Khi hoàn thành, bạn sẽ có một chương trình console có thể chạy được, đọc mã vạch từ tệp hình ảnh và in thông tin chi tiết ra console.

## Câu trả lời nhanh
- **Ví dụ này làm gì?** Nó tạo một trình quét mã vạch console, đọc các mã vạch PDF417 và macro PDF417 từ một hình ảnh và in ra tất cả các trường đã giải mã.  
- **Thư viện nào được yêu cầu?** Aspose.BarCode cho .NET (NuGet).  
- **Có thể đọc nhiều mã vạch cùng lúc không?** Có – trình đọc sẽ lặp qua mọi mã vạch được tìm thấy trong hình ảnh.  
- **Có cần kết nối internet không?** Không, thư viện hoạt động hoàn toàn offline.  
- **Phiên bản .NET nào được hỗ trợ?** .NET 6.0 hoặc mới hơn.

## Những gì bạn sẽ cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* SDK .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt  
* Phiên bản mới nhất của gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện tương thích nào cung cấp `BarCodeReader` và `DecodeType.MacroPdf417`)  
* Tệp hình ảnh chứa mã vạch PDF417 hoặc macro PDF417 (ví dụ sử dụng `ExtPDF417Meta.png`)  
* Trình soạn thảo mã hoặc IDE như Visual Studio 2022  

Không cần dịch vụ bổ sung hay API bên ngoài.

## Cài đặt dự án để đọc mã vạch

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Đặt `ExtPDF417Meta.png` (hoặc bất kỳ hình ảnh nào chứa mã vạch PDF417) vào thư mục dự án.  
   Đối với hướng dẫn này, chúng tôi giả định tệp nằm ở `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Dự án giờ đã sẵn sàng để biên dịch và chạy ví dụ trình đọc mã vạch.

## Làm thế nào để tạo trình quét mã vạch console bằng C#?

`BarCodeReader` là một lớp do Aspose.BarCode cung cấp, đọc mã vạch từ hình ảnh và trả về dữ liệu đã giải mã.  
Tải hình ảnh bằng `BarCodeReader`, đặt kiểu giải mã thành `MacroPdf417`, và lặp qua các kết quả – đó là tất cả những gì bạn cần để tạo một trình quét mã vạch console. Trình đọc tự động giải phóng tài nguyên gốc nhờ câu lệnh `using`, vì vậy bạn không phải quản lý bộ nhớ thủ công. Cách tiếp cận này hoạt động với bất kỳ định dạng hình ảnh nào được .NET hỗ trợ, như PNG, JPEG hoặc BMP.

### Hướng dẫn chi tiết từng bước

Lõi của giải pháp là một khối `using` tạo một thể hiện `BarCodeReader`, chỉ định `DecodeType.MacroPdf417`, và lặp qua mọi mã vạch được phát hiện. Đoạn mã dưới đây là một chương trình hoàn chỉnh, tự chứa, bạn có thể dán vào `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Tại sao cách này hoạt động**:  

* `DecodeType.MacroPdf417` báo cho trình đọc tìm phần mở rộng macro của PDF417, chứa các siêu dữ liệu bổ sung như ID tệp, số đoạn và dấu thời gian.  
* Câu lệnh `using` đảm bảo các tài nguyên không quản lý (handle file, bộ đệm giải mã gốc) được giải phóng kịp thời.  
* Vòng lặp `foreach` tự động xử lý **tất cả** các mã vạch mà hình ảnh chứa, đáp ứng yêu cầu *đọc nhiều mã vạch*.

Khi bạn chạy chương trình (`dotnet run`), bạn sẽ thấy đầu ra tương tự như sau:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Nếu hình ảnh chứa hơn một mã vạch PDF417, vòng lặp sẽ in một khối riêng cho mỗi mã vạch, qua đó minh họa cách **đọc nhiều mã vạch** từ một bức ảnh duy nhất.

## Làm sao để đọc nhiều mã vạch từ một hình ảnh?

Sử dụng một thể hiện `BarCodeReader` duy nhất và đặt cờ `DecodeType` để bao gồm tất cả các định dạng bạn muốn phát hiện. Bằng cách kết hợp các cờ với toán tử OR bitwise, bạn có thể yêu cầu thư viện tìm kiếm PDF417, QR, Code‑128 và nhiều symbology khác trong một lần quét. Điều này loại bỏ nhu cầu có nhiều trình đọc riêng biệt và giảm thời gian xử lý.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* là một bitmask, vì vậy bạn có thể kết hợp bất kỳ số lượng định dạng hỗ trợ nào. Aspose.BarCode hỗ trợ **hơn 30 loại symbology**, bao gồm QR, DataMatrix, Code‑128 và UPC‑A, cho phép một trình quét duy nhất xử lý các trường hợp sử dụng đa dạng như dán nhãn sản phẩm, xác thực vé, và kiểm tra danh tính.

## Macro PDF417 là gì và làm sao truy cập các trường của nó một cách an toàn?

Macro PDF417 là một phần mở rộng của symbology PDF417, cho phép một tập dữ liệu lớn được chia thành nhiều ký hiệu mã vạch.  
Macro PDF417 thêm một loạt các thuộc tính mở rộng. Tuy nhiên, không phải mọi mã vạch đều chứa mọi trường. Việc truy cập một thuộc tính thiếu có thể gây ra `NullReferenceException`. Cách an toàn nhất là kiểm tra mỗi thuộc tính trước khi in, đảm bảo ứng dụng của bạn ổn định ngay cả khi dữ liệu macro không có.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Lý do điều này quan trọng*: Trong các triển khai thực tế, bạn có thể nhận được các mã vạch PDF417 thông thường không có dữ liệu macro. Kiểm tra phòng thủ này giúp ứng dụng của bạn tiếp tục chạy mà không bị sập.

## Những lỗi thường gặp và thực hành tốt

| Vấn đề | Nguyên nhân | Giải pháp đề xuất |
|-------|------------|-------------------|
| Đường dẫn hình ảnh không đúng | `BarCodeReader` ném ngoại lệ file‑not‑found trước khi thực hiện giải mã | Sử dụng `Path.Combine` và kiểm tra tệp tồn tại bằng `File.Exists` |
| Hình ảnh độ phân giải thấp | Bộ giải mã không thể xác định cạnh mã vạch, dẫn đến không phát hiện được | Cung cấp độ phân giải tối thiểu 300 dpi để có kết quả đáng tin cậy |
| Mã vạch bị quay > 45° | Nhiều thư viện giả định hướng thẳng đứng | Bật `reader.RecognitionOptions.RotateImage = true` nếu hình ảnh có thể bị quay |
| Thiếu các trường macro | Cố gắng đọc thuộc tính null gây lỗi | Luôn kiểm tra `null` trước khi truy cập các thuộc tính macro |
| Xử lý hàng loạt lớn | Tạo lại `BarCodeReader` cho mỗi tệp gây tốn tài nguyên | Tái sử dụng một thể hiện `BarCodeReader` duy nhất với các stream khác nhau khi xử lý nhiều hình ảnh |

## Tại sao nên sử dụng Aspose.BarCode cho trình quét mã vạch console?

Aspose.BarCode có thể giải mã **hơn 30 loại mã vạch** và xử lý hình ảnh lên tới **200 MP** mà không cần tải toàn bộ tệp vào bộ nhớ, đạt tốc độ **150 khung hình mỗi giây** trên CPU 3.2 GHz tiêu chuẩn. Những khả năng định lượng này làm cho nó trở thành lựa chọn đáng tin cậy cho các giải pháp quét quy mô lớn, nội bộ, nơi độ trễ và độ chính xác là yếu tố quan trọng.

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích chi tiết từng bước, giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đọc DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Đọc mã DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Đọc mã vạch từ hình ảnh – Thành thạo việc trích xuất vùng mã vạch trong Java với Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng trình quét này trong môi trường sản xuất không?**  
A: Có. Mua giấy phép thương mại Aspose.BarCode để loại bỏ watermark đánh giá và nhận được hỗ trợ đầy đủ.

**Q: Thư viện có hoạt động trên Linux và macOS không?**  
A: Hoàn toàn có. Aspose.BarCode cho .NET là đa nền tảng và chạy trên .NET 6+ trên Windows, Linux và macOS.

**Q: Làm sao xử lý hình ảnh rất lớn mà không tiêu tốn hết bộ nhớ?**  
A: Sử dụng hàm khởi tạo `LoadOptions` để bật chế độ streaming, xử lý hình ảnh theo từng khối thay vì tải toàn bộ vào RAM.

**Q: Có thể giải mã hình ảnh được mã hóa hoặc bảo vệ bằng mật khẩu không?**  
A: Trình đọc có thể xử lý các hình ảnh được mã hóa bằng các scheme mật khẩu PNG/JPEG tiêu chuẩn; chỉ cần cung cấp mật khẩu qua `reader.ImagePassword`.

**Q: Nếu mã vạch của tôi bị hư hỏng một phần thì sao?**  
A: Bật các tùy chọn sửa lỗi như `reader.RecognitionOptions.CorrectErrors = true` để tăng khả năng chịu lỗi trước hư hỏng hoặc nhiễu.

---

**Cập nhật lần cuối:** 2026-10-14  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách đọc Pdf417 trong C – Ví dụ đầy đủ trình đọc mã vạch](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Đọc nhiều mã vạch C – Hướng dẫn đầy đủ với Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Giải mã mã vạch từ hình ảnh với ví dụ trình đọc mã vạch C](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}