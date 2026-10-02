---
category: general
date: 2026-08-19
description: Как создать штрих‑код с ECI с помощью Aspose.Barcode для Python. Узнайте,
  как добавить данные ECI, смешать обычный текст и сохранить изображение в одном понятном
  руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: ru
lastmod: 2026-08-19
og_description: Как создать штрих‑код с ECI с помощью Aspose.Barcode для Python. Следуйте
  этому руководству, чтобы узнать, как добавить данные ECI, настроить внешний вид
  и сохранить результат.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Как создать штрих‑код с ECI с помощью Aspose.Barcode Python — пошагово
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Как сгенерировать штрих‑код с ECI, используя Aspose.Barcode Python
url: /ru/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код с ECI с помощью Aspose.Barcode Python

Если вам нужно узнать **как генерировать штрих‑код**, содержащий как обычные символы, так и данные, закодированные с помощью ECI, это руководство покажет полный процесс. Вы увидите точно **как добавить eci** секции, настроить размер и записать изображение на диск с помощью одного исполняемого скрипта.

В руководстве рассматривается:

* Получение версии библиотеки Aspose.Barcode (необязательно, но полезно для отладки).  
* Формирование строки расширенного codetext, смешивающей обычные и ECI‑закодированные символы.  
* Создание генератора штрих‑кода для символьной системы, поддерживающей расширенный codetext.  
* Настройка размеров штрих‑кода и сохранение конечного PNG‑файла.

Никакой внешней документации не требуется; скопируйте код, запустите его, и вы получите изображение штрих‑кода, включающего китайские символы, закодированные с помощью ECI 26 (UTF‑8).

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* Установлен Python 3.8 или новее.  
* Пакет `aspose-barcode` установлен (`pip install aspose-barcode`).  
* Права на запись в папку, куда вы планируете сохранять PNG‑файл.

Если вы используете виртуальное окружение, сначала активируйте его, чтобы изолировать зависимости.

## Шаг 1: Проверка версии Aspose.Barcode (необязательно)

Знание точной версии библиотеки помогает, когда нужно сообщать об ошибках или сравнивать возможности разных релизов.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Почему это важно*: Вывод версии подтверждает, что среда выполнения соответствует документации, которой вы следуете. Разные версии могут поддерживать разные значения ECI, поэтому это быстрая проверка корректности.

## Шаг 2: Создание расширенного codetext с обычными и ECI‑закодированными частями

Aspose.Barcode предоставляет `ExtCodetextBuilder` для конкатенации обычных данных и ECI‑закодированных сегментов. В этом примере мы смешиваем числовую строку с китайскими символами.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Пояснение*:  
* `add_plain_codetext` вставляет данные, которые символьная система штрих‑кода воспринимает как обычные символы.  
* `add_eci_codetext` указывает генератору добавить индикатор ECI (здесь **26**, соответствующий UTF‑8) перед переданным текстом. Это именно **как добавить eci** данные в штрих‑код.

Вы можете вызывать `add_eci_codetext` несколько раз, чтобы встроить несколько блоков разных языков. Builder автоматически обрабатывает необходимые управляющие последовательности.

## Шаг 3: Выбор символьной системы, поддерживающей расширенный codetext

Не каждый тип штрих‑кода может хранить сегменты ECI. Code 128, QR и Data Matrix — распространённые варианты. В примере используется Code 128, потому что он широко поддерживается и хорошо работает с смешанными буквенно‑цифровыми данными.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Почему Code 128?*: Он принимает весь диапазон ASCII и управляющие последовательности ECI, генерируемые builder‑ом, что делает его идеальным для сценария «как генерировать штрих‑код», где смешаны обычный и закодированный текст.

## Шаг 4: Настройка внешнего вида штрих‑кода

Вы можете управлять размером, высотой, отступами и многими другими визуальными параметрами через объект `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Совет*: Если планируете печатать штрих‑код, увеличьте `x_dimension` и `bar_height` пропорционально, чтобы сохранить читаемость при целевом DPI.

## Шаг 5: Сохранение изображения штрих‑кода

Наконец, запишите сгенерированное изображение в файл. Aspose.Barcode поддерживает PNG, JPEG, BMP и многие другие форматы.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Убедитесь, что папка `output` существует, или создайте её с помощью `os.makedirs("output", exist_ok=True)` перед вызовом `save`.

### Ожидаемый результат

При открытии `extended_codetext.png` вы должны увидеть штрих‑код Code 128, который кодирует числовую строку `1234567890`, за которой следуют китайские символы «特殊字符». Сканирование штрих‑кода современным сканером, поддерживающим ECI, вернёт исходную смешанную строку.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Штрих‑код, сгенерированный примером как генерировать штрих‑код"}

## Часто задаваемые вопросы и особые случаи

### Что если мне нужен другой набор символов?

Выберите соответствующее значение ECI из таблицы ISO/IEC 18004. Например, ECI 27 представляет ISO‑8859‑1 (Latin‑1). Замените числовой идентификатор в `add_eci_codetext` соответственно.

### Можно ли встроить более одного блока ECI?

Да. Вызывайте `add_eci_codetext` несколько раз. Builder вставит необходимые коды переключения ECI между блоками, сохраняя порядок их добавления.

### Поддерживает ли генератор QR‑коды с ECI?

Абсолютно. Замените `barcode.Symbology.CODE_128` на `barcode.Symbology.QR` и настройте любые QR‑специфические параметры (например, уровень коррекции ошибок) через `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

## Полный, исполняемый скрипт

Ниже приведена полная программа, которую вы можете скопировать‑вставить в файл с именем `generate_extended_barcode.py` и запустить напрямую.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как генерировать изображение штрих‑кода с настройкой дополнительного пространства с помощью Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Как генерировать изображение штрих‑кода в Java с Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Как генерировать DataMatrix штрих‑код с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}