---
date: 2026-02-25
description: Tìm hiểu cách tạo hình ảnh mã vạch và lưu mã vạch dưới dạng PNG bằng
  Aspose.BarCode cho .NET – một ví dụ đầy đủ về Aspose Barcode.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Tạo hình ảnh mã vạch – Code 93 với Aspose.BarCode
url: /vi/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch – Mã một chiều Code 93 với Aspose.BarCode

## Giới thiệu

Trong thời đại số hiện nay, mã vạch đã trở thành một phần không thể thiếu trong cuộc sống của chúng ta, đơn giản hoá các quy trình như quản lý tồn kho, dán nhãn sản phẩm và theo dõi tại điểm bán. **Tạo hình ảnh mã vạch** thường là bước đầu tiên để tích hợp các định danh này vào ứng dụng của bạn. Aspose.BarCode for .NET cung cấp một API mạnh mẽ, dễ sử dụng, cho phép bạn tạo các mã vạch Code 93 chất lượng cao chỉ trong vài dòng code C#. Dù bạn đang xây dựng hệ thống kho, ứng dụng bán lẻ, hay công cụ báo cáo tùy chỉnh, hướng dẫn này sẽ dẫn bạn qua một **aspose barcode example** hoàn chỉnh, cho thấy cách tạo, tùy chỉnh và **lưu barcode PNG**.

## Câu trả lời nhanh
- **Nội dung hướng dẫn đề cập tới gì?** Tạo và lưu hình ảnh mã vạch Code 93 kèm xử lý checksum.  
- **Thư viện nào được sử dụng?** Aspose.BarCode for .NET (phiên bản ổn định mới nhất).  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; cần giấy phép thương mại cho môi trường sản xuất.  
- **Có thể thay đổi định dạng đầu ra không?** Có – bạn có thể lưu dưới dạng PNG, JPEG, BMP, v.v., bằng cách thay đổi `BarCodeImageFormat`.  
- **Yêu cầu tối thiểu là gì?** .NET Framework 4.6+ hoặc .NET Core 3.1+ và Visual Studio.

## Code 93 barcode là gì?
Code 93 là một ký hiệu alphanumeric mật độ cao, hỗ trợ toàn bộ bộ ký tự ASCII. Nó thường được chọn vì kích thước gọn gàng và có checksum tích hợp, giúp đảm bảo tính toàn vẹn dữ liệu khi quét.

## Tại sao nên tạo hình ảnh mã vạch với Aspose.BarCode?
- **Kiểm soát đầy đủ** loại mã hoá, checksum, kích thước và định dạng ảnh.  
- **Không phụ thuộc bên ngoài** – thư viện chạy trên bất kỳ nền tảng .NET nào.  
- **Chất lượng render xuất sắc**, phù hợp cho hiển thị trên màn hình và in ấn độ phân giải cao.  
- **Tài liệu đầy đủ** và một bộ lớn các ví dụ giúp tăng tốc quá trình phát triển.

## Yêu cầu trước

Trước khi bắt đầu viết code, hãy chắc chắn bạn đã có:

1. **Visual Studio** (bất kỳ phiên bản mới nào).  
2. **Aspose.BarCode for .NET** đã được cài đặt – bạn có thể tải từ trang tải về chính thức.  
3. Kiến thức cơ bản về **C#** và cấu trúc dự án .NET.

Sau khi đã sẵn sàng, chúng ta sẽ tiến hành theo các bước dưới đây.

## Nhập các namespace

Đầu tiên, nhập các namespace cần thiết để bạn có thể truy cập các lớp tạo mã vạch.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Bước 1: Đặt đường dẫn thư mục

Xác định nơi sẽ lưu hình ảnh mã vạch được tạo. Thay thế phần placeholder bằng một thư mục hợp lệ trên máy của bạn.

```csharp
string path = "Your Directory Path";
```

## Bước 2: Tạo mã vạch Code 93 một chiều

Khởi tạo một `BarcodeGenerator` với kiểu `Code93Extended` và dữ liệu bạn muốn mã hoá.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Bước 3: Bật Checksum (Tùy chọn)

Code 93 có checksum mặc định. Bạn có thể bật/tắt nó bằng thuộc tính `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Bước 4: Lưu hình ảnh mã vạch (Save Barcode PNG)

Tạo ảnh và lưu dưới dạng file PNG vào thư mục bạn đã chỉ định ở bước trước.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Bước 5: Xử lý ngoại lệ – Tạo mã vạch không có Checksum

Nếu bạn cần tạo mã vạch **không** có checksum, phải xử lý các ngoại lệ có thể phát sinh.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Các vấn đề thường gặp và giải pháp
- **Đường dẫn không hợp lệ** – đảm bảo thư mục tồn tại và ứng dụng có quyền ghi.  
- **Ký tự không được hỗ trợ** – Code 93 hỗ trợ toàn bộ bộ ASCII, nhưng các ký tự điều khiển có thể gây lỗi.  
- **Chưa đặt giấy phép** – nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark.

## Câu hỏi thường gặp (FAQs)

### Hỏi: Tôi có thể tìm tài liệu cho Aspose.BarCode for .NET ở đâu?
Đ: Bạn có thể tìm tài liệu tại [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Hỏi: Làm sao để tải Aspose.BarCode for .NET?
Đ: Bạn có thể tải Aspose.BarCode for .NET từ trang web tại [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Hỏi: Có bản dùng thử miễn phí cho Aspose.BarCode for .NET không?
Đ: Có, bạn có thể nhận bản dùng thử miễn phí của Aspose.BarCode for .NET từ [đây](https://releases.aspose.com/).

### Hỏi: Làm thế nào để mua giấy phép cho Aspose.BarCode for .NET?
Đ: Bạn có thể mua giấy phép tại trang mua hàng ở [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Hỏi: Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi về Aspose.BarCode for .NET ở đâu?
Đ: Bạn có thể tìm diễn đàn cộng đồng để được hỗ trợ và thảo luận tại [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2026-02-25  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}