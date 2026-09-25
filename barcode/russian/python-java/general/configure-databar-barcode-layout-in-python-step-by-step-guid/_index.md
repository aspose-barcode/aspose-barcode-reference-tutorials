---
category: general
date: 2026-08-12
description: Быстро настройте макет штрихкода Databar в Python. Узнайте, как задать
  столбцы, строки и сохранять изображения с помощью библиотеки генератора штрихкодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: ru
lastmod: 2026-08-12
og_description: Настройте макет штрих‑кода Databar в Python, чтобы управлять столбцами,
  строками и выводом изображения. Следуйте этому руководству для готового решения.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Настройка макета штрихкода Databar в Python — полный учебник
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Настройка макета штрих‑кода Databar в Python — пошаговое руководство
url: /ru/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка макета штрих‑кода Databar в Python – пошаговое руководство

Если вам нужно **настроить макет штрих‑кода Databar в Python**, это руководство проведёт вас через весь процесс. Вы увидите, как задать количество столбцов или строк для штрих‑кода Databar Expanded Stacked и как сохранить полученное изображение одним вызовом библиотеки генерации штрих‑кодов.

Контроль макета важен, когда вы размещаете штрих‑коды на узкой упаковке, чеках или экранах мобильных устройств. В разделах ниже мы рассмотрим необходимые импорты, два варианта макета (столбцы и строки) и лучшие практики сохранения чистого PNG‑изображения.

## Что понадобится

Прежде чем начать, убедитесь, что у вас есть:

* Python 3.8 или новее
* `aspose.barcode` (или любой совместимый пакет генерации штрих‑кодов) установлен  
  ```bash
  pip install aspose-barcode
  ```
* Права записи в папку, где будут храниться PNG‑файлы

Дополнительные внешние инструменты не требуются — библиотека самостоятельно обрабатывает рендеринг, масштабирование и кодирование изображения.

## Как настроить макет штрих‑кода Databar в Python

Ядром решения является класс `BarcodeGenerator`. Он принимает перечисление `EncodeTypes`, которое определяет символьность штрих‑кода — в данном случае `EncodeTypes.DatabarExpandedStacked`. После создания генератора вы можете изменить макет, задав свойства `columns` или `rows` у параметра `data_bar`.

### Шаг 1: Импортировать необходимые классы

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Эти импорты дают доступ к генератору, перечислению типов Databar и константе формата изображения PNG.

### Шаг 2: Создать генератор штрих‑кода для Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Зачем это нужно?*  
`EncodeTypes.DatabarExpandedStacked` указывает библиотеке генерировать символьность **Databar Expanded Stacked**, которая поддерживает более длинные числовые строки при компактном размере. Второй аргумент — данные для кодирования; это может быть любая строка, соответствующая спецификации Databar.

### Шаг 3: Задать количество столбцов (горизонтальный макет)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** — ключевая фраза для этой операции. При увеличении количества столбцов штрих‑код растягивается по горизонтали, что может быть полезно для широких этикеток. Библиотека автоматически пересчитывает ширину модуля, чтобы общий размер оставался неизменным.

#### Совет профессионала
Максимальное количество столбцов для Databar Expanded Stacked равно 8. Установка значения выше предела приведёт к его ограничению максимумом, но лучше проверять ввод заранее.

### Шаг 4: Сохранить изображение штрих‑кода с макетом по столбцам

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** — действие, записывающее отрисованный штрих‑код на диск. PNG — без потерь, что сохраняет резкие края, необходимые для надёжного сканирования.

### Шаг 5: Создать второй генератор для того же типа штрих‑кода (макет по строкам)

Если вам нужен вертикальный стек, используйте строки вместо столбцов. Ниже представленный код повторно использует то же значение, но создаёт новый экземпляр `BarcodeGenerator`, чтобы не смешивать настройки столбцов и строк.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Шаг 6: Задать количество строк (вертикальный макет)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** располагает модули штрих‑кода вертикально. Макет из трёх строк уменьшает высоту каждого отдельного стека, делая штрих‑код пригодным для узких чеков или мобильных экранов.

#### Пограничный случай
Если установить `rows` в 1, библиотека генерирует одно‑строчный Databar (эквивалент стандартного Databar). Значения ниже 1 игнорируются и сбрасываются к значению по умолчанию (1 строка).

### Шаг 7: Сохранить изображение штрих‑кода с макетом по строкам

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Снова **save barcode image** с использованием PNG, чтобы сохранить чёткость вывода.

## Полный исполняемый пример

Собрав все части вместе, вы получаете автономный скрипт, который можно добавить в любой проект на Python.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Ожидаемый результат**

Запуск скрипта создаёт два PNG‑файла:

* `output/ExpandedCols4.png` – штрих‑код, растянутый на четыре столбца
* `output/ExpandedRows3.png` – штрих‑код, сжатый в три строки

Оба изображения можно открыть в любом просмотрщике или импортировать напрямую в PDF‑счета, шаблоны этикеток или веб‑страницы.

## Часто задаваемые вопросы и устранение неполадок

| Question | Answer |
|----------|--------|
| *Что делать, если штрих‑код выглядит размытым?* | Увеличьте разрешение изображения, задав `barcode_generator.parameters.image_width` и `image_height` перед вызовом `save`. |
| *Можно ли использовать другие форматы изображений?* | Да. При необходимости замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`. |
| *Есть ли ограничение на длину данных?* | Databar Expanded Stacked поддерживает до 74 числовых символов. При превышении лимита генерируется `ArgumentException`. |
| *Как изменить цвет переднего плана?* | Используйте `barcode_generator.parameters.barcode.color = Color.Blue` (импортируйте `System.Drawing.Color`). |
| *Можно ли комбинировать столбцы и строки?* | Нет. API рассматривает столбцы и строки как взаимно исключающие режимы макета. Выбирайте один из них для каждого экземпляра штрих‑кода. |

## Следующие шаги

Теперь, когда вы умеете **настраивать макет штрих‑кода Databar**, рассмотрите изучение связанных тем:

* **Добавить текстовые подписи** – используйте `barcode_generator.parameters.barcode.code_text` для отображения закодированного значения под изображением.
* **Встроить штрих‑код в PDF** – объедините сгенерированный PNG с `aspose.pdf` для создания печатных документов.
* **Динамический размер** – вычисляйте оптимальное количество столбцов или строк исходя из размеров этикетки во время выполнения.
* **Пакетная обработка** – пройдитесь по CSV с кодами продуктов, чтобы автоматически создать библиотеку изображений штрих‑кодов.

Экспериментируйте с различными значениями столбцов и строк, чтобы увидеть, как они влияют на надёжность сканирования на ваших устройствах. Чем больше вы тестируете, тем лучше понимаете компромиссы между размером штрих‑кода, читаемостью и ограничениями пространства.

---

*Счастливого кодинга! Если это руководство оказалось полезным, поделитесь им с коллегами или оставьте комментарий о проблемах с макетом, с которыми вы столкнулись.*


## Что изучать дальше?


В следующих руководствах рассматриваются тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}