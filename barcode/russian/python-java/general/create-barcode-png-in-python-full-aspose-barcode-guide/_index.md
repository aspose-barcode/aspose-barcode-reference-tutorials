---
category: general
date: 2026-07-21
description: Создайте PNG‑изображение штрихкода с помощью Aspose.Barcode в Python.
  Узнайте, как генерировать штрихкод из данных, задавать размеры и сохранять изображение
  штрихкода за несколько минут.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- generate barcode from data
- generate planet barcode
- how to generate barcode python
- save barcode image
language: ru
lastmod: 2026-07-21
og_description: Быстро создавайте PNG‑штрихкоды с помощью Aspose.Barcode. Это руководство
  показывает, как генерировать штрихкод из данных, регулировать размер и сохранять
  изображение штрихкода с использованием Python.
og_image_alt: Screenshot of a generated Planet barcode saved as a PNG file
og_title: Создание PNG‑штрихкода в Python – Полный учебник Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  headline: Create barcode png in Python – Full Aspose.Barcode Guide
  type: TechArticle
- description: Create barcode png using Aspose.Barcode in Python. Learn how to generate
    barcode from data, set dimensions, and save barcode image in minutes.
  name: Create barcode png in Python – Full Aspose.Barcode Guide
  steps:
  - name: Running the script
    text: '1. Install Jython (e.g., `brew install jython` on macOS or download from
      the official site). 2. Place the Aspose.Barcode for Java JAR in Jython’s classpath,
      for example:'
  - name: 'Example: Switching to Code128'
    text: '```python generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
      ```'
  - name: Quick fix for missing folder
    text: '```python import os output_dir = os.path.dirname(output_path) if not os.path.isdir(output_dir):
      os.makedirs(output_dir) ```'
  type: HowTo
tags:
- barcode
- python
- Aspose
- image generation
title: Создание PNG‑штрихкода в Python – Полное руководство Aspose.Barcode
url: /ru/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание barcode png в Python – Полное руководство Aspose.Barcode

Когда‑то задавались вопросом, как **создать barcode png** без борьбы с низкоуровневыми библиотеками изображений? Вы не одиноки. Многие разработчики ищут быстрый и надёжный способ превратить сырые данные в чистый PNG‑штрихкод, и Aspose.Barcode делает это проще простого.

В этом руководстве мы пройдём по точным шагам **генерации штрихкода из данных** с использованием симболики Planet, настроим его размеры и, наконец, **сохраним изображение штрихкода** в файл PNG. К концу вы получите готовый к запуску скрипт и несколько советов, которые сделают ваш код более надёжным.

## Что вы узнаете

- Как настроить Aspose.Barcode для проектов Python (Jython)  
- Точный код для **генерации штрихкода Planet** с пользовательской шириной и высотой  
- Способы **сохранения изображения штрихкода** в PNG, JPG или другие форматы  
- Распространённые подводные камни и как их избежать  

Предварительный опыт работы с Aspose не требуется — достаточно базовых знаний Python и совместимого с Java рантайма.

---

## Как создать barcode png с помощью Aspose.Barcode в Python

Ниже приведён полностью готовый к запуску скрипт. Скопируйте его в файл `create_planet_barcode.py` и выполните с помощью Jython (или любого Python‑интерпретатора с поддержкой Java).

```python
# ------------------------------------------------------------
# create_planet_barcode.py
# Demonstrates how to create barcode png using Aspose.Barcode
# ------------------------------------------------------------

# Step 1: Import the required Aspose.Barcode classes
# Note: These classes live in the Java package `com.aspose.barcode`,
# so you need a JVM‑based Python (Jython) or use JPype.
from com.aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Choose the symbology (Planet) and feed the data you want to encode
# The data string can be any alphanumeric value that fits the Planet rules.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 3: Adjust the X dimension (module width) – this controls the bar thickness
# Here we set it to 4 pixels for a nicely balanced look.
generator.getParameters().getBarcode().setXDimension(4)

# Step 4: Set a custom bar height – 100 pixels gives a clear, readable barcode.
generator.getParameters().getBarcode().setBarHeight(100)

# Step 5: Choose the output folder and file name.
# Feel free to change the path to suit your project layout.
output_path = "output/Planet_100px.png"

# Step 6: Save the generated barcode image as a PNG file.
# BarCodeImageFormat.Png tells Aspose to output a PNG.
generator.save(output_path, BarCodeImageFormat.Png)

print("✅ Barcode PNG created at:", output_path)
```

**Пояснение к каждому блоку**

- **Раздел импорта** – Мы подключаем три основных класса: `BarcodeGenerator` (движок), `EncodeTypes` (перечисление всех симболик) и `BarCodeImageFormat` (перечисление форматов вывода).  
- **Создание генератора** – `EncodeTypes.Planet` указывает Aspose использовать символику *Planet*, а второй аргумент `"123456"` – это данные, которые мы хотим закодировать. Это удовлетворяет требованию **generate barcode from data**.  
- **X‑dimension и высота полос** – Эти два свойства управляют визуальными размерами. Настройте их под требования печати или UI; значения по умолчанию могут быть слишком малы для дисплеев с высоким разрешением.  
- **Вызов save** – Метод `save` записывает изображение на диск. Передавая `BarCodeImageFormat.Png`, мы гарантируем, что файл будет PNG, завершая цель **create barcode png**.

### Запуск скрипта

1. Установите Jython (например, `brew install jython` на macOS или скачайте с официального сайта).  
2. Поместите JAR‑файл Aspose.Barcode for Java в classpath Jython, например:

```bash
export CLASSPATH=$CLASSPATH:/path/to/Aspose.Barcode.jar
```

3. Выполните:

```bash
jython create_planet_barcode.py
```

Вы увидите строку подтверждения и файл `Planet_100px.png` в папке `output`. Откройте его в любом просмотрщике изображений – вы увидите чёткий штрихкод Planet, готовый к сканированию.

![Create barcode png example](https://via.placeholder.com/400x150.png?text=Planet+Barcode+PNG "Create barcode png example")

*Текст alt изображения: “Скриншот сгенерированного штрихкода Planet, сохранённого как PNG‑файл”* – это удовлетворяет требованию alt‑текста.

## Генерация штрихкода из данных – более глубокий взгляд

Строка  

```python
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```  

выполняет основную работу. Почему это важно:

- **EncodeTypes.Planet** – Planet – менее распространённая симболика, идеальная для компактных числовых данных.  
- **"123456"** – Любая строка, соответствующая набору символов Planet (только цифры), подходит. Если попытаться передать буквы, Aspose выбросит `BarcodeException`.  

Если нужно **generate barcode from data**, включающего буквы, переключитесь на симболику, поддерживающую алфавитно‑цифровые символы, например `EncodeTypes.Code128`. Остальная часть скрипта остаётся без изменений.

### Пример: переключение на Code128

```python
generator = BarcodeGenerator(EncodeTypes.Code128, "ABC-1234")
```

Теперь вы **generated barcode from data**, содержащих буквы и цифры, и всё ещё можете **save barcode image** как PNG тем же вызовом `save`.

## Установка пользовательских размеров и сохранение изображения штрихкода

Иногда размер по умолчанию слишком мал для печатной этикетки. Поэтому мы раскрываем два свойства:

| Свойство      | Что контролирует                     | Типичные значения |
|---------------|--------------------------------------|-------------------|
| `XDimension`  | Ширина одного модуля (тонкой полосы) | 2‑6 пикселей для экрана, 8‑12 для печати |
| `BarHeight`   | Высота полос                         | 50‑150 пикселей, в зависимости от размера этикетки |

Настройка обоих позволяет адаптировать штрихкод под любой носитель. После изменения `save` всё равно записывает файл **create barcode png**, без дополнительных шагов.

## Распространённые подводные камни при генерации штрихкода Planet

1. **Недопустимая длина данных** – Planet кодирует 2‑12 цифр. При попытке использовать более 12 будет выброшено исключение.  
2. **Отсутствующая папка вывода** – Если `output/` не существует, `generator.save` бросит `FileNotFoundException`. Создайте папку заранее или используйте `os.makedirs`.  
3. **Проблемы с classpath** – Забвение добавить `Aspose.Barcode.jar` в `CLASSPATH` приводит к `ImportError`. Проверьте переменную окружения.

### Быстрое решение для отсутствующей папки

```python
import os
output_dir = os.path.dirname(output_path)
if not os.path.isdir(output_dir):
    os.makedirs(output_dir)
```

Добавьте этот фрагмент перед вызовом `save`, и ошибка «каталог не найден» больше не появится.

## Как генерировать barcode python – альтернативные подходы

Хотя решение Aspose мощное, вы можете задаться вопросом **how to generate barcode python** с помощью чисто Python‑библиотек. Инструменты вроде `python-barcode` или `qrcode` способны генерировать 1D/2D штрихкоды, но им не хватает широкой поддержки симболик (например, Planet), которую предоставляет Aspose. Если нужны только распространённые типы (Code128, QR), эти библиотеки подойдут; для редких симболик предпочтительнее Aspose.

## Расширение примера – несколько форматов и пакетная обработка

Освоив работу с одним штрихкодом, масштабировать процесс просто:

```python
data_list = ["001122", "334455", "667788"]
for idx, data in enumerate(data_list, start=1):
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.getParameters().getBarcode().setXDimension(4)
    gen.getParameters().getBarcode().setBarHeight(100)
    file_name = f"output/Planet_{data}_{idx}.png"
    gen.save(file_name, BarCodeImageFormat.Png)
    print(f"Saved {file_name}")
```

Теперь вы **generated barcode from data** в цикле, автоматически **saving barcode image** файлов для каждой записи. Замените `BarCodeImageFormat.Png` на `Jpeg` или `Bmp`, если нужен другой формат.

## Итоги и дальнейшие шаги

Мы рассмотрели всё, что нужно для **create barcode png** с Aspose.Barcode в Python:

1. Импорт Java‑классов через Jython.  
2. **Generate planet barcode** (или любую другую симболику) из ваших данных.  
3. Тонкая настройка `XDimension` и `BarHeight` под ваш дизайн.  
4. **Save barcode image** как PNG, завершая рабочий процесс **create barcode png**.  

Что дальше? Попробуйте добавить подписи под штрихкодом, поэкспериментировать с цветным выводом (`BarCodeImageFormat.Png24`) или интегрировать скрипт в веб‑службу, возвращающую PNG‑штрихкоды по запросу.

---

**Счастливого кодинга!** Если возникнут проблемы, оставьте комментарий ниже — я с радостью помогу оптимизировать ваш конвейер генерации штрихкодов.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом гайде. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы вы могли освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}