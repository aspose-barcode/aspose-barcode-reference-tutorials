---
category: general
date: 2026-09-10
description: Быстро генерируйте штрих‑код PDF417 на C#. Узнайте, как создавать PDF417
  и изменять размер штрих‑кода с помощью Aspose.BarCode всего за несколько строк.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: ru
lastmod: 2026-09-10
og_description: Генерируйте штрих‑код PDF417 в C# мгновенно. Этот учебник показывает,
  как создать PDF417 и как изменить размер штрих‑кода с помощью Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Генерация штрихкода PDF417 на C# – полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Как сгенерировать штрих‑код PDF417 в C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код PDF417 в C# – пошаговое руководство

Если вам нужно **генерировать штрих‑код PDF417** в приложении .NET, это руководство покажет вам точно, как это сделать. Вы увидите краткий, готовый к запуску пример, который создает штрих‑код PDF417, позволяет управлять его размером и сохраняет результат в виде PNG‑изображения.

Генерация штрих‑кода PDF417 — распространённая задача для систем учёта, посадочных талонов и отслеживания документов. В этом учебнике мы также рассмотрим **как изменить размер штрих‑кода**, чтобы код адаптировался к различным требованиям печати или отображения на экране.

## Требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
* Visual Studio 2022 или любой IDE для C#
* Пакет **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Базовые знания о консольных приложениях C#

## Настройка проекта

1. Создайте новый консольный проект:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Добавьте ссылку на Aspose.BarCode (см. требования).  

3. Откройте `Program.cs` и замените его содержимое полным примером ниже.

## Шаг 1: Генерация штрих‑кода PDF417

Первый шаг — создать экземпляр `BarcodeGenerator`, настроенный для символьного набора **PDF417**. Этот объект является точкой входа для всех операций со штрих‑кодом.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Почему это важно* – Значение перечисления `EncodeTypes.Pdf417` сообщает Aspose.BarCode использовать стандарт PDF417, а второй аргумент передаёт данные, которые будут закодированы. Генератор теперь содержит полностью сформированный объект штрих‑кода, который можно настроить перед сохранением.

## Шаг 2: Как изменить размер штрих‑кода (размер модуля)

Штрих‑коды PDF417 состоят из небольших квадратных модулей. Изменение размера модуля меняет общие размеры изображения без изменения закодированных данных.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Почему это важно* – Больший `XDimension` даёт более крупный штрих‑код, подходящий для печати с высоким разрешением; меньший параметр лучше для отображения на экране. По умолчанию обычно используется 1 px, что может выглядеть сжато на современных мониторах.

## Шаг 3: Настройка макета – столбцы и строки

PDF417 позволяет задавать количество столбцов и строк, что влияет как на форму штрих‑кода, так и на его способность к коррекции ошибок.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Почему это важно* – Большее количество столбцов делает штрих‑код шире, а большее количество строк — выше. Регулируйте эти значения, чтобы они вписывались в доступное пространство вашего интерфейса или печатной этикетки.

## Шаг 4: Сохранение изображения штрих‑кода

Наконец, запишите штрих‑код в файл. Здесь мы используем PNG, потому что он сохраняет чёткие границы и поддерживает прозрачность.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Запуск программы создаёт `LayoutPdf417.png` в папке вывода проекта. Изображение будет выглядеть так:

![пример генерации штрих‑кода PDF417 с 4 столбцами и 9 строками](https://example.com/images/pdf417-sample.png){#barcode-image alt="пример генерации штрих‑кода PDF417 с 4 столбцами и 9 строками"}

*Совет*: Если нужен другой формат изображения (JPEG, BMP, TIFF), замените `BarCodeImageFormat.Png` на соответствующее значение перечисления.

## Как генерировать PDF417 – альтернативные источники данных

В приведённом коде используется жёстко заданная строка `"Layout test"`. В реальных сценариях данные часто берутся из базы данных, файла или ввода пользователя.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Остальные шаги (размер, макет, сохранение) остаются без изменений. Это демонстрирует **как генерировать PDF417** из динамических источников без дополнительной сложности.

## Распространённые ошибки и как их избежать

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Штрих‑код выглядит размытым | `XDimension` установлен слишком низко для выходного разрешения | Увеличьте `XDimension.Pixels` или сохраняйте в векторном формате, например SVG (`BarCodeImageFormat.Svg`) |
| Текст не помещается в выбранный макет | Слишком много символов для выбранных строк/столбцов | Уменьшите количество строк/столбцов или разбейте данные на несколько штрих‑кодов |
| Файл изображения не создан | Папка вывода не существует или отсутствуют права записи | Убедитесь, что каталог существует (`Directory.CreateDirectory`) и приложение имеет необходимые права |

## Проверка штрих‑кода

После создания изображения вы можете проверить его с помощью любого приложения‑сканера PDF417 (на смартфонах есть бесплатные сканеры) или встроенного считывателя Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Если вывод совпадает с исходным текстом, процесс **генерации штрих‑кода PDF417** завершён успешно.

## Полный, исполняемый пример

Ниже представлен полный код программы, который можно скопировать в `Program.cs`. Он включает все директивы `using`, обработку ошибок и комментарии.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Запуск этой программы выводит:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Теперь у вас есть **полное, автономное решение** для генерации штрих‑кодов PDF417 и управления их размером.

## Заключение

В этом учебнике вы узнали, как **генерировать штрих‑код PDF417** в C# с помощью Aspose.BarCode, как **изменять размер штрих‑кода** путем настройки X‑размера, а также как настраивать столбцы и строки для управления макетом. Вы также увидели, как программно проверять результат и как адаптировать код для динамических данных.

Далее вы можете изучить:

* **Как генерировать PDF417** с настройкой уровня коррекции ошибок (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Экспорт в **векторные форматы** (SVG, EPS) для бесконечного масштабирования
* Встраивание штрих‑кода в PDF‑документ с помощью **Aspose.PDF**

Экспериментируйте с различными размерами модулей и параметрами макета, чтобы подобрать оптимальное решение для вашего интерфейса или требований печати. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как сгенерировать штрих‑код PDF417 с Aspose – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [регулировка размера штрих‑кода – руководство C# по генерации штрих‑кодов PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Как сохранить штрих‑код в C# – генерация штрих‑кодов PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}