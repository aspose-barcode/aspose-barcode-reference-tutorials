---
category: general
date: 2026-10-02
description: Создайте штрих‑код stacked databars в C# быстро. Узнайте, как задать
  XDimension, настроить соотношение сторон и экспортировать PNG‑изображения с генератором
  штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: ru
lastmod: 2026-10-02
og_description: Создайте штрих‑код stacked databars на C# с полным примером кода.
  Настройте XDimension, измените соотношение сторон и сохраните PNG‑файлы всего за
  несколько строк.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Создание штрих‑кода со stacked databars в C# — быстрый учебник
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Создание штрих‑кода со стеками DataBars в C# — пошаговое руководство
url: /ru/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание stacked databars barcode в C# – пошаговое руководство

Если вам нужно **создать штрих‑код stacked databars** в проекте .NET, этот учебник покажет вам, как это сделать. Вы увидите, как настроить X‑dimension, переключать соотношения сторон и сохранять результат в виде PNG‑файлов — всё с помощью библиотеки Aspose.BarCode.

Генерация stacked DataBar barcode не требует сложного графического конвейера. К концу этого руководства у вас будет два готовых PNG‑изображения, иллюстрирующих разные соотношения сторон, и вы поймёте, почему эти параметры важны для надёжности сканирования.

## Что понадобится

- .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
- Visual Studio 2022 или любой IDE для C#
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Разрешение на запись в папку, где будут сохраняться PNG‑файлы

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новое консольное приложение (или добавьте код в существующий проект) и импортируйте необходимые пространства имён:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Почему это важно:** `Aspose.BarCode.Generation` предоставляет класс `BarcodeGenerator`, а `Aspose.BarCode` содержит перечисление `BarCodeImageFormat`, используемое для сохранения изображений.

## Шаг 2: Инициализация генератора для stacked omnidirectional DataBar

Значение `EncodeTypes.DatabarStackedOmniDirectional` выбирает символьную систему stacked DataBar. Строка данных должна соответствовать формату GS1 Application Identifier (AI); здесь мы используем фиктивное значение GTIN‑14.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Почему это важно:** Выбранный тип кодирования сообщает библиотеке отрисовать *stacked* штрих‑код, что необходимо для этикеток высокой плотности, где ограничено вертикальное пространство.

## Шаг 3: Определение размера модуля (X‑dimension) в пикселях

X‑dimension управляет шириной самого маленького штриха (модуля). Значение 2 пикселя хорошо подходит для большинства выводов с экранным разрешением.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Почему это важно:** Сканеры интерпретируют ширину модуля как базовую единицу измерения. Слишком маленькое значение может привести к размытым отпечаткам; слишком большое — тратит место.

## Шаг 4: Сохранение первого изображения с соотношением сторон 15

Свойство `AspectRatio` влияет на соотношение высоты к ширине каждого stacked‑сегмента. Соотношение 15 является распространённым значением по умолчанию для розничных приложений.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Почему это важно:** Низкое соотношение сторон даёт более плоский штрих‑код, который может быть легче сканировать на некоторых материалах этикеток. Формат PNG сохраняет без потерь качество для тестирования.

## Шаг 5: Изменение соотношения сторон на 30 и сохранение второго изображения

Увеличение соотношения сторон делает каждый stacked‑сегмент выше, что может улучшить надёжность сканирования на фонах с низким контрастом.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Почему это важно:** Разные розничные сети или логистические партнёры могут требовать специфические размеры штрих‑кода. Предоставив обе версии, вы сможете быстро сравнить эффективность сканирования.

## Полный, исполняемый пример

Ниже приведена полная программа, которую можно скопировать в `Program.cs`. После установки NuGet‑пакета Aspose.BarCode она компилируется и запускается без изменений.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Ожидаемый вывод

При запуске программы создаются два файла в папке выполнения:

| Имя файла                     | Соотношение сторон | Визуальное описание |
|-------------------------------|--------------------|---------------------|
| `DatabarAspectRatio15.png`    | 15                 | Более короткий, более плоский stacked barcode |
| `DatabarAspectRatio30.png`    | 30                 | Более высокий, более вытянутый stacked barcode |

Вы можете открыть PNG‑файлы любой программой просмотра изображений, чтобы убедиться, что штрих‑код отрисован корректно.

![Пример создания штрих‑кода stacked databars](placeholder-image.png){alt="Пример создания штрих‑кода stacked databars"}

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| **Можно ли использовать другую X‑dimension?** | Да. Типичные значения находятся в диапазоне от 1 до 4 пикселей. Большие значения увеличивают размер штрих‑кода, но могут улучшить читаемость на принтерах с низким разрешением. |
| **Что если мне нужна другая символьная система?** | Замените `EncodeTypes.DatabarStackedOmniDirectional` другим значением `EncodeTypes`, например `DatabarStacked` (не омни‑направленный) или `DatabarLimited`. |
| **Как изменить формат вывода?** | Используйте `BarCodeImageFormat.Jpeg`, `Gif` или `Bmp` в вызове `Save`. |
| **Обязателен ли формат GTIN‑14?** | Символьная система DataBar ожидает числовую строку, предварённую соответствующим AI (например, `(01)` для GTIN‑14). Скорректируйте данные в соответствии с вашими требованиями. |
| **Что насчёт настроек DPI?** | Генератор учитывает свойство `Resolution`. Для печати высокого разрешения задайте `barcodeGen.Parameters.ImageResolution.DpiX` и `DpiY` соответственно. |

## Профессиональные советы

- **Пакетная генерация:** Оберните логику сохранения в цикл и передайте список GTIN, чтобы автоматически создавать тысячи штрих‑кодов.
- **Валидация:** Вызовите `barcodeGen.Validate()` перед сохранением, чтобы вовремя обнаружить некорректные данные.
- **Производительность:** Повторное использование того же экземпляра `BarcodeGenerator` (изменяя только параметры) быстрее, чем создание нового объекта для каждого изображения.

## Следующие шаги

Теперь, когда вы умеете **создавать stacked databars barcode** с пользовательскими соотношениями сторон, можете изучить следующее:

- Добавление читаемого человеком текста под штрих‑кодом (`barcodeGen.Parameters.Barcode.CodeText`).
- Экспорт в **PDF** для печатных листов этикеток (`BarCodeImageFormat.Pdf`).
- Интеграция генератора в веб‑API для выдачи штрих‑кодов по запросу.
- Эксперименты с другими **вторичными ключевыми словами**, такими как *C# barcode generator* и *barcode aspect ratio*, для точной настройки реализации под конкретное оборудование.

Счастливого кодинга и наслаждайтесь гибкостью, которую Aspose.BarCode приносит в ваши C# проекты со штрих‑кодами!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Создать stacked databar штрих‑код в C# – пошаговое руководство](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [databar stacked omnidirectional штрих‑код в C# – Полное руководство](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Как создать PNG‑изображения databar с C# и Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}