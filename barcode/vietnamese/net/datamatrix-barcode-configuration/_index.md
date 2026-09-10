---
date: 2026-06-09
description: Tìm hiểu cách tạo mã vạch datamatrix với Aspose.BarCode cho .NET, tùy
  chỉnh tỷ lệ khung hình, các chế độ ECC và mã hóa datamatrix c40 để tạo mã vạch hiệu
  quả.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Cấu hình mã vạch DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Tạo mã vạch DataMatrix – Hướng dẫn chuyên nghiệp với Aspose.BarCode
url: /vi/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Vạch DataMatrix – Hướng Dẫn Chuyên Nghiệp với Aspose.BarCode

Chào mừng bạn đến với loạt hướng dẫn toàn diện của chúng tôi về **tạo mã vạch datamatrix** bằng Aspose.BarCode cho .NET. Dù bạn là nhà phát triển dày dặn kinh nghiệm đang tinh chỉnh đầu ra mã vạch hay là người mới muốn nắm bắt các nguyên tắc cơ bản, hướng dẫn này sẽ dẫn bạn qua từng bước — từ cấu hình cơ bản đến các kỹ thuật mã hoá nâng cao — để bạn có thể cung cấp các mã vạch đáng tin cậy, sẵn sàng quét trong bất kỳ ứng dụng .NET nào.

## Câu trả lời nhanh
- **Mục đích chính là gì?** Tạo và tùy chỉnh mã vạch DataMatrix một cách lập trình.  
- **Thư viện nào được sử dụng?** Aspose.BarCode cho .NET.  
- **Có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Hỗ trợ các phiên bản .NET nào?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Có thể tùy chỉnh tỷ lệ khung hình không?** Có – xem phần “Cách tùy chỉnh tỷ lệ khung hình DataMatrix”.

## generate datamatrix barcode là gì?
Mã vạch DataMatrix là một ma trận hai chiều gồm các ô đen và trắng có khả năng lưu trữ lên tới 2 300 ký tự chữ và số. Sử dụng Aspose.BarCode, bạn có thể **tạo mã vạch datamatrix** dưới dạng hình ảnh, PDF hoặc SVG trực tiếp từ mã .NET của mình, kiểm soát kích thước, mức độ sửa lỗi và chế độ mã hoá để đáp ứng bất kỳ tiêu chuẩn ngành nào.

## Tại sao nên dùng Aspose.BarCode cho DataMatrix?
Aspose.BarCode render các ký hiệu DataMatrix với độ phân giải lên tới **600 dpi** mà không bị pixel, đảm bảo quét sắc nét trên các máy in độ phân giải cao. Nó hỗ trợ **hơn 50 chế độ ECC và macro** — bao gồm ECC 000‑140, ECC 200 và Macro 05/06 — cho phép bạn chọn mức sửa lỗi tối ưu cho kích thước dữ liệu. API cung cấp các tùy chọn mã hoá **ASCII, C40, Text, X12 và Bytes**, giúp bạn nén dữ liệu hiệu quả. Việc tích hợp chỉ cần một gói NuGet duy nhất và không yêu cầu thư viện gốc bên ngoài.

## Cách tùy chỉnh tỷ lệ khung hình DataMatrix
Thuộc tính `AspectRatio` của `BarCodeGenerator` điều khiển tỉ lệ chiều rộng‑chiều cao của ký hiệu DataMatrix được tạo. `BarCodeGenerator` là lớp chính trong Aspose.BarCode dùng để tạo hình ảnh mã vạch.  

**Câu trả lời trực tiếp:** Đặt `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (hoặc bất kỳ giá trị nào trong khoảng 0.5‑2.0) trước khi gọi `GenerateBarCodeImage()`. Thư viện sẽ tự động tính lại kích thước mô-đun để duy trì độ tin cậy khi quét đồng thời tuân thủ tỉ lệ yêu cầu.

### Các bước thực hiện
1. **Khởi tạo** `BarCodeGenerator` với `EncodeTypes.DataMatrix`.  
2. **Điều chỉnh** `AspectRatio` tới giá trị mong muốn.  
3. **Tạo** hình ảnh và kiểm tra bằng máy quét hoặc trình đọc tích hợp của Aspose.

## Cách tạo mã vạch DataMatrix ECC 000‑140
ECC 000‑140 lý tưởng cho các chuỗi dữ liệu ngắn cần ký hiệu gọn gàng, cung cấp tới 140 mã sửa lỗi. `DataMatrixEccMode.Ecc000140` chọn chế độ sửa lỗi ECC 000‑140 cho DataMatrix.  

**Câu trả lời trực tiếp:** Sử dụng `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` trước khi render. Điều này chuyển bộ mã hoá sang thuật toán ECC 000‑140, tạo ra ma trận nhỏ nhất có thể cho dữ liệu đã cho đồng thời vẫn cung cấp khả năng sửa lỗi mạnh mẽ.

### Mẹo thực tế
Khi mã hoá dữ liệu số dưới 20 ký tự, ECC 000‑140 thường cho ra ma trận 10 × 10, giúp tiết kiệm không gian nhãn đáng kể.

## Cách tạo mã vạch DataMatrix ECC 200
ECC 200 là chế độ DataMatrix được sử dụng rộng rãi nhất, hỗ trợ tới 2 335 ký tự chữ và số và cung cấp khả năng sửa lỗi vượt trội. `DataMatrixEccMode.Ecc200` chọn chế độ sửa lỗi ECC 200 cho DataMatrix.  

**Câu trả lời trực tiếp:** Đặt `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` và cung cấp dữ liệu qua `CodeText`. Thư viện sẽ tự động chọn kích thước ma trận tối ưu.

### Khi nào nên ưu tiên ECC 200
Sử dụng ECC 200 cho các chuỗi dài, dữ liệu hỗn hợp, hoặc khi bạn cần độ bền cao nhất trước hư hỏng — lên tới **30 %** ký hiệu có thể được khôi phục.

## Cách thành thạo mã hoá DataMatrix ở chế độ ASCII
Chế độ ASCII mã hoá ký tự bằng một byte mỗi ký tự, là cách tiết kiệm không gian nhất cho văn bản thuần. `DataMatrixEncodeMode.Ascii` chỉ định bộ tạo sử dụng mã hoá ASCII cho ký hiệu DataMatrix.  

**Câu trả lời trực tiếp:** Gán `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` và đặt `CodeText` thành chuỗi ASCII của bạn. Engine sẽ nén dữ liệu mà không có overhead thêm, tạo ra ma trận nhỏ nhất có thể cho nội dung ASCII thuần.

### Tình huống ví dụ
Mã SKU kho chứa các chữ cái in hoa và số (ví dụ, “AB1234”) phù hợp hoàn hảo với chế độ ASCII, thường cho ra ma trận 12 × 12.

## Cách tạo mã vạch DataMatrix Mode (Auto)
Chế độ Auto cho phép Aspose.BarCode phân tích đầu vào và tự động chọn chế độ mã hoá hiệu quả nhất (ASCII, C40, Text, X12 hoặc Bytes). `DataMatrixEncodeMode.Auto` kích hoạt tính năng lựa chọn tự động này.  

**Câu trả lời trực tiếp:** Đặt `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Thư viện sẽ đánh giá payload, chọn chế độ tối ưu và render mã vạch trong một bước duy nhất.

### Lợi ích
Chế độ Auto giảm công sức phát triển và đảm bảo ký hiệu nhỏ nhất có thể cho dữ liệu hỗn hợp, cải thiện tốc độ quét.

## Cách sử dụng chế độ mã hoá DataMatrix (Bytes)
Chế độ Bytes được thiết kế cho dữ liệu nhị phân, chẳng hạn như payload đã mã hoá hoặc tệp nén. `DataMatrixEncodeMode.Bytes` chỉ định bộ tạo coi mỗi byte là dữ liệu thô.  

**Câu trả lời trực tiếp:** Sử dụng `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` và cung cấp chuỗi đã mã hoá Base64 làm `CodeText`. Bộ mã hoá sẽ xử lý mỗi byte như dữ liệu thô, giữ nguyên biểu diễn nhị phân.

### Trường hợp sử dụng
Nhúng GUID 128‑bit hoặc một token mã hoá nhỏ trực tiếp vào ký hiệu DataMatrix.

## Cách thành thạo chế độ mã hoá DataMatrix (C40)
Chế độ C40 nén dữ liệu chữ in hoa và số, đạt giảm kích thước lên tới **40 %** so với ASCII. `DataMatrixEncodeMode.C40` kích hoạt thuật toán nén này.  

**Câu trả lời trực tiếp:** Đặt `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` và cung cấp một chuỗi in hoa (ví dụ, “HELLO WORLD”). Engine sẽ gói ba ký tự thành hai codeword, thu nhỏ ma trận cuối cùng.

### Mẹo chuyên nghiệp
C40 hoạt động tốt nhất khi payload chủ yếu gồm chữ in hoa, số và dấu cách. Đối với dữ liệu hỗn hợp chữ thường, hãy cân nhắc chế độ Auto.

## Cách cấu hình văn bản mã DataMatrix
Thuộc tính `CodeText` xác định dữ liệu chính xác được lưu trong mã vạch. Nó có thể bao gồm văn bản thuần, chuỗi số hoặc thậm chí payload XML. `CodeText` là thuộc tính chuỗi chính của `BarCodeGenerator` chứa payload mã vạch.  

**Câu trả lời trực tiếp:** Gán `generator.Parameters.Barcode.CodeText = "YourDataHere"` trước khi render. Thuộc tính này chấp nhận bất kỳ chuỗi UTF‑8 nào lên tới độ dài tối đa được hỗ trợ bởi chế độ ECC đã chọn.

### Mẹo nâng cao
Kết hợp `CodeText` với `ExtendedDataMatrix` để nhúng siêu dữ liệu bổ sung mà không làm tăng kích thước ma trận hiển thị.

## Cách thành thạo cấu hình macro DataMatrix
Chế độ macro (Macro 05 và Macro 06) cho phép bạn nhúng một ký hiệu DataMatrix phụ bên trong ký hiệu chính, hữu ích cho việc liên kết tới nguồn dữ liệu bên ngoài. `DataMatrixMacroMode.Macro05` và `DataMatrixMacroMode.Macro06` kích hoạt các tính năng macro này.  

**Câu trả lời trực tiếp:** Bật macro bằng `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (hoặc `Macro06`) và thiết lập các thuộc tính `MacroPdf417` cho payload phụ. Bộ tạo sẽ tạo ra một ký hiệu hợp thành mà máy quét có thể hiểu là hai mã liên kết.

### Ví dụ thực tế
Nhúng URL vào phần macro trong khi giữ các định danh sản phẩm trong ma trận chính, cho phép tích hợp web‑to‑barcode liền mạch.

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## Các hướng dẫn cấu hình mã vạch DataMatrix
### [Tùy chỉnh tỷ lệ khung hình DataMatrix](./datamatrix-aspect-ratio-customization/)
Tìm hiểu cách tùy chỉnh tỷ lệ khung hình mã vạch DataMatrix bằng Aspose.BarCode cho .NET. Hướng dẫn từng bước để tạo mã vạch.
### [Tạo mã vạch DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Tạo mã vạch DataMatrix ECC 000-140 một cách dễ dàng bằng Aspose.BarCode cho .NET. Tăng hiệu quả trong quản lý tồn kho và hơn thế nữa.
### [Tạo mã vạch DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Học cách tạo mã vạch DataMatrix ECC 200 trong .NET bằng Aspose.BarCode. Tối ưu hoá quy trình với việc tạo mã vạch hiệu quả.
### [Thành thạo mã hoá DataMatrix ở chế độ ASCII](./datamatrix-encoding-mode-ascii/)
Học cách tạo mã vạch DataMatrix ở chế độ ASCII bằng Aspose.BarCode cho .NET. Hướng dẫn từng bước cho các nhà phát triển.
### [Tạo mã vạch DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
Học cách tạo DataMatrix Mode (Auto) với Aspose.BarCode cho .NET. Hướng dẫn chi tiết từ các yêu cầu tiên quyết đến việc đọc mã vạch.
### [Chế độ mã hoá DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Học cách mã hoá dữ liệu ở định dạng DataMatrix bằng chế độ Bytes với Aspose.BarCode cho .NET. Theo dõi hướng dẫn từng bước để tạo và nhận dạng mã vạch.
### [Thành thạo chế độ mã hoá DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Học chế độ mã hoá DataMatrix (C40) với Aspose.BarCode cho .NET. Tạo mã vạch tùy chỉnh một cách hiệu quả. Khám phá hướng dẫn chi tiết.
### [Cấu hình văn bản mã DataMatrix mở rộng](./datamatrix-extended-code-text-configuration/)
Học cách cấu hình văn bản mã DataMatrix mở rộng bằng Aspose.BarCode cho .NET. Tạo, nhận dạng và tích hợp mã vạch trong ứng dụng .NET của bạn.
### [Thành thạo cấu hình macro DataMatrix](./datamatrix-macro-configuration/)
Học cách cấu hình macro cho mã vạch DataMatrix với Aspose.BarCode cho .NET. Tạo, tùy chỉnh và nhận dạng mã vạch DataMatrix trong ứng dụng .NET của bạn.

## Câu hỏi thường gặp

**Q: Làm sao để quyết định chọn chế độ ECC nào?**  
A: Chọn ECC 000‑140 cho các bộ dữ liệu nhỏ với mức sửa lỗi hạn chế, hoặc ECC 200 cho dữ liệu lớn hơn và độ tin cậy cao hơn. Chế độ macro thêm một lớp dữ liệu phụ để liên kết.

**Q: Tôi có thể nhúng văn bản tùy chỉnh vào mã vạch DataMatrix không?**  
A: Có, đặt thuộc tính `CodeText` thành chuỗi tùy chỉnh của bạn, sau đó chọn chế độ mã hoá phù hợp (ASCII, C40, v.v.) để kiểm soát kích thước.

**Q: Có cách nào để tự động chọn chế độ mã hoá tốt nhất không?**  
A: Đặt `EncodeMode` thành `Auto`; Aspose.BarCode sẽ đánh giá payload và tự động chọn chế độ tiết kiệm không gian nhất.

**Q: Những cân nhắc về hiệu năng khi xử lý lô mã vạch lớn là gì?**  
A: Tái sử dụng một thể hiện `BarCodeGenerator` duy nhất, bật đa luồng, và tạo ảnh PNG để có chất lượng không mất mát hoặc JPEG để giảm kích thước tệp. Việc tạo 10 000 ký hiệu thường hoàn thành trong dưới 30 giây trên máy chủ tiêu chuẩn 8‑core.

**Q: Aspose.BarCode có hỗ trợ .NET Core và .NET 5/6 không?**  
A: Hoàn toàn – thư viện tương thích đầy đủ với .NET Framework, .NET Core và các phiên bản .NET mới nhất, cung cấp cùng một bộ tính năng trên mọi nền tảng.

---

**Cập nhật lần cuối:** 2026-06-09  
**Kiểm tra với:** Aspose.BarCode 24.12 cho .NET  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Thành thạo mã hoá DataMatrix ở chế độ ASCII với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Tạo PNG mã vạch – Tỷ lệ khung hình DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}