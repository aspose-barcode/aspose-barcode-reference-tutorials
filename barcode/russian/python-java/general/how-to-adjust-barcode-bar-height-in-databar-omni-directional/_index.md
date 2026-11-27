---
category: general
date: 2026-11-27
description: Узнайте, как настроить высоту штрихов в генераторе штрих‑кодов DataBar
  Omni‑Directional. Пошаговый код показывает установку высот 30 px и 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: ru
lastmod: 2026-11-27
og_description: Отрегулируйте высоту штрихов в генераторе штрих‑кодов DataBar Omni‑Directional
  с помощью Python. Следуйте полному руководству, чтобы установить высоты, X‑размер
  и сохранить изображения в формате PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Регулировка высоты штриха штрих‑кода в генераторе DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Как отрегулировать высоту полосы штрих‑кода в генераторе DataBar Omni‑Directional
url: /ru/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить высоту штрихов штрих‑кода в генераторе DataBar Omni‑Directional

Если вам нужно **изменить высоту штрихов штрих‑кода** для DataBar Omni‑Directional, это руководство покажет, как это сделать. Вы увидите полностью готовый, исполняемый пример на Python, который меняет высоту штрихов с 30 px до 60 px, сохраняя при этом X‑размер и формат изображения.

Изменение визуальных размеров штрих‑кода — частая необходимость, когда штрих‑код должен вписаться в определённый размер этикетки или соответствовать дизайнерским требованиям. Помимо высоты штрихов, вы также можете настроить **X‑размер** (размер модуля) или выбрать другой **формат изображения штрих‑кода**, например PNG или JPEG.

В этом учебнике вы:

* Установите необходимую библиотеку (GroupDocs.Barcode for Python)
* Создадите генератор DataBar Omni‑Directional
* Установите размер модуля с помощью `XDimension`
* Дважды измените свойство высоты штрихов
* Сохраните полученные изображения в нужном **BarCodeImageFormat**

Предыдущий опыт работы с API GroupDocs не требуется — достаточно базовых знаний Python.

## Требования

Перед началом убедитесь, что у вас есть:

* Python 3.8 или новее
* Пакет `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Права записи в папку, куда будут сохраняться PNG‑файлы

Если вы не знакомы с **DataBar Omni‑Directional штрих‑кодом**, он кодирует 14‑значный GTIN и широко используется в розничной торговле для сканирования в любой ориентации.

## Шаг 1: Настройка генератора DataBar Omni‑Directional

Сначала импортируйте необходимые классы и создайте генератор с данными GTIN, которые нужно закодировать.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Почему это важно:* Константа `EncodeTypes.DatabarOmniDirectional` указывает библиотеке создавать символьность Omni‑Directional. Строка данных включает AI `(01)`, обозначающий значение GTIN‑14.

## Шаг 2: Определите X‑размер (размер модуля)

X‑размер управляет шириной самого узкого штриха. Обычное значение для отображения на экране — **2 px на модуль**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Последовательное **установление XDimension** гарантирует корректное масштабирование штрих‑кода на разных принтерах и сканерах.

## Шаг 3: Установите высоту штрихов 30 px и сохраните изображение

Теперь изменим свойство высоты штрихов. Первая высота — **30 px**, что подходит для небольших этикеток.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Константа `BarCodeImageFormat.Png` выбирает **формат изображения штрих‑кода** PNG, сохраняющий без потерь.

### Ожидаемый результат

Файл `DatabarBarHeight30Pixels.png` содержит DataBar Omni‑Directional штрих‑код, у которого штрихи высотой 30 px. Ниже — пример превью:

![Штрих‑код DataBar с высотой штриха 30 px](images/databar_30px.png "Штрих‑код DataBar с высотой штриха 30 px")

> **Совет:** Открыв PNG в графическом редакторе, вы увидите точную высоту штрихов. Узкие штрихи имеют ширину 2 px, как было задано ранее.

## Шаг 4: Увеличьте высоту штрихов до 60 px для более высокого штрих‑кода

Для приложений, требующих большего визуального пространства — например, грузовой этикетки — можно увеличить высоту штрихов до **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Изменяется только свойство `BarHeight`; X‑размер и кодировка остаются прежними, поэтому штрих‑код остаётся сканируемым.

## Шаг 5: Сохраните обновлённое изображение штрих‑кода

Наконец, запишите более высокий штрих‑код во второй PNG‑файл.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Ожидаемый результат

Файл `DatabarBarHeight60Pixels.png` показывает те же закодированные данные, но каждый штрих теперь высотой 60 px. Визуальная разница показана ниже:

![Штрих‑код DataBar с высотой штриха 60 px](images/databar_60px.png "Штрих‑код DataBar с высотой штриха 60 px")

## Полный, исполняемый пример

Объединив всё вместе, получаем полный скрипт, который можно скопировать в файл `adjust_barcode_height.py` и запустить сразу.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Запуск скрипта:

```bash
python adjust_barcode_height.py
```

В папке `output` появятся два PNG‑файла, каждый из которых отражает установленную высоту штрихов.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| **Можно ли использовать JPEG вместо PNG?** | Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. JPEG — формат с потерями, поэтому для точного сканирования предпочтительнее PNG. |
| **Что если нужна высота штриха, не кратная 10?** | Свойство `BarHeight.Pixels` принимает любое целое значение. Просто задайте нужное количество пикселей (например, `45`). |
| **Влияет ли изменение высоты штриха на закодированные данные?** | Нет. Меняется только визуальное представление; строка данных остаётся неизменной. |
| **Как изменить X‑размер после сохранения первого изображения?** | Вы можете изменить `gen.parameters.barcode.x_dimension.pixels` в любой момент до вызова `save()`. Изменение применится к последующим изображениям. |
| **Является ли генератор потокобезопасным?** | Экземпляр `BarcodeGenerator` не гарантирует потокобезопасность. Создавайте отдельный экземпляр для каждого потока, если генерируете штрих‑коды одновременно. |

## Заключение

Теперь вы знаете, как **изменять высоту штрихов штрих‑кода** в генераторе DataBar Omni‑Directional с помощью Python. В руководстве рассмотрены создание генератора, установка **X‑размера**, изменение свойства **высоты штрихов** и сохранение изображений в нужном **формате изображения штрих‑кода**.

Дальше вы можете экспериментировать с другими высотами, различными размерами модулей или переключаться на альтернативные форматы изображений, такие как JPEG или BMP. Также стоит изучить дополнительные возможности **barcode generator python**, например, добавление читаемого человеком текста или изменение цветовых схем.

Удачной разработки, и пусть ваши штрих‑коды всегда будут чёткими и правильно масштабированными!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}