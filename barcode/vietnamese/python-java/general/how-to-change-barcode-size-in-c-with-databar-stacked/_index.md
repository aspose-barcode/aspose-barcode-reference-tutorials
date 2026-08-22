---
category: general
date: 2026-08-22
description: Cách thay đổi kích thước mã vạch trong C# bằng trình tạo DataBar Stacked
  Omni‑Directional. Tìm hiểu cách đặt kích thước X và tỷ lệ khung hình cho đầu ra
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: vi
lastmod: 2026-08-22
og_description: Cách thay đổi kích thước mã vạch trong C# bằng trình tạo DataBar Stacked
  Omni‑Directional. Thực hiện theo hướng dẫn từng bước để điều chỉnh kích thước trục
  X và tỷ lệ khung hình.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Cách thay đổi kích thước mã vạch trong C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách thay đổi kích thước mã vạch trong C# với DataBar Stacked
url: /vi/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thay đổi kích thước mã vạch trong C# với DataBar Stacked

Nếu bạn cần **cách thay đổi kích thước mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn các bước chính xác bằng cách sử dụng trình tạo mã vạch DataBar Stacked Omni‑Directional. Bạn sẽ thấy cách kiểm soát kích thước X‑dimension tính bằng pixel, điều chỉnh tỷ lệ khung hình của mã vạch, và lưu kết quả dưới dạng file PNG.

Việc thay đổi kích thước mã vạch thường cần thiết khi không gian nhãn in bị giới hạn hoặc khi cần hình ảnh độ phân giải cao cho các kênh kỹ thuật số. Bài học này bao gồm mọi thứ bạn cần, từ khởi tạo trình tạo đến việc tạo hai hình ảnh với các kích thước khác nhau.

## Các điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn được cài đặt  
* Tham chiếu tới gói NuGet **Aspose.BarCode for .NET**  
* Kiến thức cơ bản về cú pháp C#  

Không cần cấu hình bổ sung; mã chạy được trên Windows, Linux hoặc macOS.

## Cách thay đổi kích thước mã vạch trong C# – từng bước

Các phần sau chia quá trình thành các bước riêng biệt, có thể tái sử dụng. Mỗi bước giải thích **tại sao** mã cần thiết, không chỉ **cái gì** nó làm.

### Bước 1: Tạo trình tạo mã vạch DataBar Stacked Omni‑Directional

Đối tượng trình tạo chứa tất cả các thiết lập của mã vạch. Bằng cách truyền `EncodeTypes.DatabarStackedOmniDirectional` và dữ liệu mẫu, bạn tạo ra một mã vạch hợp lệ, sẵn sàng cho việc tùy chỉnh tiếp theo.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Lý do quan trọng* – Lớp **C# barcode generator** bao hàm thuật toán mã hoá. Bắt đầu với một trình tạo hợp lệ đảm bảo rằng các thay đổi kích thước sau này sẽ ảnh hưởng đúng loại mã vạch.

### Bước 2: Đặt kích thước mô-đun cơ bản (X‑dimension) tính bằng pixel

X‑dimension xác định chiều rộng của một mô-đun mã vạch. Điều chỉnh nó sẽ thay đổi tổng chiều rộng và chiều cao một cách tỷ lệ.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Lý do quan trọng* – X‑dimension lớn hơn tạo ra mã vạch lớn hơn, hữu ích cho máy in độ phân giải thấp. Ngược lại, giá trị nhỏ hơn tạo ra mã vạch gọn gàng, phù hợp cho nhãn nhỏ.

### Bước 3: Thay đổi tỷ lệ khung hình của mã vạch thành 15 và lưu ảnh

**Barcode aspect ratio** kiểm soát mối quan hệ chiều cao‑với‑chiều rộng. Tỷ lệ 15 cho ra một mã vạch tương đối cao.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Lý do quan trọng* – Các thiết bị quét khác nhau có yêu cầu tỷ lệ khung hình tối ưu. Đặt tỷ lệ thành 15 minh họa cách **cách thay đổi kích thước mã vạch** bằng cách thay đổi chiều cao trong khi giữ chiều rộng được xác định bởi X‑dimension.

#### Kết quả mong đợi

File `DatabarAspectRatio15.png` hiển thị một mã vạch DataBar Stacked Omni‑Directional cao hơn so với mặc định. Chiều rộng của mã vạch phản ánh X‑dimension 2 pixel, và chiều cao tuân theo tỷ lệ 15.

### Bước 4: Thay đổi tỷ lệ khung hình của mã vạch thành 30 và lưu ảnh mới

Tăng tỷ lệ khung hình lên 30 làm mã vạch còn cao hơn, cho thấy tính linh hoạt của việc điều chỉnh kích thước.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Lý do quan trọng* – Bằng cách thay đổi giá trị **barcode aspect ratio**, bạn ngay lập tức thấy cách **cách thay đổi kích thước mã vạch** mà không cần tạo lại trình tạo. Điều này tiết kiệm thời gian xử lý trong các kịch bản batch.

#### Kết quả mong đợi

File `DatabarAspectRatio30.png` cao hơn rõ rệt so với ảnh trước, xác nhận rằng tỷ lệ khung hình ảnh hưởng trực tiếp tới chiều cao của mã vạch.

### Bước 5: Kiểm tra các ảnh đã tạo

Mở các file PNG bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy hai mã vạch có cùng chiều rộng (được kiểm soát bởi X‑dimension) nhưng chiều cao khác nhau (được kiểm soát bởi aspect ratio). Nếu ảnh bị mờ, tăng số pixel của X‑dimension; nếu quá cao, giảm aspect ratio.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Lý do quan trọng* – Kiểm tra bằng chương trình đảm bảo các thay đổi kích thước đã được áp dụng đúng, điều này rất quan trọng cho các pipeline xây dựng tự động.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh | Lý do |
|-----------|------------|--------|
| **Nhãn rất nhỏ** | Set `XDimension.Pixels = 1` và `AspectRatio = 10` | Giảm tổng diện tích trong khi vẫn duy trì khả năng đọc |
| **In độ phân giải cao** | Set `XDimension.Pixels = 4` và `AspectRatio = 20` | Tăng mật độ pixel để có đầu ra sắc nét |
| **Định dạng ảnh khác** | Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` | Hữu ích khi hỗ trợ PNG bị hạn chế |
| **Dữ liệu động** | Truyền một chuỗi biến vào constructor `BarcodeGenerator` | Tự động tạo mã vạch cho mỗi sản phẩm |

Khi cần tạo nhiều mã vạch với các kích thước khác nhau, hãy gói các bước vào một phương thức:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Gọi `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` sẽ tạo một mã vạch với kích thước tùy chỉnh trong một dòng lệnh.

## Mẹo chuyên nghiệp để thay đổi kích thước một cách ổn định

* **Luôn đặt X‑dimension trước aspect ratio.** Thay đổi aspect ratio trước có thể gây ra việc co‑giãn không mong muốn nếu X‑dimension mặc định không phù hợp.  
* **Sử dụng thư mục đầu ra cố định.** Việc hard‑code `"YOUR_DIRECTORY"` chỉ phù hợp cho demo; trong môi trường thực tế nên dùng `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Xác thực kích thước ảnh đã tạo.** Thay đổi nhỏ trong X‑dimension có thể không nhận thấy trên màn hình; kiểm tra kích thước pixel đảm bảo thay đổi đã có hiệu lực.  

## Kết luận

Bạn đã biết **cách thay đổi kích thước mã vạch** trong C# bằng trình tạo DataBar Stacked Omni‑Directional. Bằng cách điều chỉnh **pixel X‑dimension** và **barcode aspect ratio**, bạn có thể tạo các ảnh PNG phù hợp với bất kỳ kích thước nhãn hay yêu cầu độ phân giải nào. Ví dụ hoàn chỉnh, có thể chạy ngay ở trên mô tả toàn bộ quy trình từ tạo trình tạo đến xác thực kích thước.

### Những gì nên khám phá tiếp theo

* **Màu sắc tùy chỉnh** – thử nghiệm với `barcodeGenerator.Parameters.Barcode.ForeColor` và `BackColor` để phù hợp với bộ nhận diện thương hiệu.  
* **Các loại mã vạch khác** – thay `EncodeTypes.DatabarStackedOmniDirectional` bằng `EncodeTypes.QR` hoặc `EncodeTypes.Code128` để xem các tham số kích thước thay đổi như thế nào giữa các symbology.  
* **Xử lý batch** – kết hợp phương thức `GenerateDatabar` với việc nhập CSV để tự động tạo hàng ngàn mã vạch.

Hãy tự do điều chỉnh các đoạn mã cho kiến trúc dự án của bạn, và để các điều chỉnh kích thước mã vạch cải thiện độ tin cậy khi quét và thiết kế trực quan. Chúc lập trình vui!

### Bạn nên học gì tiếp theo?

Các hướng dẫn dưới đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}