---
category: general
date: 2026-09-29
description: Hiển thị tên sản phẩm trong Python khi in ngày phát hành và truy xuất
  chi tiết phiên bản từ thư viện barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: vi
lastmod: 2026-09-29
og_description: Hiển thị tên sản phẩm trong Python và học cách in ngày phát hành,
  lấy phiên bản, và hiển thị phiên bản phụ chỉ với vài dòng mã.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Hiển thị tên sản phẩm và thông tin phiên bản trong Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Hiển thị tên sản phẩm và thông tin phiên bản trong Python
url: /vi/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hiển thị tên sản phẩm và thông tin phiên bản trong Python

Nếu bạn cần **hiển thị tên sản phẩm** từ một thư viện, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn cũng sẽ học cách **in ngày phát hành**, **lấy phiên bản**, và **hiển thị phiên bản phụ** bằng mã Python ngắn gọn.

Nhiều nhà phát triển tích hợp tính năng quét hoặc tạo mã vạch và phải hiển thị siêu dữ liệu của thư viện cho người dùng hoặc trong log. Bài học này bao gồm mọi thứ cần thiết để truy xuất và trình bày thông tin đó một cách đáng tin cậy.

## Những gì bạn sẽ học

* Truy xuất thông tin phiên bản từ thư viện `barcode`.  
* **Hiển thị tên sản phẩm** cùng với số phiên bản chính và phụ.  
* **In ngày phát hành** ở định dạng dễ đọc cho con người.  
* Xử lý các thuộc tính thiếu một cách nhẹ nhàng.  

**Yêu cầu trước**  
* Python 3.8 trở lên.  
* Truy cập vào gói `barcode` (cài đặt bằng `pip install python-barcode` hoặc thư viện cung cấp `BuildVersionInfo`).  

---

## Cách hiển thị tên sản phẩm và thông tin phiên bản trong Python

Bước đầu tiên là nhập thư viện và gọi phương thức trả về một đối tượng version‑info. Đối tượng này chứa các thuộc tính như `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR`, và `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Tại sao cách này hoạt động**  
`BuildVersionInfo()` trả về một đối tượng nhẹ, các thuộc tính của nó được khởi tạo khi import. Truy cập trực tiếp các thuộc tính tránh việc I/O thêm và đảm bảo dữ liệu hiển thị khớp với phiên bản thư viện mà mã của bạn đang sử dụng.

### Kết quả mong đợi

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Các giá trị cụ thể phụ thuộc vào phiên bản đã cài đặt của thư viện barcode.

---

## Cách lấy phiên bản từ thư viện barcode

Nếu bạn chỉ cần các số phiên bản, có thể bỏ qua việc in tên sản phẩm và tập trung vào các trường số.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Các thuộc tính `PRODUCT_MAJOR` và `PRODUCT_MINOR` tuân theo quy tắc versioning ngữ nghĩa, cho phép bạn so sánh các phiên bản một cách lập trình.*

---

## Cách in ngày phát hành

Ngày phát hành được lưu dưới dạng chuỗi theo định dạng `YYYY‑MM‑DD`. Để trình bày nó theo một locale khác, trước tiên chuyển đổi sang đối tượng `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Mẹo:** Luôn xác thực chuỗi ngày trước khi phân tích để tránh `ValueError` khi thư viện thay đổi định dạng.

---

## Hiển thị phiên bản phụ cùng với phiên bản chính

Đôi khi bạn cần hiển thị phiên bản phụ riêng biệt, ví dụ khi ghi log cảnh báo tương thích.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Sử dụng phiên bản phụ để kích hoạt các flag tính năng:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Xử lý các thuộc tính thiếu (trường hợp biên)

Các bản phát hành cũ hơn của thư viện barcode có thể không cung cấp đầy đủ các thuộc tính. Bao bọc việc truy cập thuộc tính bằng `getattr` với giá trị mặc định hợp lý.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Mô hình này đảm bảo script của bạn không bao giờ bị crash vì thiếu trường, làm cho nó mạnh mẽ cho các pipeline CI có thể chạy trên nhiều phiên bản thư viện khác nhau.

---

## Ví dụ đầy đủ, có thể chạy được

Dưới đây là script hoàn chỉnh kết hợp tất cả các thực hành tốt: xác thực thuộc tính, định dạng ngày, và đầu ra rõ ràng.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Chạy script này trên hệ thống đã cài đặt thư viện barcode sẽ cho ra kết quả tương tự như ví dụ trước, nhưng bây giờ nó đã bảo vệ khỏi các trường thiếu và định dạng ngày một cách đẹp mắt.

---

## Kết luận

Bây giờ bạn đã biết cách **hiển thị tên sản phẩm**, **in ngày phát hành**, **lấy phiên bản**, **in sản phẩm**, và **hiển thị phiên bản phụ** bằng quy trình Python đơn giản. Ví dụ hoàn chỉnh minh họa cách truy cập thuộc tính một cách đáng tin cậy, xử lý ngày tháng, và so sánh phiên bản — những kỹ năng bạn có thể tái sử dụng cho bất kỳ thư viện bên thứ ba nào cung cấp đối tượng siêu dữ liệu.

**Bước tiếp theo**

* Khám phá các phương thức siêu dữ liệu khác của thư viện barcode, chẳng hạn như `BuildCommitInfo()`.  
* Tích hợp đầu ra vào framework logging (ví dụ, `logging.info`).  
* So sánh các phiên bản một cách lập trình để thực thi yêu cầu tối thiểu phiên bản trong ứng dụng của bạn.

Hãy tự do thử nghiệm với các định dạng đầu ra khác nhau hoặc mở rộng script để ghi thông tin vào file cho mục đích kiểm toán. Chúc bạn lập trình vui vẻ!  

![Terminal output showing product name and version details](image.png "Terminal output")

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [hiển thị tên sản phẩm bằng thư viện Python barcode – hướng dẫn chi tiết](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Cách in phiên bản của Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Cách tạo mã vạch với Aspose.BarCode trong Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}