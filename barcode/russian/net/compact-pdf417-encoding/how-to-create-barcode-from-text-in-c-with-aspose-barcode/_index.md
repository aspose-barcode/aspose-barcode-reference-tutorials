---
category: general
date: 2026-10-02
description: Создайте штрих‑код из текста на C# с помощью Aspose.BarCode. Узнайте,
  как генерировать штрих‑код PDF417, и посмотрите, как генерировать штрих‑код PDF417
  в компактном режиме.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: ru
lastmod: 2026-10-02
og_description: Создайте штрих‑код из текста на C# с помощью Aspose.BarCode. Это руководство
  показывает, как сгенерировать штрих‑код PDF417 и как сгенерировать штрих‑код PDF417
  в компактном режиме.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Создание штрих‑кода из текста в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Как создать штрих‑код из текста в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код из текста в C# с помощью Aspose.BarCode

Если вам нужно **создать штрих‑код из текста** в .NET‑приложении, это руководство проведёт вас через весь процесс. Вы увидите готовый к запуску пример, который **генерирует штрих‑код PDF417**, а также получите ответ на вопрос **как сгенерировать штрих‑код PDF417** в компактном виде.

Программная генерация штрих‑кода устраняет ручные шаги и гарантирует единообразие во всех документах. К концу этого урока у вас будет PNG‑файл, содержащий штрих‑код PDF417, который можно встроить в счета, билеты или удостоверения личности.

## Что понадобится

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7.2+)
- Visual Studio 2022 или любой редактор, поддерживающий C#
- NuGet‑лицензия для **Aspose.BarCode for .NET** (бесплатная пробная версия подходит для тестов)

> **Pro tip:** Добавьте пакет NuGet через CLI, чтобы проект оставался чистым:  
> `dotnet add package Aspose.BarCode`

## Шаг 1: Создание консольного проекта

Создайте новое консольное приложение и подключите библиотеку Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Команда `dotnet new console` создаёт файл `Program.cs`, который мы заменим полным примером ниже.

## Шаг 2: Как создать штрих‑код из текста – основной код

Откройте `Program.cs` и замените его содержимое следующим кодом. Каждая строка прокомментирована, чтобы объяснить её назначение.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Почему важна каждая настройка

| Настройка | Назначение |
|----------|------------|
| `EncodeTypes.Pdf417` | Выбирает символьную схему PDF417, способную хранить большие объёмы данных в двумерной матрице. |
| `XDimension.Pixels = 2` | Управляет шириной каждого модуля; значение 2 пикселя обеспечивает баланс между читаемостью и размером файла. |
| `Pdf417.Columns = 3` | Уменьшает количество колонок, делая штрих‑код более компактным без потери данных. |
| `Pdf417.Truncate = true` | Включает компактный режим, убирая лишние отступы и сокращая штрих‑код. |
| `BarCodeImageFormat.Png` | PNG сохраняет без потерь, что идеально для дальнейшей обработки или печати. |

## Шаг 3: Генерация штрих‑кода PDF417 – запуск примера

Соберите и запустите проект:

```bash
dotnet run
```

После завершения выполнения вы увидите:

```
Barcode saved to CompactPdf417.png
```

Откройте `CompactPdf417.png`, чтобы посмотреть результат. На изображении находится штрих‑код PDF417, кодирующий строку **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: создание штрих‑кода из текста – штрих‑код PDF417, сохранённый как PNG*

## Шаг 4: Как сгенерировать штрих‑код PDF417 с пользовательским уровнем коррекции ошибок (необязательно)

Если ваша среда сканирования шумная, можно повысить уровень коррекции ошибок:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Увеличение уровня ошибок делает штрих‑код больше, но повышает устойчивость к повреждениям.

## Шаг 5: Распространённые подводные камни и обработка граничных случаев

1. **Недопустимые символы** – PDF417 поддерживает Unicode, но некоторые старые сканеры могут отклонять символы вне ASCII. Тестируйте на целевом оборудовании.  
2. **Разрешения файлового пути** – Убедитесь, что каталог, в который вы записываете, доступен для записи; иначе `Save` бросит `UnauthorizedAccessException`.  
3. **Размер изображения** – Очень большие значения `XDimension` приводят к крупным PNG‑файлам. Для большинства сценариев отображения на экране держите размер пикселя в диапазоне от 1 до 4.

## Итоги

Теперь вы знаете, как **создать штрих‑код из текста** в C# с помощью Aspose.BarCode, как **сгенерировать штрих‑код PDF417** в компактном виде и какие шаги нужны для **генерации штрих‑кода PDF417** с пользовательскими настройками. Полный, готовый к запуску код выше можно скопировать в любой .NET‑проект и адаптировать под разные входные строки или форматы вывода (например, JPEG, BMP).

## Следующие шаги

- Исследуйте другие символьные схемы, такие как QR Code или Code128, изменив `EncodeTypes`.  
- Интегрируйте сгенерированный PNG в PDF с помощью Aspose.PDF для сквозного создания документов.  
- Поэкспериментируйте с `generator.Parameters.Barcode.Pdf417.Rows`, чтобы управлять вертикальной плотностью.

Не стесняйтесь модифицировать пример, внедрять штрих‑код в свои приложения и делиться результатами с сообществом. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы реализации в ваших проектах.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}