---
category: general
date: 2026-07-15
description: Cách tạo hình ảnh mã QR trong Python bằng Aspose.Barcode. Tìm hiểu quy
  trình tạo mã QR từng bước với codetext mở rộng, mã hóa ECI và hỗ trợ Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: vi
lastmod: 2026-07-15
og_description: Cách tạo hình ảnh mã QR trong Python với Aspose.Barcode. Hướng dẫn
  này sẽ chỉ cho bạn cách tạo mã QR bằng cách sử dụng codetext mở rộng, mã hóa ECI
  và ký tự Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Cách tạo hình ảnh QR Code trong Python – Hướng dẫn đầy đủ Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Cách tạo hình ảnh mã QR trong Python với Aspose.Barcode – Hướng dẫn đầy đủ
url: /vi/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Hình Ảnh QR Code trong Python với Aspose.Barcode – Hướng Dẫn Đầy Đủ

Bạn đã bao giờ tự hỏi **cách tạo hình ảnh QR code** trong Python mà không phải tìm kiếm qua hàng chục thư viện chưa? Bạn không phải là người duy nhất. Nhiều nhà phát triển cần một cách đáng tin cậy để nhúng văn bản đa ngôn ngữ—như tiếng Nga, tiếng Ả Rập, hoặc biểu tượng cảm xúc—trong một QR code, và các thư viện có sẵn thường không đáp ứng được.

Thực tế là: Aspose.Barcode cho Python làm cho việc này trở nên vô cùng dễ dàng. Trong hướng dẫn này chúng ta sẽ đi qua các bước cụ thể, từ cài đặt gói đến tạo một chuỗi codetext mở rộng kết hợp ASCII thuần với Unicode được mã hoá bằng ECI. Khi kết thúc, bạn sẽ có một hình ảnh QR code sẵn sàng sử dụng lưu trên đĩa.

## Nội Dung Hướng Dẫn Này

- Cài đặt **Aspose.Barcode** cho Python (tương thích với Python 3.8+)
- Xây dựng **extended codetext** kết hợp các đoạn plain và Unicode
- Sử dụng **ECI encoding** để hiển thị đúng ký tự tiếng Nga
- Cấu hình `BarcodeGenerator` để tạo QR code
- Lưu hình ảnh đầu ra ở định dạng PNG
- Mẹo, các lỗi thường gặp, và ý tưởng bước tiếp theo (như thêm logo hoặc điều chỉnh mức sửa lỗi)

Bạn không cần kinh nghiệm trước với Aspose; chỉ cần một môi trường Python cơ bản và sự tò mò về QR code.

---

## Yêu Cầu Trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Python 3.8 hoặc mới hơn** đã được cài đặt trên máy của bạn.  
2. Một **virtual environment** (tùy chọn nhưng được khuyến nghị) để quản lý các phụ thuộc gọn gàng.  
3. Quyền truy cập **pip** để cài đặt gói `aspose-barcode`.  
4. Quyền ghi vào một thư mục nơi PNG được tạo sẽ được lưu.

Nếu bất kỳ mục nào trên còn lạ, hãy tạm dừng và thiết lập chúng—khi đã sẵn sàng, phần còn lại sẽ rất dễ dàng.

---

## Bước 1: Cài Đặt Aspose.Barcode cho Python

Rào cản đầu tiên là lấy được thư viện. Aspose phân phối các gói của mình trên PyPI, vì vậy một lệnh `pip` duy nhất là đủ:

```bash
pip install aspose-barcode
```

> **Mẹo:** Nếu bạn đang làm việc trong một virtual environment, bạn sẽ giữ sạch các site‑packages toàn cục. Nếu gặp lỗi quyền, hãy thêm `--user` vào trước lệnh hoặc chạy lệnh với `sudo` (mặc dù thường không cần trên các thiết lập hiện đại).

Sau khi cài đặt hoàn tất, bạn có thể kiểm tra bằng:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Nếu phiên bản được in ra mà không có lỗi, bạn đã sẵn sàng.

---

## Bước 2: Tạo Một Instance của **Extended Codetext Builder**

Aspose.Barcode cung cấp lớp `ExtCodetextBuilder` để tạo các payload QR phức tạp. Hãy nghĩ nó như một trình soạn thảo văn bản nhỏ biết cách chèn các ký tự điều khiển phù hợp cho mỗi đoạn.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Tại sao phải dùng builder? Việc nối trực tiếp các byte thô dễ gây lỗi; builder đảm bảo các chuyển đổi ECI (Extended Channel Interpretation) đúng, vì vậy máy quét QR của bạn có thể giải mã mọi ngôn ngữ một cách chính xác.

---

## Bước 3: Bắt Đầu Mới (Tùy Chọn nhưng Gọn Gàng)

Nếu bạn tái sử dụng cùng một instance của builder, gọi `clear()` sẽ xóa mọi dữ liệu trước đó. Đây là một lớp bảo vệ ngăn các đoạn thừa rò rỉ vào QR tiếp theo.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Bạn có thể bỏ qua dòng này lần đầu chạy script, nhưng giữ lại sẽ làm cho mã trở nên idempotent—hữu ích khi bạn nhúng logic này vào một hàm có thể được gọi nhiều lần.

---

## Bước 4: Thêm Đoạn Plain (Không Mã Hoá)

Hầu hết QR code bắt đầu bằng một chuỗi ASCII đơn giản—có thể là một định danh hoặc URL. Phương thức `add_plain_codetext` thêm chính đoạn đó, mà không có bất kỳ dấu hiệu ECI nào.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

Trong ví dụ này chúng ta dùng `"HelloWorld"` làm chỗ giữ. Thay thế nó bằng bất kỳ gì bạn cần—có thể là SKU sản phẩm hoặc một tin nhắn ngắn.

---

## Bước 5: Thêm Đoạn **ECI‑Encoded** (UTF‑8 = 26)

Bây giờ là phần đa ngôn ngữ. Giá trị ECI **26** tương ứng với UTF‑8, chuẩn de‑facto cho Unicode. Bằng cách truyền `26` cùng với một câu tiếng Nga, chúng ta báo cho máy quét QR chuyển sang UTF‑8 trước khi đọc các ký tự tiếp theo.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Bạn có thể thay `26` bằng các giá trị ECI khác (ví dụ, `27` cho ISO‑8859‑1) nếu cần mã hoá khác. Builder sẽ tự động chèn các ký tự điều khiển phù hợp.

---

## Bước 6: Lấy Extended Codetext Đã Kết Hợp

Khi tất cả các đoạn đã được thêm, lấy chuỗi cuối cùng mà trình tạo QR sẽ sử dụng. Chuỗi này chứa các chuỗi điều khiển ẩn, nhưng bạn vẫn có thể in ra để gỡ lỗi.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Đầu ra console sẽ trông rối rắm (do các byte điều khiển nhúng), điều này hoàn toàn bình thường. Điều quan trọng là builder đã ghép đúng phần plain và Unicode lại với nhau.

---

## Bước 7: Cấu Hình Barcode Generator

Bây giờ chúng ta truyền extended codetext cho `BarcodeGenerator` của Aspose. Đặt symbology thành `QR` và gán chuỗi đã kết hợp cho `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Bạn có thể điều chỉnh các thuộc tính bổ sung ở đây—như `resolution`, `error_correction_level`, hoặc `foreground_color`. Những tùy chọn này được mô tả trong tài liệu Aspose, nhưng đối với hình ảnh cơ bản, các giá trị mặc định hoạt động tốt.

---

## Bước 8: Lưu Hình Ảnh QR Code Đã Tạo

Cuối cùng, ghi QR code ra đĩa. Phương thức `save` nhận một đường dẫn file và tùy chọn định dạng; PNG là mặc định an toàn.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Mở file `qr_extended.png` vừa tạo bằng bất kỳ trình xem ảnh nào. Quét nó bằng điện thoại thông minh sẽ hiển thị hai thông điệp riêng biệt: “HelloWorld” và “Привет”. Hầu hết các trình đọc QR hiện đại tự động xử lý chuyển đổi ECI.

---

## Ví Dụ Hoàn Chỉnh Hoạt Động

Kết hợp tất cả lại, đây là script hoàn chỉnh bạn có thể sao chép và chạy:

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Kết quả mong đợi** (console):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Mở `qr_extended.png` → quét → bạn sẽ thấy “HelloWorld” tiếp theo là “Привет”.

---

## Câu Hỏi Thường Gặp & Trường Hợp Cạnh

### 1. *Nếu tôi cần hơn hai đoạn?*

Chỉ cần gọi `add_plain_codetext` hoặc `add_eci_codetext` bao nhiêu lần tùy thích. Builder duy trì thứ tự đúng, vì vậy QR code sẽ chứa mỗi đoạn theo thứ tự bạn thêm.

### 2. *Tôi có thể nhúng emoji không?*

Có—emoji chỉ là các ký tự Unicode. Sử dụng ECI UTF‑8 (giá trị 26) và truyền chuỗi emoji, ví dụ `builder.add_eci_codetext(26, "🚀")`. QR sẽ hiển thị biểu tượng tên lửa trên các máy quét hỗ trợ.

### 3. *Nếu QR code trở nên quá dày?*

QR code có giới hạn phiên bản. Nếu bạn vượt quá dung lượng dữ liệu, Aspose sẽ tự động nâng phiên bản lên kích thước tiếp theo, nhưng hình ảnh có thể lớn hơn. Để kiểm soát kích thước, bạn có thể giảm mức sửa lỗi:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Tôi có cần lo lắng về bộ ký tự khác ngoài UTF‑8 không?*

Chỉ khi bạn có hệ thống cũ yêu cầu một mã hoá cụ thể (ví dụ, ISO‑8859‑1). Trong trường hợp đó, thay `26` bằng giá trị ECI phù hợp (xem bảng ECI của Aspose). Đối với hầu hết các ứng dụng hiện đại, UTF‑8 là lựa chọn an toàn nhất.

### 5. *Làm sao để thêm logo ở trung tâm?*

Aspose.Barcode hỗ trợ `barcode.generator.QRCodeParameters.logo_image`. Tải một hình ảnh bằng Pillow (`from PIL import Image`) và gán nó:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

Logo sẽ được chồng lên trong khi vẫn giữ khả năng quét (Aspose tự động điều chỉnh vùng yên tĩnh).

---

## Mẹo Chuyên Nghiệp cho Sản Xuất

- **Cache builder** nếu bạn tạo QR giống nhau nhiều lần; nó tránh việc xây dựng lại chuỗi mở rộng mỗi lần.
- **Xác thực đầu ra** bằng một unit test giải mã QR (ví dụ, dùng `zxing` hoặc `pyzbar`) để đảm bảo các chuyển đổi ECI của bạn đúng.
- **Đặt tên file có tính quyết định** (có thể bao gồm hash của payload) để tránh ghi đè lên các hình ảnh hiện có.
- **Lưu ý giấy phép**: Aspose.Barcode là phần mềm thương mại. Bản dùng thử miễn phí phù hợp cho phát triển, nhưng cần giấy phép cho triển khai sản xuất.

---

## Các Bước Tiếp Theo & Chủ Đề Liên Quan

Bây giờ bạn đã biết **cách tạo QR code

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao quát các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Tạo Hình Ảnh Barcode trong Java với Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Cách tạo mã vạch Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cách tạo dotcode extended codetext với Aspose.BarCode cho .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}