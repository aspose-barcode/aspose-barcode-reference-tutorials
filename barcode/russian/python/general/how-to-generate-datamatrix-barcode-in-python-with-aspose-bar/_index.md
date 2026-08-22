---
category: general
date: 2026-08-22
description: Научитесь генерировать штрих‑код DataMatrix в Python и кодировать русский
  текст с помощью Aspose.BarCode – пошаговое руководство.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: ru
lastmod: 2026-08-22
og_description: Создайте штрих‑код DataMatrix на Python и закодируйте русский текст
  с помощью Aspose.BarCode. Следуйте полному примеру и запустите его мгновенно.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Создание штрих‑кода DataMatrix в Python — полный учебник Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Как сгенерировать штрих‑код DataMatrix в Python с помощью Aspose.BarCode
url: /ru/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать DataMatrix штрих‑код в Python с Aspose.BarCode

Если вам нужно **генерировать DataMatrix штрих‑код** в Python, одновременно **кодируя русский текст**, это руководство покажет вам точные шаги. Вы увидите полный, исполняемый пример, который создает расширенный codetext, настраивает штрих‑код и сохраняет изображение в одном скрипте.

Создание штрих‑кодов, содержащих символы не‑ASCII, часто вызывает вопросы о наборах символов и кодировании данных. Используя `ExtCodetextBuilder` из Aspose.BarCode, вы можете безопасно внедрять UTF‑8 текст, например кириллические символы, в символ DataMatrix. Результат работает с любым сканером, поддерживающим стандарт DataMatrix.

В этом руководстве вы:

* Установите необходимый пакет Aspose.BarCode.
* Сформируете расширенный codetext, комбинирующий обычные данные и русский текст.
* **Сгенерируете DataMatrix штрих‑код** с расширенной строкой.
* Настроите параметры штрих‑кода, такие как размер модуля.
* Сохраните штрих‑код в файл PNG.

Внешние сервисы не требуются; всё работает локально на вашем компьютере.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* Установленный Python 3.8 или новее.
* Действующая лицензия Aspose.BarCode для Python (бесплатная пробная версия подходит для разработки).
* Базовые знания скриптинга на Python.

Вы можете установить библиотеку Aspose.BarCode через pip:

```bash
pip install aspose-barcode
```

## Шаг 1: Создать строку расширенного codetext

Первая задача — создать одну строку, содержащую как обычный идентификатор продукта, так и русскую фразу. `ExtCodetextBuilder` позволяет конкатенировать разные части codetext, сохраняя информацию об их кодировке.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Почему этот шаг важен** – символы DataMatrix хранят необработанные байты. Когда необходимо смешивать алфавиты, вы должны указать кодировщику, какой набор символов применяется к каждому сегменту. Метод `add_eci_codetext` вставляет индикатор ECI перед русским текстом, гарантируя, что сканеры интерпретируют байты как UTF‑8. Без ECI кириллические символы будут отображаться как искажённые данные.

## Шаг 2: Создать генератор DataMatrix штрих‑кода

Когда расширенный codetext готов, создайте экземпляр `BarcodeGenerator`, указывая тип `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Почему DataMatrix?** – DataMatrix это двумерный штрих‑код, способный хранить до 2 335 буквенно‑цифровых символов или 1 556 байт. Он идеален для небольших предметов, промышленных деталей и ситуаций, когда необходимо внедрять многоязычный текст.

## Шаг 3: (Опционально) Настроить параметры штрих‑кода

Aspose.BarCode предоставляет множество параметров. Для большинства сценариев настройки по умолчанию дают читаемый символ. Однако вы можете захотеть контролировать размер каждого модуля (самый маленький квадрат в матрице), чтобы соответствовать требованиям печати.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Другие полезные параметры включают уровень коррекции ошибок, отступ и цвет фона. Регулируйте их только если ваша целевая среда сканирования требует определённых допусков.

## Шаг 4: Сохранить изображение штрих‑кода

Наконец, запишите штрих‑код в файл. Метод `save` поддерживает PNG, JPEG, BMP и несколько векторных форматов.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Когда вы откроете `extended_codetext.png`, вы увидите чёткий символ DataMatrix. Сканирование его стандартным считывателем DataMatrix вернёт две части:

1. **ABC123** – обычный идентификатор.
2. **Привет** – русское приветствие, корректно декодированное как UTF‑8.

## Полный, исполняемый пример

Ниже приведён полный скрипт, который вы можете скопировать и вставить в файл с именем `generate_datamatrix.py`. Замените `YOUR_DIRECTORY` на существующую папку в вашей системе.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Запустите скрипт из командной строки:

```bash
python generate_datamatrix.py
```

Вы должны увидеть вывод в консоли, похожий на:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Проверка результата

Чтобы убедиться, что штрих‑код правильно кодирует русскую фразу:

1. Откройте PNG‑файл в просмотрщике изображений.
2. Используйте любое приложение для сканирования DataMatrix (многие мобильные приложения поддерживают его) или аппаратный сканер.
3. Декодированная строка должна отображать `ABC123Привет` (или две части, разделённые в зависимости от интерфейса сканера).

Если русские символы отображаются как нечитаемый набор, проверьте, поддерживает ли сканер ECI UTF‑8. Большинство современных считывателей поддерживают его, но устаревшие устройства могут требовать явной настройки.

## Распространённые ошибки и как их избежать

| Проблема | Причина | Решение |
|----------|---------|---------|
| Искажённый вывод кириллицы | Отсутствует индикатор ECI | Используйте `add_eci_codetext` с `eci_encoding=3`. |
| Штрих‑код слишком мал для принтера | Размер модуля по умолчанию слишком мелкий для низкого DPI | Увеличьте `x_dimension` (например, `3.0` или `4.0`). |
| Файл не сохранён | Недействительный путь к директории | Убедитесь, что `YOUR_DIRECTORY` существует и доступен для записи. |
| Сканер не может прочитать | Слишком высокая плотность данных | Уменьшите объём кодируемых данных или увеличьте уровень коррекции ошибок (`generator.parameters.barcode.error_correction_level`). |

## Расширение примера

Вы можете адаптировать этот шаблон для других языков или типов данных:

* **Кодировать японский или арабский текст** – измените `eci_encoding` на соответствующее значение (например, 5 для ISO‑8859‑5, 6 для ISO‑8859‑7).  
* **Добавить несколько ECI‑сегментов** – вызовите `add_eci_codetext` несколько раз, каждый раз с собственной кодировкой.  
* **Создать QR‑код вместо этого** – замените `EncodeTypes.DATA_MATRIX` на `EncodeTypes.QR`.  

Все остальные шаги остаются одинаковыми, поскольку `ExtCodetextBuilder` абстрагирует работу с байтами низкого уровня.

## Заключение

Теперь вы знаете, как **генерировать DataMatrix штрих‑код** в Python и **кодировать русский текст** с помощью функции расширенного codetext в Aspose.BarCode. Полный скрипт обрабатывает согласование наборов символов, создание штрих‑кода и вывод изображения всего несколькими строками кода.

Далее изучайте другие символьные системы штрих‑кодов (PDF417, Aztec) или интегрируйте генератор в веб‑службу, возвращающую PNG‑изображения по запросу. Те же принципы — построение расширенного codetext и выбор соответствующего `EncodeTypes` — применимы ко всему набору Aspose.BarCode.

Удачной разработки и наслаждайтесь возможностями многоязычной генерации штрих‑кодов!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать DataMatrix штрих‑коды с помощью Aspose.BarCode для .NET – пошаговое руководство](/barcode/english/net/datamatrix-barcode-configuration/)
- [Генерация DataMatrix штрих‑кода в ASCII‑режиме с Aspose.BarCode для .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Как генерировать DataMatrix штрих‑коды (ECC 200) с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}