---
category: general
date: 2026-08-03
description: Быстро создавайте PNG‑штрихкоды с помощью этого руководства. Узнайте,
  как генерировать изображение штрихкода с помощью Aspose.BarCode и создавать planet‑штрихкод.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode image
- generate planet barcode
- Python barcode generation
- Aspose.BarCode tutorial
language: ru
lastmod: 2026-08-03
og_description: Создавайте PNG‑изображения штрихкода мгновенно. В этом руководстве
  показано, как генерировать изображение штрихкода и создавать planet‑штрихкод с помощью
  Aspose.BarCode.
og_image_alt: Example of a Planet barcode saved as a PNG image
og_title: Создание PNG‑штрихкода в Python — полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  headline: Create barcode PNG in Python – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  name: Create barcode PNG in Python – step‑by‑step guide
  steps:
  - name: 1. Install the Aspose.BarCode package
    text: 'Aspose provides a pure‑Python package that wraps its .NET core engine.
      Install it with `pip`:'
  - name: 2. Import required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 3. Create a barcode generator for the Planet symbology
    text: '```python # Step 1: Create a barcode generator for the Planet symbology
      with the desired data barcode_generator = BarcodeGenerator(EncodeTypes.Planet,
      "123456") ```'
  - name: 4. Set the X dimension (module width) in pixels
    text: '```python # Step 2: Set the X dimension (module width) in pixels barcode_generator.parameters.barcode.x_dimension.pixels
      = 4 ```'
  - name: 5. Define a manual bar height in pixels
    text: '```python # Step 3: Define a manual bar height in pixels barcode_generator.parameters.barcode.bar_height.pixels
      = 100 ```'
  - name: 6. Save the generated barcode as a PNG image
    text: '```python # Step 4: Save the generated barcode as a PNG image output_path
      = "output/PlanetBarHeight100.png" barcode_generator.save(output_path, BarCodeImageFormat.Png)
      print(f"Barcode saved to {output_path}") ```'
  - name: 7. Verify the output (optional)
    text: '```python from PIL import Image'
  - name: ' ## What Should You Learn Next?


      The following tutorials cover closely related topics that build on the techniques
      demonstrated in this guide. Each resource includes complete working code examples
      with step-by-step explanations to help you master additional API features and
      explore alternative implementation approaches in your own projects.

      - [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
      - [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
      - [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

      {{< /blocks/products/pf/tutorial-page-section >}}'
    text: '{{< /blocks/products/pf/main-container >}} {{< /blocks/products/pf/main-wrap-class
      >}} {{< blocks/products/products-backtop-button >}}'
  type: HowTo
tags:
- barcode
- PNG
- Python
- Aspose
title: Создание PNG‑штрихкода в Python – пошаговое руководство
url: /ru/python-java/general/create-barcode-png-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG штрих‑кода в Python – пошаговое руководство

Если вам нужно **создавать PNG‑файлы штрих‑кода** из вашего Python‑приложения, этот учебник покажет, как это сделать. Мы пройдемся по **созданию изображения штрих‑кода** с помощью Aspose.BarCode и конкретно **создадим штрих‑код Planet** с пользовательскими размерами.

Вы узнаете, как установить библиотеку, настроить симбологию Planet, отрегулировать параметры размера и сохранить результат в виде PNG высокого качества. Руководство предполагает базовые знания Python и современную версию Python 3 (3.8 или новее). Предыдущий опыт работы со стандартами штрих‑кодов не требуется.

---

## Как создать PNG штрих‑кода с помощью Aspose.BarCode

Этот раздел содержит основные шаги, необходимые для **создания PNG штрих‑кода**. Каждый шаг включает фрагмент кода, объяснение его важности и практические советы, которые можно применить сразу.

### 1. Установите пакет Aspose.BarCode

Aspose предоставляет чисто‑Python пакет, который оборачивает его .NET‑ядро. Установите его с помощью `pip`:

```bash
pip install aspose-barcode
```

*Почему этот шаг важен:* Пакет поставляет класс `BarcodeGenerator`, используемый во всём примере. Установка его глобально гарантирует, что интерпретатор сможет найти сборку во время выполнения.

### 2. Импортируйте необходимые классы

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

*Совет:* Импортируйте только те символы, которые действительно нужны; так пространство имён остаётся чистым, а загрузка модулей ускоряется.

### 3. Создайте генератор штрих‑кода для симбологии Planet

```python
# Step 1: Create a barcode generator for the Planet symbology with the desired data
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

*Почему это важно:* `EncodeTypes.Planet` указывает движку использовать стандарт штрих‑кода Planet, а второй аргумент передаёт данные для кодирования. Замена симбологии (например, `EncodeTypes.Code128`) приведёт к полностью другому визуальному паттерну.

### 4. Установите X‑размер (ширина модуля) в пикселях

```python
# Step 2: Set the X dimension (module width) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

*Объяснение:* X‑размер контролирует ширину узкой полосы. Значение 4 пикселя даёт умеренно плотный штрих‑код, который остаётся считываемым большинством устройств.

### 5. Задайте ручную высоту полосы в пикселях

```python
# Step 3: Define a manual bar height in pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

*Зачем это может понадобиться:* Некоторые розничные принтеры требуют более высоких полос для надёжного сканирования. Высота по умолчанию обычно 50 px; увеличение её до 100 px улучшает читаемость без значительного роста размера файла.

### 6. Сохраните сгенерированный штрих‑код как PNG‑изображение

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "output/PlanetBarHeight100.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

*Результат:* В папке `output` появляется файл PNG с именем **PlanetBarHeight100.png**. PNG — формат без потерь, что делает его идеальным для печати и встраивания в веб‑страницы.

### 7. Проверьте результат (по желанию)

```python
from PIL import Image

with Image.open(output_path) as img:
    img.show()   # Opens the default image viewer
    print(f"Image size: {img.size} (width, height)")
```

*Совет:* Просмотр изображения подтверждает, что размеры соответствуют заданным параметрам. Если штрих‑код выглядит искажённым, проверьте настройки X‑размера или высоты полосы.

---

## Как сгенерировать изображение штрих‑кода в формате PNG (альтернативные настройки)

Если нужен другой формат изображения или планируется последующее встраивание штрих‑кода в PDF, можно изменить перечисление `BarCodeImageFormat`:

```python
# Save as JPEG instead of PNG
barcode_generator.save("output/PlanetBar.jpeg", BarCodeImageFormat.Jpeg)

# Save as BMP for legacy Windows applications
barcode_generator.save("output/PlanetBar.bmp", BarCodeImageFormat.Bmp)
```

*Почему это важно:* PNG сохраняет каждый пиксель, что критично для штрих‑кодов с высоким контрастом. JPEG вводит артефакты сжатия, которые могут мешать сканированию, а BMP обеспечивает совместимость со старыми инструментами.

---

## Генерация штрих‑кода Planet с пользовательскими цветами (расширенный уровень)

Помимо размеров, можно настроить цвета переднего плана и фона:

```python
from aspose.barcode import Color

# Set foreground to dark blue and background to light gray
barcode_generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
barcode_generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

barcode_generator.save("output/PlanetColored.png", BarCodeImageFormat.Png)
```

*Практический совет:* Пары цветов с высоким контрастом (тёмный на светлом) максимизируют надёжность сканера. Избегайте использования схожих оттенков для переднего плана и фона.

---

## Распространённые ошибки и как их избежать

| Признак | Причина | Решение |
|---------|---------|---------|
| Штрих‑код не считывается | X‑размер слишком мал (≤ 2 px) | Увеличьте `x_dimension.pixels` минимум до 3 px |
| Изображение размыто | PNG сохранён с низким DPI | Используйте `barcode_generator.save(..., BarCodeImageFormat.Png, 300)` для указания 300 DPI (если поддерживается) |
| Исключение `ImportError` | Aspose.BarCode не установлен | Выполните `pip install aspose-barcode` в той же среде, где находится ваш скрипт |
| Неправильная симбология | Был использован `EncodeTypes.Code128` вместо `EncodeTypes.Planet` | Замените на `EncodeTypes.Planet` при создании генератора |

---

## Итоги полного решения

Ниже представлен полностью готовый к запуску скрипт, который **создаёт PNG штрих‑кода** от начала до конца:

```python
# full_example.py
# -------------------------------------------------
# Demonstrates how to generate a Planet barcode PNG
# -------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create generator with Planet symbology
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# 2️⃣ Configure dimensions
generator.parameters.barcode.x_dimension.pixels = 4          # module width
generator.parameters.barcode.bar_height.pixels = 100        # bar height

# 3️⃣ Optional: set colors (uncomment to use)
# from aspose.barcode import Color
# generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
# generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

# 4️⃣ Save as PNG
png_path = os.path.join(output_dir, "PlanetBarHeight100.png")
generator.save(png_path, BarCodeImageFormat.Png)

print(f"✅ Barcode PNG created at: {png_path}")

# 5️⃣ Verify (opens the image on most OSes)
try:
    from PIL import Image
    with Image.open(png_path) as img:
        img.show()
        print(f"Image size: {img.size}")
except Exception as e:
    print(f"Verification step skipped: {e}")
```

Запуск этого скрипта создаёт чёткий **PNG штрих‑код Planet**, который можно встраивать в HTML, прикреплять к письмам или печатать на этикетках продукции.

---

## Следующие шаги и связанные темы

* **Интеграция с Flask или Django** – обслуживайте сгенерированный PNG напрямую из веб‑эндпоинта.  
* **Пакетная генерация** – перебирайте список идентификаторов продуктов, чтобы создать папку с PNG‑файлами штрих‑кодов.  
* **Комбинация с генерацией PDF** – используйте `aspose-pdf` для размещения PNG в счёте или транспортной этикетке.  
* **Исследование других симбологий** – замените `EncodeTypes.Planet` на `EncodeTypes.QR`, `EncodeTypes.DataMatrix` или `EncodeTypes.Code128`, чтобы удовлетворить различные бизнес‑требования.

Освоив перечисленные шаги, вы теперь знаете, **как программно генерировать изображение штрих‑кода**, и можете расширять эту схему на любой стандарт штрих‑кода, поддерживаемый Aspose.BarCode.

---

###

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}