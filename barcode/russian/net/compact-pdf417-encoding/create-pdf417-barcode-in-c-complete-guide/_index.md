---
category: general
date: 2026-09-22
description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Узнайте, как
  генерировать изображения штрих‑кода PDF417, задавать количество столбцов/строк и
  сохранять их в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
language: ru
lastmod: 2026-09-22
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Узнайте,
  как генерировать изображения штрих‑кода PDF417, настраивать макет и экспортировать
  в PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
    PDF417 barcode images, set columns/rows, and save as PNG.
  headline: Create PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
- image generation
title: Создание штрихкода PDF417 в C# — полное руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PDF417 barcode на C# – полное руководство

Если вам нужно **создать PDF417 barcode** в .NET приложении, этот учебник покажет вам точно как. Вы увидите полный, исполняемый пример, который генерирует PDF417 barcode, настраивает его расположение столбцов и строк и сохраняет результат в виде PNG‑изображения.

Генерация штрихкодов является распространённой задачей для систем учёта, платформ продажи билетов и автоматизации документов. К концу этого руководства вы сможете ответить на вопрос *how to generate PDF417 barcode* программно, не покидая свою IDE.

## Требования

- .NET 6.0 или более поздняя версия (код также работает с .NET Framework 4.8)
- Последняя версия **Aspose.BarCode for .NET** (бесплатная пробная версия подходит для разработки)
- IDE, например Visual Studio 2022 или Visual Studio Code
- Базовое знакомство с синтаксисом C#

> **Pro tip:** Если вы используете CI/CD конвейер, добавьте NuGet‑пакет `Aspose.BarCode` в файл проекта, чтобы сборка восстанавливала его автоматически.

## Шаг 1: Установите NuGet‑пакет Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию библиотеки в ваш проект и соответственно обновит файл `.csproj`.

## Шаг 2: Создайте генератор штрихкода PDF417

Объект‑генератор является точкой входа для всех операций со штрихкодами. Вы указываете символьный набор (`EncodeTypes.Pdf417`) и текст, который хотите закодировать.

```csharp
using Aspose.BarCode.Generation;

// ...

// Step 2: Instantiate the generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

Класс `BarcodeGenerator` абстрагирует алгоритм кодирования, поэтому вам не нужно работать с низкоуровневой манипуляцией битами.

## Шаг 3: Настройте макет PDF417 – столбцы и строки

PDF417 позволяет управлять количеством столбцов (горизонтальные модули) и строк (вертикальные модули). Изменение этих значений меняет плотность штрихкода и его физический размер.

```csharp
// Step 3: Configure layout
generator.Parameters.Barcode.Pdf417.Columns = 4; // supported range: 2‑10
generator.Parameters.Barcode.Pdf417.Rows = 9;    // optional; if omitted, rows are auto‑calculated
```

- **Columns**: Определяет, сколько столбцов данных будет содержать штрихкод. Меньшее количество столбцов приводит к более высокому штрихкоду.
- **Rows**: Позволяет задать конкретную высоту. Оставив значение `0`, вы позволяете движку выбрать оптимальное количество.

## Шаг 4: Сохраните изображение штрихкода в формате PNG

Наконец, экспортируйте штрихкод в формат изображения, подходящий большинству UI‑фреймворков.

```csharp
using Aspose.BarCode;

// ...

// Step 4: Save as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png` enum обеспечивает сжатие без потерь, что идеально для дальнейшей обработки или печати.

## Полный рабочий пример

Соберите всё вместе в консольном приложении под названием `Pdf417Demo`.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Install Aspose.BarCode via NuGet before running this code

            // 2️⃣ Create the generator
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 3️⃣ Set layout – 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;

            // 4️⃣ Define output path
            string outputPath = Path.Combine(
                Environment.CurrentDirectory, "Pdf417_4x9.png");

            // 5️⃣ Save the barcode
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created at: {outputPath}");
        }
    }
}
```

### Ожидаемый вывод

Запуск программы выводит строку подтверждения и создаёт файл, похожий на скриншот ниже:

![Generated PDF417 barcode](/images/pdf417-example.png "Create PDF417 barcode – PNG output")

Сохранённый `Pdf417_4x9.png` содержит чёткий, сканируемый символ PDF417, который кодирует текст **“Sample”**.

## Как сгенерировать PDF417 barcode с пользовательскими данными

Если вам нужно закодировать более одного слова, просто замените второй аргумент `BarcodeGenerator` любой строкой (включая разрывы строк). Библиотека автоматически разбивает данные по строкам и столбцам в соответствии с заданным макетом.

```csharp
var generator = new BarcodeGenerator(
    EncodeTypes.Pdf417,
    "OrderID: 12345\nDate: 2026-09-22\nCustomer: John Doe");
```

Те же настройки макета (columns = 4, rows = 9) по‑прежнему применяются, но штрихкод будет расти вертикально, если данные превысят доступное пространство.

## Пограничные случаи и устранение неполадок

| Ситуация | Что проверить | Рекомендуемое решение |
|-----------|---------------|-----------------|
| Штрихкод выглядит слишком маленьким на экране | DPI сохранённого PNG | Передайте объект `Resolution`: `generator.Save(path, BarCodeImageFormat.Png, new Resolution(300))` |
| Строки игнорируются | `Rows` установлен в `0` или не задан | Явно задайте положительное целое (например, `Rows = 9`) |
| Текст обрезается | Количество столбцов слишком мало для длины данных | Увеличьте `Columns` (макс 10) или позвольте движку автоматически подобрать размер, задав `Columns = 0` |
| Сканирование не удаётся на мобильных устройствах | Недостаточный контраст | Используйте `generator.Parameters.Barcode.ForegroundColor = Color.Black` и `BackgroundColor = Color.White` |

Эти советы помогут вам точно настроить штрихкод для реальных сканирующих устройств.

## Почему стоит использовать Aspose.BarCode для PDF417

- **Full control** над макетом (столбцы, строки, коррекция ошибок)
- **Zero‑dependency** генерация изображений – не требуются внешние графические библиотеки
- **Cross‑platform** поддержка (Windows, Linux, macOS), так как библиотека ориентирована на .NET Standard
- **Extensive documentation** и пример кода непосредственно от поставщика

Выбор этой библиотеки гарантирует, что задача **create PDF417 barcode** останется поддерживаемой и готовой к будущим изменениям.

## Заключение

Теперь вы знаете, как **create PDF417 barcode** в C# с помощью Aspose.BarCode, настроить его столбцы и строки и экспортировать результат в PNG‑файл. Это полное решение отвечает на вопрос *how to generate PDF417 barcode* для любого .NET проекта, и вы можете расширить его, изменив кодируемый текст, формат изображения или разрешение.

**Следующие шаги**

- Экспериментируйте с другими форматами изображений, такими как `Jpeg` или `Bmp`.
- Объедините штрихкод с PDF‑документом, используя `Aspose.PDF` для сквозной генерации отчётов.
- Исследуйте уровни коррекции ошибок (`generator.Parameters.Barcode.Pdf417.ErrorLevel`), чтобы повысить надёжность сканирования в шумных условиях.

Удачной разработки, и наслаждайтесь внедрением надёжных PDF417 символов в ваши приложения!

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сохранить штрихкод в C# – Генерация PDF417 штрихкодов](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Пример Aspose barcode: генерация Macro PDF417 в C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Генерация PDF417 barcode C# – полное руководство с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}