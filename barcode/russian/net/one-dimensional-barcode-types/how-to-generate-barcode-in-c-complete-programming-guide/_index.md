---
category: general
date: 2026-07-21
description: Как быстро генерировать штрих‑код в C#. Узнайте, как задавать размеры,
  менять столбцы и использовать генератор штрих‑кодов для PNG‑изображений в пошаговом
  руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change columns
- barcode generator for png
language: ru
lastmod: 2026-07-21
og_description: Как генерировать штрих‑код в C#? Это руководство показывает, как задать
  размеры, изменить столбцы и экспортировать генератор штрих‑кода в PNG с полным кодом.
og_image_alt: Screenshot of a MicroPDF417 barcode saved as a PNG file
og_title: Как генерировать штрих‑код в C# – полное руководство по выводу PNG.
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode in C# quickly. Learn how to set dimensions,
    change columns, and use a barcode generator for PNG images in a step‑by‑step tutorial.
  headline: How to Generate Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn how to set dimensions,
    change columns, and use a barcode generator for PNG images in a step‑by‑step tutorial.
  name: How to Generate Barcode in C# – Complete Programming Guide
  steps:
  - name: Create a New Console Application
    text: 'Open a terminal and run:'
  - name: Add the Aspose.BarCode Dependency
    text: '```bash dotnet add package Aspose.BarCode ```'
  - name: Verifying the Barcode
    text: You can scan the PNG with any barcode scanner app (most smartphones have
      one built‑in). It should decode back to `Åspóse.Barcóde©`. If it doesn’t, double‑check
      that the image isn’t corrupted and that your scanner supports MicroPDF417.
  - name: Changing the Barcode Type
    text: 'If you need a classic **Code128** or a QR code, swap the `EncodeTypes`
      enum:'
  - name: Exporting to Other Formats
    text: 'Aspose supports JPEG, BMP, GIF, and TIFF:'
  - name: Dynamically Setting Dimensions
    text: 'Suppose you receive width/height from user input:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Как генерировать штрих‑код в C# – полное руководство по программированию
url: /ru/net/one-dimensional-barcode-types/how-to-generate-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код в C# – Полное руководство по программированию

Когда‑нибудь задумывались **как генерировать штрих‑код** в C# без борьбы с непонятными библиотеками? Вы не одиноки. Нужно ли вам небольшая бирка для инвентаря или стильный QR‑код для билета, создание штрих‑кода программно может существенно сэкономить время. В этом руководстве мы пройдём каждый шаг — **как задать размеры**, настроить макет и, наконец, экспортировать **генератор штрих‑кода для PNG**‑изображений.

Мы будем использовать популярную библиотеку **Aspose.BarCode** (бесплатная пробная версия отлично подходит для тестов). К концу этого руководства у вас будет готовое консольное приложение, которое выводит чёткий MicroPDF417 штрих‑код в PNG, а также вы поймёте, как адаптировать код под другие форматы или типы изображений.

## Требования

- .NET 6.0 SDK (или любая современная версия .NET)
- Visual Studio 2022 (или VS Code с расширением C#)
- Aspose.BarCode for .NET NuGet‑пакет  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Базовое знакомство с консольными проектами C# (глубокая экспертиза не требуется)

> **Совет:** Если вы предпочитаете другую IDE, шаги остаются теми же — просто скорректируйте команду создания проекта.

## Настройка проекта

### Шаг 1: Создать новое консольное приложение

Откройте терминал и выполните:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Эта команда создаст минимальный файл `Program.cs` и файл `.csproj`, нацеленный на .NET 6.0.

### Шаг 2: Добавить зависимость Aspose.BarCode

```bash
dotnet add package Aspose.BarCode
```

Пакет добавит все необходимые классы: `BarcodeGenerator`, `EncodeTypes` и перечисления форматов изображений.

## Реализация генератора штрих‑кода

Ниже представлен **полный, готовый к запуску код**. Скопируйте его в `Program.cs`, замените `YOUR_DIRECTORY` на абсолютный или относительный путь, куда у вас есть права записи, и выполните `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the text you want to encode.
            //    Using characters with accents demonstrates Unicode support.
            string barcodeText = "Åspóse.Barcóde©";

            // 2️⃣ Create the generator for MicroPDF417 (compact version of PDF417).
            //    This is the core of “how to generate barcode”.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, barcodeText);

            // 3️⃣ Adjust visual properties.
            //    • How to set dimensions? – we tweak XDimension (module width).
            //    • How to change columns? – we set the Columns property (max 4 for MicroPDF417).
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // finer detail
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // layout control

            // 4️⃣ Choose the output folder.
            //    For safety, we resolve a full path relative to the project directory.
            string outputPath = System.IO.Path.Combine(
                AppContext.BaseDirectory, "MicroPdf417.png");

            // 5️⃣ Save as PNG – this fulfills “barcode generator for png”.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to: {outputPath}");
        }
    }
}
```

#### Почему важны эти настройки

- **XDimension** определяет ширину каждой маленькой полоски (модуля). Значение `2` пикселя даёт более чёткое изображение без увеличения размера файла.
- **Pdf417.Columns** задаёт количество колонок, на которые разбиваются данные. MicroPDF417 ограничен 4; меньше колонок делает штрих‑код выше, больше — шире. Регулируйте в зависимости от размеров этикетки.
- **BarCodeImageFormat.Png** обеспечивает безпотерьное сжатие, идеально подходящее для печати или встраивания в PDF.

## Запуск примера

1. Сборка и запуск проекта:

   ```bash
   dotnet run
   ```

2. После выполнения вы увидите сообщение в консоли с полным путём к `MicroPdf417.png`. Откройте файл — ваш штрих‑код будет выглядеть примерно так:

![Снимок экрана сгенерированного MicroPDF417 штрих‑кода PNG](https://example.com/placeholder.png "MicroPDF417 штрихкод сохранён как PNG")  
*Текст альтернативного изображения: Снимок экрана сгенерированного MicroPDF417 штрих‑кода, сохранённого как PNG‑файл.*

> **Примечание:** URL‑адрес‑заполнитель используется только для иллюстрации. Замените его реальным URL, если разместите изображение.

### Проверка штрих‑кода

Вы можете отсканировать PNG любой программой‑сканером штрих‑кодов (на большинстве смартфонов такая функция встроена). Он должен декодировать строку `Åspóse.Barcóde©`. Если этого не происходит, проверьте, что изображение не повреждено и ваш сканер поддерживает MicroPDF417.

## Настройка генератора

### Смена типа штрих‑кода

Если нужен классический **Code128** или QR‑код, замените перечисление `EncodeTypes`:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Code128, barcodeText);
```

Все остальные вызовы параметров остаются прежними, но некоторые свойства (например, `Pdf417.Columns`) становятся неактуальными — Aspose просто игнорирует их.

### Экспорт в другие форматы

Aspose поддерживает JPEG, BMP, GIF и TIFF:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

JPEG ещё больше уменьшает размер файла, но вводит артефакты сжатия — используйте его только тогда, когда небольшая потеря резкости приемлема.

### Динамическая установка размеров

Предположим, вы получаете ширину/высоту от пользователя:

```csharp
int userPixels = int.Parse(Console.ReadLine() ?? "3");
generator.Parameters.Barcode.XDimension.Pixels = userPixels;
```

Всегда проверяйте ввод (минимум 1 пиксель, максимум, например, 10), чтобы избежать нечитаемых штрих‑кодов.

## Распространённые проблемы и профессиональные советы

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Штрих‑код выглядит размытым | XDimension слишком низкий или сохранён при небольшом DPI | Увеличьте `XDimension.Pixels` или экспортируйте с более высоким DPI (`generator.Save(..., BarCodeImageFormat.Png, 300)`) |
| Сканер не читает | Слишком много колонок для заданной ширины изображения | Уменьшите `Pdf417.Columns` или увеличьте размер выходного изображения |
| Юникод‑символы превращаются в � | Неправильная кодировка или устаревшая версия библиотеки | Убедитесь, что используете Aspose.BarCode 23.9+ с полной поддержкой Unicode |
| Ошибка «файл не найден» | Папка назначения не существует | Перед сохранением вызовите `Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!)` |

**Профессиональный совет:** При генерации большого количества штрих‑кодов в пакетном режиме переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только свойство `CodeText`. Это уменьшит количество выделений объектов и ускорит обработку.

## Полный пример «от начала до конца» (пакетный режим)

Ниже расширенный фрагмент, который читает CSV с кодами продуктов и создаёт PNG‑файл для каждого. Он демонстрирует масштабируемость и закрепляет концепцию «как генерировать штрих‑код».

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class BatchGenerator
{
    static void Main()
    {
        string csvPath = "products.csv"; // format: Id,BarcodeText
        string outputDir = Path.Combine(AppContext.BaseDirectory, "BatchOutput");
        Directory.CreateDirectory(outputDir);

        foreach (var line in File.ReadLines(csvPath))
        {
            var parts = line.Split(',');
            if (parts.Length != 2) continue; // skip malformed rows

            string id = parts[0];
            string text = parts[1];

            var gen = new BarcodeGenerator(EncodeTypes.MicroPdf417, text);
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            gen.Parameters.Barcode.Pdf417.Columns = 4;

            string fileName = Path.Combine(outputDir, $"barcode_{id}.png");
            gen.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

Запустите его после создания простого `products.csv`:

```
001,ABC123
002,XYZ789
003,Åspóse.Barcóde©
```

Каждая строка генерирует отдельный PNG, что идеально подходит для массовой печати этикеток.

## Заключение

Мы рассмотрели **как генерировать штрих‑код** в C# с нуля, изучили **как задавать размеры**, узнали **как менять колонки**, и в конце экспортировали результат с помощью **генератора штрих‑кода для PNG**. Полный готовый к копированию код выше работает сразу, а объяснения отвечают как на вопрос «что», так и «почему» для каждой настройки.

Дальше вы можете:

- Поэкспериментировать с другими `EncodeTypes` (QR, DataMatrix, Code128) — отлично подходит для мобильных приложений.
- Интегрировать генератор в ASP.NET Core API, чтобы ваш веб‑сервис возвращал штрих‑коды по запросу.
- Погрузиться в расширенные возможности стилизации Aspose (цвета, рамки, встроенные логотипы) для брендинга.

Есть вопросы о конкретном формате штрих‑кода или требованиях к изображению? Оставляйте комментарий, и happy coding!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы вы могли освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}