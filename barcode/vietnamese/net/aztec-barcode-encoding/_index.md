---
date: 2026-05-19
description: Tìm hiểu cách tạo Aztec barcode bằng Aspose.BarCode cho .NET, tùy chỉnh
  aspect ratios, encode bytes hoặc text, và master symbol modes.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec Barcode Encoding
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cách tạo Aztec barcode với Aspose.BarCode cho .NET
url: /vi/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mã vạch Aztec

Bạn đã sẵn sàng khám phá thế giới Mã vạch Aztec và học cách **tạo hình ảnh mã vạch Aztec** với Aspose.BarCode cho .NET chưa? Thư viện này cho phép bạn kiểm soát hoàn toàn kích thước, sửa lỗi và cách biểu diễn dữ liệu, làm cho nó lý tưởng cho mọi thứ từ vé di động đến theo dõi tồn kho.

## Câu trả lời nhanh
- **Thư viện nào hỗ trợ mã vạch Aztec?** Aspose.BarCode for .NET  
- **Tôi có thể thay đổi tỷ lệ khung hình không?** Có, thông qua thuộc tính `AspectRatio`  
- **Có thể mã hoá ở mức byte không?** Chắc chắn – sử dụng phương thức `EncodeBytes`  
- **Các mức sửa lỗi nào có sẵn?** Các mức 0 đến 4 (cao hơn = nhiều dư thừa hơn)  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có, giấy phép thương mại loại bỏ giới hạn đánh giá  

## Mã vạch Aztec là gì?
Mã vạch Aztec là một mã ma trận hai chiều có thể mã hoá lên tới 3.000 ký tự số hoặc 2.300 ký tự chữ và số. Nó có một mẫu định vị trung tâm, cho phép quét nhanh ngay cả khi ký hiệu được in ở độ phân giải thấp. Vì mẫu này nằm ở trung tâm, mã có thể được đọc từ bất kỳ hướng nào, làm cho nó rất đáng tin cậy cho các ứng dụng di động và công nghiệp.

## Làm thế nào để tùy chỉnh tỷ lệ khung hình của mã vạch Aztec?
`BarcodeGenerator` là lớp chính được sử dụng để tạo mã vạch trong Aspose.BarCode. Đặt thuộc tính `AspectRatio` trên đối tượng `BarcodeGenerator` thành tỷ lệ chiều rộng‑chiều cao mong muốn, sau đó tạo hình ảnh. Điều chỉnh tỷ lệ khung hình giúp vừa mã vạch vào không gian UI hoặc bố cục nhãn hạn chế mà không làm giảm độ tin cậy khi quét, đồng thời cho phép bạn phù hợp với hướng dẫn thương hiệu hoặc yêu cầu máy in cụ thể.

### Các bước để tùy chỉnh tỷ lệ khung hình
1. **Tạo một thể hiện `BarcodeGenerator`** với `EncodeTypes.Aztec`.  
2. **Gán dữ liệu của bạn** (văn bản, byte, hoặc chuỗi số).  
3. **Đặt `AspectRatio`** – ví dụ, `1.5` cho thanh rộng hơn.  
4. **Tạo hình ảnh** bằng cách sử dụng `Save` hoặc `GetBarCodeImage`.  

## Làm thế nào để mã hoá byte thô vào mã vạch Aztec?
`EncodeBytes` là một phương thức nhận một mảng byte và chuyển nó thành ma trận Aztec. Gửi một mảng byte tới phương thức `EncodeBytes` của `BarcodeGenerator`. API tự động chuyển dữ liệu nhị phân thành ma trận Aztec gọn gàng, bảo toàn mọi bit. Điều này hoàn hảo để nhúng payload đã mã hoá, định danh nhị phân, hoặc tệp nén trực tiếp vào mã vạch.

### Các bước để mã hoá byte
1. **Chuẩn bị mảng byte** (ví dụ, `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Khởi tạo `BarcodeGenerator`** với `EncodeTypes.Aztec`.  
3. **Gọi `EncodeBytes(data)`** để tải nội dung nhị phân.  
4. **Hiển thị mã vạch** bằng `Save` hoặc `GetBarCodeImage`.  

## Làm thế nào để mã hoá văn bản vào mã vạch Aztec?
`CodeText` là một thuộc tính chứa dữ liệu văn bản thuần để mã hoá. Sử dụng thuộc tính `CodeText` của `BarcodeGenerator` để cung cấp dữ liệu văn bản thuần. Thư viện tự động chọn chế độ mã hoá tối ưu (số, chữ và số, hoặc byte) và áp dụng mức sửa lỗi phù hợp. Điều này giúp dễ dàng nhúng URL, ID sản phẩm, hoặc bất kỳ chuỗi có thể đọc được nào.

### Các bước để mã hoá văn bản
1. **Tạo trình tạo** với `EncodeTypes.Aztec`.  
2. **Đặt `CodeText`** thành chuỗi bạn muốn mã hoá.  
3. **Tùy chọn điều chỉnh `ErrorLevel`** để tăng độ bền.  
4. **Tạo hình ảnh** bằng `Save` hoặc `GetBarCodeImage`.  

## Làm thế nào để tạo mã vạch Aztec với các mức sửa lỗi khác nhau?
`ErrorLevel` là một thuộc tính kiểm soát lượng dữ liệu dư thừa được thêm vào mã vạch. Điều chỉnh thuộc tính `ErrorLevel` (0‑4) trước khi render. Các mức cao hơn tăng lượng dữ liệu dư thừa, cho phép mã vạch được đọc ngay cả khi lên tới 30 % ký hiệu bị hỏng. Điều này quan trọng trong môi trường khắc nghiệt như dán nhãn công nghiệp hoặc biển hiệu ngoài trời.

### Các bước để thiết lập sửa lỗi
1. **Khởi tạo `BarcodeGenerator`** cho Aztec.  
2. **Gán dữ liệu của bạn** (văn bản hoặc byte).  
3. **Đặt `ErrorLevel`** – ví dụ, `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Render mã vạch** với định dạng đầu ra bạn muốn.  

## Các chế độ Symbol Aztec khác nhau là gì và làm thế nào sử dụng chúng?
`SymbolMode` là một cài đặt xác định kích thước ma trận và dung lượng dữ liệu của mã Aztec được tạo. Chế độ Symbol Aztec quyết định kích thước ma trận và dung lượng dữ liệu. Thư viện cung cấp bốn chế độ: **Auto**, **FullRange**, **Compact**, và **Rune**.  

- **Auto** – trình tạo chọn kích thước nhỏ nhất có thể.  
- **FullRange** – cho phép kích thước ma trận tối đa cho tập dữ liệu rất lớn.  
- **Compact** – tạo một ký hiệu nhỏ hơn, dày đặc, lý tưởng cho không gian hạn chế.  
- **Rune** – chế độ chuyên biệt để mã hoá Unicode runes.  

Chọn chế độ qua `Generator.Parameters.Barcode.Aztec.SymbolMode`. Mỗi chế độ cân bằng giữa kích thước, khả năng đọc và dung lượng dữ liệu, cho phép bạn tùy chỉnh mã vạch theo các ràng buộc của ứng dụng.

## Hướng dẫn mã hoá mã vạch Aztec
Dưới đây là các hướng dẫn chi tiết từng bước đi sâu hơn vào mỗi chủ đề đã đề cập ở trên. Nhấp vào bất kỳ liên kết nào để khám phá mẫu mã đầy đủ, các yêu cầu trước và các mẹo thực hành tốt nhất.

### [Tùy chỉnh tỷ lệ khung hình mã vạch Aztec](./aztec-aspect-ratio-customization/)
Tìm hiểu cách tùy chỉnh tỷ lệ khung hình mã vạch Aztec bằng Aspose.BarCode cho .NET. Tạo các mã vạch độc đáo, linh hoạt cho các ứng dụng .NET của bạn.

### [Mã hoá Byte Aztec](./aztec-bytes-encoding/)
Tìm hiểu cách thực hiện Mã hoá Byte Aztec với Aspose.BarCode cho .NET. Hướng dẫn từng bước, các yêu cầu trước và ví dụ mã được bao gồm.

### [Mã hoá Văn bản Aztec](./aztec-code-text-encoding/)
Khám phá sức mạnh của Mã hoá Văn bản Aztec với Aspose.BarCode cho .NET. Tìm hiểu cách tạo và nhận dạng mã Aztec trong các ứng dụng .NET của bạn.

### [Tạo mã vạch Aztec với mức sửa lỗi](./aztec-error-level-example/)
Tìm hiểu cách tạo mã vạch Aztec với các mức sửa lỗi khác nhau bằng Aspose.BarCode cho .NET. Hướng dẫn toàn diện về việc tạo mã vạch.

### [Thành thạo chế độ Symbol Aztec](./aztec-symbol-mode-example/)
Khám phá chế độ Symbol Aztec trong Aspose.BarCode cho .NET và học cách tạo mã vạch đa năng một cách dễ dàng. Thực hành với các chế độ Auto, FullRange, Compact và Rune trong hướng dẫn toàn diện này.

## Câu hỏi thường gặp

**Q: Phiên bản .NET nào được Aspose.BarCode hỗ trợ cho việc mã hoá Aztec?**  
A: Thư viện hoạt động với .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 và các phiên bản sau.

**Q: Tôi có thể tạo mã vạch Aztec độ phân giải cao để in không?**  
A: Có—đặt thuộc tính `Resolution` (ví dụ, 300 dpi) trước khi lưu hình ảnh để có chất lượng sẵn sàng in.

**Q: Mã vạch Aztec có thể chứa lượng dữ liệu lớn bao nhiêu?**  
A: Lên tới 3.000 ký tự số hoặc 2.300 ký tự chữ và số, hoặc khoảng 1.800 byte dữ liệu thô trong chế độ Compact.

**Q: Có thể đọc mã vạch Aztec đã bị quay không?**  
A: Chắc chắn—bộ giải mã của Aspose.BarCode tự động phát hiện hướng và chỉnh sửa trong quá trình đọc.

**Q: Tôi có cần giấy phép cho việc phát triển và thử nghiệm không?**  
A: Có giấy phép đánh giá miễn phí cho việc thử nghiệm; giấy phép thương mại cần thiết cho triển khai sản xuất.

---

**Last Updated:** 2026-05-19  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách tạo mã vạch Aztec với tỷ lệ khung hình tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Mã hoá Byte Aztec bằng trình tạo mã vạch .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Cách tạo mã vạch Aztec với sửa lỗi trong .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}