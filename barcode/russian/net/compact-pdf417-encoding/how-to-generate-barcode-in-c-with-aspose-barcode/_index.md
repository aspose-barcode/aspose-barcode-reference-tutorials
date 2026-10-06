---
category: general
date: 2026-09-16
description: Узнайте, как генерировать штрих‑код и задавать его размер в C#. Пошаговое
  руководство по использованию Aspose.BarCode для создания изображения Micro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: ru
lastmod: 2026-09-16
og_description: Как генерировать штрих‑код в C# и задавать его размер с помощью Aspose.BarCode.
  Следуйте этому краткому руководству, чтобы создать PNG‑изображение Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Как сгенерировать штрих‑код в C# – полное руководство по Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Как сгенерировать штрих‑код в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код в C# с помощью Aspose.BarCode

Если вам нужно узнать **как генерировать штрих‑код** в проекте .NET, этот учебник проведет вас через весь процесс с использованием библиотеки Aspose.BarCode. Вы также узнаете, как **установить размер штрих‑кода**, чтобы изображение соответствовало требованиям вашего UI или печати.

Руководство охватывает всё: от установки пакета NuGet до настройки символа Micro PDF417 и сохранения его в файл PNG. К концу вы получите готовый пример кода, который можно вставить в любое консольное или веб‑приложение на C#.

## Что понадобится

- .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
- Visual Studio 2022 или любой IDE, поддерживающий C#
- Доступ в Интернет для загрузки пакета NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Базовое знакомство с синтаксисом C#

## Как генерировать штрих‑код с помощью Aspose.BarCode

Первый шаг — создать экземпляр `BarcodeGenerator`, который знает, какую символьную систему использовать и какие данные кодировать.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Почему это важно:** `EncodeTypes.MicroPdf417` указывает библиотеке создавать компактный вариант PDF417, идеальный для небольших этикеток или отпечатков, похожих на QR‑коды. Строка `"Micro data"` становится читаемым человеком полезным содержимым, встроенным в штрих‑код.

## Установка размера и размеров штрих‑кода

Читаемый штрих‑код должен иметь правильный размер модуля (X) и достаточное количество столбцов для размещения данных. Здесь вы **устанавливаете размер штрих‑кода**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** управляет шириной самого маленького штриха («модуля»). Значение `2` пикселя хорошо подходит для отображения на экране; увеличьте его для печати с высоким разрешением.
- **Pdf417.Columns** ограничивает количество вертикальных столбцов. Формат Micro PDF417 поддерживает до 7 столбцов; `4` обеспечивает сбалансированный размер без потери ёмкости данных.

> **Совет:** Если полученное изображение выглядит слишком маленьким, увеличьте `XDimension.Pixels` до `3` или `4`. Напротив, при ограниченном пространстве UI можно уменьшить его до `1`, но убедитесь, что сканер, который вы планируете использовать, всё ещё может считывать символ.

## Сохранение изображения штрих‑кода

После настройки размера вы просто указываете генератору записать изображение на диск.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Метод `Save` принимает любой формат, поддерживаемый Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG — без потерь, сохраняет чёткие границы, необходимые для надёжного сканирования.

**Ожидаемый результат:** Файл с именем `micro.png` появится в рабочем каталоге проекта. При открытии вы увидите крошечный, высококонтрастный штрих‑код Micro PDF417, готовый к тестированию любым стандартным сканером.

## Полный пример

Собрав все части вместе, вы получаете автономную программу, которую можно сразу запустить.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Запустите программу (`dotnet run` из консоли), и вы увидите сообщение подтверждения. Сгенерированный PNG можно встроить в отчёты, напечатать на этикетках продукции или отобразить на веб‑странице.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|---|---|
| **Могу ли я генерировать другие типы штрих‑кодов?** | Да. Замените `EncodeTypes.MicroPdf417` любым значением из перечисления `EncodeTypes` (например, `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Что если мне нужно более крупное изображение?** | Увеличьте `XDimension.Pixels` или используйте `generator.Parameters.Image.Width/Height`, чтобы задать конкретный размер в пикселях. |
| **Поддерживает ли библиотека прозрачные фоны?** | Установите `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` перед вызовом `Save`. |
| **Как считать штрих‑код обратно?** | Используйте `Aspose.BarCode.BarCodeReader` для сохранённого изображения; он автоматически определяет символьную систему. |
| **Безопасен ли PNG для печати?** | PNG — без потерь, но для печати в CMYK рекомендуется сохранять в формате TIFF (`BarCodeImageFormat.Tiff`). |

## Заключение

Теперь вы знаете **как генерировать штрих‑код** в C# и как **устанавливать размер штрих‑кода** с помощью Aspose.BarCode. Полный пример демонстрирует создание символа Micro PDF417, настройку его размеров и экспорт в файл PNG. Имея эту основу, вы можете изучать другие символьные системы, настраивать цвета или интегрировать генерацию штрих‑кодов в сервисы ASP.NET Core.

### Следующие шаги

- Попробуйте сгенерировать QR‑код (`EncodeTypes.QR`) и сравнить размеры модулей.  
- Поэкспериментируйте с `generator.Parameters.Image`, чтобы добавить отступы или изменить DPI для готового к печати вывода.  
- Скомбинируйте генерацию штрих‑кода с **Aspose.PDF**, чтобы встроить изображение непосредственно в PDF‑отчёт.

Удачной разработки и наслаждайтесь гибкостью, которую Aspose.BarCode предоставляет вашим .NET проектам со штрих‑кодами!

## Что вам стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать изображение штрих‑кода PDF417 в C# с Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Как сгенерировать штрих‑код PDF417 с Aspose – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Как сгенерировать штрих‑код в C# – Полное руководство по Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}