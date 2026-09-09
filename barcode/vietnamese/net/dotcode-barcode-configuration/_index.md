---
date: 2026-06-14
description: Tìm hiểu cách tạo mã vạch DotCode với Aspose.BarCode cho .NET, bao gồm
  aspect ratio, encoding modes, extended text và reader initialization.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Cách tạo mã vạch DotCode – Hướng dẫn cấu hình
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cách tạo mã vạch DotCode – Hướng dẫn cấu hình
url: /vi/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hướng Dẫn Cấu Hình Tạo Mã Vạch DotCode

## Giới thiệu
**Việc tạo mã vạch DotCode** nhanh chóng và đáng tin cậy là một yêu cầu phổ biến đối với các nhà phát triển xây dựng các giải pháp quản lý tồn kho, theo dõi hoặc quét di động. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn qua mọi tùy chọn cấu hình mà Aspose.BarCode cho .NET cung cấp cho các ký hiệu DotCode — điều chỉnh tỷ lệ khung hình, các chế độ mã hoá Auto và Bytes, xử lý văn bản mã mở rộng, khởi tạo bộ đọc, bố trí hàng/cột, và chế độ Structured Append. Khi kết thúc, bạn sẽ có thể tạo ra các hình ảnh DotCode có kích thước hoàn hảo, mật độ cao, đáp ứng tiêu chuẩn ngành và tích hợp liền mạch vào bất kỳ ứng dụng .NET nào.

## Câu trả lời nhanh
- **Lớp chính để tạo mã vạch DotCode là gì?** `BarcodeGenerator` với `EncodeTypes.DotCode`.
- **Thuộc tính nào điều khiển tỷ lệ khung hình?** `BarCodeImageAspectRatio`.
- **Tôi có thể chuyển đổi giữa mã hoá Auto và Bytes không?** Có, thông qua thuộc tính `EncodeMode`.
- **Cần một bộ đọc riêng cho DotCode không?** Không, cùng một `BarcodeGenerator` có thể giải mã khi gọi `ReadBarcode`.
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Cách tạo mã vạch DotCode bằng Aspose.BarCode cho .NET?
`BarcodeGenerator` là lớp chính trong Aspose.BarCode để tạo hình ảnh mã vạch. Tải `BarcodeGenerator` với `EncodeTypes.DotCode`, thiết lập các thuộc tính mong muốn (tỷ lệ khung hình, chế độ mã hoá, hàng/cột, v.v.), và gọi `GenerateBarCodeImage()` — thư viện sẽ trả về một `System.Drawing.Image` hoặc một mảng byte đã sẵn sàng sử dụng. Quy trình một bước này xử lý tất cả các chi tiết mã hoá cấp thấp, hỗ trợ các định dạng đầu ra như PNG, JPEG và SVG, và có thể render hình ảnh lên tới 10 000 × 10 000 px mà không tiêu tốn quá nhiều bộ nhớ.

## Mã vạch DotCode là gì?
Mã vạch DotCode là một ký hiệu 2D dạng vuông, mật độ cao, có khả năng lưu trữ tới 1 200 ký tự số hoặc 800 ký tự chữ‑số trong một ma trận chấm nhỏ gọn. Nó được tối ưu cho việc dán nhãn gói hàng nhỏ và quét di động, cung cấp tốc độ đọc nhanh ngay cả trên các camera độ phân giải thấp.

## Tại sao nên sử dụng DotCode với Aspose.BarCode?
Aspose.BarCode hỗ trợ **hơn 20** loại mã vạch 2D, bao gồm DotCode, và có thể xử lý các tệp lớn hơn **200 MB** mà không cần tải toàn bộ hình ảnh vào bộ nhớ. Thư viện đảm bảo độ chính xác quét **99,9 %** trên các camera smartphone tiêu chuẩn và cung cấp các mức sửa lỗi tích hợp để giảm thiểu lỗi đọc.

## Yêu cầu trước
- .NET Framework 4.5 hoặc cao hơn, hoặc .NET Core 3.1 / .NET 5+.
- Aspose.BarCode cho .NET (phiên bản mới nhất được khuyến nghị).
- Một khóa giấy phép tạm thời hoặc đầy đủ (bản dùng thử hoạt động cho phát triển).

## Tùy chỉnh Tỷ lệ Khung hình DotCode
**Tỷ lệ khung hình** xác định độ kéo dài hoặc nén của ma trận DotCode. Sử dụng thuộc tính `BarCodeImageAspectRatio` để đặt giá trị trong khoảng **0.5** (cao hơn) và **2.0** (rộng hơn). Tỷ lệ **1.0** tạo ra một ký hiệu vuông hoàn hảo, đây là mặc định và hoạt động tốt nhất cho hầu hết các máy quét.

> **Mẹo:** Khi in trên nhãn hẹp, tỷ lệ **0.75** thường cải thiện khả năng đọc mà không làm giảm dung lượng dữ liệu.

## Chế độ Mã hoá DotCode (Auto)
Trong chế độ **Auto**, thư viện phân tích chuỗi đầu vào và tự động chọn cách mã hoá hiệu quả nhất (số, chữ‑số, hoặc byte). Điều này tối đa hoá mật độ dữ liệu và giảm kích thước tổng thể của ký hiệu.

> **Câu trả lời trực tiếp:** Đặt `EncodeMode = EncodeModes.Auto` trên `BarcodeGenerator` để cho Aspose.BarCode quyết định cách mã hoá tối ưu cho dữ liệu của bạn, đảm bảo DotCode nhỏ nhất có thể đồng thời giữ nguyên tất cả các ký tự.

## Chế độ Mã hoá DotCode (Bytes)
Khi bạn cần lưu trữ dữ liệu nhị phân hoặc mảng byte đã mã hoá trước, chọn chế độ **Bytes**. Điều này buộc trình tạo coi đầu vào là byte thô, bỏ qua việc tự động phát hiện bộ ký tự.

> **Câu trả lời trực tiếp:** Sử dụng `EncodeMode = EncodeModes.Bytes` và cung cấp payload kiểu `byte[]` để nhúng thông tin nhị phân như định danh đã mã hoá hoặc tệp nén trực tiếp vào ký hiệu DotCode.

## Cấu hình Văn bản Mã mở rộng DotCode
Văn bản mã mở rộng cho phép bạn gắn kèm thông tin bổ sung không thuộc phần dữ liệu chính nhưng có thể hiển thị cùng với mã vạch trong báo cáo hoặc giao diện người dùng. Đặt thuộc tính `ExtendedCodeText` thành bất kỳ chuỗi nào (tối đa **256** ký tự) và chọn phông chữ qua `ExtendedCodeTextFont`.

> **Mẹo chuyên nghiệp:** Kết hợp văn bản mở rộng với kích thước phông chữ nhỏ hơn (ví dụ, 8 pt) để giảm diện tích hiển thị trong khi vẫn cung cấp ngữ cảnh có thể đọc được bởi con người.

## Khởi tạo Đọc mã DotCode
`BarCodeReader` là lớp dùng để giải mã mã vạch từ hình ảnh hoặc luồng. Đọc một hình ảnh DotCode cũng đơn giản như việc tạo. Khởi tạo một `BarCodeReader` với luồng ảnh và chỉ định `EncodeTypes.DotCode`. Gọi `ReadBarCode()` để lấy chuỗi đã giải mã.

> **Câu trả lời trực tiếp:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – khối mã này giải mã ký hiệu mà không cần phụ thuộc bên ngoài.

## Cấu hình Hàng và Cột DotCode
DotCode cho phép kiểm soát rõ ràng số hàng và cột, ảnh hưởng đến kích thước ký hiệu và khả năng sửa lỗi. Sử dụng các thuộc tính `Rows` và `Columns` để đặt giá trị trong khoảng **10** đến **144**. Ma trận lớn hơn tăng dung lượng dữ liệu và độ bền.

> **Thực hành tốt:** Đối với thẻ kho cần chịu va đập, cấu hình **Rows = 64** và **Columns = 64** để thêm dư thừa.

## Cấu hình Chế độ Nối cấu trúc DotCode
Structured Append cho phép chia một payload lớn thành nhiều ký hiệu DotCode có thể đọc tuần tự. Đặt `StructuredAppend = true` và xác định `StructuredAppendCount` và `StructuredAppendIndex` cho mỗi phần.

> **Câu trả lời trực tiếp:** Bật `StructuredAppend` trên mỗi `BarcodeGenerator`, gán chỉ số duy nhất (bắt đầu từ 1), và đặt tổng số; thư viện sẽ tự động nhúng thông tin liên kết cần thiết.

## Các vấn đề thường gặp và Giải pháp
- **Mã vạch không đọc được trên màn hình độ phân giải thấp:** Tăng thuộc tính `Resolution` lên ít nhất **300 dpi** trước khi tạo.
- **Cảnh báo cắt ngắn dữ liệu:** Kiểm tra độ dài đầu vào không vượt quá tối đa cho hàng/cột đã chọn; điều chỉnh kích thước hoặc chuyển sang chế độ Bytes nếu cần.
- **Giấy phép hết hạn trong quá trình phát triển:** Sử dụng giấy phép tạm thời lấy từ cổng thông tin Aspose; thay thế bằng khóa vĩnh viễn trước khi triển khai sản phẩm.

## Câu hỏi thường gặp

**Q: Tôi có thể tạo mã vạch DotCode ở định dạng SVG không?**  
A: Có, đặt `BarCodeImageFormat = BarCodeImageFormat.Svg` trên trình tạo để nhận đầu ra vector có thể mở rộng.

**Q: Có thể nhúng logo vào trong ký hiệu DotCode không?**  
A: Aspose.BarCode không hỗ trợ nhúng logo trực tiếp cho DotCode, nhưng bạn có thể chồng một hình ảnh lên sau khi tạo bằng các thư viện đồ họa tiêu chuẩn.

**Q: Cơ chế sửa lỗi cho DotCode hoạt động như thế nào?**  
A: Ký hiệu này bao gồm sửa lỗi Reed‑Solomon tích hợp; tăng số hàng/cột sẽ tự động nâng mức sửa lỗi.

**Q: Tôi có cần thư viện riêng để đọc DotCode từ PDF không?**  
A: Không, cùng một `BarCodeReader` có thể trích xuất DotCode từ các trang PDF, hình ảnh hoặc luồng mà không cần công cụ bổ sung.

**Q: Kích thước dữ liệu tối đa cho một ký hiệu DotCode là bao nhiêu?**  
A: Lên tới **1 200** ký tự số hoặc **800** ký tự chữ‑số, tùy thuộc vào cấu hình hàng/cột đã chọn.

**Cập nhật lần cuối:** 2026-06-14  
**Kiểm tra với:** Aspose.BarCode 24.11 cho .NET  
**Tác giả:** Aspose  

## Các hướng dẫn cấu hình mã vạch DotCode
### [Tùy chỉnh Tỷ lệ Khung hình DotCode](./dotcode-aspect-ratio-customization/)
Học cách tùy chỉnh tỷ lệ khung hình mã vạch DotCode bằng Aspose.BarCode cho .NET. Tạo các mã vạch được thiết kế riêng cho ứng dụng của bạn một cách dễ dàng.
### [Chế độ Mã hoá DotCode (Auto)](./dotcode-encoding-mode-auto/)
Khám phá chế độ Mã hoá DotCode (Auto) trong Aspose.BarCode cho .NET, một công cụ mạnh mẽ để tạo mã vạch. Học cách tạo mã vạch DotCode từng bước. Xem tài liệu, tải thư viện và nhận giấy phép tạm thời.
### [Chế độ Mã hoá DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Học cách mã hoá DotCode với Aspose.BarCode cho .NET: Hướng dẫn từng bước để tạo mã vạch.
### [Cấu hình Văn bản Mã mở rộng DotCode](./dotcode-extended-code-text-configuration/)
Tạo cấu hình Văn bản Mã mở rộng DotCode một cách dễ dàng bằng Aspose.BarCode cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi để tạo mã vạch hiệu quả.
### [Khởi tạo Đọc mã DotCode](./dotcode-reader-initialization/)
Học cách khởi tạo Đọc mã DotCode bằng Aspose.BarCode cho .NET. Tạo mã vạch DotCode một cách dễ dàng cho nhiều ứng dụng.
### [Cấu hình Hàng và Cột DotCode](./dotcode-rows-columns-configuration/)
Học cách cấu hình Hàng và Cột DotCode với Aspose.BarCode cho .NET. Tạo mã vạch 2D chính xác và tùy chỉnh một cách dễ dàng.
### [Cấu hình Chế độ Nối cấu trúc DotCode](./dotcode-structured-append-mode-configuration/)
Học cách cấu hình Chế độ Nối cấu trúc DotCode với Aspose.BarCode cho .NET và tạo các mã vạch hiệu quả.

## Hướng dẫn liên quan

- [Tùy chỉnh Tỷ lệ Khung hình DotCode với Aspose.BarCode cho .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Cấu hình Văn bản Mã mở rộng DotCode với Aspose.BarCode cho .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Chế độ Mã hoá DotCode (Auto) trong Aspose.BarCode cho .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}