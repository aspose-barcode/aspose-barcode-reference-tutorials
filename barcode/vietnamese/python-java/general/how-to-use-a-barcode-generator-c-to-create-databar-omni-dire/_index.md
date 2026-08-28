---
category: general
date: 2026-08-22
description: Hướng dẫn tạo mã vạch C# cho thấy cách tạo các tệp PNG mã vạch, tạo mã
  vạch DataBar và điều chỉnh chiều cao mã vạch chỉ trong vài bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: vi
lastmod: 2026-08-22
og_description: Hướng dẫn tạo mã vạch C# giúp bạn biết cách tạo PNG mã vạch, tạo mã
  DataBar và điều chỉnh chiều cao mã vạch một cách hiệu quả.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: trình tạo mã vạch C# – tạo mã vạch DataBar và điều chỉnh chiều cao
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách sử dụng trình tạo mã vạch C# để tạo mã DataBar đa hướng
url: /vi/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng barcode generator C# để tạo DataBar Omni‑directional barcodes

Nếu bạn cần một **barcode generator C#** có thể tạo ra các hình ảnh PNG chất lượng cao, hướng dẫn này sẽ đáp ứng nhu cầu của bạn. Bạn sẽ học cách tạo các tệp PNG mã vạch, tạo mã vạch DataBar Omni‑directional và điều chỉnh chiều cao mã vạch mà không rời khỏi IDE của mình.

Việc tạo mã vạch bằng chương trình loại bỏ bước thủ công sử dụng trình chỉnh sửa đồ họa. Khi kết thúc tutorial này, bạn sẽ có hai tệp PNG—một với chiều cao thanh 30 pixel và một với chiều cao thanh 60 pixel—sẵn sàng đưa vào hoá đơn, nhãn mác hoặc hệ thống quản lý tồn kho.

**Prerequisites**

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Tham chiếu tới gói NuGet `Aspose.BarCode` (hoặc bất kỳ thư viện nào cung cấp API tương tự)
- Kiến thức cơ bản về C# và Visual Studio hoặc IDE ưa thích của bạn

---

## Step 1: Set up the barcode generator C# project

Tạo một thể hiện **barcode generator C#** là việc đầu tiên bạn thực hiện. Constructor nhận hai đối số: loại mã vạch (`EncodeTypes.DatabarOmniDirectional`) và dữ liệu payload. Trong ví dụ này payload tuân theo định dạng GS1 Application Identifier cho GTIN 14‑digit.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Why this matters:** Enum `EncodeTypes.DatabarOmniDirectional` thông báo cho thư viện render một DataBar có thể đọc được từ bất kỳ hướng nào, rất phù hợp cho các nhãn bán lẻ nhỏ.

---

## Step 2: Define the module dimension (X‑dimension)

X‑dimension kiểm soát độ rộng của một mô-đun mã vạch đơn lẻ. Đặt giá trị 2 pixel cho ra hình ảnh sắc nét, dễ đọc đồng thời giữ kích thước tệp thấp.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** Nếu bạn cần mã vạch gọn hơn cho không gian hạn chế, giảm giá trị xuống 1 pixel, nhưng hãy kiểm tra độ đọc được bằng máy quét.

---

## Step 3: Generate the first PNG with a 30‑pixel bar height

Chiều cao thanh quyết định độ cao của các thanh. Chiều cao 30 pixel là mặc định phổ biến cho các nhãn tiêu chuẩn.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Tệp `DatabarBarHeight30Pixels.png` hiện chứa một **generate barcode PNG** có thể dùng trực tiếp trong trang web hoặc in theo yêu cầu.

---

## Step 4: Adjust barcode height to 60 pixels and save a second PNG

Thay đổi chiều cao thanh chỉ cần gán một giá trị mới cho cùng một thuộc tính. Điều này minh họa khả năng **adjust barcode height** của generator.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Bây giờ bạn có `DatabarBarHeight60Pixels.png`, lý tưởng cho bao bì lớn hơn nơi mã vạch cần được quét từ khoảng cách xa.

**Expected output**

- `DatabarBarHeight30Pixels.png` – một DataBar Omni‑directional gọn gàng, cao 30 px.
- `DatabarBarHeight60Pixels.png` – cùng mã vạch, tăng gấp đôi chiều cao để dễ nhìn hơn.

Cả hai hình ảnh đều là tệp PNG, giữ chất lượng lossless và hỗ trợ trong suốt nếu cần.

---

## How to generate barcode PNG files in different formats

Mặc dù tutorial này tập trung vào PNG, phương thức `Save` chấp nhận các định dạng khác như `Jpeg`, `Bmp` và `Svg`. Để **how to generate barcode** ở định dạng khác, chỉ cần thay `BarCodeImageFormat.Png` bằng giá trị enum mong muốn:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Chọn SVG rất tiện khi bạn cần một hình ảnh vector có thể phóng to mà không bị pixel hoá.

---

## Common pitfalls when you **create DataBar barcode** images

| Issue | Cause | Fix |
|-------|-------|-----|
| Mã vạch bị mờ | X‑dimension quá thấp so với độ phân giải mục tiêu | Tăng `XDimension.Pixels` lên 3 hoặc 4 |
| Máy quét không thể đọc mã | Chiều cao thanh quá ngắn so với quang học của máy quét | Sử dụng tối thiểu 30 pixel hoặc tuân theo thông số kỹ thuật của máy quét |
| Chuỗi dữ liệu bị từ chối | Định dạng GS1 không đúng | Đảm bảo chuỗi bắt đầu bằng Application Identifier đúng, ví dụ `(01)` cho GTIN‑14 |

Giải quyết những vấn đề này sớm sẽ tiết kiệm thời gian khi tích hợp mã vạch vào quy trình sản xuất.

---

## Advanced tip: Reusing the same generator for multiple barcodes

Nếu bạn cần **generate barcode PNG** cho một loạt sản phẩm, hãy tái sử dụng cùng một thể hiện `BarcodeGenerator` và chỉ cập nhật thuộc tính `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Mẫu này giảm thiểu chi phí tạo đối tượng và giữ cho mã của bạn ngắn gọn.

---

## Conclusion

Bạn giờ đã có một quy trình **barcode generator C#** hoàn chỉnh, có thể **creates DataBar barcodes**, **generates barcode PNG** và cho phép **adjust barcode height** chỉ bằng một thay đổi thuộc tính. Ví dụ bao phủ mọi khía cạnh từ thiết lập dự án đến xử lý các trường hợp đặc biệt, giúp bạn tích hợp việc tạo mã vạch vào bất kỳ ứng dụng .NET nào một cách tự tin.

**Next steps**

- Khám phá các symbology mã vạch khác (`EncodeTypes.QR`, `EncodeTypes.Code128`) để mở rộng giải pháp.
- Kết hợp generator với ASP.NET Core để phục vụ mã vạch ngay lập tức qua endpoint API.
- Thử nghiệm các tùy chọn màu (`generator.Parameters.Barcode.ForeColor`) để phù hợp với thương hiệu.

Chúc lập trình vui vẻ, và hy vọng các lần quét của bạn luôn nhanh chóng!

## What Should You Learn Next?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Tạo và Điều Chỉnh Chiều Cao Mã Vạch cho One-Dimensional Databar bằng Aspose.BarCode cho .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Tạo Mã Vạch One-Dimensional Databar 2D Bằng Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Cách Tạo Mã Vạch DataMatrix Bằng Aspose.BarCode cho .NET – Hướng Dẫn Từng Bước](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}