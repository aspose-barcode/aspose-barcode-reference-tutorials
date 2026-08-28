---
category: general
date: 2026-07-30
description: Как генерировать штрих‑код с помощью Aspose.BarCode в Python — узнайте,
  как задать размеры, изменить заливку и сохранить PNG‑изображения за считанные минуты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: ru
lastmod: 2026-07-30
og_description: Как быстро генерировать штрих‑код с помощью Aspose.BarCode в Python.
  Узнайте, как задавать размеры, менять заливку и экспортировать PNG‑файлы для любого
  приложения.
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: Как генерировать штрих‑код с Aspose.BarCode – руководство по Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: Как сгенерировать штрих‑код с помощью Aspose.BarCode в Python
url: /ru/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑коды с помощью Aspose.BarCode в Python

Когда‑то задавались вопросом **как генерировать штрих‑коды** в проекте на Python без борьбы с низкоуровневыми библиотеками изображений? Вы не одиноки. Будь то система печати транспортных этикеток, платформа для билетов или просто быстрый QR‑код для демо, умение генерировать штрих‑коды может сэкономить часы проб и ошибок.

В этом руководстве мы пройдём полный, готовый к запуску пример, показывающий **как генерировать штрих‑коды** с помощью библиотеки Aspose.BarCode, как задавать размеры и как менять заливку. В конце у вас будет два PNG‑файла — один с заполненными полосами, другой с пустыми — прямо в вашей папке вывода.

## Требования

Прежде чем приступить, убедитесь, что у вас есть:

* Python 3.8+ установлен (код работает в Windows, macOS и Linux)
* Действующая лицензия Aspose.BarCode for Python via .NET (можно начать с бесплатной пробной версии)
* Выполненная команда `pip install aspose-barcode` в вашем виртуальном окружении
* Папка, в которую можно записывать файлы — в примерах мы будем называть её `YOUR_DIRECTORY`

Никаких дополнительных сторонних пакетов не требуется.

## Шаг 1: Установить и импортировать Aspose.BarCode

Первым делом нам нужна сама библиотека. Выполните один раз в терминале:

```bash
pip install aspose-barcode
```

Теперь можно импортировать нужные классы. Здесь и начинается **как генерировать штрих‑коды**, потому что без правильных импортов вызвать генератор невозможно.

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **Совет:** Если вы используете виртуальное окружение, активируйте его перед запуском `pip install`. Это сохраняет вашу глобальную установку Python в порядке.

## Шаг 2: Создать штрих‑код Planet – версия по умолчанию (заполненная)

Штрих‑код Planet — классическая символьная система 2‑of‑5, используемая почтовыми службами. Начнём с самого простого случая: заполненного штрих‑кода. Этот шаг демонстрирует **как генерировать штрих‑коды** с настройками по умолчанию.

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### Зачем задавать `x_dimension.pixels`?

Хотя значение по умолчанию работает, часто требуется **как задавать размеры**, чтобы соответствовать DPI принтера или ограничениям UI. Свойство `x_dimension` управляет шириной одной полосы в пикселях; большие числа дают более толстый штрих‑код, а меньшие — более компактный.

## Шаг 3: Создать штрих‑код Planet с пустыми (незаполненными) полосами

Теперь ответим на вопрос **как изменить заливку**. Переключив флаг `filled_bars`, можно перейти от сплошной чёрной полосы к пустой, которая всё равно кодирует те же данные.

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

Когда откроете `PostalPlanetFilled.png` и `PostalPlanetEmpty.png` рядом, увидите визуальную разницу: заполненная версия полностью чёрная, а пустая — только контуры полос. Это удобно, когда нужен более лёгкий визуальный вес для наложения в UI.

## Шаг 4: Полный, готовый к запуску скрипт (полное решение)

Ниже представлен весь код, который можно скопировать в файл `generate_planet_barcodes.py`. В нём есть всё — от импортов до сохранения изображений, так что не придётся искать недостающие части.

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### Ожидаемый вывод

При запуске скрипт выведет что‑то вроде:

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

Откройте два PNG‑файла в любом просмотрщике изображений; вы увидите классический штрих‑код Planet — один сплошной, один пустой. Оба кодируют строку `123456`.

## Шаг 5: Настройка размеров для разных сценариев

Теперь, когда вы знаете **как задавать размеры**, рассмотрим пару типичных ситуаций.

### 5.1 Увеличение штрих‑кода для печати

Если печатаете на этикеточном принтере с 300 dpi, 4‑пиксельная полоса может выглядеть крошечной. Увеличьте `x_dimension`, например, до 8 пикселей:

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 Уменьшение штрих‑кода для мобильных экранов

И наоборот, для мобильного приложения может потребоваться более компактный штрих‑код. Установка `x_dimension` в 2 пикселя уменьшит ширину без потери читаемости (Aspose автоматически масштабирует).

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

Помните, высота штрих‑кода автоматически подстраивается под спецификации символьной системы, поэтому вам нужно беспокоиться только о ширине.

## Шаг 6: Расширенные варианты заливки и зачем они могут понадобиться

Помимо простого булевого `filled_bars`, Aspose.BarCode позволяет настраивать цвета полос, цвета фона и даже добавлять градиенты. Если когда‑нибудь понадобится **как изменить заливку** более гибко, можно сделать так:

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*(Примечание: выше используется .NET‑структура цвета; в чистом Python следует использовать соответствующий enum Aspose.)* Это удобно для брендинга — представьте логотип компании, слегка вписанный в фон штрих‑кода.

## Распространённые ошибки и как их избежать

| Симптом | Возможная причина | Решение |
|---------|-------------------|---------|
| Штрих‑код выглядит размытым в сохранённом PNG | `x_dimension` слишком мал для целевого DPI | Увеличьте `x_dimension` или масштабируйте изображение после сохранения |
| Сканер отказывается считывать пустой штрих‑код | `filled_bars = False` не поддерживается некоторыми устаревшими сканерами | Оставьте заполненную версию для максимальной совместимости |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode не установлен или несовместим с .NET‑runtime | Переустановите через `pip install aspose-barcode` и убедитесь, что установлен .NET Core runtime |

## Итоги: Что мы рассмотрели

* **Как генерировать штрих‑коды** с Aspose.BarCode в Python
* **Как задавать размеры** с помощью `x_dimension.pixels`
* **Как изменить заливку** через флаг `filled_bars` (и кратко о настройке цветов)
* Полный скрипт, готовый к копированию и адаптации под любые данные

## Что дальше? (Следующие шаги и связанные темы)

Если руководство оказалось полезным, изучите:

* **Генерацию QR‑кодов** (`EncodeTypes.QR`) — идеально для URL‑ов и контактных данных.
* **Добавление подписи** под штрих‑кодом (`parameters.caption`) для человекочитаемых значений.
* **Экспорт в другие форматы** вроде SVG или PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) — отлично для векторной графики.
* **Пакетную генерацию** — цикл по CSV с идентификаторами продуктов для создания целого каталога штрих‑кодов за один запуск.

Все эти темы также связаны с нашими вторичными ключевыми словами: *generate barcode with aspose* и *how to set dimensions* для разных форматов вывода.

---

Оставляйте комментарии, если столкнётесь с проблемами, или делитесь своими вариантами. Приятного создания штрих‑кодов!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to Colorize Barcode Images in Java with Aspose.BarCode](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}