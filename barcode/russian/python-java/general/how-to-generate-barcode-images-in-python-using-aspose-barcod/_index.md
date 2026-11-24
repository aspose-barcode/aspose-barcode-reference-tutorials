---
category: general
date: 2026-11-23
description: Как генерировать изображения штрих‑кодов в Python с помощью Aspose.BarCode.
  Узнайте, как создать штрих‑код Planet, настроить X‑размер и вывести PNG с пустыми
  полосами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: ru
lastmod: 2026-11-23
og_description: Как генерировать штрих‑код в Python с помощью Aspose.BarCode. Этот
  учебник проведёт вас через процесс создания штрих‑кода Planet с пустыми полосами
  и сохранения его в формате PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Как сгенерировать штрих‑код в Python – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Как генерировать изображения штрихкодов в Python с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать изображения штрих‑кодов в Python с помощью Aspose.BarCode

Генерировать изображения штрих‑кодов в Python просто с библиотекой Aspose.BarCode. В этом руководстве показано пошагово, как создать штрих‑код с использованием символьного набора Planet, настроить X‑размер и получить PNG‑файл в стиле пустых полос.

Вы увидите полностью готовый, исполняемый скрипт, который можно скопировать в свой проект. Руководство также охватывает распространённые варианты — например, переключение на другой символьный набор или формат вывода — чтобы вы могли адаптировать решение под свои требования.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* Python 3.8 или новее.
* Доступ к терминалу или командной строке.
* Действующая лицензия Aspose.BarCode for Python (бесплатная оценочная версия подходит для тестирования).
* Базовые знания управления пакетами Python (`pip`).

## Шаг 1: Установите пакет Aspose.BarCode

Aspose распространяет свой Python API через PyPI. Установите его стандартным менеджером пакетов:

```bash
pip install asposebarcode
```

> **Совет:** Используйте виртуальное окружение (`python -m venv venv`), чтобы изолировать зависимости от других проектов.

## Шаг 2: Импортируйте необходимые классы Aspose.BarCode

Эта инструкция импорта подтягивает генератор, перечисление символьных наборов и перечисление форматов изображений.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` создаёт объект штрих‑кода.
* `EncodeTypes` перечисляет все поддерживаемые символьные наборы — здесь мы будем использовать `Planet`.
* `BarCodeImageFormat` определяет тип выходного файла (PNG, JPEG и т.д.).

## Шаг 3: Создайте генератор штрих‑кода для символьного набора Planet

Создайте экземпляр генератора с нужным символьным набором и данными, которые нужно закодировать.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Символьный набор `Planet` формирует круговой узор, идеальный для декоративных или брендовых целей.

## Шаг 4: Настройте X‑размер (ширина модуля)

X‑размер контролирует ширину самого маленького столбца (модуля). Установка значения 4 пикселя даёт чёткое, высококачественное изображение.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Изменение X‑размера полезно, когда требуется штрих‑код, который хорошо масштабируется для печати или отображения на экране.

## Шаг 5: Отключите заполненные полосы для стиля пустых полос

Штрих‑код в стиле пустых полос отображает только контуры столбцов, что может быть полезно в дизайне‑ориентированных приложениях.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Когда `filled_bars` равно `False`, генератор рисует полые формы вместо сплошных.

## Шаг 6: Сохраните изображение штрих‑кода в файл PNG

Наконец, запишите штрих‑код на диск. PNG — это без потерь и широко поддерживаемый формат.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

Метод `save` автоматически создаёт целевую директорию, если её нет.

## Полный пример — готовый к запуску скрипт

Объединив все части, получаем автономную программу, которую можно сразу выполнить:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Ожидаемый результат:** После запуска скрипта файл `output/PlanetEmptyBars.png` будет содержать изображение 200 × 200 пикселей штрих‑кода Planet с пустыми полосами. Открытие файла в любом просмотрщике покажет круговой узор с закодированным числовым значением внутри.

## Распространённые варианты и граничные случаи

### Переключение на другой символьный набор

Если нужен QR‑code, Code 128 или любой другой формат, замените `EncodeTypes.Planet` на соответствующее значение перечисления:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Смена формата изображения

Aspose.BarCode поддерживает PNG, JPEG, BMP и TIFF. Чтобы получить JPEG, используйте:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Регулировка размера изображения без потери качества

Общий размер изображения можно контролировать через свойство `resolution` или масштабируя одновременно X‑ и Y‑размеры. Для печати с высоким разрешением задайте более высокий DPI:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Обработка длинных строк данных

Символьный набор Planet имеет ограниченную ёмкость данных (до 8 символов). При попытке закодировать более длинную строку генератор выбросит исключение. Проверьте длину перед созданием штрих‑кода:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Советы и подводные камни

* **Активация лицензии:** Для продакшн‑использования подключите файл лицензии в начале скрипта с помощью `asposebarcode.License().set_license("Aspose.Total.lic")`. Пропуск этого шага добавит водяной знак в результирующее изображение.
* **Потокобезопасность:** Экземпляры `BarcodeGenerator` не являются потокобезопасными. Создавайте отдельный объект для каждого потока, если генерируете штрих‑коды параллельно.
* **Производительность:** Переиспользование генератора для разных значений (через `barcode.value = "new data"`) быстрее, чем создание нового объекта каждый раз.
* **Пути к файлам:** Используйте `os.path.join` для построения кроссплатформенных путей, особенно при развертывании на Linux или macOS.

## Заключение

Теперь вы знаете, как генерировать изображения штрих‑кодов в Python с помощью Aspose.BarCode, настраивать X‑размер, создавать стиль пустых полос и сохранять результат в PNG. Полный пример можно адаптировать под другие символьные наборы, форматы вывода и визуальные стили, получая гибкую основу для любой функции, связанной со штрих‑кодами, в ваших приложениях.

**Следующие шаги:** Исследуйте дополнительные ключевые слова, такие как *Python barcode generation*, пробуя разные кодировки, экспериментируя с настройками сжатия *barcode image PNG* или интегрируя сгенерированные изображения в веб‑службу на Flask или FastAPI. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}