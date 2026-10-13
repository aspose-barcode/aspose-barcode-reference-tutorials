---
date: 2026-09-28
description: Tìm hiểu cách tạo custom space cho barcode cho phiếu giảm giá GS1 bằng
  Aspose.BarCode cho .NET và tăng khả năng đọc barcode. Thực hiện theo hướng dẫn từng
  bước của chúng tôi.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Cấu hình không gian Coupon Supplement GS1
og_description: Tìm hiểu cách tạo custom space cho barcode cho phiếu giảm giá GS1
  bằng Aspose.BarCode cho .NET và tăng khả năng đọc barcode. Bao gồm mã mẫu và mẹo
  từng bước.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Tạo custom space cho barcode cho phụ lục phiếu giảm giá GS1 – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Cách tạo custom space cho barcode cho phụ lục phiếu giảm giá GS1
url: /vi/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cấu hình không gian bổ sung phiếu giảm giá GS1

## Câu trả lời nhanh
- **Không gian bổ sung kiểm soát gì?** Nó định nghĩa khu vực trống (tính bằng pixel) giữa dữ liệu phiếu giảm giá và phần còn lại của mã vạch.  
- **Loại mã vạch nào được sử dụng?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Tôi có thể thay đổi kích thước không gian không?** Có – đặt `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` thành bất kỳ giá trị nguyên nào.  
- **Tôi có cần giấy phép cho tính năng này không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các định dạng đầu ra nào được hỗ trợ?** PNG, JPEG, BMP, GIF, TIFF, và nhiều hơn nữa qua `BarCodeImageFormat`.

## Không gian bổ sung phiếu giảm giá GS1 là gì?
Không gian bổ sung phiếu giảm giá GS1 là một vùng trống được xác định xuất hiện trong mã vạch GS1‑Databar cho phiếu giảm giá. Các hệ thống bán lẻ sử dụng không gian này để cải thiện độ tin cậy khi quét và tuân thủ các tiêu chuẩn ngành yêu cầu lề tối thiểu quanh dữ liệu bổ sung.

## Tại sao cần cấu hình không gian bổ sung?
Không gian bổ sung trực tiếp **tăng khả năng đọc mã vạch** và giúp bạn đáp ứng các hướng dẫn nghiêm ngặt của nhà bán lẻ. Bằng cách thêm các pixel bổ sung, bạn giảm khả năng đọc sai trên máy quét độ phân giải thấp, đảm bảo quét nhất quán trên các kích thước nhãn khác nhau, và cung cấp sự linh hoạt về mặt hình ảnh để cân bằng mã vạch trong bố cục in.

## Yêu cầu trước

Trước khi chúng ta bắt đầu cấu hình Không gian bổ sung phiếu giảm giá GS1 với Aspose.BarCode cho .NET, hãy chắc chắn bạn đã có:

1. **Visual Studio** – IDE chính cho phát triển .NET.  
2. **Aspose.BarCode for .NET** – Tải thư viện từ [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework hoặc .NET 5+** – Cần có kiến thức về C# và môi trường .NET.

Bây giờ môi trường đã sẵn sàng, chúng ta chuyển sang phần thực hiện.

## Nhập không gian tên

```csharp
using Aspose.BarCode;
```

## Bước 1: xác định đường dẫn

Chọn một thư mục nơi các hình ảnh được tạo sẽ được lưu. Đường dẫn phải kết thúc bằng dấu phân cách thư mục thích hợp cho hệ điều hành của bạn.

```csharp
string path = "Your Directory Path";
```

## Bước 2: tạo cấu hình không gian bổ sung phiếu giảm giá GS1

Đoạn mã sau tạo một mã vạch, đặt kích thước X‑dimension và điều chỉnh không gian bổ sung.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

Trong ví dụ này chúng tôi:

1. **Tạo** một thể hiện `BarcodeGenerator` cho loại `UpcaGs1DatabarCoupon`.  
2. **Đặt** X‑dimension thành 2 pixel, xác định độ rộng thanh hẹp nhất.  
3. **Điều chỉnh** thuộc tính `SupplementSpace.Pixels` thành 30 px, tạo ảnh, sau đó lặp lại với 50 px.  

Bạn có thể thử nghiệm với các giá trị pixel khác để phù hợp với quy trình in của mình.

## Các vấn đề thường gặp & mẹo

- **Đường dẫn không hợp lệ** – Đảm bảo biến `path` kết thúc bằng dấu gạch chéo ngược (`\`) hoặc dấu gạch chéo xuôi (`/`) phù hợp với hệ điều hành của bạn.  
- **Quyền không đủ** – Chạy Visual Studio với quyền Administrator hoặc chọn thư mục mà ứng dụng có quyền ghi.  
- **Định dạng dữ liệu không đúng** – Chuỗi dữ liệu phải tuân theo cú pháp GS1 (`(8110)` biểu thị định danh bổ sung).  

## Tại sao điều này quan trọng đối với doanh nghiệp của bạn
Aspose.BarCode hỗ trợ **hơn 60 loại mã vạch** và có thể tạo hình ảnh lên tới **10.000 × 10.000 pixel** mà không gây cạn bộ nhớ. Đối với các triển khai bán lẻ quy mô lớn, điều này có nghĩa là bạn có thể tạo hàng loạt phiếu giảm giá GS1 độ phân giải cao trong chế độ batch trong khi thời gian xử lý mỗi hình ảnh dưới một giây trên phần cứng máy chủ tiêu chuẩn.

## Câu hỏi thường gặp

**Q: Mục đích của không gian bổ sung phiếu giảm giá GS1 trong mã vạch là gì?**  
A: Nó thêm một lề trống bắt buộc xung quanh dữ liệu bổ sung, cải thiện độ tin cậy của máy quét và đáp ứng các chiều rộng tối thiểu do nhà bán lẻ quy định.

**Q: Tôi có thể tùy chỉnh độ rộng của không gian bổ sung phiếu giảm giá GS1 bằng Aspose.BarCode cho .NET không?**  
A: Có, đặt `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` thành bất kỳ giá trị nguyên nào; thư viện sẽ áp dụng thay đổi ngay lập tức cho hình ảnh được tạo.

**Q: Tôi có thể tìm tài liệu và hỗ trợ bổ sung cho Aspose.BarCode cho .NET ở đâu?**  
A: Tham khảo [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) và truy cập [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) để được cộng đồng hỗ trợ.

**Q: Aspose.BarCode cho .NET có phù hợp cho cả người mới bắt đầu và nhà phát triển có kinh nghiệm không?**  
A: Chắc chắn. API cung cấp các phương thức đơn giản cho các tác vụ nhanh và các tùy chọn nâng cao cho việc tạo mã vạch tinh chỉnh.

**Q: Tôi có thể nhận giấy phép tạm thời cho Aspose.BarCode cho .NET để đánh giá các tính năng không?**  
A: Có, yêu cầu giấy phép dùng thử từ [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Kết luận

Bằng cách thực hiện các bước trên, bạn đã biết cách **tạo không gian tùy chỉnh cho mã vạch** cho Không gian bổ sung phiếu giảm giá GS1, một kỹ thuật then chốt để **tăng khả năng đọc mã vạch** và đáp ứng tiêu chuẩn bán lẻ. Hãy tích hợp mã vào các giải pháp quét hiện có, thử nghiệm với các giá trị pixel khác nhau, và khám phá các loại mã vạch khác do Aspose.BarCode cho .NET cung cấp.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Hướng dẫn liên quan

- [Tạo mã vạch Databar Aspose.BarCode bằng API .NET – Cấu hình Hàng & Cột](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Cách tạo mã DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn chi tiết](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}