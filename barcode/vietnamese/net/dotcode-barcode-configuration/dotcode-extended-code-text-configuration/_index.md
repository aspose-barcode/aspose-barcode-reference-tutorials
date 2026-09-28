---
date: 2026-09-28
description: Tìm hiểu cách tạo mã vạch ma trận 2d với Aspose.BarCode cho .NET – hướng
  dẫn từng bước để tạo mã vạch DotCode với văn bản mã mở rộng.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Cấu hình Văn bản Mã Mở rộng cho DotCode
og_description: Tìm hiểu cách tạo mã vạch ma trận 2d bằng Aspose.BarCode cho .NET.
  Hướng dẫn này trình bày chi tiết cách tạo mã vạch DotCode với văn bản mã mở rộng.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Tạo mã vạch ma trận 2d với Aspose.BarCode cho .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Cách tạo mã vạch ma trận 2d bằng Aspose.BarCode cho .NET
url: /vi/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch ma trận 2d bằng Aspose.BarCode cho .NET

## Giới thiệu

Trong lĩnh vực tạo và quản lý mã vạch, Aspose.BarCode cho .NET nổi bật như một giải pháp đa năng hỗ trợ **hơn 50 định dạng đầu vào và đầu ra** và có thể xử lý tài liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ. Dù bạn cần mã vạch cho việc theo dõi sản phẩm, kiểm soát tồn kho, hay các ứng dụng dữ liệu phong phú, việc tạo **mã vạch ma trận 2d** như DotCode với codetext mở rộng cho phép bạn nhúng cả dữ liệu văn bản và nhị phân trong một ký hiệu vuông gọn gàng. Hướng dẫn này sẽ dẫn bạn qua quá trình xây dựng codetext mở rộng từng bước và hiển thị hình ảnh cuối cùng.

## Câu trả lời nhanh
- **“create dotcode extended codetext” có nghĩa là gì?** Nó có nghĩa là xây dựng một mã vạch DotCode bao gồm FNC1, ECICodetext, văn bản thuần và ký tự ngăn cách trong một payload mở rộng duy nhất.  
- **Thư viện nào cần thiết?** Aspose.BarCode cho .NET.  
- **Có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Thời gian triển khai khoảng bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản.

## Cách tạo dotcode extended codetext

Tải dự án của bạn, đặt thư mục, xây dựng codetext mở rộng và tạo hình ảnh – tất cả trong chưa đầy một chục dòng mã. Câu trả lời trực tiếp dưới đây tóm tắt toàn bộ quy trình:

Tải `BarcodeGenerator` với `EncodeTypes.DotCode`, xây dựng codetext mở rộng bằng `DotCodeExtendedCodetextBuilder` (thêm FNC1, ECICodetext, văn bản thuần và ký tự ngăn cách FNC3), sau đó gọi `Save` để ghi file PNG. Quy trình này tạo ra một mã vạch ma trận 2d hoàn toàn tuân chuẩn chỉ trong một lần gọi.

## Dotcode extended codetext là gì?

**dotcode extended codetext** là một chuỗi tổng hợp kết hợp nhiều đoạn dữ liệu — chẳng hạn như định danh FNC1, ECICodetext, văn bản thuần và ký tự ngăn cách FNC3 — thành một payload mà DotCode có thể giải mã. Nó cho phép mã hoá văn bản đa ngôn ngữ, khối dữ liệu nhị phân và dữ liệu có cấu trúc trong một mã vạch ma trận 2d duy nhất, rất thích hợp cho chuỗi cung ứng, chăm sóc sức khỏe và các kịch bản IoT.

## Tại sao sử dụng Aspose.BarCode cho nhiệm vụ này?

Aspose.BarCode xử lý **lên tới 500 trang mỗi giây** trên phần cứng máy chủ tiêu chuẩn và hỗ trợ **hơn 30 loại mã vạch**, bao gồm DotCode. API `GetExtendedCodetext` của nó đảm bảo vị trí chính xác của các ký tự điều khiển, loại bỏ lỗi nối chuỗi thủ công và đảm bảo tuân thủ ISO/IEC 24724. Ngoài ra, nó còn cung cấp khả năng sửa lỗi tích hợp và xử lý vùng yên tĩnh tự động, giảm nhu cầu tinh chỉnh thủ công.

## Yêu cầu trước

- **Aspose.BarCode cho .NET** – tải về từ [tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/).  
- Môi trường phát triển .NET (khuyến nghị Visual Studio 2022 hoặc phiên bản mới hơn).  
- Tùy chọn: file giấy phép tạm thời để đánh giá.

## Nhập không gian tên

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Các không gian tên này cung cấp lớp `BarcodeGenerator` và trợ giúp `DotCodeExtendedCodetextBuilder` cần thiết cho ví dụ.

```csharp
using Aspose.BarCode.Generation;
```

Bây giờ chúng ta đã hoàn thành các yêu cầu trước, hãy phân tích quy trình tạo DotCode Extended Code Text thành hướng dẫn từng bước.

## Bước 1: xác định đường dẫn thư mục

Xác định nơi sẽ lưu PNG được tạo. Sử dụng đường dẫn tuyệt đối hoặc tương đối mà ứng dụng của bạn có thể ghi vào.

```csharp
string path = "Your Directory Path";
```

Thay thế `"Your Directory Path"` bằng đường dẫn thực tế trên hệ thống của bạn.

## Bước 2: tạo dotcode extended codetext

Lớp `DotCodeExtendedCodetextBuilder` tập hợp các đoạn khác nhau thành một chuỗi codetext mở rộng duy nhất.

Để tạo DotCode Extended Code Text, thực hiện các bước phụ sau:

### 2.1 thêm định danh định dạng fnc1

Định danh định dạng FNC1 đánh dấu bắt đầu của một trường dữ liệu mới. Nó bắt buộc cho các ký hiệu DotCode tuân thủ GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 thêm ecicodetext

ECICodetext mã hoá các ký tự đặc biệt và văn bản quốc tế. Trong ví dụ này chúng ta mã hoá `"犬Right狗"` bằng UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 thêm plain codetext

Bạn cũng có thể thêm văn bản thuần vào DotCode Extended Code Text. Ở đây, chúng ta thêm `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 thêm ký tự ngăn cách fnc3

Ký tự ngăn cách FNC3 tách các phần khác nhau của mã, cải thiện khả năng đọc cho máy quét.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 thêm khởi tạo trình đọc fnc3

Bước này thêm thông tin Khởi tạo Đọc giả FNC3, cho máy quét biết cách diễn giải dữ liệu tiếp theo.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 tạo codetext

Bây giờ tạo DotCode Extended Codetext bằng cách gọi phương thức `GetExtendedCodetext` trên đối tượng `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Bước 3: tạo ảnh dotcode

Hiển thị hình ảnh mã vạch từ codetext mở rộng.

#### 3.1 khởi tạo barcode generator

Lớp `BarcodeGenerator` là đối tượng cốt lõi của Aspose.BarCode để tạo bất kỳ mã vạch nào. Bạn khởi tạo nó với loại ký hiệu mong muốn (`EncodeTypes.DotCode`) và codetext mở rộng vừa xây dựng.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Cuối cùng, gọi `Save` để ghi file PNG vào đĩa. Hình ảnh đã sẵn sàng để nhúng vào báo cáo, ứng dụng di động hoặc nhãn in.

## Các vấn đề thường gặp và giải pháp

- **Mã hoá không đúng** – Đảm bảo sử dụng `ECIEncodings.UTF8` khi thêm văn bản đa ngôn ngữ; nếu không ký tự có thể bị lỗi.  
- **Lỗi truy cập tệp** – Kiểm tra ứng dụng có quyền ghi vào thư mục đích hay không.  
- **Thiếu vùng yên tĩnh** – Đặt `gen.Parameters.Barcode.Margin` nếu máy quét yêu cầu thêm không gian trắng quanh ký hiệu.

## Câu hỏi thường gặp

**Hỏi: Tôi có thể sử dụng mã vạch đã tạo trong ứng dụng di động không?**  
**Đ: Có.** Ảnh PNG do trình tạo tạo ra có thể được nhúng vào iOS, Android, hoặc bất kỳ ứng dụng di động đa nền tảng nào.

**Hỏi: Nếu tôi cần mã hoá dữ liệu nhị phân thay vì văn bản thì sao?**  
**Đ: Sử dụng phương thức `AddECICodetext` với `ECIEncodings` phù hợp (ví dụ, `ECIEncodings.Base64`) để nhúng tải trọng nhị phân.**

**Hỏi: Làm sao thay đổi kích thước mã vạch mà không ảnh hưởng tới khả năng đọc?**  
**Đ: Điều chỉnh thuộc tính `XDimension.Pixels`; giá trị cao hơn làm tăng kích thước mô-đun, giá trị thấp hơn làm mã vạch gọn hơn.**

**Hỏi: Có cách nào thêm vùng yên tĩnh quanh mã vạch không?**  
**Đ: Có. Đặt `gen.Parameters.Barcode.Margin` để xác định vùng yên tĩnh mong muốn tính bằng pixel.**

**Hỏi: Thư viện có hỗ trợ .NET 8 không?**  
**Đ: Các bản phát hành mới nhất của Aspose.BarCode tương thích với .NET 8; chỉ cần tham chiếu phiên bản NuGet phù hợp.**

Nếu bạn cần thêm hướng dẫn hoặc có câu hỏi, đừng ngần ngại truy cập [tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/) hoặc tham gia cộng đồng trên [diễn đàn hỗ trợ Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2026-09-28  
**Được kiểm tra với:** Aspose.BarCode 24.12 cho .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo mã vạch DotCode .NET (Chế độ Tự động) với Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Cách tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn từng bước](/barcode/net/datamatrix-barcode-configuration/)
- [Cách tạo mã vạch Aztec với Aspose.BarCode cho .NET](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}