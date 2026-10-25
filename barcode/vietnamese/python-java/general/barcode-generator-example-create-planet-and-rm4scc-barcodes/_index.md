---
category: general
date: 2026-10-24
description: Ví dụ trình tạo mã vạch cho thấy cách tạo mã vạch Planet và cách đặt
  chiều cao mã vạch bằng Python. Thực hiện theo hướng dẫn từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: vi
lastmod: 2026-10-24
og_description: Ví dụ trình tạo mã vạch cho thấy cách tạo mã vạch Planet và cách đặt
  chiều cao mã vạch trong Python. Nhận giải pháp đầy đủ, có thể chạy được.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Ví dụ trình tạo mã vạch – tạo mã vạch Planet và RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Ví dụ tạo mã vạch – tạo mã vạch Planet và RM4SCC với chiều cao tùy chỉnh
url: /vi/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ví dụ tạo mã vạch – tạo mã Planet và RM4SCC với chiều cao tùy chỉnh

Nếu bạn đang tìm kiếm một **ví dụ tạo mã vạch**, hướng dẫn này cung cấp cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy **cách tạo hình ảnh mã Planet**, học **cách đặt chiều cao mã vạch**, và hiểu những khác biệt nhỏ giữa việc tính kích thước tự động và thủ công.

Bài hướng dẫn đi qua hai kịch bản thực tế: một mã Planet sử dụng chiều cao mặc định (tự động), và một mã RM4SCC mà chiều cao được ép buộc là 100 px. Khi kết thúc, bạn có thể tạo các tệp PNG cho bất kỳ loại mã vạch được hỗ trợ nào chỉ với một API nhất quán.

## Các điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* Python 3.8 trở lên đã được cài đặt.
* Gói `aspose-barcode` (hoặc bất kỳ thư viện nào cung cấp `BarcodeGenerator`, `EncodeTypes`, và `BarCodeImageFormat`). Cài đặt bằng  

  ```bash
  pip install aspose-barcode
  ```
* Quyền ghi vào thư mục nơi các tệp PNG sẽ được lưu.

Không cần bất kỳ phụ thuộc hệ thống bổ sung nào.

## Tổng quan về giải pháp

Cốt lõi của **ví dụ tạo mã vạch** bao gồm ba bước có thể tái sử dụng:

1. **Khởi tạo** một `BarcodeGenerator` với giá trị `EncodeTypes` mong muốn và chuỗi dữ liệu.
2. **Cấu hình** kích thước X‑dimension (độ rộng mô-đun) và, khi cần, chiều cao mã vạch.
3. **Lưu** hình ảnh vào đĩa ở định dạng PNG.

Cả hai ví dụ đều chia sẻ bước 1 và 3; chỉ bước 2 khác nhau vì mã Planet dựa vào việc tính chiều cao tự động của thư viện, trong khi mã RM4SCC minh họa **cách đặt chiều cao mã vạch** một cách thủ công.

Dưới đây là sơ đồ cấp cao mô tả luồng công việc:

![Ví dụ tạo mã vạch hiển thị mã Planet và RM4SCC](barcode-example.png)

*Alt text: Ví dụ tạo mã vạch hiển thị mã Planet và RM4SCC với các chiều cao khác nhau.*

## Cách tạo mã Planet – chiều cao tự động

Mã Planet là một phần của họ mã bưu chính được nhiều dịch vụ bưu chính quốc gia sử dụng. Trong hầu hết các trường hợp, bạn để SDK quyết định chiều cao, giúp duy trì tỉ lệ hình ảnh đúng cho các độ dài dữ liệu khác nhau.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Tại sao cách này hoạt động**

* `EncodeTypes.Planet` báo cho thư viện sử dụng ký hiệu Planet.
* Đặt `x_dimension.pixels` thành 4 sẽ cho mỗi mô-đun có độ rộng 4 px, đây là giá trị mặc định phổ biến cho nhãn in.
* Không đặt chiều cao cụ thể; SDK tính toán chiều cao tối ưu dựa trên dữ liệu và X‑dimension, vì vậy đây là **ví dụ tạo mã vạch** đơn giản nhất cho các mã bưu chính.

**Kết quả mong đợi**

Một tệp PNG 2‑D có tên `PostalPlanetBarHeightAuto.png` chứa mã Planet sắc nét. Chiều cao sẽ vào khoảng 30 px (tùy phiên bản thư viện) và chiều rộng sẽ là 4 px × số mô-đun.

## Cách đặt chiều cao mã vạch – ví dụ RM4SCC tùy chỉnh

RM4SCC là một mã bưu chính khác thường yêu cầu chiều cao cố định để phù hợp với mẫu nhãn. Phần này của hướng dẫn cho thấy **cách đặt chiều cao mã vạch** tới một số pixel chính xác.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Tại sao cách này hoạt động**

* `EncodeTypes.RM4SCC` chọn ký hiệu RM4SCC.
* X‑dimension vẫn giữ ở 4 px để duy trì kích thước mô-đun nhất quán giữa cả hai mã.
* `bar_height.pixels = 100` ép mã vạch có chiều cao chính xác 100 px, ghi đè lên tính toán tự động. Đây là cách được khuyến nghị **cách đặt chiều cao mã vạch** khi bố cục của bạn yêu cầu kích thước cụ thể.

**Kết quả mong đợi**

Một tệp PNG có tên `PostalRM4SCCBarHeight100Pixels.png` hiển thị mã RM4SCC cao. Chiều rộng vẫn được xác định bởi X‑dimension, trong khi chiều cao cố định ở 100 px, phù hợp cho các máy in nhãn độ phân giải cao.

## Kịch bản đầy đủ – kết hợp cả hai ví dụ

Nếu bạn muốn một kịch bản duy nhất tạo cả hai hình ảnh, sao chép đoạn mã sau vào `generate_barcodes.py` và chạy nó.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Giải thích kịch bản**

* Hai hàm trợ giúp giúp mã không bị lặp lại (DRY – Don’t Repeat Yourself) và dễ mở rộng cho các ký hiệu khác.
* Điều kiện `if __name__ == "__main__":` cho phép tệp được nhập như một module mà không thực thi logic tạo mã, hữu ích cho kiểm thử đơn vị.
* Tất cả các tham số (chuỗi dữ liệu, X‑dimension, chiều cao) đều được khai báo rõ ràng, vì vậy kịch bản này đóng vai trò là **ví dụ tạo mã vạch** tham khảo cho các dự án tương lai.

## Các câu hỏi thường gặp và trường hợp đặc biệt

| Câu hỏi | Trả lời |
|----------|--------|
| *Nếu tôi cần một X‑dimension khác thì sao?* | Thay đổi `x_dimension.pixels` thành độ rộng mô-đun mong muốn. Giá trị lớn hơn sẽ làm tăng kích thước tổng thể của mã vạch tỷ lệ. |
| *Tôi có thể tạo các định dạng ảnh khác không?* | Có. Thay `BarCodeImageFormat.Png` bằng `Jpg`, `Bmp`, hoặc `Gif` tùy theo enum của thư viện. |
| *Điều gì sẽ xảy ra nếu chuỗi dữ liệu chứa ký tự không hợp lệ?* | Trình tạo sẽ ném ra `ArgumentException`. Hãy xác thực dữ liệu với bộ ký tự của ký hiệu trước khi gọi constructor. |
| *Có thể đặt chiều cao tối thiểu trong khi vẫn giữ tự động thu phóng không?* | Sử dụng `gen.parameters.barcode.bar_height.min_pixels = <value>` (nếu SDK cung cấp thuộc tính `min_pixels`). Điều này ngăn mã vạch thu nhỏ dưới mức có thể đọc được. |
| *Tôi có cần giải phóng bộ tạo không?* | Lớp `BarcodeGenerator` triển khai `IDisposable` trong .NET; trong Python bộ thu gom rác sẽ xử lý, nhưng bạn có thể gọi `gen.dispose()` nếu tạo nhiều instance trong vòng lặp. |

## Mẹo cho việc sử dụng trong môi trường sản xuất

* **Mẹo chuyên nghiệp:** Lưu các giá trị X‑dimension và chiều cao trong tệp cấu hình để có thể điều chỉnh mà không cần biên dịch lại.
* **Cẩn thận với:** Sử dụng chiều cao quá nhỏ đối với ký hiệu đã chọn; máy quét có thể không đọc được mã vạch.
* **Lưu ý về hiệu năng:** Tạo một loạt lớn mã vạch nhanh hơn khi bạn tái sử dụng một instance `BarcodeGenerator` duy nhất và chỉ thay đổi thuộc tính `code_text` giữa các lần lưu.

## Kết luận

**Ví dụ tạo mã vạch** này minh họa cả **cách tạo mã Planet** với kích thước tự động và **cách đặt chiều cao mã vạch** thủ công cho mã RM4SCC. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp việc tạo mã vạch vào bất kỳ ứng dụng Python nào, tùy chỉnh kích thước và tạo ra các tệp PNG sẵn sàng cho việc in hoặc hiển thị kỹ thuật số.

### Các bước tiếp theo

* Khám phá các ký hiệu khác như `EncodeTypes.Postnet` hoặc `EncodeTypes.Code128` – mẫu sử dụng vẫn giống nhau.
* Thử nghiệm **cách đặt chiều cao mã vạch** cho QR code hoặc DataMatrix; hầu hết các thư viện đều cung cấp thuộc tính `bar_height` tương tự.
* Kết hợp trình tạo với thư viện PDF để nhúng mã vạch trực tiếp vào hoá đơn hoặc nhãn vận chuyển.

Hãy tự do điều chỉnh kịch bản, chia sẻ kết quả và cho chúng tôi biết bạn sẽ thêm loại mã vạch nào tiếp theo!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}