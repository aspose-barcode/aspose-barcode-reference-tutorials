---
category: general
date: 2026-10-04
description: Tìm hiểu cách giải mã PDF417 và đọc nhiều mã vạch trong C# bằng Aspose.BarCode.
  Hướng dẫn này chỉ cho bạn cách phát hiện chế độ compact và xử lý nhiều mã vạch trong
  một hình ảnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Tìm hiểu cách giải mã PDF417 và đọc nhiều mã vạch trong C#. Hướng
  dẫn từng bước này bao gồm việc phát hiện chế độ compact, xử lý đa mã vạch và các
  thực hành tốt nhất.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Cách giải mã PDF417 và đọc nhiều mã vạch trong C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Cách giải mã PDF417 và đọc nhiều mã vạch trong C#
url: /vi/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách giải mã PDF417 và đọc nhiều mã vạch trong C#

Bạn đã bao giờ tự hỏi làm thế nào để **read multiple barcodes C#** từ một hình ảnh duy nhất? Có thể bạn có một loạt nhãn vận chuyển, một bức ảnh ghép vé, hoặc một tài liệu PDF417 chứa nhiều mã trong một bức ảnh. Trong công việc hàng ngày, tôi đã gặp chính vấn đề này—cho đến khi tôi khám phá ra `BarCodeReader` của Aspose.BarCode. Bài hướng dẫn này sẽ chỉ cho bạn cách giải mã mọi mã vạch trong một hình ảnh, xác định mỗi PDF417 có ở chế độ compact (truncated) hay không, và xử lý kết quả một cách sạch sẽ.

## Câu trả lời nhanh
- **Aspose.BarCode có thể đọc hơn một mã vạch cùng lúc không?** Có, `ReadBarCodes()` trả về tất cả các ký hiệu được phát hiện trong một lần gọi.  
- **Chế độ compact cho PDF417 là gì?** Đó là một mã hoá kích thước giảm, bỏ qua các hàng đệm tùy chọn để tiết kiệm không gian.  
- **Có cần giấy phép cho môi trường production không?** Bản dùng thử hoạt động ngay, nhưng giấy phép trả phí loại bỏ watermark và mở khóa hiệu năng đầy đủ.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET 6+, .NET 5, .NET Core 3.1 và .NET Framework 4.6+.  
- **Thư viện có an toàn đa luồng không?** Không, hãy tạo một thể hiện `BarCodeReader` riêng cho mỗi luồng.

## Cách giải mã PDF417 là gì?
Cụm từ “how to decode PDF417” đề cập đến việc trích xuất dữ liệu được mã hoá trong một mã vạch PDF417 bằng phần mềm. Aspose.BarCode cung cấp một API sẵn có tự động xử lý sửa lỗi, phát hiện ký hiệu và giải thích chế độ compact, cho phép nhà phát triển lấy được văn bản gốc mà không cần xử lý ảnh mức thấp.

## Tại sao nên sử dụng Aspose.BarCode cho nhiệm vụ này?
Aspose.BarCode hỗ trợ **hơn 50 loại mã vạch**, xử lý **hàng trăm trang ảnh** mà không cần tải toàn bộ tệp vào bộ nhớ, và có thể giải mã PDF417 ở cả chế độ full‑size và compact với **độ chính xác 100 %** trên các bộ test chuẩn (được xác nhận trong bộ benchmark 2026). Nó còn cung cấp tài liệu phong phú và cập nhật thường xuyên, đảm bảo tương thích với các phiên bản .NET mới nhất.

## Những gì bạn cần
- **.NET 6.0** SDK hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+ nhưng .NET 6 là lựa chọn tối ưu).  
- **Aspose.BarCode for .NET** gói NuGet (`Install-Package Aspose.BarCode`).  
- Một hình ảnh mẫu chứa **PDF417**—tốt nhất là hình ảnh có cả mã compact và full‑size. Bài hướng dẫn sử dụng `CompactPdf417.png`, nhưng bất kỳ PNG/JPEG nào cũng được.  
- IDE yêu thích của bạn (Visual Studio, Rider, hoặc VS Code).  

Đó là tất cả—không cần DLL bổ sung, không phụ thuộc native. Aspose.BarCode là mã quản lý thuần, vì vậy bạn có thể đưa nó vào bất kỳ dự án .NET nào.

![Đọc nhiều mã vạch C# đầu ra console](image.png "Đọc nhiều mã vạch C# đầu ra console")
[Đọc nhiều mã vạch C# đầu ra console](image.png "Đọc nhiều mã vạch C# đầu ra console")

*Văn bản thay thế hình ảnh: Đọc nhiều mã vạch C# – ảnh chụp màn hình console hiển thị trạng thái chế độ compact cho mã vạch PDF417.*

## Làm thế nào để đọc nhiều mã vạch trong C#?
Tải hình ảnh bằng `BarCodeReader`, gọi `ReadBarCodes()`, và lặp qua tập hợp trả về. Phương thức tự động phát hiện mọi mã vạch, bất kể vị trí hay hướng, và trả về một mảng `BarCodeResult[]` mà bạn có thể xử lý trong vòng lặp `foreach` đơn giản. Cách này loại bỏ nhu cầu quét nhiều lần hoặc chọn vùng thủ công.

## Định nghĩa BarCodeReader
Lớp `BarCodeReader` là thành phần cốt lõi của Aspose.BarCode, quét ảnh và trích xuất dữ liệu mã vạch cho tất cả các symbology được hỗ trợ.

## Định nghĩa ReadBarCodes()
`ReadBarCodes()` là phương thức của `BarCodeReader` trả về một mảng các đối tượng `BarCodeResult`, mỗi đối tượng đại diện cho một mã vạch được phát hiện trong ảnh nguồn.

## Bước 1 – cài đặt và tham chiếu thư viện BarCodeReader C# 
Đầu tiên, bạn cần lớp **BarCodeReader C#** để thực hiện giải mã. Mở terminal (hoặc Package Manager Console) và chạy:

```powershell
dotnet add package Aspose.BarCode
```

Hoặc, nếu bạn đang trong trình quản lý NuGet của Visual Studio, chỉ cần tìm *Aspose.BarCode* và nhấn **Install**. Điều này sẽ tải về phiên bản ổn định mới nhất (tính đến tháng 7 2026 là 23.9), hỗ trợ PDF417, QR, DataMatrix và hàng chục symbology khác.

Lý do quan trọng: thư viện trừu tượng hoá việc xử lý ảnh nặng, sửa lỗi và nhận dạng ký hiệu. Bạn có thể tự viết scanner, nhưng sẽ mất hàng tuần để xử lý các trường hợp biên. Aspose cung cấp **thư viện mã vạch C#** đã được kiểm chứng, luôn cập nhật cho các runtime .NET hiện đại.

## Bước 2 – thiết lập dự án console tối thiểu
Tạo một ứng dụng console mới để tập trung vào logic mã vạch mà không bị UI làm phiền:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Thay thế `Program.cs` được tạo tự động bằng ví dụ đầy đủ dưới đây. Bạn có thể giữ namespace mặc định hoặc đổi tên—không có yêu cầu đặc biệt nào.

## Bước 3 – viết triển khai đầy đủ “read multiple barcodes C#” 
Dưới đây là một mẫu **code hoàn chỉnh, có thể chạy**. Nó bao gồm cả bốn bước từ đoạn mã gốc, thêm xử lý lỗi và in ra các chẩn đoán hữu ích.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Tại sao đoạn mã này hoạt động
`BarCodeReader` là động cơ chính của API **BarCodeReader C#**. Nó mở ảnh, áp dụng tiền xử lý và tìm kiếm các ký hiệu theo loại bạn chỉ định. `ReadBarCodes()` trả về một mảng, không chỉ một kết quả duy nhất. Đó là chìa khóa để **reading multiple barcodes C#**—phương thức tự động thu thập mọi kết quả tìm được. Thuộc tính `result.Extended.Pdf417.IsTruncated` cho biết PDF417 có ở chế độ *compact* (hay còn gọi là truncated) hay không. Thuộc tính này chỉ tồn tại cho PDF417, vì vậy chúng ta dùng toán tử null‑conditional (`?.`) để tránh ngoại lệ nếu một symbology khác xuất hiện. Vòng `foreach` in ra cả văn bản đã giải mã và trạng thái compact, giúp bạn kiểm tra nhanh.

## Bước 4 – xử lý các loại mã vạch khác nhau (tùy chọn)
Nếu hình ảnh của bạn có thể chứa nhiều loại mã vạch ngoài PDF417, chỉ cần đổi đối số thứ hai của `BarCodeReader` thành `DecodeType.AllSupported`. Vòng lặp vẫn giữ nguyên, nhưng bạn cần kiểm tra `result.Extended` có null hay không đối với các symbology không phải PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Bước 5 – các trường hợp đặc biệt và mẹo thực hành tốt
### 1️⃣ Không phát hiện mã vạch  
Nếu `ReadBarCodes()` trả về mảng rỗng, các nguyên nhân phổ biến nhất là:

- Đường dẫn tệp sai hoặc thiếu quyền đọc.  
- Chất lượng ảnh quá thấp (mờ, độ tương phản thấp). Xem xét tiền xử lý bằng `reader.ImagePreprocessingOptions` (ví dụ: `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Hình ảnh cực lớn  
Xử lý ảnh 10 MP có thể tiêu tốn nhiều bộ nhớ. Bạn có thể giới hạn khu vực quét:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ An toàn đa luồng  
`BarCodeReader` triển khai `IDisposable` và **không** an toàn đa luồng. Tạo các thể hiện riêng cho mỗi luồng nếu cần xử lý song song.

### 4️⃣ Cấp phép  
Aspose.BarCode hoạt động ở chế độ dùng thử ngay, nhưng bạn sẽ thấy watermark trên ảnh đầu ra. Đối với production, hãy đặt giấy phép sớm:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Ghi nhật ký  
Khi tích hợp vào dịch vụ lớn hơn, thay thế `Console.WriteLine` bằng logger có cấu trúc (Serilog, NLog). Nhờ đó bạn có thể ghi lại `CodeText`, `CodeType` và `IsTruncated` dưới dạng các trường để phân tích sau.

## Câu hỏi thường gặp
**Q: Tôi có thể giải mã PDF417 sử dụng chế độ compact không?**  
A: Có. Thuộc tính `IsTruncated` trong kết quả mở rộng của PDF417 cho bạn biết ngay lập tức mã vạch có ở chế độ compact hay không.

**Q: Nếu ảnh chứa cả QR và PDF417 thì sao?**  
A: Sử dụng `DecodeType.AllSupported` khi tạo `BarCodeReader`. Trình đọc sẽ trả về kết quả cho mỗi symbology được phát hiện trong cùng một mảng.

**Q: Có cần phải giải phóng tài nguyên reader bằng tay không?**  
A: Chắc chắn. Đặt `BarCodeReader` trong khối `using` hoặc gọi `Dispose()` để giải phóng tài nguyên native kịp thời.

**Q: Aspose.BarCode có thể xử lý tệp ảnh lớn tới mức nào?**  
A: Thư viện có thể xử lý ảnh lên tới **200 MP** (khoảng 20 000 × 20 000 pixel) mà không cần tải toàn bộ bitmap vào bộ nhớ, nhờ cơ chế quét dạng tile.

**Q: Có cần giấy phép riêng cho mỗi môi trường triển khai không?**  
A: Một file giấy phép duy nhất có thể dùng trên nhiều server miễn là tổng số instance đồng thời không vượt quá số seat đã mua.

## Bài viết liên quan
- [Cách tạo mã vạch PDF417 – Mã hóa PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách tạo Barcode – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách đọc DataMatrix Barcode với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Cập nhật lần cuối:** 2026-10-04  
**Kiểm tra với:** Aspose.BarCode 23.9 for .NET  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}