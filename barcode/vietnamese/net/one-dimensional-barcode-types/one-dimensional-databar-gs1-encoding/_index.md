---
title: Mã hóa GS1 thanh dữ liệu một chiều
linktitle: Mã hóa GS1 thanh dữ liệu một chiều
second_title: API Aspose.BarCode .NET
description: Tìm hiểu cách tạo mã vạch được mã hóa Databar GS1 trong .NET bằng Aspose.BarCode. Tạo mã vạch một cách dễ dàng. Thực hiện theo hướng dẫn từng bước của chúng tôi.
weight: 18
url: /vi/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mã hóa GS1 thanh dữ liệu một chiều


Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo mã vạch mã hóa Databar GS1 một chiều bằng thư viện Aspose.BarCode cho .NET. Cho dù bạn đang tìm cách tạo mã vạch có hoặc không có mã hóa GS1, chúng tôi đều sẵn sàng hỗ trợ bạn. Hướng dẫn từng bước này sẽ giúp bạn hiểu các điều kiện tiên quyết, nhập vùng tên và trình bày từng ví dụ để tạo mã vạch mã hóa Databar GS1 một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.BarCode for .NET: Bạn nên cài đặt Aspose.BarCode for .NET. Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/barcode/net/).

2.  Đường dẫn thư mục của bạn: Thay thế`"Your Directory Path"` trong các ví dụ mã có đường dẫn thực tế nơi bạn muốn lưu hình ảnh mã vạch được tạo.

Bây giờ bạn đã có sẵn các điều kiện tiên quyết cần thiết, hãy chuyển sang phần viết mã.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên có liên quan cho Aspose.BarCode. Thêm các dòng mã sau vào đầu dự án .NET của bạn:

```csharp
using Aspose.BarCode;
using System;
```

## Bước 1: Khởi tạo Trình tạo mã vạch

Bước đầu tiên là khởi tạo đối tượng BarcodeGenerator với kiểu mã hóa mong muốn. Trong trường hợp này, chúng tôi đang sử dụng mã hóa mở rộng Databar. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Bước 2: Tạo mã vạch bằng mã hóa GS1

Bây giờ, chúng ta sẽ thiết lập văn bản mã bằng tính năng kiểm tra GS1Encoding và lưu hình ảnh mã vạch đã tạo. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Bước 3: Tạo mã vạch mã hóa biến đổi

Trong bước này, chúng tôi sẽ tạo mã vạch có văn bản mã thay đổi mà không cần kiểm tra Mã hóa GS1.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Bước 4: Xử lý ngoại lệ khi kiểm tra mã hóa GS1

Nếu bạn cố gắng tạo mã vạch có văn bản mã thay đổi và bật tính năng kiểm tra Mã hóa GS1, nó sẽ đưa ra một ngoại lệ. Đây là cách bạn có thể xử lý nó:

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

Bây giờ bạn đã tạo thành công mã vạch mã hóa Databar GS1 một chiều bằng Aspose.BarCode for .NET. Bạn có thể khám phá thêm và tùy chỉnh việc tạo mã vạch dựa trên các yêu cầu cụ thể của mình.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày quy trình tạo mã vạch được mã hóa Databar GS1 một chiều bằng Aspose.BarCode cho .NET. Chúng tôi đã thảo luận về các điều kiện tiên quyết, nhập các không gian tên cần thiết và cung cấp hướng dẫn từng bước để tạo cả mã vạch GS1 và mã hóa biến đổi.

 Với Aspose.BarCode cho .NET, việc tạo mã vạch trở thành một nhiệm vụ liền mạch, mang lại sự linh hoạt và khả năng kiểm soát nhu cầu tạo mã vạch của bạn. Nếu bạn gặp bất kỳ vấn đề hoặc có thắc mắc, đừng ngần ngại truy cập[Tài liệu Aspose.BarCode](https://reference.aspose.com/barcode/net/) hoặc tìm kiếm sự giúp đỡ trên[Diễn đàn hỗ trợ Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Các câu hỏi thường gặp

### 1. Mã GS1 trong mã vạch là gì?
Mã hóa GS1 là một tiêu chuẩn được sử dụng trong mã vạch để đảm bảo cấu trúc dữ liệu và nhận dạng phù hợp. Nó thường được sử dụng cho các mặt hàng trong lĩnh vực bán lẻ, chăm sóc sức khỏe và hậu cần để tạo điều kiện thuận lợi cho việc theo dõi và trao đổi thông tin chính xác.

### 2. Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Có, bạn có thể tùy chỉnh giao diện của mã vạch được tạo bằng Aspose.BarCode cho .NET. Bạn có quyền kiểm soát các thông số khác nhau như kích thước, màu sắc và kiểu dáng.

### 3. Tôi có thể tìm thêm tài nguyên và tài liệu cho Aspose.BarCode ở đâu?
 Bạn có thể tìm thấy tài liệu và ví dụ toàn diện tại[Tài liệu Aspose.BarCode](https://reference.aspose.com/barcode/net/). Đó là một nguồn tài nguyên có giá trị cho việc học tập và khắc phục sự cố.

### 4. Có phiên bản dùng thử cho Aspose.BarCode không?
 Có, bạn có thể tải phiên bản dùng thử miễn phí của Aspose.BarCode cho .NET từ[đây](https://releases.aspose.com/).

### 5. Làm cách nào tôi có thể mua giấy phép Aspose.BarCode cho .NET?
 Để mua giấy phép cho Aspose.BarCode cho .NET, hãy truy cập[trang mua hàng](https://purchase.aspose.com/buy) trên trang web Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
