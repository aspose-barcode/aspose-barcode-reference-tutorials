---
category: general
date: 2026-07-30
description: Создайте штрих‑код Databar Stacked Omnidirectional на Python. Следуйте
  этому пошаговому руководству, чтобы настроить соотношение сторон, XDimension и экспортировать
  PNG с помощью генератора штрих‑кодов на Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: ru
lastmod: 2026-07-30
og_description: Создайте штрих‑код Databar Stacked Omnidirectional в Python. Это руководство
  показывает, как установить XDimension, настроить соотношение сторон DataBar и сохранить
  в PNG с помощью BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Создание многослойного всенаправленного штрих‑кода Databar – учебник по
  Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Создать штрих‑код Databar Stacked Omnidirectional в Python
url: /ru/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание Databar Stacked Omnidirectional штрих‑кода в Python

Когда‑нибудь нужно было **create databar stacked omnidirectional** штрих‑код в Python, но вы не знали, с чего начать? Вы не одиноки — многие разработчики сталкиваются с этим препятствием, когда впервые работают с классом `BarcodeGenerator`. Хорошая новость в том, что весь процесс довольно прост, как только вы поймёте ключевые свойства.

В этом руководстве мы пройдём полный, готовый к запуску пример, использующий **python barcode generator** для установки XDimension, настройки соотношения сторон DataBar и, наконец, экспорта двух PNG‑файлов. К концу вы будете уверенно генерировать высококачественные stacked omnidirectional символы для любого проекта в сфере инвентаризации или логистики.

## Что вы узнаете

- Как создать **databar stacked omnidirectional** генератор с полезной нагрузкой GTIN‑14.  
- Почему **XDimension pixel size** важен для надёжности сканирования.  
- Как **DataBar aspect ratio** влияет на ширину строки относительно её высоты.  
- Как сохранить результат в файл **BarCodeImageFormat PNG**.  
- Советы по повторному использованию того же объекта генератора для создания нескольких вариантов без лишних затрат памяти.

### Предварительные требования

- Python 3.8+ (используемая библиотека написана полностью на Python, без необходимости в скомпилированных wheel‑файлах).  
- Пакет `barcode-generator` (устанавливается командой `pip install barcode-generator`).  
- Папка, в которую можно записывать файлы — скрипт сохранит туда два PNG‑изображения.

Если вы уверенно работаете с базовыми импортами Python и объектно‑ориентированным кодом, вы готовы приступить.

## Создание Databar Stacked Omnidirectional штрих‑кода – обзор шагов

Ниже мы разбиваем процесс на шесть небольших шагов. Каждый шаг — самостоятельный фрагмент кода, который можно скопировать и вставить в REPL или файл скрипта. Экспериментируйте — изменение соотношения сторон или XDimension мгновенно даст иной визуальный стиль.

---

## Шаг 1: Создание Databar Stacked Omnidirectional генератора

Первое, что мы делаем, — **create databar stacked omnidirectional** генератор, передавая соответствующее перечисление `EncodeTypes` и строку данных.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Почему это важно:** Флаг `EncodeTypes.DatabarStackedOmniDirectional` сообщает библиотеке, что нужно создать stacked omnidirectional символ, единственный вариант DataBar, способный кодировать до 14 цифр и при этом оставаться читаемым под любым углом.

---

## Настройка XDimension Pixel Size

**XDimension pixel size** управляет самым маленьким модулем (самой тонкой чёрной полосой). Значение `2` пикселя хорошо подходит для большинства сценариев отображения на экране.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** Если планируете печатать штрих‑код с высоким DPI, увеличьте это значение до 3 или 4, чтобы избежать размытых краёв.

---

## Регулировка DataBar Aspect Ratio (15)

**DataBar aspect ratio** определяет, насколько широкой будет каждая строка по сравнению с её высотой. Соотношение `15` даёт более широкие строки, что многие сканеры предпочитают для быстрого захвата движения.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Почему 15?** Официальная спецификация GS1 рекомендует соотношение от 10 до 20 для stacked omnidirectional символов. Мы выбираем `15` как сбалансированное значение по умолчанию.

---

## Экспорт штрих‑кода в PNG с помощью BarCodeImageFormat

Теперь, когда генератор настроен, сохраняем изображение. Перечисление `BarCodeImageFormat.Png` гарантирует без потерь вывод, идеальный для последующей обработки.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Что вы увидите:** Откройте полученный PNG; вы заметите чистый, контрастный штрих‑код с относительно широкими строками.

---

## Изменение DataBar Aspect Ratio до 30

Иногда нужны более высокие строки вместо более широких — возможно, чтобы разместить их на узкой этикетке. Переключение **DataBar aspect ratio** на `30` делает каждую строку выше.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** Очень высокие соотношения (например, >40) могут привести к тому, что штрих‑код превысит типичные высоты этикеток, поэтому протестируйте на реальном принтере перед окончательным использованием.

---

## Повторный экспорт штрих‑кода с новым соотношением сторон

Наконец, мы повторно используем тот же объект `barcode_generator`, чтобы записать второй PNG. Нет необходимости заново создавать генератор — просто измените свойство и вызовите `Save` ещё раз.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Результат:** У вас теперь два PNG‑файла — один с широкими строками (`AR15`), другой с высокими строками (`AR30`). Сравните их бок‑о‑бок, чтобы решить, какой лучше подходит для вашей сканирующей установки.

---

## Полный рабочий пример

Объединив всё вместе, получаем полный скрипт, готовый к мгновенному запуску. Замените `YOUR_DIRECTORY` на абсолютный путь к папке на вашем компьютере.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Ожидаемый вывод** (в консоли):

```
✅ Two PNG files created – AR15 and AR30
```

И два файла‑изображения появятся в целевой папке, готовые к тестированию сканирования.

---

## Заключение

Мы только что **created databar stacked omnidirectional** штрих‑коды в Python, отрегулировали **XDimension pixel size**, поэкспериментировали с двумя различными настройками **DataBar aspect ratio** и экспортировали результаты как файлы **BarCodeImageFormat PNG**. Весь процесс укладывается в несколько строк кода, но даёт полный контроль над визуальными характеристиками, важными для сканеров.

Что дальше? Попробуйте заменить полезную нагрузку на другой GTIN, поиграйте с цветами, преобразовав PNG в палитровое изображение, или сгенерируйте PDF‑отчёт, встраивая оба PNG рядом. Класс `BarcodeGenerator` достаточно гибок, чтобы справиться со всеми этими сценариями, так что экспериментируйте без ограничений.

Есть вопросы по конкретному случаю использования или возникла ошибка? Оставьте комментарий ниже, и я с радостью помогу. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, развивая техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}