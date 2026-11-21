---
category: general
date: 2026-11-20
description: Tạo hình ảnh mã vạch bưu chính trong C# nhanh chóng. Tìm hiểu cách tạo
  mã vạch Planet và mã vạch RM4SCC với các kiểu thanh có thể tùy chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: vi
lastmod: 2026-11-20
og_description: Tạo hình ảnh mã vạch bưu chính trong C# với Aspose.BarCode. Hướng
  dẫn này cho thấy cách tạo mã vạch Planet, tùy chỉnh kiểu thanh mã vạch và tạo hình
  ảnh RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Tạo hình ảnh mã vạch bưu chính trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Tạo hình ảnh mã vạch bưu chính và tạo mã vạch hành tinh
url: /vi/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch bưu chính và tạo mã vạch planet

Tạo hình ảnh mã vạch bưu chính trong C# bằng thư viện Aspose.BarCode. Nếu bạn cần tạo mã vạch planet hoặc mã vạch RM4SCC cho các ứng dụng gửi thư, hướng dẫn này cung cấp một giải pháp hoàn chỉnh, sẵn sàng chạy.

Việc tạo mã vạch cho các dịch vụ bưu chính thường yêu cầu kích thước chính xác và tùy chọn chuyển đổi giữa kiểu thanh đầy và thanh rỗng. Hướng dẫn này sẽ chỉ cho bạn cách thiết lập thư mục đầu ra, tạo cả mã vạch Planet đầy và rỗng, và tạo mã vạch RM4SCC với cùng cài đặt hiển thị. Khi hoàn thành, bạn sẽ có bốn tệp PNG có thể sử dụng ngay trong quy trình gửi thư của mình.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào bạn ưa thích)  
* Gói **Aspose.BarCode** NuGet (`Install-Package Aspose.BarCode`)  

Không cần cấu hình bổ sung; mã chỉ sử dụng phông chữ mặc định và bộ mã hoá PNG.

## Tạo hình ảnh mã vạch bưu chính – tổng quan

Cốt lõi của quá trình là lớp `BarcodeGenerator`. Nó nhận một giá trị `EncodeTypes` xác định loại mã vạch (ví dụ, `EncodeTypes.Planet` cho mã vạch Planet). Sau khi cấu hình bộ tạo, bạn gọi `Save` để ghi tệp hình ảnh.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Ví dụ tạo hình ảnh mã vạch bưu chính hiển thị các thanh đầy và trống.*

## Bước 1: Thiết lập thư mục đầu ra

Đầu tiên xác định thư mục nơi các tệp PNG sẽ được lưu. Sử dụng đường dẫn tuyệt đối hoặc tương đối đều hoạt động tương tự; chỉ cần đảm bảo thư mục tồn tại hoặc để mã tự tạo nó.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Tạo thư mục bằng chương trình ngăn ngừa `DirectoryNotFoundException` khi hướng dẫn chạy trên máy mới.

## Bước 2: Tạo mã vạch planet với thanh đầy

Mã vạch Planet có thanh đầy là kiểu hiển thị mặc định. Đoạn mã dưới đây tạo mã vạch, đặt kích thước X‑dimension thành 4 pixel (kích thước phổ biến cho các ứng dụng bưu chính), và lưu hình ảnh.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Tại sao cách này hoạt động:**  
* `EncodeTypes.Planet` báo cho bộ tạo sử dụng ký hiệu Planet, được yêu cầu bởi nhiều dịch vụ bưu chính.  
* `XDimension.Pixels` kiểm soát độ rộng của mỗi thanh; 4 px tạo ra hình ảnh rõ ràng, dễ quét mà không làm tệp quá lớn.  
* Phương thức `Save` tự động chọn bộ mã hoá PNG dựa trên enum `BarCodeImageFormat`.

## Bước 3: Tạo mã vạch planet với thanh rỗng

Một số tiêu chuẩn bưu chính ưu thích các thanh (trắng) rỗng trên nền tối. Bạn có thể đạt được điều này bằng cách đặt `FilledBars` thành `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Mẹo:** Khi `FilledBars` là `false`, bộ tạo sẽ vẽ các thanh bằng màu nền (mặc định là trắng) và các khoảng trống bằng màu tiền cảnh (đen). Nếu bạn cần bảng màu khác, hãy điều chỉnh `Parameters.Barcode.ForeColor` và `BackColor`.

## Bước 4: Tạo mã vạch RM4SCC với thanh đầy

RM4SCC là một ký hiệu bưu chính khác được sử dụng ở Vương quốc Anh. Các bước tạo tương tự như ví dụ Planet; chỉ có giá trị `EncodeTypes` thay đổi.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Kết quả mong đợi:** PNG tạo ra hiển thị một mã vạch RM4SCC gọn gàng, tuân thủ các hướng dẫn bưu chính của Anh. Kích thước hình ảnh sẽ tương tự như các mã vạch Planet vì X‑dimension giống nhau.

## Bước 5: Kiểm tra các hình ảnh đã tạo

Sau khi chạy chương trình, mở bốn tệp trong thư mục `Barcodes`. Bạn sẽ thấy:

* `PostalPlanetFilledBars.png` – các thanh tối trên nền sáng  
* `PostalPlanetEmptyBars.png` – các thanh sáng trên nền tối (ngược)  
* `PostalRM4SCCFilledBars.png` – mẫu RM4SCC tiêu chuẩn  

Nếu bất kỳ hình ảnh nào bị biến dạng, hãy kiểm tra các mục sau:

* **X‑dimension** – quá nhỏ (< 2 px) có thể gây mờ; quá lớn (> 10 px) có thể vượt quá giới hạn kích thước nhãn.  
* **Chuỗi dữ liệu** – giá trị `"123456"` phải đáp ứng yêu cầu độ dài của ký hiệu đã chọn (Planet yêu cầu 6 chữ số, RM4SCC cũng yêu cầu 6 chữ số).  
* **Quyền thư mục** – đảm bảo ứng dụng có quyền ghi vào thư mục đầu ra.

## Các biến thể phổ biến và trường hợp đặc biệt

| Kịch bản | Điều chỉnh |
|----------|------------|
| **Dữ liệu mã vạch khác** | Thay `"123456"` bằng bất kỳ chuỗi số hợp lệ nào. Đối với Planet, độ dài phải chính xác 6 chữ số; RM4SCC cũng yêu cầu 6 chữ số. |
| **Màu tùy chỉnh** | Đặt `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` và `BackColor = System.Drawing.Color.LightYellow;`. |
| **Độ phân giải cao hơn** | Tăng `XDimension.Pixels` lên 6 hoặc 8 để in lớn hơn. |
| **Định dạng hình ảnh khác** | Sử dụng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp` trong lời gọi `Save`. |
| **Tạo hàng loạt** | Lặp qua một tập hợp các chuỗi và gọi cùng một logic bộ tạo bên trong vòng lặp, tái sử dụng đường dẫn `outputFolder`. |

## Ví dụ đầy đủ, có thể chạy được

Sao chép đoạn mã dưới đây vào một dự án console C# mới. Nó biên dịch với .NET 6.0 và tự động tạo ra cả bốn hình ảnh mã vạch.



## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh cùng giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}