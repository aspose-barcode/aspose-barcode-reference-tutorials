---
category: general
date: 2026-07-21
description: Tạo mã vạch C# nhanh chóng với Aspose.BarCode. Học cách tạo mã vạch DataBar,
  tùy chỉnh kích thước mã vạch và xuất hình ảnh mã vạch chỉ trong vài bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: vi
lastmod: 2026-07-21
og_description: Tạo mã vạch C# bằng Aspose.BarCode. Tạo mã vạch DataBar, tùy chỉnh
  kích thước và xuất hình ảnh ngay lập tức.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Tạo mã vạch C# – Xây dựng mã DataBar với kích thước tùy chỉnh
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Tạo mã vạch C# – Tạo mã DataBar
url: /vi/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch C# – Tạo mã DataBar

Bạn đang muốn **tạo mã vạch C#** mà không phải lục lọi qua vô số tài liệu? Bạn đã đến đúng nơi. Trong hướng dẫn này chúng ta sẽ đi qua cách tạo **mã DataBar**, điều chỉnh kích thước của nó, và cuối cùng **xuất ảnh mã vạch**—tất cả chỉ với vài dòng C#.

Hãy tưởng tượng bạn cần một nhãn sản phẩm gọn gàng vừa trên thẻ kệ nhỏ. Ký hiệu DataBar Expanded Stacked chính là giải pháp, và với Aspose.BarCode bạn có thể kiểm soát chính xác số cột hoặc hàng mà nó sử dụng. Sẵn sàng? Hãy bắt đầu.

## Những gì bạn sẽ đạt được

- **Tạo mã DataBar** (phiên bản “expanded stacked”) từ đầu.  
- **Tùy chỉnh kích thước mã vạch** bằng cách đặt trực tiếp số cột hoặc hàng.  
- **Thay đổi kích thước mã vạch** ngay lập tức mà không cần xây dựng lại bộ tạo.  
- **Xuất ảnh mã vạch** sang PNG (hoặc bất kỳ định dạng nào mà Aspose hỗ trợ).  

Không cần dịch vụ bên ngoài, không có cấu hình rắc rối—chỉ có mã C# sạch sẽ, có thể chạy ngay.

## Yêu cầu trước

- .NET 6.0 hoặc mới hơn (mã cũng chạy trên .NET Framework 4.7+).  
- Giấy phép Aspose.BarCode for .NET hợp lệ (hoặc bạn có thể chạy ở chế độ dùng thử).  
- Một IDE mà bạn thích—Visual Studio, Rider, hoặc VS Code đều được.  

Nếu bạn chưa cài đặt gói NuGet, chạy:

```bash
dotnet add package Aspose.BarCode
```

Xong—không cần phụ thuộc nào khác.

## Bước 1: Thiết lập bộ tạo mã vạch (Cách **tạo mã vạch C#**)

Đầu tiên, chúng ta cần một thể hiện `BarcodeGenerator` trỏ tới ký hiệu **DataBar Expanded Stacked**. Đối tượng này là động cơ tạo ảnh sau này.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Lý do quan trọng*: Enum `EncodeTypes.DatabarExpandedStacked` thông báo cho Aspose rằng chúng ta muốn phiên bản xếp chồng, lý tưởng cho không gian hẹp. Văn bản chúng ta truyền vào sẽ trở thành giá trị được mã hoá; bạn có thể thay bằng bất kỳ chuỗi số nào mà ứng dụng của bạn yêu cầu.

## Bước 2: **Tùy chỉnh kích thước mã vạch** – đặt số cột

Mã DataBar cho phép bạn ảnh hưởng tới mật độ hình ảnh bằng cách chỉ định số **cột** *hoặc* **hàng**. Hãy bắt đầu với cột. Số hàng sẽ được tính tự động để mã vẫn hợp lệ.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Mẹo*: Số cột ảnh hưởng tới chiều rộng của mã vạch. Nhiều cột → mã rộng hơn, có thể cải thiện độ tin cậy khi quét trên máy in độ phân giải thấp.

## Bước 3: **Xuất ảnh mã vạch** với cài đặt cột

Bây giờ chúng ta ghi ảnh ra đĩa. Bạn có thể chọn PNG, JPEG, BMP, hoặc thậm chí SVG. Dưới đây là PNG cho đầu ra sắc nét, không mất dữ liệu.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Kết quả mong đợi** – Mở `DatabarCols4.png` và bạn sẽ thấy một DataBar xếp chồng gọn gàng với bốn cột. Nó trông giống một chồng dày các thanh dọc, hoàn hảo cho nhãn nhỏ.

## Bước 4: **Thay đổi kích thước mã vạch** – đặt số hàng thay vì cột

Đôi khi bạn cần một mã vạch cao hơn thay vì rộng hơn. Chuyển sang điều khiển hàng; Aspose sẽ tự động tính lại số cột.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Tại sao chuyển?* Hàng ảnh hưởng tới chiều cao của mã vạch. Nhiều hàng → ký hiệu cao hơn, hữu ích khi bạn có không gian dọc nhưng chiều rộng hạn chế.

## Bước 5: **Xuất ảnh mã vạch** với cài đặt hàng

Lưu biến thể thứ hai. Lưu ý tên tệp phản ánh sự thay đổi; bạn cũng có thể giữ cả hai ảnh để so sánh.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Kết quả** – `DatabarRows3.png` bây giờ hiển thị phiên bản cao hơn của cùng dữ liệu, vẫn quét được một cách hoàn hảo.

## Ví dụ hoàn chỉnh

Kết hợp lại, đây là một ứng dụng console tự chứa mà bạn có thể sao chép‑dán và chạy ngay:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Chạy chương trình, sau đó mở hai tệp PNG. Bạn vừa **tạo mã vạch C#**, **tùy chỉnh kích thước mã vạch**, **thay đổi kích thước mã vạch**, và **xuất ảnh mã vạch**—tất cả trong chưa đầy một phút.

## Câu hỏi thường gặp & các trường hợp đặc biệt

- **Nếu tôi cần định dạng ảnh khác thì sao?**  
  Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, `Gif` hoặc `Svg`. API sẽ tự động thực hiện chuyển đổi.

- **Có thể đồng thời thay đổi cả hàng và cột không?**  
  Kỹ thuật bạn có thể đặt cả hai, nhưng Aspose sẽ ưu tiên thuộc tính cuối cùng bạn thay đổi. An toàn hơn là chỉ đặt *một* chiều và để thư viện tính toán chiều còn lại cho một DataBar hợp lệ.

- **Làm sao áp dụng màu nền/màu chữ?**  
  Sử dụng `barcodeGen.Parameters.Barcode.ForegroundColor` và `BackgroundColor`. Ví dụ:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Có giới hạn kích thước dữ liệu được mã hoá không?**  
  DataBar Expanded Stacked hỗ trợ tối đa 74 ký tự số (hoặc 30 ký tự alphanumeric). Vượt quá sẽ gây ra ngoại lệ.

## Bước tiếp theo

Bây giờ bạn đã nắm vững các kiến thức cơ bản về **tạo mã databar**, hãy cân nhắc:

- Thêm **chú thích văn bản** dưới mã vạch (`barcodeGen.Parameters.CaptionAbove.Text`).
- Nhúng PNG trực tiếp vào PDF bằng Aspose.PDF.
- Tạo mã vạch hàng loạt bằng cách lặp qua một CSV chứa các ID sản phẩm.

Mỗi chủ đề này đều dựa trên cùng một đối tượng `BarcodeGenerator`, vì vậy bạn sẽ không cần bắt đầu lại từ đầu.

---

**Kết luận**: Bạn đã biết cách **tạo mã vạch C#**, **tùy chỉnh kích thước mã vạch**, **thay đổi kích thước mã vạch**, và **xuất ảnh mã vạch** với Aspose.BarCode. Hãy thử nghiệm các giá trị cột/hàng, thay đổi định dạng ảnh, và tích hợp mã vào hệ thống quản lý kho hoặc POS của bạn. Chúc lập trình vui vẻ!


## Bạn Nên Học Gì Tiếp Theo?


Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ cùng giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}