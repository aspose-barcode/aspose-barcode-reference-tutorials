---
category: general
date: 2026-09-10
description: Tạo mã vạch PDF417 trong C# một cách nhanh chóng. Tìm hiểu cách bật chế
  độ compact, đặt số cột và tạo PNG bằng BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: vi
lastmod: 2026-09-10
og_description: Tạo mã vạch PDF417 trong C# bằng cách bật chế độ compact, thiết lập
  số cột và lưu dưới dạng PNG. Thực hiện theo hướng dẫn chi tiết từng bước.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn chế độ gọn
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cách tạo mã vạch PDF417 trong C# với chế độ nén
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo PDF417 barcode trong C# với chế độ compact

Nếu bạn cần **tạo PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác. Bạn sẽ thấy cách **bật chế độ compact**, đặt số cột, và lưu kết quả dưới dạng ảnh PNG bằng thư viện BarcodeGenerator C#.

Việc tạo mã vạch là một yêu cầu phổ biến cho việc theo dõi hàng tồn kho, hệ thống vé, và các ứng dụng quét di động. Khi kết thúc tutorial này, bạn sẽ có một ví dụ tự chứa, có thể chạy được, tạo ra một PDF417 barcode compact sẵn sàng cho việc sử dụng trong sản xuất.

## Yêu cầu trước

* .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt (mã cũng hoạt động với .NET Framework 4.7+)
* Phiên bản mới nhất của thư viện **BarcodeGenerator** (ví dụ: Aspose.BarCode for .NET)
* Một IDE hoặc trình soạn thảo như Visual Studio 2022 hoặc VS Code
* Quyền ghi vào thư mục nơi PNG sẽ được lưu

Không cần thêm bất kỳ gói NuGet nào ngoài thư viện barcode.

## Bước 1: Tạo trình tạo PDF417 barcode

Bước đầu tiên là khởi tạo một đối tượng `BarcodeGenerator` với enum `EncodeTypes.Pdf417` và văn bản bạn muốn mã hoá. Đối tượng này điều khiển toàn bộ quá trình tạo.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Tại sao điều này quan trọng*: Giá trị `EncodeTypes.Pdf417` thông báo cho thư viện sử dụng ký hiệu PDF417, trong khi đối số thứ hai cung cấp dữ liệu. Bạn có thể thay `"Compact mode"` bằng bất kỳ chuỗi alphanumeric nào bạn cần mã hoá.

## Bước 2: Đặt kích thước X (độ rộng mô-đun)

Kích thước X kiểm soát độ rộng của mỗi ô vuông nhỏ (module) trong mã vạch. Giá trị nhỏ hơn tạo ra hình ảnh chặt hơn, hữu ích khi không gian hạn chế.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Giá trị `2` pixel là sự cân bằng tốt giữa khả năng đọc và độ gọn cho hầu hết các máy quét dựa trên màn hình.

## Bước 3: Xác định số cột

PDF417 có thể sắp xếp dữ liệu trong một lưới gồm các hàng và cột. Điều chỉnh số cột sẽ thay đổi tỷ lệ khung hình của mã vạch.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Đặt **how to set columns** thành `3` tạo ra một mã vạch ngắn, rộng, phù hợp với nhãn. Bạn có thể thử các giá trị từ `1` đến `30` tùy thuộc vào lượng dữ liệu và máy quét mục tiêu.

## Bước 4: Bật chế độ compact

Chế độ compact loại bỏ các hàng đệm không cần thiết, làm cho mã vạch nhỏ hơn mà không mất tính toàn vẹn dữ liệu. Đây là bước quan trọng để tạo **compact PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Khi `Truncate` là `true`, thư viện tự động tính toán số hàng tối thiểu cần thiết để lưu trữ dữ liệu, vì vậy hình ảnh cuối cùng trông “chặt”.

## Bước 5: Lưu mã vạch đã tạo dưới dạng ảnh PNG

Cuối cùng, ghi mã vạch ra file. PNG giữ được các cạnh sắc nét cần thiết cho việc quét đáng tin cậy.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Thay `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối hoặc tương đối mà ứng dụng của bạn có thể ghi vào. Sau khi chạy, bạn sẽ thấy một file `CompactPdf417.png` chứa mã vạch.

### Mã nguồn đầy đủ

Kết hợp tất cả các bước lại với nhau sẽ cho bạn một chương trình duy nhất, sẵn sàng chạy:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Chạy chương trình này sẽ tạo ra `CompactPdf417.png` trong cùng thư mục với tệp thực thi. Mở ảnh bằng bất kỳ trình xem nào; bạn sẽ thấy một PDF417 barcode dày đặc, độ tương phản cao, sẵn sàng để quét.

## Cách bật chế độ compact trong các kịch bản khác

* **Tạo hàng loạt** – Khi tạo nhiều mã vạch, đặt `Truncate` một lần trên trình tạo và tái sử dụng cho mỗi payload mới.
* **Định dạng ảnh khác** – Phương thức `Save` tương tự hoạt động với `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp` nếu bạn cần loại tệp khác.
* **Số cột động** – Nếu độ dài chuỗi đã mã hoá thay đổi, tính toán số cột tối ưu dựa trên độ dài chuỗi và độ phân giải của máy quét.

## Cách đặt số cột cho các trường hợp sử dụng cụ thể

* **In nhãn** – Sử dụng số cột thấp (ví dụ: `2`‑`5`) để giữ mã vạch ngắn đủ để vừa trên nhãn hẹp.
* **Quét di động** – Số cột cao hơn (`10`‑`15`) tạo ra mã vạch cao hơn, dễ dàng hơn cho camera điện thoại lấy nét.
* **Thỏa hiệp sửa lỗi** – Nhiều cột hơn giảm số hàng, có thể ảnh hưởng đến khả năng sửa lỗi tích hợp của mã vạch. Kiểm tra với máy quét mục tiêu để tìm điểm cân bằng.

## Những lỗi thường gặp và mẹo chuyên nghiệp

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Mã vạch không đọc được | Kích thước X quá thấp (ví dụ: `1` pixel) | Tăng `XDimension.Pixels` lên ít nhất `2` |
| Hình ảnh quá lớn | Số cột được đặt quá cao cho payload ngắn | Giảm `Pdf417.Columns` hoặc bật `Truncate` |
| File PNG trống | Thư mục đầu ra không tồn tại hoặc thiếu quyền ghi | Đảm bảo thư mục tồn tại và tiến trình có quyền ghi |
| Máy quét báo “dữ liệu bị hỏng” | Truncate bị tắt khi sử dụng nhiều cột | Bật `Truncate` hoặc giảm số cột |

## Xác minh kết quả

Bạn có thể xác minh mã vạch bằng bất kỳ ứng dụng quét PDF417 nào (nhiều ứng dụng Android/iOS miễn phí). Mở `CompactPdf417.png` trong ứng dụng và xác nhận rằng văn bản đã giải mã khớp với payload gốc (“Compact mode”). Nếu văn bản khác nhau, hãy kiểm tra lại cờ `Truncate` và cài đặt cột.

## Các bước tiếp theo

* **Tích hợp với ASP.NET Core** – Trả về PNG trực tiếp từ một hành động controller thay vì lưu vào đĩa.
* **Thêm văn bản có thể đọc được** – Sử dụng `barcodeGenerator.Parameters.Barcode.CodeTextParameters` để hiển thị chuỗi đã mã hoá dưới mã vạch.
* **Khám phá các ký hiệu khác** – Lớp `BarcodeGenerator` tương tự hỗ trợ QR, Code128, DataMatrix, và nhiều hơn nữa. Thay đổi `EncodeTypes` để thử chúng.

---

### Kết luận

Bạn bây giờ đã biết cách **tạo PDF417 barcode** trong C# đồng thời **bật chế độ compact**, kiểm soát **cách đặt số cột**, và sử dụng API **barcode generator C#** để **tạo mã vạch** đáp ứng các ràng buộc kích thước thực tế. Áp dụng các bước này vào bất kỳ dự án .NET nào cần mã vạch compact, mật độ cao, và mở rộng mẫu này sang các định dạng mã vạch khác khi cần. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo PDF417 Barcode trong C# – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Cách đặt mức lỗi trong PDF417 Barcode – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cách lưu Barcode trong C# – Tạo PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}