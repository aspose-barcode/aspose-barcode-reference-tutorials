---
category: general
date: 2026-10-04
description: Быстро создайте штрих‑код PDF417 в C#. Узнайте, как генерировать штрих‑код
  PDF417 и сохранять его изображение в формате PNG с помощью Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Создайте штрих‑код PDF417 в C# с помощью Aspose.Barcode. В этом руководстве
  показано, как сгенерировать компактный штрих‑код PDF417, настроить его внешний вид
  и сохранить в виде изображения PNG для мобильного сканирования или печати этикеток.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Создание штрих‑кода PDF417 в C# – полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
- Aspose.Barcode
title: Создание штрих‑кода PDF417 в C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать штрих‑код PDF417 в C# – пошаговое руководство

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как именно сгенерировать штрих‑код PDF417 и как сохранить изображение штрих‑кода в файл PNG. Вы получите компактное изображение, которое отлично подходит для мобильного сканирования, систем билетов или этикеточных принтеров.

## Быстрые ответы
- **Какая библиотека обрабатывает генерацию PDF417?** Aspose.Barcode for .NET.  
- **В каком формате сохраняет пример?** PNG, using `BarCodeImageFormat.Png`.  
- **Сколько строк кода требуется?** About 10 lines after project setup.  
- **Можно ли настроить размер и усечение?** Yes – `Columns`, `Rows`, and `Truncate` properties.  
- **Совместим ли код с .NET‑6?** Fully, and it also works with .NET Framework 4.7+.

## Что нужно для создания штрих‑кода PDF417 в C#?
Для начала вам нужен современный .NET SDK, IDE, например Visual Studio 2022, и пакет NuGet **Aspose.Barcode for .NET**. Эти инструменты позволяют собрать и запустить пример без дополнительной настройки.

- .NET 6.0 SDK или новее (также работает с .NET Framework 4.7+)
- Visual Studio 2022 или любой редактор, совместимый с C#
- Доступ в Интернет для загрузки пакета NuGet Aspose.Barcode

## Как настроить проект .NET для генерации штрих‑кода PDF417?
Создайте новый консольный проект, добавьте пакет Aspose.Barcode и откройте сгенерированный `Program.cs`. Это подготовит чистую рабочую область, где вы сможете создать генератор штрих‑кода и записать файл вывода.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Как сгенерировать штрих‑код PDF417 с помощью Aspose.Barcode?
`BarcodeGenerator` — класс Aspose.Barcode, который создает изображения штрих‑кодов из предоставленных данных и символьных наборов. Вы указываете символьный набор PDF417, задаёте текст для кодирования и при необходимости регулируете размер или параметры коррекции ошибок.

```bash
   dotnet add package Aspose.Barcode
   ```

### Почему это важно
* **EncodeTypes.Pdf417** указывает библиотеке использовать стандарт PDF417, который поддерживает большие объёмы данных и коррекцию ошибок.
* Предоставление Unicode‑символов доказывает, что генератор обрабатывает ввод не‑ASCII без дополнительной настройки.

## Как настроить внешний вид штрих‑кода PDF417?
Вы можете управлять размером модуля, количеством столбцов и тем, использует ли штрих‑код компактный (усечённый) режим. Эти параметры напрямую влияют на читаемость на небольших экранах и общий размер PNG‑файла.

`generator.Parameters.Barcode.XDimension` задаёт ширину одного модуля, а `Columns` и `Rows` определяют размеры матрицы. Установка `Truncate` в `true` удаляет зоны тишины, делая изображение более компактным.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Практический совет
Если вам нужен более высокий штрих‑код при ограниченном горизонтальном пространстве, увеличьте `Columns`. Установка `Truncate` в `true` уменьшает общую высоту, удаляя зоны тишины, что идеально для мобильных экранов.

## Как сохранить изображение штрих‑кода в PNG?
`Save` — метод `BarcodeGenerator`, который записывает сгенерированное изображение в файл. Передайте путь к файлу и `BarCodeImageFormat.Png`, чтобы создать PNG‑изображение за один шаг.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Ожидаемый результат
Запуск программы создаёт `CompactPdf417.png` в папке проекта. При открытии файла отображается компактный штрих‑код PDF417, кодирующий строку *Åspóse.Barcóde©*. Изображение можно встроить в HTML, PDF‑отчёты или распечатать на этикетках.

## Как проверить сгенерированный файл штрих‑кода?
После завершения программы вы можете проверить наличие файла с помощью быстрой команды. Эта простая проверка подтверждает, что шаги генерации и сохранения завершились без ошибок.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Если файл появился, процесс **создания штрих‑кода PDF417** завершился успешно.

## Какие распространённые варианты и граничные случаи при генерации штрих‑кодов PDF417?
Разные сценарии могут требовать корректировки настроек генератора. Ниже представлена справочная таблица, показывающая, как обрабатывать типичные варианты.

| Ситуация | Корректировка |
|-----------|------------|
| **Более длинная строка данных** | Увеличьте `Columns` или задайте `Rows`, чтобы разместить больше кодовых слов. |
| **Другой формат изображения** | Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`. |
| **Более высокое разрешение** | Установите `generator.Parameters.ImageResolution` перед вызовом `Save`. |
| **Цвет фона** | Используйте `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Обработка исключений** | Оберните `generator.Save` в блок `try/catch` для перехвата ошибок ввода‑вывода. |

Эти варианты позволяют адаптировать штрих‑код под конкретные устройства или требования брендинга.

## Каков следующий шаг после создания штрих‑кода?
Теперь, когда вы можете генерировать и сохранять штрих‑код PDF417, вы можете изучить связанные возможности, такие как генерация QR‑кодов, встраивание штрих‑кодов в PDF‑документы или настройка цветов под бренд. Все они используют один и тот же API `BarcodeGenerator`, поэтому расширить пример можно с минимальными усилиями.

## Связанные руководства
- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Как сгенерировать штрих‑код Aztec с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Часто задаваемые вопросы

**Q: Можно ли использовать этот код в веб‑приложении?**  
A: Да. Тот же класс `BarcodeGenerator` работает в проектах ASP.NET, MVC или Blazor; просто убедитесь, что у сервера есть права записи в папку вывода.

**Q: Поддерживает ли Aspose.Barcode другие 2‑D символьные наборы?**  
A: Абсолютно. Поддерживается более 30 типов 2‑D штрих‑кодов, включая QR, DataMatrix и Aztec.

**Q: Какой максимальный размер штрих‑кода я могу создать?**  
A: PDF417 может кодировать до 1 850 символов в одном символе; вы также можете разбить данные по нескольким строкам, регулируя `Rows` и `Columns`.

**Q: Требуется ли лицензия для использования в продакшене?**  
A: Да. Доступна бесплатная пробная версия для оценки, но для развертывания необходима коммерческая лицензия.

**Q: Какие версии .NET совместимы?**  
A: Aspose.Barcode поддерживает .NET Framework 4.5+, .NET Core 3.1+, а также .NET 5/6/7.

---

**Последнее обновление:** 2026-10-04  
**Тестировано с:** Aspose.Barcode 24.11 for .NET  
**Автор:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}