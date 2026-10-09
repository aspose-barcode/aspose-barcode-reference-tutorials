---
category: general
date: 2026-10-08
description: Tạo mã vạch hành tinh trống bằng C# và học cách tạo mã vạch bưu chính
  bằng Aspose.BarCode. Bao gồm mã mẫu từng bước và các mẹo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: vi
lastmod: 2026-10-08
og_description: Tạo mã vạch hành tinh trống bằng Aspose.BarCode trong C# và xem cách
  tạo hình ảnh mã vạch bưu chính cho các ứng dụng gửi thư.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Tạo mã vạch hành tinh trống – Hướng dẫn mã vạch bưu chính C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Tạo mã vạch hành tinh trống, tạo mã vạch bưu chính bằng C#
url: /vi/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch planet trống, tạo mã vạch bưu chính bằng C#

Nếu bạn cần **tạo mã vạch planet trống** cho hệ thống gửi thư, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng Aspose.BarCode cho .NET. Bạn cũng sẽ học **cách tạo mã vạch bưu chính** dưới dạng hình ảnh như Planet và RM4SCC, tùy chỉnh độ rộng thanh, và kiểm soát tùy chọn thanh đã điền.

Việc tạo mã vạch bưu chính không yêu cầu một thư viện đồ họa riêng. Aspose.BarCode SDK cung cấp một API duy nhất xử lý mã hoá, render ảnh và lựa chọn định dạng ảnh. Khi kết thúc hướng dẫn này, bạn sẽ có ba tệp PNG sẵn sàng sử dụng:

* `PostalPlanetEmptyBars.png` – một mã vạch Planet có thanh trống  
* `PostalPlanetFilledBars.png` – mã vạch Planet thanh đã điền mặc định  
* `PostalRM4SCCFilledBars.png` – mã vạch RM4SCC thanh đã điền  

Bạn có thể chèn các tệp này vào bất kỳ mẫu nhãn thư nào, in chúng lên phong bì, hoặc truyền cho dịch vụ bên thứ ba.

## Yêu cầu trước

* .NET 6.0 trở lên (mã cũng hoạt động với .NET Framework 4.7+).  
* Visual Studio 2022 hoặc bất kỳ IDE C# nào.  
* Aspose.BarCode cho .NET – cài đặt qua NuGet:

```bash
dotnet add package Aspose.BarCode
```

Không cần phụ thuộc bổ sung.

## Tạo mã vạch planet trống với Aspose.BarCode

Ký hiệu Planet là một phần của họ mã vạch United States Postal Service (USPS). Mặc định SDK vẽ các thanh **đã điền**. Để **tạo mã vạch planet trống**, bạn tắt cờ `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Tại sao cách này hoạt động:**  
`EncodeTypes.Planet` cho trình tạo biết sử dụng ký hiệu Planet. `XDimension.Pixels` kiểm soát độ rộng thực tế của mỗi thanh, điều này quan trọng đối với các máy quét bưu chính yêu cầu kích thước mô-đun cụ thể. Đặt `FilledBars` thành `false` khiến trình render chỉ vẽ viền của mỗi thanh, tạo ra *giao diện trống* mà một số tiêu chuẩn gửi thư yêu cầu.

### Kết quả mong đợi

Bạn sẽ tìm thấy `PostalPlanetEmptyBars.png` trong thư mục đích. Hình ảnh hiển thị một mã vạch Planet mà mỗi thanh chỉ là viền thay vì hình chữ nhật đặc.

![Ví dụ mã vạch Planet trống](empty-planet.png){: .align-center alt="Tạo mã vạch planet trống – ví dụ mã vạch Planet có thanh trống"}

## Cách tạo hình ảnh mã vạch bưu chính (phiên bản đã điền)

Hầu hết các quy trình bưu chính sử dụng phiên bản thanh đã điền mặc định. Cùng một API có thể tạo mã vạch Planet đã điền và mã vạch RM4SCC chỉ với vài dòng code.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Tại sao bạn có thể cần RM4SCC:**  
RM4SCC là mã vạch USPS mới hơn, mã hoá cùng dữ liệu như Planet nhưng với mật độ cao hơn. Một số nhà vận chuyển yêu cầu RM4SCC để được giảm giá gửi thư bulk. Đoạn code trên minh họa cách **cách tạo mã vạch bưu chính** cho cả hai tiêu chuẩn mà không thay đổi quy trình chung.

### Kết quả mong đợi

* `PostalPlanetFilledBars.png` – một mã vạch Planet thanh đã điền cổ điển.  
* `PostalRM4SCCFilledBars.png` – một mã vạch RM4SCC thanh đã điền, nhìn tương tự nhưng có khoảng cách chặt hơn.

Cả hai tệp đều có thể mở bằng bất kỳ trình xem ảnh nào để xác minh các mẫu thanh.

## Điều chỉnh độ rộng thanh cho các độ phân giải in khác nhau

Máy quét bưu chính thường chỉ định độ rộng mô-đun tối thiểu (ví dụ, 0.013 inch). Nếu máy in của bạn hoạt động ở 300 dpi, một mô-đun 4‑pixel tương đương 0.013 inch. Điều chỉnh giá trị `XDimension.Pixels` để phù hợp với phần cứng của bạn:

| Độ rộng mô-đun mong muốn (inch) | DPI | Số pixel cần (`XDimension`) |
|-------------------------------|-----|-----------------------------|
| 0.013                         | 300 | 4                           |
| 0.013                         | 600 | 8                           |
| 0.015                         | 300 | 5                           |

**Mẹo:** Luôn kiểm tra a


## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ code hoàn chỉnh kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch planet PNG bằng C# – hướng dẫn từng bước](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Tạo Mã Vạch Bưu Chính bằng C# – Hướng Dẫn Đầy Đủ với Mã Vạch Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Cách tạo mã vạch bưu chính bằng C# với Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}