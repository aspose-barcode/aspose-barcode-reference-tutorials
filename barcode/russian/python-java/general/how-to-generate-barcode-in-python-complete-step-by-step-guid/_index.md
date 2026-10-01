---
category: general
date: 2026-08-12
description: Как быстро генерировать штрих‑код с помощью Python. Узнайте, как создать
  штрих‑код из данных и экспортировать изображение штрих‑кода с помощью одной библиотеки.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: ru
lastmod: 2026-08-12
og_description: Как генерировать штрих‑код в Python с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы создать штрих‑код из данных и экспортировать изображение
  штрих‑кода в формате PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Как генерировать штрих‑код в Python — быстрый, надёжный гид
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Как сгенерировать штрих‑код в Python — полное пошаговое руководство
url: /ru/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код в Python – полное пошаговое руководство

Если вам нужно **how to generate barcode** в приложении на Python, этот учебник покажет точный код, который вам нужен. Вы научитесь **create barcode from data**, настраивать его внешний вид и **export barcode image** в виде PNG‑файла — всё это менее чем в десяти строках кода.

Создание штрих‑кода может казаться отдельной задачей от остальной бизнес‑логики, но с помощью одной библиотеки вы можете интегрировать процесс в ваш существующий код. В последующих разделах вы увидите полностью рабочий пример, поймёте, почему важна каждая строка, и узнаете о распространённых вариациях, таких как изменение ширины модуля или отрисовка штрих‑кода только с контурами.

## Как генерировать штрих‑код с библиотекой Aspose.BarCode

Библиотека Aspose.BarCode для Python (через .NET) предоставляет простой API для множества символогий, включая штрих‑код Planet, используемый в этом руководстве. Прежде чем начать, убедитесь, что пакет установлен:

```bash
pip install aspose-barcode
```

> **Pro tip:** Используйте виртуальное окружение, чтобы избежать конфликтов версий с другими проектами.

### 1. Импортировать необходимые классы

Эти импорты дают вам доступ к классу генератора, перечислению типов штрих‑кодов и перечислению форматов изображений, используемых при сохранении результата.

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

### 2. Создать штрих‑код из данных

Первый шаг — **create barcode from data**. Конструктор `BarcodeGenerator` принимает символогию и исходную строку, которую нужно закодировать.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Значение `EncodeTypes.Planet` выбирает штрих‑код Planet, а `"123456"` — это полезные данные, которые появятся в конечном изображении.

### 3. Настроить X‑dimension (ширина модуля)

X‑dimension управляет шириной каждого модуля штрих‑кода (тонкой полосы). Установка значения в 4 пикселя даёт чёткое, читаемое изображение без излишнего увеличения размера файла.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Why this matters:** Большая X‑dimension повышает надёжность сканирования на принтерах с низким разрешением, а меньшее значение уменьшает размер файла для веб‑использования.

### 4. Экспортировать изображение штрих‑кода (заполненный стиль)

Теперь вы можете **export barcode image** с помощью метода `save`. В примере сохраняется PNG‑файл, но вы можете выбрать JPEG, BMP или TIFF, изменив перечисление `BarCodeImageFormat`.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

Файл `PlanetFilled.png` содержит полностью заполненный штрих‑код Planet, готовый к печати или встраиванию в PDF.

### 5. Создать второй генератор для штрих‑кода только с контурами

Если вам нужна версия с контурами (пустые полосы), необходимо создать новый генератор, поскольку флаг `filled_bars` нельзя изменить после сохранения изображения.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Применить тот же параметр X‑dimension

При создании второго генератора необходимо повторить все визуальные настройки, которые вы хотите сохранить одинаковыми.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Отключить заполненные полосы для контурного штрих‑кода

Установка `filled_bars` в `False` указывает рендереру рисовать только контуры каждого модуля, создавая более лёгкое изображение, полезное для дизайнерских целей.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Экспортировать контурное изображение штрих‑кода

Наконец, **export barcode image** ещё раз, на этот раз сохраняя контурную версию.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Теперь у вас есть два PNG‑файла: один с сплошными полосами (`PlanetFilled.png`) и один только с контурами (`PlanetEmpty.png`).

## Экспортировать изображение штрих‑кода в других форматах (необязательно)

Метод `save` поддерживает несколько форматов. Чтобы экспортировать в JPEG с качеством 90 %:

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Если нужен прозрачный фон для веб‑использования, выберите PNG с альфа‑каналом:

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Распространённые вариации и граничные случаи

| Сценарий | Необходимое изменение | Фрагмент кода |
|----------|-----------------------|---------------|
| **Разная симвология** (например, QR) | Использовать другое значение `EncodeTypes` | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Custom foreground color** | Установить `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Более высокое разрешение** | Увеличить DPI через `image_width` и `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Большие строки данных** | Убедиться, что длина данных соответствует спецификации символогии | Validate length before creating the generator |

> **Watch out for:** Предоставление данных, превышающих максимальную длину для выбранной символогии, вызывает исключение во время выполнения. Всегда проверяйте длину строки или перехватывайте `ArgumentException`.

## Полный, исполняемый пример

Ниже приведён полный скрипт, который вы можете скопировать и вставить в файл с именем `generate_planet_barcode.py`. Измените `YOUR_DIRECTORY`, указав путь к существующей на вашем компьютере папке.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

Запуск этого скрипта создаст два PNG‑файла в указанной директории. Проверьте результат, открыв изображения в любом просмотрщике; оба должны отображать штрих‑код Planet, кодирующий строку `123456`.

## Заключение

Теперь вы знаете **how to generate barcode** в Python с использованием Aspose.BarCode, как **create barcode from data**, и как **export barcode image** как в заполненном, так и в контурном стиле. Та же схема применима к другим символогиям, форматам изображений и визуальным настройкам, предоставляя гибкую основу для любой функции, связанной со штрих‑кодами, в вашем приложении.

### Следующие шаги

* Изучить другие символогии, такие как QR, Code‑128 или DataMatrix, заменив `EncodeTypes.Planet` на нужное значение.  
* Интегрировать сгенерированные PNG‑файлы в PDF‑отчёты с помощью библиотек, таких как `ReportLab` или `PyPDF2`.  
* Экспериментировать с динамическими значениями X‑dimension, чтобы адаптировать размер штрих‑кода в зависимости от разрешения экрана или DPI принтера.

Удачной разработки, и не стесняйтесь адаптировать пример под требования вашего проекта!

## Что вам стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}