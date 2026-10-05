---
category: general
date: 2026-08-09
description: Создайте QR‑штрихкод на Python с помощью Aspose.BarCode. Узнайте, как
  построить расширенный код текста, настроить внешний вид и сохранить изображение —
  всё в одном руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: ru
lastmod: 2026-08-09
og_description: Создайте QR‑код в Python с помощью Aspose.BarCode. Это руководство
  показывает, как построить расширенный код текста, задать визуальные параметры и
  экспортировать изображение.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Создайте QR‑штрихкод с Aspose.BarCode в Python — полный пример кода
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Создание QR‑кода с Aspose.BarCode в Python — пошаговое руководство
url: /ru/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание QR‑штрихкода с Aspose.BarCode в Python – пошаговое руководство

Если вам нужно **создать QR‑штрихкод** в Python, этот учебник проведет вас через весь процесс с использованием библиотеки Aspose.BarCode. Независимо от того, кодируете ли вы идентификаторы продуктов, многоязычный текст или пользовательские данные, вы увидите, как построить расширенный codetext, настроить визуальные параметры и сохранить окончательное изображение в одном исполняемом скрипте.

Пример также демонстрирует, как вывести версию библиотеки, что помогает убедиться, что вы используете совместимый релиз. К концу этого руководства у вас будет готовое изображение QR‑штрихкода и чёткое понимание каждой опции конфигурации.

## Предварительные требования

- Установлен Python 3.8+.
- Пакет `aspose-barcode` (установить через `pip install aspose-barcode`).
- Базовое знакомство с синтаксисом Python.
- Права записи в каталог вывода, где будет сохранён файл PNG.

> **Совет:** Используйте виртуальное окружение, чтобы избежать конфликтов версий с другими проектами.

## Шаг 1: Проверка версии библиотеки Aspose.BarCode

Отображение версии библиотеки гарантирует, что вы используете релиз, поддерживающий расширенный codetext и кодирование QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Почему это важно:**  
Старые релизы могут не содержать класс `ExtCodetextBuilder`, необходимый для смешанных обычных и ECI‑сегментов. Подтверждение версии предотвращает ошибки выполнения позже в процессе.

## Шаг 2: Создание строки расширенного codetext

Расширенный codetext позволяет комбинировать обычные ASCII‑данные с Unicode‑сегментами (ECI), что необходимо для многоязычных QR‑кодов.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Почему это важно:**  
Метод `add_plain_codetext` сохраняет данные как стандартный ASCII, тогда как `add_eci_codetext` добавляет префикс Unicode‑блока с соответствующим обозначением ECI. Такой подход обеспечивает правильную интерпретацию японского текста сканерами QR, избегая искажённых символов.

### Распространённые варианты

- **Несколько ECI‑сегментов:** Вызывайте `add_eci_codetext` несколько раз, чтобы смешать несколько языков.
- **Разные идентификаторы ECI:** Используйте `27` для ISO‑8859‑1, `28` для ISO‑8859‑2 и т.д., в зависимости от требуемой кодировки.

## Шаг 3: Генерация QR‑штрихкода с использованием расширенного codetext

Теперь, когда у нас есть правильно отформатированная строка, мы можем создать QR‑код.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Почему это важно:**  
`EncodeTypes.QR` указывает Aspose.BarCode использовать символьный набор QR. Передача `extended_codetext` напрямую связывает смешанные данные с матрицей QR, сохраняя как обычные, так и Unicode‑части.

## Шаг 4: Настройка визуального вида (необязательно, но рекомендуется)

Точная настройка визуальных параметров штрихкода улучшает надёжность сканирования и соответствует требованиям бренда.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Почему это важно:**  
- **`x_dimension`** контролирует размер каждого модуля QR; слишком маленький размер может вызвать ошибки чтения на устройствах с низким разрешением.  
- **`border_width`** добавляет тихую зону. Некоторые сканеры требуют минимум 4‑модульную тихую зону; библиотека добавляет её автоматически, но вы можете увеличить её для дополнительной надёжности.

### Обработка граничных случаев

- **Данные высокой плотности:** Если кодируемые данные велики, возможно, потребуется увеличить `x_dimension` или выбрать более высокий уровень коррекции ошибок (через `qr_generator.parameters.qr.error_correction_level`).  
- **Прозрачный фон:** Установите `qr_generator.parameters.barcode.bg_color = Color.Transparent` для PNG‑файлов с альфа‑каналом.

## Шаг 5: Сохранение изображения QR‑штрихкода

Наконец, запишите изображение на диск в выбранном вами формате.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Почему это важно:**  
Сохранение в PNG сохраняет без потерь, что идеально для QR‑кодов, требующих чётких краёв. Если нужен другой формат для веб‑приложения, просто измените перечисление `BarCodeImageFormat`.

### Проверка результата

Откройте сохранённый файл в любом просмотрщике изображений. Вы должны увидеть QR‑код, который при сканировании возвращает объединённую строку:

```
ABC12345
こんにちは
```

Большинство современных приложений‑сканеров отображают сначала обычный сегмент, а затем корректно выводят японское приветствие.

---

## Полный исполняемый скрипт

Скопируйте весь блок ниже в файл с именем `create_qr_barcode.py` и запустите его командой `python create_qr_barcode.py`. Измените `YOUR_DIRECTORY` на папку, доступную для записи на вашем компьютере.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Запуск этого скрипта выводит версию, расширенный codetext и подтверждение создания PNG‑файла.

---

## Заключение

Теперь вы знаете, как **создать QR‑штрихкод** в Python с помощью Aspose.BarCode. В руководстве рассмотрено:

1. Проверка версии библиотеки.  
2. Создание расширенного codetext с обычными и ECI (Unicode) сегментами.  
3. Генерация QR‑кода.  
4. Настройка визуальных параметров, таких как размер модуля и ширина границы.  
5. Сохранение окончательного изображения в формате PNG.

Далее вы можете исследовать:

- Изменение уровней коррекции ошибок (`qr_generator.parameters.qr.error_correction_level`).  
- Добавление логотипа или фонового изображения (`qr_generator.parameters.qr.logo`).  
- Экспорт в другие форматы, например SVG, для масштабируемой веб‑графики.  
- Интеграцию генератора в endpoint Flask или Django для создания QR‑кодов «на лету».

Экспериментируйте с различными полезными нагрузками данных и визуальными настройками, чтобы они соответствовали брендингу вашего приложения и требованиям сканирования. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать расширенный codetext для dotcode с Aspose.BarCode для .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Создание штрихкода aspose .net — настройка текста DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Как создать тихую зону штрихкода для ITF-14 с использованием Aspose.BarCode для .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}