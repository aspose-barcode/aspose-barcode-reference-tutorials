---
date: 2026-03-07
description: Tìm hiểu cách tạo mã vạch EAN‑13 với dữ liệu bổ sung trong C# bằng Aspose.BarCode
  cho .NET – nhanh chóng tạo mã vạch PNG.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Tạo mã vạch EAN-13 với dữ liệu bổ sung – Aspose.BarCode
url: /vi/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã vạch EAN-13 với Dữ liệu Bổ sung – Aspose.BarCode cho .NET

Trong tutorial thực hành này, bạn sẽ **tạo mã vạch EAN-13** có bao gồm dữ liệu bổ sung EAN‑2 hoặc EAN‑5, và bạn sẽ thấy cách **tạo file PNG cho mã vạch** chỉ với vài dòng C#. Dù bạn đang xây dựng hệ thống thanh toán bán lẻ, ứng dụng logistics, hay công cụ quản lý tồn kho đơn giản, khả năng thêm thông tin bổ sung sẽ làm cho mã vạch của bạn trở nên hữu ích hơn nhiều.

## Trả lời nhanh
- **“Dữ liệu bổ sung” có nghĩa là gì?** Các chữ số bổ sung (EAN‑2/EAN‑5) được in bên cạnh mã vạch chính, thường dùng để ghi giá hoặc số phát hành.  
- **Loại mã vạch nào được sử dụng?** EAN‑13 là ký hiệu chính, kèm theo tùy chọn bổ sung EAN‑2 hoặc EAN‑5.  
- **Tôi có thể xuất ra ảnh PNG không?** Có – phương thức `Save` cho phép xuất trực tiếp sang PNG.  
- **Tôi có cần giấy phép để phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần cho môi trường sản xuất.  
- **Có tương thích với .NET Core / .NET 6 không?** Hoàn toàn – Aspose.BarCode hỗ trợ tất cả các runtime .NET hiện đại.

## Yêu cầu trước

Trước khi bắt đầu viết code, hãy chắc chắn rằng bạn đã có:

- Visual Studio (hoặc bất kỳ IDE nào hỗ trợ .NET).  
- Một bản sao Aspose.BarCode cho .NET – tải **[tại đây](https://releases.aspose.com/barcode/net/)**.  
- Kiến thức cơ bản về C#.  
- Một thư mục có quyền ghi để lưu các file PNG được tạo.

## Nhập các namespace

Đầu tiên, thêm namespace Aspose.BarCode để bạn có thể truy cập các lớp tạo mã vạch:

```csharp
using Aspose.BarCode.Generation;
```

> **Mẹo chuyên nghiệp:** Nếu bạn đang dùng .NET Core, hãy thêm package NuGet `Aspose.BarCode` vào dự án thay vì tham chiếu DLL thủ công.

## Mã vạch bổ sung là gì?

Mã vạch bổ sung là một chuỗi số phụ được in cạnh mã vạch chính.  
- **EAN‑2** – bổ sung hai chữ số, thường dùng cho số phát hành trên tạp chí.  
- **EAN‑5** – bổ sung năm chữ số, thường dùng cho phần mở rộng giá trên mặt hàng bán lẻ.

Việc thêm các bổ sung này không thay đổi dữ liệu EAN‑13 chính; chúng chỉ cung cấp ngữ cảnh bổ sung mà máy quét có thể đọc.

## Tại sao nên dùng Aspose.BarCode cho dữ liệu bổ sung?

- **API một dòng** – cấu hình cả mã vạch chính và bổ sung trong một đối tượng duy nhất.  
- **Kiểm soát đầy đủ kích thước** – điều chỉnh X‑dimension, khoảng cách bổ sung và định dạng ảnh.  
- **Đa nền tảng** – hoạt động trên .NET Framework, .NET Core và .NET 5/6+.  

## Hướng dẫn từng bước

### Bước 1: Thiết lập thư mục đầu ra

Xác định nơi sẽ lưu các file PNG. Thay thế placeholder bằng đường dẫn thực tế trên máy của bạn.

```csharp
string path = "Your Directory Path";
```

### Bước 2: Khởi tạo Barcode Generator (Barcode Generator C#)

Tạo một thể hiện `BarcodeGenerator`, chỉ định **EAN‑13** làm loại chính và cung cấp dữ liệu 13 chữ số.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Bước 3: Điều chỉnh kích thước mã vạch

Tinh chỉnh kích thước hiển thị của mã vạch và không gian dành cho phần bổ sung.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Bước 4: Thêm bổ sung EAN‑2

Đặt dữ liệu bổ sung thành giá trị hai chữ số (ví dụ, “12”). Giá trị này sẽ xuất hiện ở phía bên phải của mã vạch chính.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Bước 5: Lưu mã vạch EAN‑2 dưới dạng PNG

Xuất ảnh. Tham số `BarCodeImageFormat.Png` đảm bảo file PNG chất lượng cao.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Bước 6: Chuyển sang bổ sung EAN‑5

Thay đổi `SupplementData` thành chuỗi năm chữ số cho phần mở rộng giá.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Bước 7: Lưu mã vạch EAN‑5 dưới dạng PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Tại sao cách này hoạt động:** Cùng một thể hiện `BarcodeGenerator` được tái sử dụng, vì vậy bạn chỉ cần thay đổi thuộc tính `SupplementData` trước mỗi lần gọi `Save`. Điều này giúp code gọn gàng và tránh việc tạo đối tượng không cần thiết.

## Các vấn đề thường gặp & Mẹo

- **Đường dẫn thư mục không hợp lệ** – đảm bảo thư mục tồn tại và ứng dụng có quyền ghi.  
- **Độ dài bổ sung không đúng** – EAN‑2 yêu cầu đúng 2 chữ số, EAN‑5 yêu cầu 5; nếu không sẽ ném ngoại lệ.  
- **Ảnh không hiển thị** – xác nhận rằng đã dùng `BarCodeImageFormat.Png`; các định dạng khác (ví dụ, JPEG) có thể gây ra hiện tượng nén làm giảm khả năng đọc của máy quét.  

## Câu hỏi thường gặp

### Tôi có thể dùng Aspose.BarCode cho .NET trong dự án .NET Core không?
Có, Aspose.BarCode cho .NET hoàn toàn tương thích với .NET Core, .NET 5 và .NET 6.

### Có bản dùng thử miễn phí cho Aspose.BarCode cho .NET không?
Có, bạn có thể thử miễn phí bằng cách truy cập **[liên kết này](https://releases.aspose.com/)**.

### Tôi có thể lấy giấy phép tạm thời cho Aspose.BarCode cho .NET ở đâu?
Bạn có thể nhận giấy phép tạm thời từ **[liên kết này](https://purchase.aspose.com/temporary-license/)**.

### Aspose.BarCode có hỗ trợ nhiều loại mã vạch không?
Chắc chắn – nó hỗ trợ EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 và nhiều loại khác.

### Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Có, bạn có thể thay đổi màu sắc, phông chữ, lề và thậm chí thêm ảnh nền bằng API `Parameters` phong phú.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch EAN-13** với dữ liệu bổ sung EAN‑2 hoặc EAN‑5 và **tạo file PNG cho mã vạch** bằng Aspose.BarCode cho .NET. Cách tiếp cận này cho phép bạn kiểm soát toàn diện kích thước mã vạch, khoảng cách bổ sung và định dạng đầu ra, rất phù hợp cho bán lẻ, logistics và bất kỳ trường hợp nào cần thông tin số bổ sung.

Để khám phá sâu hơn, hãy xem hướng dẫn tham chiếu đầy đủ: **[tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/)**.

---

**Cập nhật lần cuối:** 2026-03-07  
**Đã kiểm tra với:** Aspose.BarCode 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}