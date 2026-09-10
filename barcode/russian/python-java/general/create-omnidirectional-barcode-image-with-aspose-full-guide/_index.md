---
category: general
date: 2026-07-27
description: Создайте всенаправленное изображение штрихкода с помощью Aspose.BarCode.
  Узнайте, как генерировать штрихкод с Aspose, регулировать соотношение сторон и сохранять
  файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: ru
lastmod: 2026-07-27
og_description: Создайте всенаправленное изображение штрихкода с помощью Aspose. Следуйте
  этому руководству, чтобы сгенерировать штрихкод с Aspose, настроить соотношения
  сторон и экспортировать PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Создайте всенаправленное изображение штрихкода с Aspose – пошагово
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Создание всенаправленного изображения штрихкода с Aspose – Полное руководство
url: /ru/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание омнидирекционального изображения штрих‑кода с Aspose – Полное руководство

Когда‑нибудь вам нужно было **создать омнидирекциональное изображение штрих‑кода**, но вы не знали, какую библиотеку выбрать? Вы не одиноки. Во многих проектах логистики и розничной торговли формат DataBar Stacked Omnidirectional — это секретный ингредиент для компактного, высокоплотного кодирования.  

Хорошая новость? С **Aspose.BarCode** вы можете сгенерировать такой штрих‑код в паре строк кода, подправить его соотношение сторон и сразу сохранить PNG на диск. Ниже вы увидите, как **generate barcode with Aspose**, почему каждое параметр важен и на что обратить внимание при изменении соотношения сторон.

---

## Что покрывает этот учебник

Мы пройдем весь жизненный цикл:

1. Настройка папки вывода.  
2. Создание генератора DataBar Stacked Omnidirectional.  
3. Конфигурация пиксельных размеров и соотношения сторон.  
4. Сохранение штрих‑кода в виде PNG‑файлов.  
5. Расширение примера для других форматов и граничных случаев.

К концу вы получите готовое консольное приложение C#, которое выводит два разных изображения штрих‑кода. Никаких внешних инструментов, только чистый код Aspose.

**Prerequisites**

- .NET 6.0 SDK или новее (код также работает на .NET Framework 4.7.2).  
- NuGet‑пакет Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`).  
- Папка на диске, куда можно записать изображения.

Если всё уже готово, приступаем.

---

## Шаг 1: Подготовьте папку вывода

Сначала укажем программе, куда сбрасывать PNG‑файлы. Жёстко прописанный путь подходит для демонстрации, но в продакшене его обычно читают из конфигурации.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Почему это важно:* `Directory.CreateDirectory` идемпотентен; он не бросит исключение, если папка уже существует, избавляя от необходимости писать блок `try‑catch`.

---

## Шаг 2: Создайте генератор DataBar Stacked Omnidirectional

Теперь создаём генератор с нужным типом кодирования и примерными данными. Строка `"(01)12345678901231"` следует синтаксису GS1 Application Identifier для 14‑значного GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Explanation:* `EncodeTypes.DatabarStackedOmniDirectional` сообщает Aspose использовать омнидирекциональный вариант, который читается из любой ориентации — идеально для небольших этикеток, которые могут быть повернуты.

---

## Шаг 3: Установите общие параметры штрих‑кода

Прежде чем что‑то рендерить, задаём минимальный размер элемента (X‑Dimension). Значение **2 пикселя** дает чёткое изображение без увеличения размера файла.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tip:* Если нужна более высокая разрешающая способность для печати, увеличьте до 3 или 4. Помните, что больший X‑Dimension пропорционально увеличивает и ширину, и высоту.

---

## Шаг 4: Сгенерируйте и сохраните с соотношением сторон 15

Семейство DataBar позволяет регулировать **соотношение сторон**, которое управляет отношением высоты к ширине. Соотношение сторон **15** — распространённое значение по умолчанию для омнидирекционных штрих‑кодов.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*What you’ll see:* Относительно высокий штрих‑код, который всё равно удобно помещается на этикетке 2 × 1 см. Формат PNG сохраняет без потерь, что идеально для дальнейшей обработки или печати.

---

## Шаг 5: Измените соотношение сторон на 30 и сохраните снова

Хотите более «короткий» штрих‑код? Просто измените свойство `AspectRatio` и вызовите `Save` ещё раз. Не нужно заново создавать генератор.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Почему повторно использовать тот же генератор?* Объекты Aspose лёгкие; изменение свойства и повторное сохранение быстрее, чем создание нового экземпляра, и гарантирует, что те же настройки кодирования (например, X‑Dimension) останутся согласованными.

---

## Полный рабочий пример

Собрав всё вместе, получаем полностью самостоятельную программу, которую можно скопировать в новый консольный проект.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Expected output**

При запуске программа создаст подпапку `Barcodes` со следующими файлами:

- `DatabarAspectRatio15.png` – выше, классический вид.  
- `DatabarAspectRatio30.png` – шире, лучше подходит для широких этикеток.

Оба изображения кодируют одинаковый GTIN; различаются только визуальными пропорциями.

---

## Расширение примера (граничные случаи и варианты)

### 1. Другие форматы изображений

Aspose поддерживает BMP, JPEG, TIFF и SVG помимо PNG. Поменяйте значение enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG — векторный формат, его можно масштабировать без потери резкости — удобно для адаптивных веб‑приложений.

### 2. Настройка цветов

Возможно, понадобится белый штрих‑код на тёмном фоне. Установите `ForeColor` и `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Обработка недопустимых соотношений сторон

Aspose проверяет диапазон (обычно 5‑50). При передаче значения вне диапазона бросается `ArgumentException`. Оберните вызов `Save` в `try‑catch`, чтобы вывести дружелюбное сообщение:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Пакетная генерация

Если у вас список GTIN‑ов, пройдитесь по нему в цикле, обновляйте `CodeText` и сохраняйте каждый файл под уникальным именем. Объект генератора можно переиспользовать, экономя память.

---

## Частые ошибки и профессиональные советы

- **Никогда не забывайте установить `XDimension`** перед сохранением; значение по умолчанию (0.33 mm) может давать размытые изображения на низкоразрешающих экранах.  
- **Соотношение сторон — это высота‑к‑ширине**, а не наоборот. Большое число делает штрих‑код *короче* по вертикали.  
- **Пути к файлам:** используйте `Path.Combine`, чтобы избежать проблем с разделителями платформы — особенно если код работает в Linux‑контейнерах.  
- **Лицензирование:** Aspose.BarCode коммерческий. В режиме триала на изображении появляется водяной знак. Зарегистрируйте лицензию заранее, чтобы избежать сюрпризов в продакшене.

---

## Заключение

Теперь вы знаете, как **create omnidirectional barcode image** с помощью Aspose, регулировать соотношение сторон и экспортировать PNG‑файлы — всё это в менее чем 30 строках C#. Этот учебник показал пошаговый процесс, объяснил, почему каждый параметр важен, и рассмотрел расширения, такие как другие форматы, цвета и пакетная обработка.

Готовы к следующему вызову? Попробуйте генерировать QR‑коды, внедрять штрих‑код в PDF или интегрировать вывод в ASP.NET Core API. Принципы **generate barcode with Aspose** одинаковы для всех типов штрих‑кодов, так что вы сможете переиспользовать полученные знания.

Есть вопросы или хотите поделиться своими доработками? Оставляйте комментарий ниже — happy coding!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}