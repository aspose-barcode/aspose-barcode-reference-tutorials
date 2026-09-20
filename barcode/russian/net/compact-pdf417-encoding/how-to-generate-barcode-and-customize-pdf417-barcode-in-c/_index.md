---
category: general
date: 2026-09-19
description: Как генерировать штрих‑код в C# с пошаговым руководством. Узнайте, как
  настроить параметры штрих‑кода PDF417 и создать изображение штрих‑кода, которое
  разработчики C# могут использовать сразу.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: ru
lastmod: 2026-09-19
og_description: Как генерировать штрих‑код в C# с подробными инструкциями. Настройте
  параметры штрих‑кода PDF417 и создайте изображение штрих‑кода, которое проекты на
  C# могут использовать уже сегодня.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Как сгенерировать штрих‑код и настроить PDF417 в C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Как генерировать штрих‑код и настраивать штрих‑код PDF417 в C#
url: /ru/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑коды и настраивать PDF417 штрих‑код в C#

Если вам нужно **как генерировать штрих‑коды** в приложении .NET, этот учебник покажет готовое решение, готовое к запуску. Вы узнаете, как настраивать размеры PDF417 штрих‑кода, выбирать количество столбцов и, наконец, **создавать изображение штрих‑кода C#**, которое проекты могут внедрять напрямую.

Генерация штрих‑кода не требует сложного конвейера сборки. К концу этого руководства у вас будет PNG‑файл, содержащий MicroPDF417 штрих‑код точного размера и разрешения, которое вам нужно.

## Предварительные требования

Перед началом убедитесь, что установлено следующее:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.6+)
* Visual Studio 2022 (или любой предпочитаемый редактор C#)
* NuGet‑пакет Aspose.BarCode for .NET – установить с помощью  
  `dotnet add package Aspose.BarCode`

Дополнительные внешние инструменты не требуются.

## Шаг 1: Создание проекта и импорт пространств имён

Создайте новый консольный проект и добавьте ссылку на Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Откройте `Program.cs` и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Эти пространства имён предоставляют классы, позволяющие **как генерировать штрих‑коды** и управлять параметрами PDF417.

## Шаг 2: Инициализация генератора MicroPDF417 с нужным текстом

Первая строка создаёт экземпляр `BarcodeGenerator`, настроенный для символьного набора MicroPDF417. Конструктор принимает тип кодирования и строку данных, которую нужно закодировать.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Почему это важно:** MicroPDF417 — компактный вариант полного стандарта PDF417, идеальный для небольших этикеток или мобильных экранов. Инициализация генератора с правильным `EncodeTypes` гарантирует, что библиотека использует нужный алгоритм кодирования.

## Шаг 3: Настройка X‑размера (ширины модуля) для более высокой чёткости

X‑размер управляет шириной отдельного модуля штрих‑кода (самой маленькой чёрной или белой полоски). Установка небольшого значения в пикселях даёт изображение с более высоким разрешением.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** Большой X‑размер упрощает чтение штрих‑кода сканерами низкого разрешения, а маленькое значение упаковывает больше данных в ограниченное пространство. Регулируйте значение в зависимости от условий сканирования.

## Шаг 4: Определение количества столбцов для контроля размера штрих‑кода

MicroPDF417 поддерживает 1‑4 столбца. Большее количество столбцов создаёт более короткий, широкий штрих‑код; меньшее — более высокий, узкий.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Почему это важно:** Выбор правильного количества столбцов позволяет разместить штрих‑код в конкретном элементе интерфейса или на печатной этикетке без ручного масштабирования.

## Шаг 5: Сохранение штрих‑кода как PNG‑изображения

Наконец, запишите сгенерированный штрих‑код на диск. PNG сохраняет без потерь, что важно для чёткого сканирования.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Если целевая папка не существует, метод `Save` бросит `ArgumentException`. Можно защититься простой проверкой:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Полный исходный код

Объединив все части, получаем полностью рабочую программу:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Запуск этой программы создаёт файл **MicroPdf417.png**, выглядящий как скриншот ниже (изображение опущено). Штрих‑код кодирует текст *Sample* и учитывает заданные X‑размер и количество столбцов.

## Настройка других параметров PDF417

Хотя в этом руководстве рассматриваются **настройка pdf417 штрих‑кода** параметры, влияющие на размер, Aspose.BarCode предлагает множество дополнительных настроек, которые могут понадобиться:

| Свойство | Назначение | Типичные значения |
|----------|------------|-------------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Управляет количеством строк (высотой) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Устанавливает уровень коррекции ошибок (чем выше — тем более устойчив) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Генерирует усечённый штрих‑код (без стоп‑паттерна) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Выбирает числовую, текстовую или байтовую компакцию | `CompactionModes.Numeric` и др. |

**Совет:** Когда нужен штрих‑код фиксированной ширины, начните с увеличения `Columns` и уменьшения `XDimension`. Если сканер сообщает о пропущенных символах, повысите `ErrorLevel` для улучшения избыточности.

## Обработка граничных случаев

* **Текст слишком длинный для MicroPDF417:** Вариант Micro поддерживает до 1 KB данных. Если строка превышает этот лимит, переключитесь на полный символьный набор `Pdf417`, заменив `EncodeTypes.MicroPdf417` на `EncodeTypes.Pdf417`.
* **Неподдерживаемый формат изображения:** `BarCodeImageFormat` также поддерживает `Jpeg`, `Bmp` и `Gif`. Выберите формат, соответствующий вашему последующему конвейеру обработки.
* **Кроссплатформенные пути:** Используйте `Path.Combine` вместо жёстко заданных обратных слешей при работе под Linux или macOS.

## Проверка штрих‑кода

Проверьте полученное изображение любой стандартной программой‑сканером штрих‑кодов (мобильной или настольной). Сканер должен вернуть исходный текст **Sample**. Если это не происходит:

1. Убедитесь, что X‑размер не установлен ниже 1 пикселя (некоторые сканеры не распознают субпиксельные модули).
2. Проверьте, что выходной файл не повреждён — запустите программу повторно и сравните размеры файлов.
3. Увеличьте `ErrorLevel` для повышения устойчивости.

## Заключение

Теперь вы знаете **как генерировать штрих‑коды** в C# с помощью Aspose.BarCode, как **настраивать pdf417 штрих‑код** по размерам и количеству столбцов, а также как **создавать изображение штрих‑кода C#**, которое проекты могут внедрять напрямую. Полный пример демонстрирует практический рабочий процесс от настройки проекта до финального PNG‑файла.

Далее изучайте другие символьные наборы, такие как QR, Code128 или DataMatrix, меняя значение перечисления `EncodeTypes`. Настройка дополнительных параметров, например `Resolution` или `Margin`, позволяет точно подогнать каждый штрих‑код под ваши требования.

Удачной разработки, и пусть ваши штрих‑коды усиливают ваш следующий проект автоматизации!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как сгенерировать изображение PDF417 штрих‑кода в C# с Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Как создать PDF417 штрих‑код с Aspose — полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Как сохранить штрих‑код в C# — генерация PDF417 штрих‑кодов](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}