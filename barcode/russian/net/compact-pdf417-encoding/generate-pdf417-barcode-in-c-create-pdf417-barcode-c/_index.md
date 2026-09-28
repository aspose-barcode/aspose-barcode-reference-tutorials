---
category: general
date: 2026-07-24
description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Узнайте, как
  за несколько минут создать PDF417‑штрих‑код в C# в компактном режиме.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: ru
lastmod: 2026-07-24
og_description: Быстро генерируйте штрих‑код PDF417 на C# с помощью Aspose.BarCode.
  Этот учебник покажет, как создать штрих‑код PDF417 в C# в компактном режиме, охватывая
  настройку, код и проверку.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Создание штрих‑кода PDF417 на C# – Быстрое руководство
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Генерация штрихкода PDF417 в C# – Создание штрихкода PDF417 на C#
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# – Полный пошаговый пример

Когда‑нибудь задумывались, как **создать штрих‑код PDF417** в приложении на C# без бесконечного поиска по форумам? Вы не одиноки. Будь то система билетов, защищённая ID‑карта или просто быстрый способ внедрить данные в печатный формат, освоение формата PDF417 может сэкономить часы проб и ошибок.

В этом руководстве мы пройдём через **полный, готовый к запуску пример**, который покажет, как **создать PDF417 штрих‑код C#** с помощью популярной библиотеки Aspose.BarCode. Мы охватим всё: от установки пакета NuGet до настройки компактного режима, чтобы вы могли скопировать‑вставить код и сразу увидеть результат.

## Что вы узнаете

- Как подключить библиотеку Aspose.BarCode в проект .NET.  
- Точные C#‑операторы, необходимые для **генерации штрих‑кода PDF417** с пользовательским текстом, размером модуля и количеством колонок.  
- Почему переключение опции *Compact* (Truncate) важно для плотных данных.  
- Как сохранить штрих‑код в PNG и проверить полученный результат.  

Предыдущий опыт работы со штрих‑кодами не требуется; достаточно базовых знаний C# и Visual Studio (или любой другой IDE). К концу вы получите переиспользуемый метод, который можно вставить в любой проект, требующий изображение PDF417.

## Требования

| Требование | Почему это важно |
|-------------|----------------|
| .NET 6.0 или новее (или .NET Framework 4.7+) | Aspose.BarCode поддерживает обе платформы; более новые среды дают лучшую производительность. |
| Visual Studio 2022 (или VS Code с расширениями C#) | Обеспечивает IntelliSense и удобную отладку. |
| Интернет‑соединение (для первой загрузки NuGet) | Библиотека скачивается с NuGet.org. |
| Базовые знания C# | Необходимо для понимания структуры классов и вызовов методов. |

Если всё уже готово — отлично, приступаем.

## Установка пакета Aspose.BarCode NuGet

Откройте папку проекта в терминале и выполните:

```bash
dotnet add package Aspose.BarCode
```

Или в Visual Studio щёлкните правой кнопкой **Dependencies → Manage NuGet Packages**, найдите *Aspose.BarCode* и нажмите **Install**. Эта одна строка добавит все типы, которые нам понадобятся, включая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`.

> **Pro tip:** После установки выполните очистку и повторную сборку решения, чтобы убедиться, что сборка правильно подключена.

## Генерация PDF417 штрих‑кода – настройка и зависимости

Первым делом нам нужен блок `using`, который импортирует нужные пространства имён.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти пространства имён дают доступ к классу генератора и перечислению типов штрих‑кодов. Ничего сложного — всего три строки, и мы готовы приступить к созданию штрих‑кода.

## Создание PDF417 штрих‑кода C# – пошаговая реализация

Ниже представлен **самодостаточный консольный проект**, который создаёт компактный PDF417 штрих‑код из строки `"Åspóse.Barcóde©"` и сохраняет его как `CompactPdf417.png`. При желании замените текст на любой другой — генератор без проблем обработает Unicode‑символы.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Почему каждый шаг важен

1. **Определение данных** — PDF417 может хранить до ~1850 символов, но для демонстрации мы используем короткую строку. Поддержка Unicode гарантирует, что акцентированные символы не вызовут проблем.  
2. **Создание генератора** — Значение `EncodeTypes.Pdf417` указывает Aspose, какой символьный набор использовать; заменив его на `EncodeTypes.QR`, вы получите QR‑код.  
3. **X‑dimension** — Управляет шириной каждого модуля (маленького квадратика, из которого состоит штрих‑код). Значение `2` пикселя даёт чёткое изображение, которое остаётся читаемым при печати 300 dpi.  
4. **Опции PDF417** — `Columns` влияет на соотношение сторон штрих‑кода; меньше колонок делает изображение выше, что удобно для чеков. `Truncate` (также называется *Compact mode*) убирает лишние старт‑/стоп‑паттерны, уменьшая размер файла без потери данных.  
5. **Путь сохранения** — Использование `Environment.CurrentDirectory` гарантирует, что изображение окажется рядом с исполняемым файлом, что упрощает поиск во время разработки.  
6. **Сохранение** — `BarCodeImageFormat.Png` обеспечивает без потерь качество, идеально подходящее для дальнейшей обработки или встраивания в PDF.

Запустите программу (`dotnet run` или нажмите **F5** в Visual Studio). Через несколько секунд вы увидите сообщение в консоли с подтверждением пути к файлу, а PNG появится в папке проекта.

![Generate PDF417 barcode example](generated-pdf417.png)

*Текст альтернативного изображения: пример генерации PDF417 штрих‑кода — PNG‑изображение компактного PDF417, созданного с помощью C#.*

## Настройка компактного режима – c# barcode generator pdf417 Options

Если нужен более крупный штрих‑код (например, для сканирования с расстояния), подкорректируйте свойства `Columns` и `Rows`. Ниже короткий фрагмент, демонстрирующий альтернативные конфигурации:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Распространённый вопрос:** *Отключит ли отключение Truncate работу существующих сканеров?*  
> Обычно нет. Большинство современных сканеров понимают как полноразмерный, так и компактный PDF417. Однако, если вы ориентируетесь на устаревшее оборудование, оставьте `Truncate` равным `false`.

## Сохранение и проверка – how to generate pdf417 barcode Output

После сохранения откройте PNG в любом просмотрщике изображений. Чтобы убедиться, что штрих‑код действительно содержит нужные данные, используйте `BarCodeReader` от Aspose:



## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Add barcode to PDF using Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}