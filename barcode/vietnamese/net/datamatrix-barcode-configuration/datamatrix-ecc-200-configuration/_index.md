---
date: 2026-08-02
description: Tìm hiểu cách tạo DataMatrix barcode, tạo datamatrix, và khám phá high
  density barcode generation với Aspose.BarCode cho các dự án .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Cấu hình DataMatrix ECC 200
og_description: Tạo DataMatrix barcode với Aspose.BarCode cho .NET. Hướng dẫn này
  trình bày high density barcode generation, thiết lập temporary Aspose license, và
  step‑by‑step C# code.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Tạo DataMatrix barcode – hướng dẫn Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Cách tạo DataMatrix barcode (ECC 200) với Aspose.BarCode cho .NET
url: /vi/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ **tạo mã vạch DataMatrix** (ECC 200) bằng Aspose.BarCode cho .NET. Cho dù bạn đang xây dựng một hệ thống theo dõi tồn kho, một hệ thống điểm bán hàng, hoặc tự động hoá quy trình tài liệu, một mã vạch mật độ cao có thể lưu trữ rất nhiều dữ liệu trong không gian rất nhỏ. Chúng tôi sẽ hướng dẫn từng bước cấu hình, giải thích lý do mỗi thiết lập quan trọng, và cung cấp cho bạn các đoạn mã C# sẵn sàng chạy.

## Câu trả lời nhanh

- **Thư viện nào là tốt nhất cho DataMatrix trong .NET?** Aspose.BarCode for .NET  
- **Mức ECC nào mà ECC 200 cung cấp?** Sửa lỗi mật độ cao cho việc quét ổn định.  
- **Tôi có cần giấy phép để chạy mẫu không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tôi có thể xuất PNG, JPEG hoặc TIFF không?** Có – phương thức `Save` hỗ trợ nhiều định dạng ảnh.

## DataMatrix ECC 200 là gì?

DataMatrix ECC 200 là một mã vạch hai chiều mật độ cao có thể lưu trữ lên tới 2.335 ký tự chữ và số hoặc 1.556 byte dữ liệu nhị phân trong một mẫu vuông hoặc hình chữ nhật gọn gàng. Nó sử dụng kỹ thuật sửa lỗi Reed‑Solomon để khôi phục các mô-đun bị mất hoặc hỏng, làm cho nó trở nên lý tưởng cho các ứng dụng như đánh dấu bộ phận hàng không, dán nhãn dược phẩm và logistics, nơi độ tin cậy là rất quan trọng.

## Tại sao nên sử dụng Aspose để tạo mã vạch?

Aspose.BarCode hỗ trợ **hơn 30 loại ký hiệu**, có thể render hình ảnh lên tới 10.000 × 10.000 px mà không cần tải toàn bộ tệp vào bộ nhớ, và cung cấp kết quả xác định trên Windows, Linux và macOS. API của nó cho phép bạn kiểm soát mọi tham số render, làm cho nó trở thành lựa chọn linh hoạt nhất cho các kịch bản **barcode generation ASP.NET**.

## Yêu cầu trước

1. **Môi trường phát triển** – Visual Studio với .NET framework phù hợp đã được cài đặt.  
2. **Aspose.BarCode cho .NET** – Tải xuống và cài đặt từ trang web, [tại đây](https://releases.aspose.com/barcode/net/).  
3. **Giấy phép** – Nhận giấy phép tạm thời để thử nghiệm từ [tại đây](https://purchase.aspose.com/temporary-license/).  
4. **Cơ bản C#** – Quen thuộc với cú pháp C# và cấu trúc dự án.

Bây giờ chúng ta đã nắm vững các kiến thức cơ bản, hãy chuyển sang cấu hình DataMatrix ECC 200.

## Nhập không gian tên

`Aspose.BarCode.Generation` là không gian tên chứa tất cả các lớp cần thiết cho việc tạo mã vạch. Nhập nó ở đầu file của bạn:

```csharp
using Aspose.BarCode.Generation;
```

## Cách tạo mã vạch DataMatrix (ECC 200) từng bước

Để tạo một mã vạch DataMatrix ECC 200, bạn chỉ cần tải dữ liệu muốn mã hoá, cấu hình một vài tham số quan trọng trên `BarcodeGenerator`, và sau đó gọi `Save` để ghi file ảnh. Quy trình ba bước này xử lý việc mã hoá, sửa lỗi, và lựa chọn định dạng đầu ra, cho phép bạn tích hợp việc tạo mã vạch vào bất kỳ ứng dụng .NET nào với ít mã.

### Bước 1: Khởi tạo Barcode Generator

`BarcodeGenerator` là lớp cốt lõi của Aspose.BarCode dùng để tạo và render mã vạch. Nó nhận loại ký hiệu và văn bản cần mã hoá.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Thay thế `"Your Directory Path"` bằng thư mục mà bạn muốn lưu ảnh.

### Bước 2: Đặt XDimension và loại ECC

`XDimension` xác định kích thước pixel của mỗi mô-đun DataMatrix, trong khi `DataMatrixEcc` chọn mức độ sửa lỗi. ECC 200 cung cấp khả năng sửa lỗi cao nhất cho loại ký hiệu này.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Điều chỉnh giá trị pixel nếu bạn cần mô-đun lớn hơn hoặc nhỏ hơn; giá trị điển hình là 4‑6 px cho hiển thị trên màn hình và 8‑10 px cho nhãn in.

### Bước 3: Tạo và lưu ảnh mã vạch

Phương thức `Save` ghi mã vạch vào một file. Bạn có thể chọn PNG, JPEG hoặc TIFF bằng cách truyền giá trị enum `BarCodeImageFormat` tương ứng.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Tiff` nếu quy trình của bạn yêu cầu định dạng khác.

## Vấn đề thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Mã vạch bị mờ | XDimension quá thấp | Tăng `XDimension.Pixels` lên 6‑8 |
| Quét không thành công trên điện thoại | Mức ECC sai | Đảm bảo `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| File không được tạo | Chuỗi đường dẫn không hợp lệ | Sử dụng đường dẫn tuyệt đối hoặc đảm bảo thư mục tồn tại |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng đoạn mã này trong ứng dụng console .NET Core không?**  
A: Có, cùng một API hoạt động trong các dự án .NET Core, .NET 5 và .NET 6.

**Q: Làm thế nào để thay đổi định dạng đầu ra thành JPEG?**  
A: Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` trong lời gọi `Save`.

**Q: Có thể nhúng mã vạch trực tiếp vào PDF không?**  
A: Có – tạo ảnh trước, sau đó thêm vào PDF bằng Aspose.PDF hoặc bất kỳ thư viện PDF nào.

**Q: Nếu tôi cần mã hoá ký tự Unicode thì sao?**  
A: DataMatrix hỗ trợ UTF‑8; chỉ cần truyền chuỗi Unicode cho generator như minh họa.

**Q: Thư viện có hỗ trợ tạo hàng loạt nhiều mã vạch không?**  
A: Chắc chắn – đặt mã tạo trong một vòng lặp và thay đổi dữ liệu/giá trị cho mỗi lần lặp.

## Kết luận

Chúng tôi đã bao phủ mọi thứ bạn cần để **tạo mã vạch DataMatrix** (ECC 200) với Aspose.BarCode cho .NET: từ các yêu cầu trước và việc nhập không gian tên đến cấu hình X‑dimension, chọn mức ECC, và lưu ảnh ở định dạng bạn muốn. Hãy thử nghiệm với nhiều thuộc tính bổ sung—như lề, màu nền và xoay—để tinh chỉnh kết quả cho trường hợp sử dụng cụ thể của bạn.

Nếu bạn gặp bất kỳ khó khăn nào, cộng đồng sẵn sàng hỗ trợ trên [diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Chúc bạn lập trình vui vẻ!

---

**Cập nhật lần cuối:** 2026-08-02  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách tạo mã vạch DataMatrix ECC 000-140 với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Cách đọc mã vạch DataMatrix với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-reading/)
- [Tạo Barcode PNG – Tỷ lệ khung hình DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}