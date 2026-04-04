---
date: 2026-01-15
description: Hướng dẫn từng bước về mã vạch để đọc mã DataMatrix bằng C# và tạo hình
  ảnh mã vạch bằng C# sử dụng Aspose.BarCode cho .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Đọc mã vạch DataMatrix C# – Chế độ tạo DataMatrix (Tự động)
url: /vi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc mã vạch DataMatrix C# – Tạo chế độ DataMatrix (Auto)

Trong thế giới số ngày nay phát triển nhanh chóng, khả năng **đọc mã vạch DataMatrix C#** một cách nhanh chóng và đáng tin cậy là điều cần thiết cho mọi thứ từ theo dõi tồn kho đến xử lý tài liệu an toàn. Hướng dẫn này sẽ chỉ cho bạn cách tạo mã vạch DataMatrix ở chế độ *Auto* bằng Aspose.BarCode cho .NET và sau đó cho thấy cách đọc lại mã vạch đó trong C#. Dù bạn đang theo dõi một **hướng dẫn tutorial barcode** hay chỉ cần một ví dụ mã nguồn chắc chắn, bạn sẽ hoàn thành hướng dẫn này với một giải pháp hoạt động sẵn có thể đưa vào dự án của mình.

## Trả lời nhanh
- **Chế độ “Auto” làm gì?** Nó cho phép Aspose.BarCode tự động chọn phương án mã hoá tốt nhất cho dữ liệu của bạn.  
- **Thư viện nào cần thiết?** Aspose.BarCode cho .NET (có bản dùng thử miễn phí).  
- **Có thể đọc mã vạch trong cùng một ứng dụng không?** Có – dùng `BarCodeReader` với `DecodeType.DataMatrix`.  
- **Cần giấy phép cho môi trường production không?** Cần giấy phép thương mại cho việc sử dụng trong sản phẩm.  
- **Các phiên bản .NET được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## DataMatrix barcode C# là gì?
Đọc mã vạch DataMatrix trong C# có nghĩa là giải mã ma trận hai chiều gồm các mô-đun đen và trắng trở lại thành văn bản hoặc dữ liệu gốc. Aspose.BarCode cung cấp một API đơn giản, trừu tượng hoá việc xử lý ảnh mức thấp, cho phép bạn tập trung vào logic nghiệp vụ.

## Tại sao nên dùng Aspose.BarCode để tạo ảnh mã vạch C#?
- **Độ tin cậy:** Hỗ trợ tất cả các tiêu chuẩn DataMatrix và tự động chọn phương án mã hoá tối ưu.  
- **Linh hoạt:** Kiểm soát toàn bộ kích thước, mã hoá ECI và định dạng ảnh.  
- **Đa nền tảng:** Hoạt động với .NET Framework, .NET Core và các ứng dụng .NET 5+.  

## Yêu cầu trước

1. **Môi trường .NET** – Cài đặt runtime .NET mới nhất từ [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode cho .NET** – Tải thư viện từ [website](https://releases.aspose.com/barcode/net/).  

## Nhập các namespace

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Bây giờ các namespace đã sẵn sàng, chúng ta sẽ đi qua mã nguồn từng bước.

## Bước 1: Đặt đường dẫn thư mục

```csharp
string path = "Your Directory Path";
```

Thay `"Your Directory Path"` bằng thư mục mà bạn muốn lưu PNG (hoặc định dạng khác) đã tạo.

## Bước 2: Tạo mã vạch DataMatrix ở chế độ Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Cài đặt `DataMatrixEncodeMode.Auto` cho phép thư viện quyết định phương án mã hoá tốt nhất cho văn bản được cung cấp. Bạn có thể thay thế văn bản mẫu bằng bất kỳ chuỗi nào cần **tạo ảnh mã vạch C#**.

## Bước 3: Đọc mã vạch (đọc DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Đoạn mã này giải mã ảnh vừa tạo và in ra văn bản gốc trên console, minh họa một vòng tròn đầy đủ từ tạo đến đọc.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Không phát hiện được mã vạch** | Độ phân giải ảnh quá thấp | Tăng `XDimension.Pixels` (ví dụ: lên 6) |
| **Ký tự rác** | Mã hoá ECI sai | Đặt `ECIEncoding` phù hợp với dữ liệu (UTF‑8, ASCII, …) |
| **Ngoại lệ khi gọi `ReadBarCodes`** | Bitmap bị giải phóng trước khi đọc | Giữ lại instance `Bitmap` cho đến khi đọc xong |

## Câu hỏi thường gặp

**H: Chế độ mã hoá DataMatrix “Auto” là gì?**  
Đ: Nó cho phép Aspose.BarCode tự động chọn phương pháp mã hoá tối ưu cho dữ liệu được cung cấp, đơn giản hoá quy trình **cách tạo mã vạch datamatrix**.

**H: Tôi có thể tùy chỉnh kích thước của mã vạch được tạo không?**  
Đ: Có – điều chỉnh `generator.Parameters.Barcode.XDimension.Pixels` để thay đổi kích thước mô-đun.

**H: Aspose.BarCode cho .NET có phù hợp cho mục đích thương mại không?**  
Đ: Hoàn toàn phù hợp. Mua giấy phép tại [website](https://purchase.aspose.com/buy).

**H: Có bản dùng thử miễn phí không?**  
Đ: Có, bạn có thể khám phá Aspose.BarCode với bản dùng thử miễn phí từ [liên kết này](https://releases.aspose.com/).

**H: Các tùy chọn mã hoá nào có sẵn cho mã vạch DataMatrix?**  
Đ: Aspose.BarCode hỗ trợ UTF‑8, ASCII và các mã hoá ECI khác; đặt giá trị mong muốn qua `ECIEncoding`.

## Kết luận

Bạn đã có một ví dụ hoàn chỉnh, sẵn sàng cho môi trường production, có thể **đọc DataMatrix barcode C#**, tạo mã vạch ở chế độ Auto và xác thực kết quả – tất cả đều sử dụng Aspose.BarCode cho .NET. Hãy thử nghiệm với các văn bản, kích thước và cài đặt ECI khác nhau để phù hợp với kịch bản của bạn, và tham khảo [tài liệu chính thức](https://reference.aspose.com/barcode/net/) để tùy chỉnh sâu hơn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-15  
**Đã kiểm tra với:** Aspose.BarCode 24.12 cho .NET  
**Tác giả:** Aspose  

---