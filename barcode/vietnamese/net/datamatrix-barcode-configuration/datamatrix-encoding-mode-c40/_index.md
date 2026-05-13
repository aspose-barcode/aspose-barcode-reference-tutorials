---
date: 2026-01-15
description: Tìm hiểu cách lưu tệp PNG khi sử dụng Chế độ Mã hóa DataMatrix (C40)
  với Aspose.BarCode cho .NET – một hướng dẫn mã vạch từng bước.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: Cách lưu PNG bằng DataMatrix C40 với Aspose.BarCode
url: /vi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chế độ Mã hoá DataMatrix (C40) Master với Aspose.BarCode cho .NET

## Giới thiệu

Nếu bạn đang tìm kiếm một hướng dẫn rõ ràng, thực tế về **cách lưu PNG** khi tạo mã vạch DataMatrix, bạn đã đến đúng nơi. Dù bạn đang xây dựng hệ thống quản lý tồn kho, công cụ tạo nhãn vận chuyển, hay bất kỳ giải pháp nào cần mã vạch mật độ cao, việc nắm vững chế độ mã hoá C40 sẽ mang lại hiệu quả về kích thước và biểu diễn dữ liệu đáng tin cậy. Trong tutorial này, chúng ta sẽ đi qua quy trình **quy trình tạo mã vạch từng bước**, từ các yêu cầu trước đến tệp PNG cuối cùng, sử dụng Aspose.BarCode cho .NET.

## Câu trả lời nhanh
- **“how to save png” đề cập đến gì?** Lưu mã vạch đã tạo dưới dạng tệp ảnh PNG.  
- **Chế độ mã hoá nào được đề cập?** DataMatrix C40 encoding.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép cần thiết cho môi trường sản xuất.  
- **Tôi có thể chạy trên .NET Core không?** Có, Aspose.BarCode hỗ trợ .NET Framework và .NET Core.  
- **Định dạng tệp nào được tạo?** PNG (Portable Network Graphics) image.

## Cách lưu PNG với mã hoá DataMatrix C40
Lưu mã vạch dưới dạng PNG là bước cuối cùng sau khi bạn đã cấu hình trình tạo. Phương thức `Save` nhận đường dẫn tệp, tên tệp mong muốn và định dạng ảnh (`BarCodeImageFormat.Png`). Điều này đảm bảo mã vạch được lưu ở định dạng không mất dữ liệu, hoạt động trên các trình duyệt, máy in và thiết bị di động.

## DataMatrix Encoding Mode (C40) là gì?
C40 là một bộ ký tự hiệu quả cho dữ liệu alphanumeric, cho phép bạn đóng gói nhiều thông tin hơn vào một biểu tượng DataMatrix nhỏ hơn. Nó đặc biệt hữu ích khi bạn cần mã hoá văn bản chứa chữ cái, số và một tập hợp hạn chế các ký tự đặc biệt.

## Tại sao nên sử dụng Aspose.BarCode cho .NET?
- **Kiểm soát đầy đủ** kích thước mã vạch, sửa lỗi và các chế độ mã hoá.  
- **Không phụ thuộc** – không cần dịch vụ bên ngoài.  
- **Hỗ trợ đa nền tảng** cho .NET Framework, .NET Core và .NET 5/6+.  

## Yêu cầu trước

Trước khi chúng ta bắt đầu với mã, hãy chắc chắn bạn có những thứ sau:

1. **Môi trường phát triển .NET** – Visual Studio, Rider hoặc bất kỳ IDE nào hỗ trợ C#.  
2. **Aspose.BarCode cho .NET** – được cài đặt qua NuGet hoặc trình cài đặt chính thức. Xem [documentation](https://reference.aspose.com/barcode/net/) để biết chi tiết.  
3. **Kiến thức C# cơ bản** – bạn nên quen thuộc với namespaces, classes và using statements.  
4. **Thư mục có quyền ghi** – một thư mục trên máy của bạn nơi PNG sẽ được lưu.

## Nhập các namespace cần thiết

Thêm namespace cần thiết ở đầu tệp nguồn C# của bạn để có thể truy cập các lớp tạo mã vạch:

```csharp
using Aspose.BarCode.Generation;
```

## Quy trình tạo mã vạch từng bước

Dưới đây là hướng dẫn **quy trình tạo mã vạch từng bước**. Mỗi bước được giải thích bằng ngôn ngữ đơn giản, và các khối mã gốc được giữ nguyên để tiện sao chép.

### Bước 1: Xác định đường dẫn thư mục
Đặt thư mục nơi ảnh PNG sẽ được lưu. Thay thế placeholder bằng đường dẫn thực tế trên máy của bạn.

```csharp
string path = "Your Directory Path";
```

### Bước 2: Thiết lập tạo mã vạch
Tạo một thể hiện `BarcodeGenerator`, chỉ định `EncodeTypes.DataMatrix`, và cung cấp dữ liệu bạn muốn mã hoá.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Bước 3: Tùy chỉnh mã vạch
Cấu hình X‑dimension (độ rộng pixel của các mô-đun) và chuyển chế độ mã hoá sang C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Bước 4: Lưu ảnh mã vạch
Cuối cùng, lưu mã vạch đã tạo dưới dạng tệp PNG. Đây là câu trả lời cụ thể cho **cách lưu png** với Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Khi bạn chạy chương trình, bạn sẽ thấy `DataMatrixEncodeModeC40.png` trong thư mục bạn đã chỉ định, sẵn sàng để sử dụng trong báo cáo, nhãn hoặc trang web.

## Vấn đề thường gặp & Mẹo

- **Đường dẫn không hợp lệ** – Đảm bảo thư mục tồn tại và bạn có quyền ghi; nếu không `gen.Save` sẽ ném ngoại lệ.  
- **Chế độ mã hoá không đúng** – Nếu bạn cần mã hoá các ký tự ngoài tập C40, chuyển sang `DataMatrixEncodeMode.Auto` hoặc chế độ phù hợp khác.  
- **Kích thước ảnh** – Điều chỉnh `XDimension.Pixels` để tăng hoặc giảm kích thước tổng thể của mã vạch mà không ảnh hưởng đến khả năng đọc.

## Câu hỏi thường gặp

**Q: DataMatrix Encoding Mode (C40) là gì?**  
A: C40 là một phương pháp mã hoá alphanumeric gọn nhẹ cho các ký hiệu DataMatrix, lý tưởng cho văn bản bao gồm chữ cái, số và một tập hợp hạn chế các ký tự đặc biệt.

**Q: Tôi có thể tìm tài liệu Aspose.BarCode cho .NET ở đâu?**  
A: Bạn có thể tìm tài liệu [tại đây](https://reference.aspose.com/barcode/net/). Nó cung cấp hướng dẫn chi tiết về tất cả các loại mã vạch và các tùy chọn mã hoá.

**Q: Aspose.BarCode cho .NET có tương thích với mọi phiên bản .NET không?**  
A: Có, thư viện hỗ trợ nhiều phiên bản .NET, từ .NET Framework 4.5+ đến .NET 6 và các phiên bản sau.

**Q: Tôi có thể dùng thử Aspose.BarCode cho .NET trước khi mua không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí của Aspose.BarCode cho .NET bằng cách truy cập [đây](https://releases.aspose.com/). Nó cho phép bạn thử nghiệm các tính năng và khả năng của thư viện.

**Q: Tôi có thể nhận hỗ trợ cho Aspose.BarCode cho .NET ở đâu?**  
A: Bạn có thể tìm cộng đồng hỗ trợ và truy cập hỗ trợ cho Aspose.BarCode cho .NET trên [diễn đàn Aspose](https://forum.aspose.com/c/barcode/13).

## Kết luận

Bằng cách làm theo hướng dẫn **quy trình tạo mã vạch từng bước** này, bạn giờ đã biết chính xác **cách lưu PNG** các tệp được tạo với mã hoá DataMatrix C40 bằng Aspose.BarCode cho .NET. Cách tiếp cận này cho phép bạn kiểm soát hoàn toàn giao diện, kích thước và cách biểu diễn dữ liệu của mã vạch, giúp dễ dàng tích hợp các mã vạch chất lượng cao vào bất kỳ ứng dụng .NET nào.

---

**Cập nhật lần cuối:** 2026-01-15  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}