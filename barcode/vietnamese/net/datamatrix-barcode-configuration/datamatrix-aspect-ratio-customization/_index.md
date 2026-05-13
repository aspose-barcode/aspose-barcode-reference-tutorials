---
date: 2026-01-12
description: Tìm hiểu cách tạo mã vạch PNG với tỷ lệ khung DataMatrix tùy chỉnh bằng
  Aspose.BarCode cho .NET. Hướng dẫn chi tiết từng bước về việc tạo mã vạch và tùy
  chỉnh kích thước.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Tạo mã vạch PNG – Tỷ lệ khung DataMatrix – Aspose.BarCode
url: /vi/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Barcode PNG – Tỷ lệ Khía cạnh DataMatrix – Aspose.BarCode

Việc **tạo barcode PNG** với tỷ lệ khía cạnh DataMatrix tùy chỉnh là một yêu cầu phổ biến khi bạn cần barcode vừa với các ràng buộc bố cục cụ thể. Trong hướng dẫn này, chúng tôi sẽ trình bày chi tiết các bước **tạo file barcode PNG** bằng Aspose.BarCode cho .NET, giải thích lý do bạn có thể muốn điều chỉnh tỷ lệ khía cạnh, và chỉ cho bạn cách tinh chỉnh đầu ra cho ứng dụng của mình.

## Trả lời nhanh
- **“Tỷ lệ khía cạnh” điều khiển gì?** Nó xác định tỉ lệ chiều rộng‑so‑với‑chiều cao của các mô-đun DataMatrix.  
- **Tôi có thể xuất PNG, JPEG, hoặc SVG không?** Có – phương thức `Save` hỗ trợ PNG, JPEG, BMP, GIF và nhiều định dạng khác.  
- **Tôi có cần giấy phép cho tính năng này không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Có bao nhiêu giá trị tỷ lệ‑khía‑cạnh hợp lệ?** Bất kỳ số thực dương nào; các giá trị thường gặp là 0.5 – 2.0.

## DataMatrix là gì và tại sao cần điều chỉnh tỷ lệ khía cạnh?
DataMatrix là một loại barcode ma trận 2‑chiều lưu trữ lượng dữ liệu lớn trong không gian nhỏ. Điều chỉnh **tỷ lệ khía cạnh** cho phép bạn kéo hoặc nén các mô-đun theo chiều ngang, hữu ích khi cần đặt barcode vào các cột hẹp hoặc nhãn rộng mà không làm giảm khả năng đọc.

## Yêu cầu trước

Trước khi bắt đầu tùy chỉnh tỷ lệ khía cạnh DataMatrix, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:

1. **Visual Studio** – bất kỳ phiên bản mới nào cũng được.  
2. **Aspose.BarCode cho .NET** – tải xuống [tại đây](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – dự án của bạn phải nhắm tới một phiên bản được hỗ trợ.

## Nhập không gian tên

Đầu tiên, bạn cần nhập không gian tên cần thiết trong dự án C# của mình:

```csharp
using Aspose.BarCode.Generation;
```

> **Mẹo:** Giữ câu lệnh `using` này ở đầu file để lớp `BarcodeGenerator` luôn sẵn sàng.

## Hướng dẫn từng bước

### Bước 1: Thiết lập dự án
Tạo một dự án console hoặc Windows Forms mới trong Visual Studio và thêm tham chiếu tới DLL Aspose.BarCode.

### Bước 2: Khởi tạo Barcode Generator
Tạo một đối tượng `BarcodeGenerator` với loại DataMatrix và dữ liệu bạn muốn mã hoá:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Dòng này tạo một generator sẵn sàng tạo barcode DataMatrix chứa văn bản mẫu.

### Bước 3: Tùy chỉnh tỷ lệ khía cạnh và lưu file PNG
Bây giờ bạn có thể thay đổi **tỷ lệ khía cạnh** và lưu mỗi phiên bản dưới dạng ảnh PNG:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Lệnh đầu tiên tạo một barcode có tỷ lệ vuông (`AspectRatio = 1`).  
- Lệnh thứ hai nén barcode theo chiều ngang (`AspectRatio = 0.5`), tạo ra hình dạng rộng hơn.

Bạn đã có hai file **barcode PNG** với các tỷ lệ khía cạnh khác nhau, sẵn sàng dùng trong báo cáo, nhãn hoặc các thành phần UI.

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Hình ảnh tạo ra mờ** | Tăng tham số `Resolution` trước khi lưu (`gen.Parameters.ImageResolution = 300`). |
| **Barcode không quét được** | Đảm bảo tỷ lệ khía cạnh nằm trong khoảng 0.5 – 2.0 và giữ đủ vùng yên lặng (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Lỗi đường dẫn file** | Sử dụng `Path.Combine` để xây dựng đường dẫn đầu ra và kiểm tra thư mục tồn tại. |

## Câu hỏi thường gặp

**H: Tôi có thể tùy chỉnh tỷ lệ khía cạnh của các loại barcode khác bằng Aspose.BarCode cho .NET không?**  
Đ: Có, nhiều barcode 2‑D (ví dụ QR, PDF417) hỗ trợ điều chỉnh tỷ lệ khía cạnh thông qua các đối tượng tham số riêng của chúng.

**H: Có bản dùng thử miễn phí cho Aspose.BarCode cho .NET không?**  
Đ: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.BarCode cho .NET [tại đây](https://releases.aspose.com/).

**H: Tôi có thể mua giấy phép cho Aspose.BarCode cho .NET ở đâu?**  
Đ: Bạn có thể mua giấy phép trên trang web Aspose [tại đây](https://purchase.aspose.com/buy).

**H: Aspose.BarCode cho .NET có tương thích với các phiên bản .NET Framework khác nhau không?**  
Đ: Có, nó hoạt động với .NET Framework 4.x, .NET Core 3.1+, và các phiên bản .NET mới nhất.

**H: Tôi có thể tạo barcode ở các định dạng khác nhau bằng Aspose.BarCode cho .NET không?**  
Đ: Chắc chắn – PNG, JPEG, BMP, GIF, TIFF, SVG và PDF đều được hỗ trợ ngay từ đầu.

## Kết luận

Việc tùy chỉnh **tỷ lệ khía cạnh** của barcode DataMatrix và **tạo barcode PNG** là rất đơn giản với Aspose.BarCode cho .NET. Bằng cách làm theo các bước trên, bạn có thể tạo ra các barcode có kích thước chính xác đáp ứng yêu cầu bố cục của dự án. Khám phá các tham số khác như `Resolution`, `Margin`, và `Color` để tinh chỉnh đầu ra hơn nữa.

Để tìm hiểu sâu hơn, hãy xem tài liệu chính thức [tại đây](https://reference.aspose.com/barcode/net/) hoặc tham gia cộng đồng trên [diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2026-01-12  
**Đã kiểm tra với:** Aspose.BarCode 24.12 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}