---
category: general
date: 2026-11-17
description: Узнайте, как создать штрих‑код PDF417 в C# — полное руководство по генерации
  штрих‑кода из строки с помощью генератора штрих‑кодов на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: ru
lastmod: 2026-11-17
og_description: Быстро создайте штрих‑код PDF417 на C#. В этом руководстве показано,
  как генерировать штрих‑код из строки с помощью генератора штрих‑кодов на C# и включён
  полный исходный код.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Как создать штрих‑код PDF417 в C# с помощью генератора штрих‑кодов
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PDF417 barcode в C# с помощью генератора штрих‑кодов

Если вам нужно **create PDF417 barcode** в .NET‑приложении, это руководство показывает точно, как это сделать. Вы узнаете **how to generate barcode** из обычной строки, настроите размер символа и сохраните результат в файл PNG — всё с помощью надёжного **c# barcode generator**.

Программная генерация штрих‑кодов устраняет ручные шаги и гарантирует стабильное качество. В этом руководстве мы рассмотрим всё — от настройки проекта до получения окончательного изображения, чтобы вы могли интегрировать создание штрих‑кодов в любое C#‑решение уже сегодня.

## Требования

* .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
* Visual Studio 2022 (или любой IDE, поддерживающий C#)
* Лицензия или бесплатная пробная версия **Aspose.BarCode for .NET** — библиотека, используемая в примерах
* Базовые знания синтаксиса C#

Дополнительные пакеты не требуются; пакет NuGet `Aspose.BarCode` содержит все необходимые классы.

## Шаг 1 — Настройка генератора штрих‑кодов на C#

Первое, что вы делаете, когда **create PDF417 barcode**, — создаёте объект `BarcodeGenerator`. Этот объект представляет **c# barcode generator**, который будет выполнять кодирование, рендеринг и сохранение.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Почему это важно*: Перечисление `EncodeTypes.Pdf417` указывает библиотеке использовать символьную схему PDF417, которая является тем же стандартом, что используется для удостоверений личности и транспортных этикеток. Строка `"(01)12345678901234"` — пример **generate barcode from string**, который также демонстрирует, как **create GS1 barcode** данные.

## Шаг 2 — Настройка X‑размера (ширина модуля)

X‑размер определяет ширину самого маленького штриха (модуля). Обычное значение для отображения на экране — 2 пикселя.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Явная установка X‑размера предотвращает использование генератором значения по умолчанию, которое может привести к слишком маленькому штрих‑коду для некоторых сканеров.

## Шаг 3 — Определение количества столбцов

PDF417 позволяет регулировать количество столбцов, влияя как на форму штрих‑кода, так и на ёмкость данных. Для компактной этикетки хорошо подходит четыре столбца.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Если нужен более высокий штрих‑код, увеличьте количество столбцов; библиотека автоматически рассчитает необходимое количество строк.

## Шаг 4 — Сохранение штрих‑кода как изображения

Наконец, экспортируйте штрих‑код в файл PNG. PNG сохраняет чёткие края и поддерживает прозрачность.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Запуск программы создаёт `output/Gs1Pdf417.png`. Откройте файл в любом просмотрщике изображений — вы увидите чистый **PDF417 barcode**, который кодирует предоставленные вами данные GS1.

### Ожидаемый результат

![Сгенерированный PDF417 barcode, показывающий GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Сгенерированный PDF417 barcode, созданный с помощью генератора штрих‑кодов на C#"}

*Изображение выше демонстрирует результат полного примера кода. Штрих‑код может быть считан любым считывателем, совместимым с PDF417.*

## Дополнительные параметры и распространённые варианты

### Изменение формата изображения

Если вы предпочитаете JPEG или BMP, просто замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`. Остальная часть кода остаётся неизменной.

### Регулировка уровня коррекции ошибок

PDF417 поддерживает уровни коррекции ошибок от 0 до 8. Более высокие уровни увеличивают избыточность, но также делают штрих‑код больше.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Генерация других GS1 штрих‑кодов

Тот же `BarcodeGenerator` может создавать **create GS1 barcode** для других символьных схем, таких как `EncodeTypes.Gs1DataMatrix` или `EncodeTypes.Gs1Qr`. Просто замените значение перечисления:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Обработка пустых или null данных

Когда вы **generate barcode from string**, всегда проверяйте входные данные:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Это предотвращает исключения во время выполнения и гарантирует, что штрих‑код соответствует правилам форматирования GS1.

## Полный, исполняемый пример

Ниже приведена полная программа, которую можно скопировать и вставить в новый консольный проект. Она включает все необходимые директивы `using`, создание папок и обработку ошибок.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Run the program** (`dotnet run`) и вы найдёте `Gs1Pdf417.png` в папке *output*. Считайте его любым считывателем PDF417, чтобы убедиться, что GTIN `(01)12345678901234` закодирован правильно.

## Часто задаваемые вопросы

**Q: Можно ли использовать этот код на .NET Framework 4.6?**  
A: Да. Библиотека Aspose.BarCode ориентирована на .NET Standard 2.0, который совместим с .NET Framework 4.6 и более новыми версиями.

**Q: Что делать, если нужна более высоко‑разрешающая картинка?**  
A: Установите свойство `Resolution` перед сохранением:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Является ли штрих‑код действительным без идентификатора приложения GS1?**  
A: Это будет обычный PDF417 barcode, но он не будет распознан как символ, соответствующий GS1. Добавьте префикс `(01)`, когда требуется соответствие **create GS1 barcode**.

## Заключение

Теперь вы знаете, как **create PDF417 barcode** в C# с помощью надёжного **c# barcode generator**. В руководстве рассмотрено:

* Создание экземпляра `BarcodeGenerator` с данными GS1
* Настройка X‑размера и количества столбцов
* Сохранение результата в виде PNG‑изображения
* Расширение решения с помощью коррекции ошибок, разных форматов и проверки ввода

С этой базой вы можете генерировать любой PDF417 или GS1 штрих‑код напрямую из строки, внедрять его в отчёты или отправлять на принтеры. Изучите API Aspose.BarCode, чтобы добавить цвета, отступы или объединить несколько штрих‑кодов в одно изображение.

**Next steps**: попробуйте сгенерировать **create GS1 barcode** для DataMatrix, поэкспериментируйте с динамическими расчётами столбцов или интегрируйте генератор в веб‑службу ASP.NET Core, которая по запросу возвращает изображения штрих‑кодов.

Удачной разработки!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать PDF417 barcode в C# – полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Как создать micro pdf417 barcode и сгенерировать PNG в C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Как создать macro PDF417 barcode в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}