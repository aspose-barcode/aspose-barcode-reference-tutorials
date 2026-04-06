---
date: 2026-03-07
description: Tìm hiểu cách tạo mã vạch databar một chiều được mã hoá GS1 trong .NET
  bằng Aspose.BarCode. Hướng dẫn này chỉ ra cách thiết lập GS1, cấu hình trình tạo
  mã vạch và tạo mã vạch nhanh chóng.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Tạo mã Databar một chiều GS1 với Aspose.BarCode
url: /vi/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Databar Một Chiều GS1 với Aspose.BarCode

Trong hướng dẫn này, bạn sẽ **tạo mã vạch databar một chiều** tuân theo tiêu chuẩn GS1, sử dụng thư viện Aspose.BarCode cho .NET. Dù bạn cần kiểm tra GS1 nghiêm ngặt hay một mã vạch linh hoạt hơn, chúng tôi sẽ hướng dẫn từng bước—từ cài đặt thư viện đến xử lý ngoại lệ mã hoá—để bạn có thể tạo mã vạch đáng tin cậy trong các ứng dụng của mình.

## Câu trả lời nhanh
- **“tạo mã databar một chiều” có nghĩa là gì?** Nó có nghĩa là tạo một mã vạch tuyến tính (1‑D) thuộc họ Databar, thường được dùng trong bán lẻ và logistics.  
- **Làm sao để thiết lập kiểm tra GS1?** Đặt `IsAllowOnlyGS1Encoding` thành `true` trên các tham số `DataBar`.  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; cần giấy phép thương mại cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Tải thư viện ở đâu?** Từ trang phát hành chính thức của Aspose (xem phần yêu cầu trước).

## “tạo mã databar một chiều” là gì?
Databar một chiều (còn gọi là RSS) là một mã vạch tuyến tính gọn nhẹ có thể mã hoá dữ liệu số, ngày tháng hoặc chuỗi AI (Application Identifier). Khi kết hợp với mã hoá GS1, mã vạch tuân theo cấu trúc dữ liệu được công nhận toàn cầu, rất phù hợp cho bán lẻ, y tế và chuỗi cung ứng.

## Tại sao nên dùng Aspose.BarCode cho .NET?
Aspose.BarCode cung cấp API mượt mà, hỗ trợ đầy đủ GS1 và khả năng tinh chỉnh mọi khía cạnh hình ảnh của mã vạch. Nó loại bỏ việc phải tự mình xử lý mã hoá cấp thấp, cho phép bạn tập trung vào logic nghiệp vụ.

## Yêu cầu trước

1. **Aspose.BarCode cho .NET** – tải và cài đặt từ [đây](https://releases.aspose.com/barcode/net/).  
2. **Đường dẫn thư mục của bạn** – thay thế `"Your Directory Path"` trong các mẫu bằng thư mục mà bạn có quyền ghi.

## Nhập không gian tên

Thêm các câu lệnh `using` cần thiết ở đầu file C# của bạn:

```csharp
using Aspose.BarCode;
using System;
```

## Bước 1: Khởi tạo Barcode Generator

Tạo một thể hiện `BarcodeGenerator` và chỉ định ký hiệu Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Bước 2: Cách thiết lập GS1 – Tạo mã vạch với kiểm tra GS1 nghiêm ngặt

Bật mã hoá chỉ GS1, gán codetext tuân theo GS1 và lưu ảnh:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Bước 3: Tạo mã vạch với Aspose – Mã hoá biến (không kiểm tra GS1)

Nếu bạn cần một mã vạch **không** áp dụng quy tắc GS1, tắt kiểm tra:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Bước 4: Kiểm tra GS1 của Barcode generator – Xử lý ngoại lệ

Khi `IsAllowOnlyGS1Encoding` được đặt `true` nhưng codetext không tuân GS1, Aspose sẽ ném ngoại lệ. Mẫu dưới đây cho thấy cách bắt và ghi log:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Những lỗi thường gặp & Mẹo
- **Lỗi:** Cung cấp chuỗi không phải GS1 trong khi kiểm tra GS1 được bật sẽ làm dừng việc tạo mã vạch.  
- **Mẹo chuyên nghiệp:** Kiểm tra chuỗi AI trước khi gán cho `CodeText` để tránh lỗi thời gian chạy.  
- **Mẹo:** Sử dụng đường dẫn tuyệt đối hoặc `Path.Combine` để xây dựng tên file một cách an toàn trên mọi nền tảng.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã databar một chiều** với mã hoá GS1, cách bật/tắt kiểm tra GS1 và cách xử lý các ngoại lệ liên quan—tất cả đều sử dụng Aspose.BarCode cho .NET. Hãy khám phá các tùy chọn định dạng bổ sung như kích thước, màu sắc và lề qua đối tượng `Parameters.Barcode`.

Nếu gặp bất kỳ vấn đề nào, tài liệu chính thức và diễn đàn cộng đồng là những nguồn tài nguyên tuyệt vời:

- [Tài liệu Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Diễn đàn hỗ trợ Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Câu hỏi thường gặp

### 1. Mã hoá GS1 trong mã vạch là gì?
Mã hoá GS1 là cách chuẩn hoá cấu trúc dữ liệu (ví dụ: mã định danh sản phẩm) bên trong mã vạch, đảm bảo khả năng tương tác giữa các nhà bán lẻ, nhà sản xuất và nhà cung cấp logistics.

### 2. Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Có. Aspose.BarCode cho phép bạn điều chỉnh kích thước, màu sắc, lề và thậm chí thêm văn bản đọc được bằng mắt người thông qua cài đặt `Parameters.Barcode`.

### 3. Tôi có thể tìm tài liệu và ví dụ bổ sung cho Aspose.BarCode ở đâu?
Bạn có thể tìm tài liệu chi tiết và các ví dụ tại [Tài liệu Aspose.BarCode](https://reference.aspose.com/barcode/net/). Đây là nguồn tài nguyên quý giá để học và khắc phục sự cố.

### 4. Có phiên bản dùng thử cho Aspose.BarCode không?
Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.BarCode cho .NET từ [đây](https://releases.aspose.com/).

### 5. Làm sao để mua giấy phép cho Aspose.BarCode cho .NET?
Để mua giấy phép cho Aspose.BarCode cho .NET, hãy truy cập [trang mua hàng](https://purchase.aspose.com/buy) trên website của Aspose.

---

**Cập nhật lần cuối:** 2026-03-07  
**Đã kiểm tra với:** Aspose.BarCode 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}