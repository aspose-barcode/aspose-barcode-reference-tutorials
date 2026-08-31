---
category: general
date: 2026-07-15
description: Как генерировать изображение QR‑кода в Python с помощью Aspose.Barcode.
  Узнайте пошаговое создание QR‑кода с расширенным кодовым текстом, кодированием ECI
  и поддержкой Unicode.
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
language: ru
lastmod: 2026-07-15
og_description: Как сгенерировать изображение QR‑кода в Python с помощью Aspose.Barcode.
  Это руководство проведёт вас через процесс создания QR‑кодов с использованием расширенного
  текста кода, кодировки ECI и символов Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Как сгенерировать изображение QR‑кода в Python – Полный учебник Aspose.Barcode
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
title: Как сгенерировать изображение QR‑кода в Python с помощью Aspose.Barcode – полное
  руководство
url: /ru/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение QR‑кода в Python с помощью Aspose.Barcode – Полное руководство

Вы когда‑нибудь задумывались **как создать изображение QR‑кода** в Python, не перебирая десятки библиотек? Вы не одиноки. Многие разработчики нуждаются в надёжном способе внедрять многоязычный текст — например русский, арабский или эмодзи — в QR‑код, а встроенные библиотеки часто не справляются.

Дело в том, что Aspose.Barcode для Python делает это удивительно простым. В этом руководстве мы пройдём все шаги, от установки пакета до создания строки расширенного кода, которая сочетает обычный ASCII с Unicode, закодированным через ECI. К концу у вас будет готовое к использованию изображение QR‑кода, сохранённое на диске.

## Что охватывает это руководство

- Установка **Aspose.Barcode** для Python (совместимо с Python 3.8+)
- Создание **extended codetext**, объединяющего обычные и Unicode‑сегменты
- Использование **ECI encoding** для корректного отображения русских символов
- Настройка `BarcodeGenerator` для создания QR‑кода
- Сохранение полученного изображения в формате PNG
- Советы, распространённые подводные камни и идеи для дальнейших шагов (например, добавление логотипов или настройка уровня коррекции ошибок)

Предыдущий опыт работы с Aspose не требуется; достаточно базовой настройки Python и интереса к QR‑кодам.

---

## Prerequisites

Before we dive in, make sure you have:

1. **Python 3.8 or newer** installed on your machine.  
2. A **virtual environment** (optional but recommended) to keep dependencies tidy.  
3. **pip** access to install the `aspose-barcode` package.  
4. Write permission to a folder where the generated PNG will be saved.

Если что‑то из перечисленного вам незнакомо, сделайте паузу и настройте необходимое — как только всё будет готово, остальное будет проще простого.

---

## Step 1: Install Aspose.Barcode for Python

The first hurdle is getting the library. Aspose distributes its packages on PyPI, so a single `pip` command does the trick:

```bash
pip install aspose-barcode
```

> **Pro tip:** If you’re inside a virtual environment, you’ll keep your global site‑packages clean. If you hit permission errors, prepend `--user` or run the command with `sudo` (though the latter is rarely needed on modern setups).

After the install finishes, you can verify it with:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

If the version prints without complaint, you’re good to go.

---

## Step 2: Create an **Extended Codetext Builder** Instance

Aspose.Barcode provides the `ExtCodetextBuilder` class to compose complex QR payloads. Think of it as a tiny text editor that knows how to prepend the right control characters for each segment.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Why use a builder? Directly concatenating raw bytes is error‑prone; the builder guarantees the correct ECI (Extended Channel Interpretation) switches, so your QR scanner can decode every language correctly.

---

## Step 3: Start Fresh (Optional but Clean)

If you ever reuse the same builder instance, calling `clear()` wipes any previous data. It’s a safety net that prevents stray segments from leaking into the next QR.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

You can skip this line the first time you run the script, but keeping it makes the code idempotent—useful when you embed this logic inside a function that might be called repeatedly.

---

## Step 4: Add a Plain (Un‑encoded) Segment

Most QR codes start with a simple ASCII string—perhaps an identifier or a URL. The `add_plain_codetext` method adds exactly that, without any ECI marker.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

In this example we use `"HelloWorld"` as a placeholder. Replace it with whatever you need—maybe a product SKU or a short message.

---

## Step 5: Add an **ECI‑Encoded** Segment (UTF‑8 = 26)

Now for the multilingual part. The ECI value **26** corresponds to UTF‑8, the de‑facto standard for Unicode. By passing `26` together with a Russian phrase, we tell the QR scanner to switch to UTF‑8 before reading the following characters.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

You can swap `26` for other ECI values (e.g., `27` for ISO‑8859‑1) if you need a different encoding. The builder will automatically insert the proper control characters.

---

## Step 6: Retrieve the Combined Extended Codetext

Once all segments are added, pull the final string that the QR generator will consume. This string contains invisible control sequences, but you can still print it for debugging.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

The console output will look garbled (because of embedded control bytes), which is perfectly normal. The important part is that the builder has stitched the plain and Unicode parts together correctly.

---

## Step 7: Configure the Barcode Generator

Now we hand the extended codetext to Aspose’s `BarcodeGenerator`. Set the symbology to `QR` and assign the combined string to `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

You can tweak additional properties here—like `resolution`, `error_correction_level`, or `foreground_color`. Those options are covered in the Aspose docs, but for a basic image the defaults work well.

---

## Step 8: Save the Generated QR Code Image

Finally, write the QR code to disk. The `save` method accepts a file path and an optional format; PNG is a safe default.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Open the resulting `qr_extended.png` with any image viewer. Scanning it with a smartphone should reveal two separate messages: “HelloWorld” and “Привет”. Most modern QR readers automatically handle the ECI switch.

---

## Full Working Example

Putting it all together, here’s the complete script you can copy‑paste and run:

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

**Expected output** (console):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Open `qr_extended.png` → scan → you’ll see “HelloWorld” followed by “Привет”.

---

## Common Questions & Edge Cases

### 1. *What if I need more than two segments?*  
Simply call `add_plain_codetext` or `add_eci_codetext` as many times as you like. The builder maintains the correct ordering, so the QR code will contain each segment in the sequence you add them.

### 2. *Can I embed emojis?*  
Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and pass the emoji string, e.g., `builder.add_eci_codetext(26, "🚀")`. The QR will display the rocket emoji on supporting scanners.

### 3. *What if the QR becomes too dense?*  
QR codes have version limits. If you exceed the data capacity, Aspose will automatically bump the version up to the next size, but the image might become larger. To control size, you can lower the error correction level:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Do I need to worry about character sets other than UTF‑8?*  
Only if you have legacy systems that require a specific encoding (e.g., ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.

### 5. *How do I add a logo in the center?*  
Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`. Load an image with Pillow (`from PIL import Image`) and assign it:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

The logo will be overlaid while preserving scannability (Aspose automatically adjusts quiet zones).

---

## Pro Tips for Production Use

- **Cache the builder** if you generate the same QR repeatedly; it avoids rebuilding the extended string each time.
- **Validate the output** with a unit test that decodes the QR (e.g., using `zxing` or `pyzbar`) to ensure your ECI switches are correct.
- **Set a deterministic file name** (maybe include a hash of the payload) to avoid overwriting existing images.
- **Mind the licensing**: Aspose.Barcode is commercial software. The free evaluation works for development, but a license is required for production deployment.

---

## Next Steps & Related Topics

Now that you know **how to generate QR code

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Как сгенерировать изображение штрих‑кода в Java с помощью Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Как сгенерировать Aztec‑штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как создать расширенный codetext для dotcode с помощью Aspose.BarCode для .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}