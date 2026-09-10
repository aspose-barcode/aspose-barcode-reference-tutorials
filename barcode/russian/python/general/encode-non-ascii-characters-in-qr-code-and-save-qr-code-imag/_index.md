---
category: general
date: 2026-09-10
description: Кодировать не‑ASCII символы в QR‑коде и сохранять изображение QR‑кода
  с помощью простого Python‑строителя. Следуйте пошаговому руководству, используя
  ExtCodetextBuilder и BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: ru
lastmod: 2026-09-10
og_description: Кодировать не‑ASCII символы в QR‑коде и сохранять изображение QR‑кода
  с помощью Python. Этот учебник показывает, как создать расширенный текст кода, сгенерировать
  QR‑код и сохранить изображение.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Кодирование не‑ASCII символов в QR‑коде и сохранение изображения QR‑кода
  — пошаговое руководство по Python
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Кодировать не‑ASCII символы в QR‑коде и сохранить изображение QR‑кода
url: /ru/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Кодировать не‑ASCII символы в QR‑коде и сохранять изображение QR‑кода

Если вам нужно **закодировать не‑ASCII символы** в QR‑коде, это руководство покажет, как именно это сделать, а затем **сохранить изображение QR‑кода** на диск. Независимо от того, работаете ли вы с русским, китайским или эмодзи, ExtCodetextBuilder позволяет смешивать обычный текст и сегменты, закодированные с помощью ECI, без ручного управления байтами.

Вы узнаете, как создать строку расширенного codetext, сгенерировать QR‑код, который понимает эту строку, и, наконец, записать изображение штрихкода в файл. В руководстве предполагаются базовые знания Python и наличие установленного SDK `barcode`.

## Требования

* Установлен Python 3.8+.
* Пакет Python `barcode` (или соответствующий SDK), предоставляющий `ExtCodetextBuilder`, `CodetextEncodingType` и `BarcodeGenerator`.
* Права записи в каталог, где вы хотите **сохранить изображение QR‑кода**.

Вы можете установить SDK с помощью pip (замените `barcode-sdk` на фактическое имя пакета):

```bash
pip install barcode-sdk
```

## Шаг 1: Создать расширенный codetext builder

Первый шаг — создать экземпляр `ExtCodetextBuilder`. Этот объект собирает несколько текстовых сегментов и формирует одну строку, которую может интерпретировать символьная система QR‑кода.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Почему это важно*: QR‑коды поддерживают **расширенный codetext**, что означает возможность внедрять несколько режимов кодирования (plain, ECI и т.д.) в один штрихкод. Builder абстрагирует низкоуровневое форматирование, требуемое спецификацией QR.

## Шаг 2: Добавить сегмент обычного текста

Обычный текст — режим по умолчанию и работает с ASCII‑символами. Добавление его первым обеспечивает читаемую альтернативу для сканеров, игнорирующих ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Если пропустить этот шаг, QR‑код будет содержать только сегмент ECI, который некоторые старые считыватели могут некорректно декодировать.

## Шаг 3: Добавить сегмент, закодированный с помощью ECI, для не‑ASCII символов

Чтобы включить символы за пределами диапазона ASCII — такие как кириллица, китайские иероглифы или эмодзи — необходимо указать кодировку ECI (Extended Channel Interpretation). Здесь мы используем UTF‑8 для русского слова «Привет».

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Почему это работает*: Спецификация QR определяет значения ECI, которые указывают сканеру, какой набор символов использовать. Без маркера ECI необработанные байты будут интерпретированы как ISO‑8859‑1, что приведёт к искажённому выводу.

## Шаг 4: Получить объединённую строку расширенного codetext

После добавления всех необходимых сегментов вызовите `get_extended_codetext()`, чтобы получить окончательную строку, ожидаемую генератором штрихкода.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Выведенное значение выглядит как серия управляющих символов, за которыми следует фактический текст, но вам никогда не придётся разбирать его вручную.

## Шаг 5: Сгенерировать QR‑код, используя расширенный codetext

Теперь создайте `BarcodeGenerator`, установите символьную систему в QR (единственная распространённая 2‑D система, поддерживающая расширенный codetext) и передайте объединённую строку.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Совет*: Если попытаться выполнить тот же процесс с Code‑128 или DataMatrix, SDK выбросит исключение, поскольку эти форматы не могут интерпретировать маркеры ECI.

## Шаг 6: Сохранить изображение QR‑кода

Наконец, запишите штрихкод в файл PNG. Здесь вы **сохраняете изображение QR‑кода** для последующего использования.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Убедитесь, что папка `output` существует, или создайте её с помощью `os.makedirs('output', exist_ok=True)` перед вызовом `save`.

### Полный исполняемый пример

Объединив все шаги, вы получаете автономный скрипт, который можно запустить сразу:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Ожидаемый вывод** (консоль):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Открытие `qr_extended.png` любым QR‑сканером отобразит `HelloWorldПривет`. Сканеры, поддерживающие ECI, корректно отобразят кириллические символы; остальные покажут только ASCII‑часть.

## Часто задаваемые вопросы и пограничные случаи

| Question | Answer |
|----------|--------|
| *Можно ли использовать другие кодировки, например Shift‑JIS?* | Да. Замените `CodetextEncodingType.UTF_8` на `CodetextEncodingType.SHIFT_JIS` и предоставьте соответствующий текст. |
| *Что делать, если объединённые данные превышают ёмкость QR?* | У QR‑кодов есть ограничения по версиям (до 177 × 177 модулей). Если builder выдаёт исключение о размере, либо увеличьте уровень коррекции ошибок, либо разбейте данные на несколько QR‑кодов. |
| *Нужно ли задавать конкретную версию QR?* | SDK автоматически выбирает наименьшую версию, подходящую под данные. При необходимости можно принудительно задать версию с помощью `qr_generator.set_qr_version(10)`. |
| *Будет ли изображение прозрачным?* | По умолчанию SDK сохраняет PNG с белым фоном. При необходимости прозрачности используйте `qr_generator.set_background_color(Color.Transparent)` перед `save`. |

## Заключение

В этом руководстве вы узнали, как **закодировать не‑ASCII символы** в QR‑коде с помощью `ExtCodetextBuilder`, а затем **сохранить изображение QR‑кода** с помощью `BarcodeGenerator`. Процесс включает построение строки расширенного codetext, добавление как обычных, так и ECI‑закодированных сегментов, генерацию QR‑символьной системы и, наконец, запись файла изображения.

Отсюда вы можете исследовать:

* Добавление дополнительных ECI‑сегментов (разные языки или эмодзи).
* Регулирование уровней коррекции ошибок QR для большей надёжности.
* Встраивание сгенерированного PNG в PDF‑файлы или веб‑страницы.

Удачной разработки и приятного создания многоязычных QR‑кодов!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать изображение QR‑кода в Python с Aspose.Barcode – Полное руководство](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Создать штрихкод Code128 с Aspose.Barcode Python – Полное руководство](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Отображение названия продукта с помощью библиотеки Python barcode – пошаговое руководство](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}