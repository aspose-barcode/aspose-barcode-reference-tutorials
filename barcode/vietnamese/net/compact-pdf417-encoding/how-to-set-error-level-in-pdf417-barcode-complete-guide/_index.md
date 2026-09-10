---
category: general
date: 2026-07-18
description: Cách đặt mức lỗi trong mã vạch PDF417 bằng Aspose.BarCode. Học cách tạo
  mã vạch PDF417 với văn bản tùy chỉnh và điều chỉnh mức sửa lỗi trong vài phút.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: vi
lastmod: 2026-07-18
og_description: cách thiết lập mức lỗi trong mã vạch PDF417 nhanh chóng. Hướng dẫn
  này sẽ chỉ cho bạn cách tạo mã vạch PDF417 với văn bản tùy chỉnh và các mức sửa
  lỗi khác nhau.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Cách thiết lập mức lỗi trong mã vạch PDF417 – Hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Cách Đặt Mức Lỗi Trong Mã Vạch PDF417 – Hướng Dẫn Toàn Diện
url: /vi/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đặt Mức Lỗi trong Mã Vạch PDF417 – Hướng Dẫn Toàn Diện

Bạn đã bao giờ tự hỏi **cách đặt lỗi** khi tạo mã vạch PDF417 chưa? Bạn không phải là người duy nhất—hầu hết các nhà phát triển gặp khó khăn này khi cần một mã vạch mạnh hơn để quét trong môi trường khắc nghiệt. Tin tốt là gì? Việc điều chỉnh mức sửa lỗi rất dễ dàng với Aspose.BarCode, và bạn cũng sẽ học **cách tạo PDF417** với văn bản tùy chỉnh của riêng mình.

Trong hướng dẫn này, chúng ta sẽ đi qua từng bước, từ việc tạo trình tạo mã vạch với các ký tự đặc biệt đến lưu hai tệp PNG hiển thị các mức sửa lỗi khác nhau. Khi kết thúc, bạn sẽ thoải mái với **việc tạo mã vạch PDF417**, điều chỉnh X‑dimension, số cột, và quan trọng nhất, **đặt mức lỗi** phù hợp với trường hợp sử dụng của bạn.

## Yêu Cầu Trước

- .NET 6.0 trở lên (mã cũng hoạt động với .NET Framework)
- Aspose.BarCode cho .NET đã được cài đặt (`Install-Package Aspose.BarCode` qua NuGet)
- Một thư mục trên đĩa nơi có thể ghi ảnh (thay thế `YOUR_DIRECTORY/` trong mẫu)
- Kiến thức cơ bản về C#—nếu bạn đã từng viết `Console.WriteLine`, bạn đã sẵn sàng

> **Mẹo chuyên nghiệp:** Nếu bạn đang hướng tới việc quét trên thiết bị di động, hãy chọn mức lỗi cao hơn (Level 5) để chịu được bụi bẩn, trầy xước hoặc điều kiện ánh sáng yếu.

## Bước 1: Tạo Trình Tạo Mã Vạch với Văn Bản Tùy Chỉnh

Điều đầu tiên bạn cần là một thể hiện `BarcodeGenerator` biết rằng nó sẽ tạo **mã vạch PDF417** và chứa đúng văn bản bạn muốn mã hoá. Lưu ý việc sử dụng các ký tự có dấu và ký hiệu bản quyền—điều này chứng minh trình tạo có thể xử lý Unicode ngay từ đầu.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Tại sao điều này quan trọng:* Cờ `EncodeTypes.Pdf417` thông báo cho Aspose rằng bạn đang làm việc với mã vạch 2‑D xếp chồng, trong khi đối số chuỗi trở thành dữ liệu tải. Nếu bỏ qua bước này, bạn sẽ nhận được mã vạch Code128 mặc định thay vì PDF417 có dung lượng cao mà bạn cần.

## Bước 2: Tinh Chỉnh Tham Số Trực Quan

Mã vạch PDF417 không chỉ là dữ liệu; nó còn là một mẫu hình ảnh. Điều chỉnh **X‑dimension** (độ rộng của thanh nhỏ nhất) và số **cột** cho phép bạn kiểm soát kích thước vật lý và khả năng đọc của mã vạch.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Tại sao điều này quan trọng:* X‑dimension nhỏ hơn tạo ra hình ảnh gọn hơn nhưng có thể trở nên không đọc được trên máy quét độ phân giải thấp. Ba cột cung cấp tỷ lệ cân bằng cho hầu hết các kích thước nhãn.

## Bước 3: Đặt Mức Sửa Lỗi Thành 2 và Lưu

Sửa lỗi là cốt lõi của **cách đặt lỗi** cho PDF417. Enum `Pdf417ErrorLevel` có các mức từ `Level0` (không có dữ liệu bổ sung) đến `Level5` (tối đa dư thừa). Ở đây chúng ta bắt đầu với **Level 2**, mức này thêm một lượng vừa phải khả năng chịu lỗi mà không làm tăng kích thước ảnh quá nhiều.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Sau khi chạy đoạn mã này, bạn sẽ thấy `Pdf417ErrorLevel2.png` trong thư mục của mình. Mở nó lên, bạn sẽ thấy một mã vạch ba cột sạch sẽ nhưng vẫn chứa một lượng dư thừa đáng kể.

## Bước 4: Tăng Mức Sửa Lỗi lên Level 5 và Lưu Lại

Đôi khi bạn cần mã vạch chịu được tổn thương mạnh hơn—hãy tưởng tượng sàn kho nơi nhãn bị trầy xước. Chuyển sang **Level 5** tối đa hoá sửa lỗi nhưng sẽ làm ảnh hơi lớn hơn.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Bây giờ bạn có hai tệp PNG cạnh nhau: một với mức sửa lỗi vừa phải, một với mức tối đa. So sánh chúng; phiên bản Level 5 sẽ có nhiều mô-đun tối hơn, chính là những gì thuật toán thêm vào để bảo vệ dữ liệu.

![cách đặt mức lỗi trong ví dụ mã vạch PDF417](image.png)

*Mô tả hình ảnh (alt text): cách đặt mức lỗi trong ví dụ mã vạch PDF417 – hiển thị hai tệp PNG với các mức sửa lỗi khác nhau.*

## Kết Quả Mong Đợi

| Tên tệp                       | Mức lỗi     | Kích thước xấp xỉ (px) |
|-------------------------------|-------------|--------------------------|
| `Pdf417ErrorLevel2.png`       | Level 2     | 150 × 80                 |
| `Pdf417ErrorLevel5.png`       | Level 5     | 180 × 95                 |

Cả hai hình ảnh đều mã hoá chuỗi **“Åspóse.Barcóde©”** và có thể được quét bằng bất kỳ trình đọc PDF417 tiêu chuẩn nào (ví dụ: ZXing, Scandit). Hình Level 5 chịu được tới ~30 % hư hỏng, trong khi Level 2 chịu được khoảng ~15 %.

## Câu Hỏi Thường Gặp & Trường Hợp Cạnh

### Nếu văn bản của tôi chứa dấu ngắt dòng thì sao?

PDF417 tự động mã hoá ký tự xuống dòng (`\n`). Chỉ cần đưa chúng vào chuỗi:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Tôi có thể sử dụng định dạng ảnh khác không?

Chắc chắn rồi. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Svg` tùy thuộc vào quy trình làm việc tiếp theo của bạn.

### Thay đổi X‑dimension có ảnh hưởng đến sửa lỗi không?

Gián tiếp, có. X‑dimension lớn hơn tạo ra các mô-đun lớn hơn, có thể cải thiện độ tin cậy khi quét nhưng **không** thay đổi mức sửa lỗi logic. Điều chỉnh cả hai tham số một cách độc lập để đạt kết quả tốt nhất.

### Cách tạo mã vạch PDF417 trong một Web API?

Đặt cùng một đoạn mã trong một controller ASP.NET Core và truyền PNG về dưới dạng `FileResult`. Logic cốt lõi không thay đổi, nghĩa là **cách tạo PDF417** vẫn nhất quán giữa môi trường desktop và web.

## Tóm Tắt

Chúng ta đã đề cập đến **cách đặt lỗi** cho mã vạch PDF417, trình bày **cách tạo PDF417** với văn bản Unicode tùy chỉnh, và cho bạn thấy cách tinh chỉnh các thiết lập trực quan như X‑dimension và số cột. Bằng cách thay `Pdf417ErrorLevel.Level2` bằng `Level5` bạn có thể kiểm soát sự cân bằng giữa kích thước ảnh và độ bền.

## Bước Tiếp Theo

- Thử nghiệm với **mã vạch với văn bản tùy chỉnh** có chứa URL hoặc ID sản phẩm.
- Thử các số cột khác nhau (`generator.Parameters.Barcode.Pdf417.Columns = 5`) để xem hình dạng thay đổi như thế nào.
- Kết hợp PDF417 với các loại mã vạch khác trong cùng một tài liệu để tạo giải pháp quét đa chế độ.
- Khám phá [tài liệu chính thức của Aspose](https://docs.aspose.com/barcode/net/) để biết các tính năng nâng cao như macro PDF417 hoặc chế độ compact.

Nếu gặp bất kỳ khó khăn nào, hãy để lại bình luận, hoặc chia sẻ kết quả quét của bạn. Chúc bạn tạo mã vạch vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Tạo Mã Vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã vạch Aztec với sửa lỗi trong .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Cách Tạo Mã Vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}