---
category: general
date: 2026-10-15
description: Создайте штрих‑код из строки в Python с помощью Aspose.BarCode, узнайте,
  как сгенерировать штрих‑код Code 128 и сохранить его в PNG за несколько строк кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: ru
lastmod: 2026-10-15
og_description: Создайте штрих‑код из строки в Python, закодируйте данные в штрих‑код
  Code 128 и сохраните его в файл PNG с помощью Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Создайте штрих‑код из строки в Python — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Создание штрихкода из строки в Python с помощью Aspose.BarCode
url: /ru/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрихкода из строки в Python с Aspose.BarCode

Если вам нужно **создать штрихкод из строки** в Python, это руководство покажет точные шаги с Aspose.BarCode. Вы узнаете, как **сгенерировать штрихкод Code 128**, настроить его внешний вид и **сохранить штрихкод PNG** на диск. Решение работает на любой платформе, поддерживающей Python 3.9+, и требует всего несколько строк кода.

Программная генерация штрихкодов устраняет ошибки ручного ввода и упрощает процессы, такие как учёт запасов, билеты и печать этикеток. К концу этого урока вы сможете **закодировать данные в штрихкод**, настроить размеры и сохранить изображение там, где это необходимо.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- Установлен Python 3.9 или новее  
- Доступ в Интернет для загрузки пакета Aspose.BarCode  
- Права записи в каталог, куда будет сохраняться PNG‑файл  

Если вы используете виртуальное окружение (настоятельно рекомендуется), активируйте его сейчас.

## Установка пакета Aspose.BarCode для Python

Aspose предоставляет чисто‑Python библиотеку, которая обрабатывает все распространённые символьные наборы штрихкодов, включая Code 128. Установите её с помощью pip:

```bash
pip install aspose-barcode
```

*Совет:* Зафиксируйте версию (например, `aspose-barcode==23.9`), чтобы избежать неожиданных изменений в продакшене.

## Создание штрихкода из строки в Python

Первый рабочий шаг — импортировать необходимые классы и создать генератор для нужного символьного набора. В этом примере используется **Code 128**, идеальный для алфавитно‑цифровых данных.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Почему это важно:** `EncodeTypes.CODE_128` указывает библиотеке, какой стандарт штрихкода применять, а второй аргумент (`"1234567890"`) — это **строка, которую вы хотите закодировать в штрихкод**. Вы можете заменить её любой ASCII‑строкой длиной до 80 символов для Code 128.

## Генерация штрихкода Code 128

После настройки генератора вы можете создать изображение штрихкода в памяти. Библиотека автоматически отрисовывает штрихкод на основе переданных данных.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

На данном этапе `barcode_image` является экземпляром `System.Drawing.Image` (в Windows) или совместимым объектом изображения на других платформах. Его можно сразу отобразить в GUI, встроить в PDF или продолжить настройку.

## Настройка внешнего вида штрихкода

Точная настройка визуальных свойств гарантирует надёжное сканирование штрихкода в вашей среде. Часто меняют X‑размер (ширина самого узкого штриха) и общую высоту штриха.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Зачем менять эти значения?*  
- **X‑размер** влияет на плотность штрихкода; меньшее значение даёт более плотный штрихкод, который помещается на небольших этикетках.  
- **Высота штриха** влияет на читаемость; более высокие штрихи легче обнаруживаются сканерами с расстояния.

Вы также можете менять цвета, добавлять отступы или встраивать человекочитаемый текст через объект `parameters`. См. документацию Aspose.BarCode для полного списка опций.

## Как сохранить штрихкод как PNG

Сохранение сгенерированного изображения — последний шаг в процессе **создания штрихкода из строки**. Библиотека поддерживает несколько форматов; PNG — без потерь и широко поддерживается.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

Метод `save` записывает изображение в файловую систему в указанном формате. Если целевой каталог (`output/` в этом примере) не существует, Python выбросит `FileNotFoundError`. Создайте каталог заранее или обработайте исключение:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Ожидаемый результат:** После выполнения скрипта `output/barcode.png` содержит чёткий штрихкод Code 128, кодирующий `"1234567890"`. Открытие файла в любом просмотрщике изображений покажет чёрно‑белый штрихкод, готовый к сканированию.

## Полный, готовый к запуску пример

Объединив все части, получаем автономный скрипт, который можно скопировать, вставить и запустить:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Запустите скрипт командой `python create_barcode.py`. Если всё установлено правильно, вы увидите:

```
Barcode saved to output/barcode.png
```

Откройте PNG‑файл и проверьте, что штрихкод соответствует исходной строке, используя любое приложение‑сканер штрихкодов.

## Часто задаваемые вопросы и особые случаи

- **Что делать, если нужен другой символьный набор?**  
  Замените `EncodeTypes.CODE_128` на другое значение перечисления, например `EncodeTypes.QR`, `EncodeTypes.EAN_13` или `EncodeTypes.PDF_417`. Остальная часть кода остаётся без изменений.

- **Можно ли генерировать штрихкод из не‑ASCII символов?**  
  Code 128 поддерживает полный набор 128‑символьного ASCII. Для Unicode‑данных используйте QR‑Code (`EncodeTypes.QR`), который нативно работает с UTF‑8.

- **Как изменить формат изображения?**  
  Передайте другое значение из `BarCodeImageFormat` в `save`, например `BarCodeImageFormat.JPEG` или `BarCodeImageFormat.BMP`.

- **Что если каталог вывода доступен только для чтения?**  
  Оберните вызов `save` в блок `try/except` и обработайте `PermissionError`, например, запросив у пользователя альтернативный путь.

- **Подсказка по производительности:**  
  Генерация тысяч штрихкодов в цикле может быть ресурсоёмкой. Переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только `generator.parameters.barcode.code_text` между итерациями.

## Заключение

Теперь вы знаете, как **создать штрихкод из строки** в Python с помощью Aspose.BarCode, **сгенерировать штрихкод Code 128**, настроить его размер и **сохранить штрихкод PNG** на диск. Это сквозное решение позволяет **закодировать данные в штрихкод** быстро и надёжно, облегчая интеграцию штрихкодов в системы учёта, билеты или любые приложения, требующие машинно‑читаемых идентификаторов.

**Следующие шаги**

- Исследуйте другие символьные наборы (альтернативы `generate code 128 barcode`) такие как QR или DataMatrix.  
- Добавьте обработку ошибок, чтобы скрипт был устойчив к сбоям в продакшене (`how to save barcode`).  
- Встраивайте сгенерированный PNG в PDF‑документы или HTML‑отчёты (`generate barcode png` для веб).  

Удачной разработки и наслаждайтесь простотой программной генерации штрихкодов!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}