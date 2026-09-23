---
category: general
date: 2026-08-12
description: Создайте омни‑направленный Databar с помощью Python и узнайте, как создать
  изображение штрих‑кода в Python, используя Aspose.BarCode. Следуйте пошаговому руководству
  для получения полного решения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: ru
lastmod: 2026-08-12
og_description: Создайте омнинаправленный Databar с помощью Python и за несколько
  минут сгенерируйте изображение штрихкода. Этот учебник демонстрирует полный, готовый
  к запуску пример.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Создайте омни‑направленный датабар – полное руководство по Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Создайте всенаправленный DataBar и изображение штрихкода в Python
url: /ru/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание omni directional databar и изображения штрихкода в Python

Если вам нужно **создать omni directional databar** в проекте на Python, это руководство покажет, как это сделать, а также как **создать изображение штрихкода в Python** с использованием библиотеки Aspose.BarCode. Вы получите готовый к запуску скрипт, который генерирует два PNG‑файла с разными соотношениями сторон.

Генерация DataBar, соответствующего спецификации Omni‑directional, является распространённым требованием для розничных и логистических приложений. В руководстве рассматриваются установка, настройка X‑размера, корректировка соотношения сторон и сохранение окончательных изображений. Внешние сервисы не требуются; всё работает локально.

## Что вам понадобится

* Python 3.8 или новее, установленный на вашем компьютере.
* Доступ к терминалу или командной строке.
* Права записи в папку, где будут сохраняться изображения штрихкода.

Единственная сторонняя зависимость — **Aspose.BarCode for Python via .NET**, который из коробки поддерживает тип Omni‑directional DataBar.

## Шаг 1: Установите Aspose.BarCode для Python

Aspose.BarCode предоставляет класс `BarcodeGenerator`, используемый в примере кода. Установите пакет с помощью `pip`:

```bash
pip install aspose-barcode
```

Пакет включает необходимые привязки к .NET‑runtime, поэтому отдельная установка .NET SDK не требуется.

## Шаг 2: Импортируйте библиотеку и создайте генератор

Первая строка скрипта создаёт генератор для stacked Omni‑directional DataBar. В качестве примерных данных используется значение GTIN‑14 `(01)12345678901231`.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Почему этот шаг важен*: Константа `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` указывает библиотеке кодировать значение как Omni‑directional DataBar, формат, требуемый многими сканерами точек продаж.

## Шаг 3: Установите X‑dimension (ширина модуля)

X‑dimension определяет ширину самого маленького бар‑модуля. Значение `2` пикселя даёт чёткий, читаемый штрихкод без избыточного размера файла.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Почему этот шаг важен*: Регулировка X‑dimension позволяет сбалансировать читаемость и размеры изображения. Слишком маленькая X‑dimension может плохо отображаться на принтерах с низким разрешением.

## Шаг 4: Настройте соотношение сторон и сохраните первое изображение

Соотношение сторон влияет на общую высоту DataBar относительно его ширины. Соотношение `15` создаёт компактный визуальный стиль.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tip**: Используйте `pathlib.Path` для построения пути вывода — он автоматически создаёт недостающие каталоги.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Шаг 5: Измените соотношение сторон для второго визуального стиля и сохраните другое изображение

Переключение соотношения сторон на `30` даёт более высокий штрихкод, который может потребоваться определённому сканирующему оборудованию.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Почему этот шаг важен*: Разные розничные сети и сканеры имеют свои ограничения по размеру. Предоставление обоих соотношений в одном скрипте позволяет генерировать нужный стиль без дублирования кода.

## Полный скрипт – создание omni directional databar и изображения штрихкода в Python

Ниже приведён полностью готовый к запуску пример, включающий все предыдущие шаги. Сохраните его как `generate_databar.py` и запустите командой `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Ожидаемый результат

Запуск скрипта создаёт следующие файлы:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Оба изображения отображают корректный Omni‑directional DataBar, который может быть считан стандартным розничным оборудованием.

![пример создания omni directional databar и изображения штрихкода в Python](example_databar.png "создание omni directional databar и изображения штрихкода python")

*Изображение выше является заглушкой, иллюстрирующей два сохранённых PNG‑файла.*

## Решение распространённых проблем

| Проблема | Причина | Решение |
|----------|---------|---------|
| `ImportError: No module named aspose` | Aspose.BarCode не установлен или установлен в другой среде. | Активируйте правильное виртуальное окружение и выполните `pip install aspose-barcode`. |
| `PermissionError` при сохранении | Скрипт не имеет прав записи в целевую папку. | Выберите каталог, к которому у вас есть доступ, или запустите скрипт с соответствующими привилегиями. |
| Штрихкод не считывается | X‑dimension слишком мала или соотношение сторон несовместимо со сканером. | Увеличьте `x_dimension.pixels` до 3 или 4 и протестируйте разные значения `aspect_ratio` (например, 20, 25). |
| Отсутствует .NET runtime | Aspose.BarCode зависит от .NET runtime на Windows/Linux. | Установите последнюю версию .NET runtime с сайта Microsoft; в документации пакета есть рекомендации для разных платформ. |

## Расширение примера

Вы можете адаптировать скрипт для генерации других вариантов DataBar (например, `DATABAR_STACKED`, `DATABAR_EXPANDED`). Замените соответствующую константу `EncodeTypes`.

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Если необходимо встроить штрихкод в PDF, Aspose.PDF for Python может напрямую импортировать PNG‑файл, либо можно воспользоваться методом `save` с параметром `BarCodeImageFormat.Pdf`.

## Заключение

В этом руководстве показано, как **создать omni directional databar** и как **создать изображение штрихкода в Python** с помощью Aspose.BarCode. Теперь у вас есть полностью воспроизводимый скрипт, генерирующий два PNG‑файла с разными соотношениями сторон, учитывающий типичные подводные камни и готовый к расширению под другие форматы штрихкодов.

Далее изучайте генерацию QR‑кодов, добавление штрихкода в PDF‑счета или автоматизацию пакетной обработки больших каталогов товаров. Все эти темы опираются на тот же шаблон `BarcodeGenerator`, продемонстрированный здесь. Приятного кодинга!

## Что следует изучить дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Генерация изображения штрихкода – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Создание изображения штрихкода DotCode – строки и столбцы (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Как создать изображение штрихкода и отобразить его в Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}