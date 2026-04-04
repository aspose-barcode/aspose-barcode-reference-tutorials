---
date: 2026-02-25
description: Học cách tạo hình ảnh mã vạch bằng Aspose.BarCode cho .NET. Hướng dẫn
  từng bước này cho thấy cách tạo mã vạch Code 39 có và không có checksum.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Cách tạo mã vạch – Cấu hình Code 39 với Aspose.BarCode
url: /vi/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cấu hình Code 39 một chiều

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách tạo hình ảnh mã vạch**, cụ thể là các mã vạch Code 39 một chiều, bằng Aspose.BarCode cho .NET. Mã vạch đóng một vai trò quan trọng trong các doanh nghiệp hiện đại, từ việc theo dõi tồn kho đến việc cho phép truy xuất dữ liệu nhanh chóng và chính xác. Aspose.BarCode cho .NET là một thư viện mạnh mẽ giúp đơn giản hoá việc tạo và tùy chỉnh mã vạch trong các ứng dụng .NET. Hướng dẫn từng bước này chia quá trình thành các phần dễ hiểu, đảm bảo ngay cả những nhà phát triển mới với việc tạo mã vạch cũng có thể theo dõi.

## Câu trả lời nhanh
- **Thư viện chính là gì?** Aspose.BarCode cho .NET  
- **Tôi có thể tạo mã vạch có checksum không?** Có – đặt `IsChecksumEnabled = EnableChecksum.Yes`  
- **Checksum có bắt buộc không?** Không – bạn có thể tạo mã vạch mà không có checksum bằng cách tắt nó  
- **Định dạng ảnh nào được sử dụng trong các ví dụ?** PNG (`BarCodeImageFormat.Png`)  
- **Tôi có cần giấy phép cho việc phát triển không?** Một giấy phép tạm thời có sẵn để đánh giá  

## Tạo mã vạch với Aspose.BarCode là gì?
Tạo mã vạch là quá trình chuyển đổi văn bản hoặc dữ liệu số thành một mẫu hình ảnh có thể đọc được bằng máy. Aspose.BarCode cho .NET hỗ trợ hàng chục loại symbology, bao gồm Code 39, và cho phép bạn kiểm soát mọi thứ từ kích thước, màu sắc đến việc tính toán checksum.

## Tại sao sử dụng Code 39 và các tùy chọn checksum?
Code 39 được áp dụng rộng rãi trong logistics và sản xuất vì nó mã hoá dữ liệu alphanumeric mà không cần ký tự đặc biệt. Thêm checksum (hoặc không) cho phép bạn cân bằng giữa phát hiện lỗi và tính đơn giản—hoàn hảo cho nhãn kho, nhãn vận chuyển, hoặc các hệ thống bán hàng đơn giản.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn đã có:

1. **Môi trường phát triển .NET** – kiến thức cơ bản về .NET framework và một IDE như Visual Studio. Nếu bạn mới với .NET, hãy bắt đầu với tài liệu chính thức: [Tài liệu Microsoft .NET](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode cho .NET** – tải về và cài đặt thư viện. Tài liệu và bản tải về có sẵn tại đây: [Tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/) và [Tải Aspose.BarCode cho .NET](https://releases.aspose.com/barcode/net/).

Bây giờ chúng ta đã hoàn thành các yêu cầu trước, hãy chuyển sang các bước chính để tạo mã vạch Code 39 một chiều.

## Cách tạo mã vạch: Nhập không gian tên
Để bắt đầu làm việc với Aspose.BarCode cho .NET, nhập các không gian tên cần thiết vào dự án của bạn. Thêm các câu lệnh `using` này sẽ cho phép bạn truy cập các lớp tạo mã vạch.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Cách tạo mã vạch Code 39 (có và không có checksum)

Dưới đây chúng ta sẽ tạo hai mã vạch: một **không có checksum** và một **có checksum**. Mã nguồn giống hệt nhau ngoại trừ cờ `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**Những gì mã thực hiện**

1. **Instantiate** `BarcodeGenerator` với `EncodeTypes.Code39Extended` và chuỗi dữ liệu `"CODE"`.  
2. **Toggle** `IsChecksumEnabled` để kiểm soát việc có hay không một chữ số checksum được thêm vào.  
3. **Save** mỗi mã vạch dưới dạng tệp PNG vào thư mục đã chỉ định.

Bạn giờ đã có hai hình ảnh mã vạch sẵn sàng sử dụng: `OneCSCode39WithoutChecksum.png` và `OneCSCode39WithChecksum.png`.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Đường dẫn tệp không tồn tại** | Biến `path` trỏ tới thư mục không tồn tại. | Đảm bảo thư mục tồn tại hoặc sử dụng `Directory.CreateDirectory(path)`. |
| **Ký tự không hợp lệ trong dữ liệu** | Code 39 chỉ hỗ trợ các ký tự chữ và số và một vài ký tự đặc biệt. | Sử dụng Code 39 mở rộng (`Code39Extended`) hỗ trợ toàn bộ bộ ASCII, như đã trình bày ở trên. |
| **Lỗi checksum** | Quên thiết lập `IsChecksumEnabled` khi cần. | Thiết lập rõ ràng cờ thành `EnableChecksum.Yes` hoặc `No` tùy trường hợp. |

## Câu hỏi thường gặp (FAQs):

### Q: Tôi có thể sử dụng Aspose.BarCode cho .NET với các ngôn ngữ lập trình khác không?
A: Aspose.BarCode chủ yếu được thiết kế cho .NET, nhưng Aspose cũng cung cấp các thư viện mã vạch cho các nền tảng khác.

### Q: Có các tùy chọn cấp phép nào cho Aspose.BarCode cho .NET không?
A: Có, bạn có thể khám phá các tùy chọn cấp phép và yêu cầu giấy phép tạm thời trên trang web của Aspose: [Cấp phép Aspose.BarCode](https://purchase.aspose.com/temporary-license/).

### Q: Aspose.BarCode cho .NET có phù hợp với các ứng dụng web không?
A: Có, Aspose.BarCode cho .NET có thể được sử dụng trong các ứng dụng web, phù hợp với nhiều dự án phát triển khác nhau.

### Q: Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
A: Chắc chắn, bạn có thể tùy chỉnh nhiều khía cạnh của mã vạch, bao gồm kích thước, màu sắc và phông chữ.

### Q: Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi về Aspose.BarCode cho .NET ở đâu?
A: Bạn có thể tìm câu trả lời và nhận hỗ trợ trên diễn đàn Aspose.BarCode: [Diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Các câu hỏi thường gặp bổ sung

**Q: Sự khác nhau giữa mã vạch có checksum và không có checksum là gì?**  
A: Checksum thêm một chữ số phụ giúp phát hiện lỗi nhập liệu. Sử dụng nó khi tính toàn vẹn dữ liệu là quan trọng.

**Q: Kích thước PNG tạo ra có thể lớn bao nhiêu?**  
A: Kích thước được kiểm soát qua `gen.Parameters.ImageWidth/Height`. Điều chỉnh các thuộc tính này trước khi gọi `Save`.

**Q: Tôi có thể tạo mã vạch ở các định dạng ảnh khác không?**  
A: Có, Aspose.BarCode hỗ trợ JPEG, BMP, GIF, TIFF và nhiều định dạng khác—chỉ cần thay đổi enum `BarCodeImageFormat`.

**Q: Có cách nào tạo mã vạch trong ứng dụng web mà không ghi vào đĩa không?**  
A: Bạn có thể lưu vào một `MemoryStream` và trả về mảng byte trực tiếp cho client.

## Kết luận
Bằng cách làm theo các bước đơn giản này, bạn có thể **tạo hình ảnh mã vạch** trong .NET với khả năng kiểm soát đầy đủ checksum, định dạng ảnh và kiểu dáng trực quan. Dù bạn đang quản lý tồn kho, xử lý đơn hàng, hay xây dựng một cổng thông tin web hỗ trợ mã vạch, Aspose.BarCode cho .NET cung cấp giải pháp đáng tin cậy và thân thiện với nhà phát triển.

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 cho .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}