---
category: general
date: 2026-10-28
description: Создайте изображение штрихкода в C# быстро. Узнайте, как использовать
  генератор штрихкодов C#, как задать размер пикселя и как изменить соотношение сторон
  для DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: ru
lastmod: 2026-10-28
og_description: Создайте изображение штрихкода в C# с помощью генератора штрихкодов.
  Следуйте этому руководству, чтобы задать размер пикселя, изменить соотношение сторон
  и генерировать штрихкоды DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Создание изображения штрих‑кода в C# – пошаговое руководство
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Как создать изображение штрихкода на C# с использованием генератора штрихкодов
url: /ru/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода с помощью C# и Barcode Generator

Если вам нужно **создать изображение штрих‑кода** в .NET‑приложении, это руководство покажет, как это сделать. Вы увидите полностью готовый, исполняемый пример, использующий библиотеку Barcode Generator C# для генерации штрих‑кода DataBar stacked omnidirectional, установки размера пикселя и изменения соотношения сторон.

Программная генерация штрих‑кодов устраняет необходимость во внешних инструментах и позволяет встраивать изображение напрямую в PDF, отчёты или UI‑элементы. В нижеприведённых шагах мы также рассмотрим **как задать размер пикселя** и **как изменить соотношение сторон** — два распространённых требования, когда нужен чёткий, правильно масштабированный штрих‑код.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия  
* IDE, поддерживающая C# (Visual Studio, Rider или VS Code)  
* NuGet‑пакет `BarcodeGenerator` (например, `GroupDocs.Barcode` или `Aspose.Barcode`), установленный в проекте  

Пакет можно добавить следующей командой:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tip:** Убедитесь, что версия пакета соответствует целевой платформе, чтобы избежать несовместимостей во время выполнения.

## Создание изображения штрих‑кода с помощью Barcode Generator C#

Первый шаг — создать экземпляр генератора с нужным типом штрих‑кода и данными. Пример ниже создаёт **DataBar stacked omnidirectional** штрих‑код, который идеально подходит для розничных сканеров.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Почему важна каждая строка

* **Создание `BarcodeGenerator`** – Конструктор принимает символьную схему штрих‑кода (`EncodeTypes.DatabarStackedOmniDirectional`) и строку исходных данных. Выбор правильной схемы гарантирует, что сканер сможет прочитать код.  
* **Установка `XDimension.Pixels`** – Это свойство управляет шириной самого маленького элемента штриха. Значение `2` даёт детализированное изображение, читаемое на большинстве экранов. Увеличьте его, если нужен более крупный штрих‑код для принтеров с низким разрешением.  
* **Настройка `AspectRatio`** – Семейство DataBar поддерживает несколько соотношений сторон, влияющих на отношение высоты к ширине. Значения `15` и `30` являются типичными; `15` даёт более короткий штрих‑код, а `30` — более высокий.  
* **Метод `Save`** – Сохраняет сгенерированный штрих‑код в файл PNG. При необходимости можно заменить `BarCodeImageFormat.Png` на `Jpeg` или `Bmp`, если ваша система требует другой формат.

## Как задать размер пикселя для разных контекстов рендеринга

Размер пикселя определяет визуальную плотность штрих‑кода. Если штрих‑код будет отображаться на мониторе с высоким DPI, можно увеличить размер пикселя до `3` или `4`. Для низкокачественных термопринтеров меньший размер пикселя (например, `1`) экономит чернила.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Edge case:** Установка размера пикселя слишком низким (< 1) приводит к `ArgumentOutOfRangeException`. Всегда проверяйте значение перед присвоением.

## Как изменить соотношение сторон без пересоздания генератора

Изменить соотношение сторон можно простым обновлением свойства; **не требуется** пересоздавать экземпляр `BarcodeGenerator`. Это экономит память и повышает производительность, когда нужно создать несколько изображений с разными формами.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Если требуется более двух соотношений, можно пройтись по массиву:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Ожидаемый результат

Запуск программы создаёт два PNG‑файла (или больше, если используется цикл). Откройте их в любом просмотрщике изображений — вы увидите чистый DataBar штрих‑код:

* **DatabarAspectRatio15.png** – короткий, широкий штрих‑код, подходящий для узких этикеток.  
* **DatabarAspectRatio30.png** – более высокий штрих‑код, повышающий надёжность сканирования под углом.

Оба изображения используют одинаковый размер пикселя (2 px на модуль), различаясь только высотой, что демонстрирует **как изменить соотношение сторон**, оставив остальные параметры неизменными.

## Распространённые ошибки и способы их избежать

| Симптом | Причина | Решение |
|---------|--------|--------|
| Штрих‑код выглядит размытым | `XDimension.Pixels` установлен слишком низко для текущего разрешения вывода | Увеличьте размер пикселя минимум до `2` для экранов, `3` для печати |
| Сканер не может прочитать код | Неправильный `EncodeTypes` для формата данных | Убедитесь, что данные GTIN‑14 соответствуют выбранной символьной схеме |
| `ArgumentOutOfRangeException` при изменении соотношения сторон | Значение соотношения не поддерживается библиотекой (допустимый диапазон: 15‑30) | Используйте только задокументированные значения или перехватите исключение и задайте значение по умолчанию |
| Файл не найден после `Save` | Относительный путь указывает на несуществующую директорию | Укажите абсолютный путь или предварительно вызовите `Directory.CreateDirectory` |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Следующие шаги — расширение рабочего процесса со штрих‑кодами

Теперь, когда вы умеете **создавать изображение штрих‑кода**, вы можете:

* **Встраивать PNG в PDF** с помощью библиотек `PdfSharp` или `iTextSharp`.  
* **Генерировать другие символьные схемы** (QR, Code128, PDF417), изменив значение перечисления `EncodeTypes`.  
* **Применять цветовые трансформации**, получая доступ к `barcode.Parameters.Barcode.Image.Color`.  
* **Отдавать изображение через endpoint ASP.NET Core** для генерации «на лету» в веб‑приложениях.

Все эти темы опираются на те же базовые концепции, рассмотренные в этом руководстве, такие как использование **barcode generator c#**, управление размером пикселя и манипуляции соотношением сторон.

## Заключение

Теперь вы знаете, как **создать изображение штрих‑кода** в C# с помощью Barcode Generator, как задать размер пикселя, как изменить соотношение сторон и как эффективно генерировать DataBar штрих‑коды. Полный, готовый к запуску пример можно скопировать в любой .NET‑проект, адаптировать под другие символьные схемы и расширять под реальные задачи.

Экспериментируйте с различными значениями `XDimension`, соотношениями сторон и форматами вывода. Если возникнут проблемы, обратитесь к таблице «Распространённые ошибки» или изучите официальную документацию библиотеки для более глубоких настроек. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}