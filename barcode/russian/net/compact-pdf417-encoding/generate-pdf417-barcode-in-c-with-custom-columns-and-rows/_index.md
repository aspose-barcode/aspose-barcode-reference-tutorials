---
category: general
date: 2026-10-21
description: Быстро генерируйте штрих‑код PDF417 на C#. Узнайте, как создавать штрих‑код
  PDF417 с пользовательским макетом, колонками, строками и выводом в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: ru
lastmod: 2026-10-21
og_description: Создайте штрих‑код PDF417 на C#. Следуйте этому руководству, чтобы
  узнать, как генерировать штрих‑код PDF417 с пользовательскими столбцами, строками
  и выводом в PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Создание штрих‑кода PDF417 в C# — полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Создать штрих‑код pdf417 в C# с пользовательскими столбцами и строками
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сгенерировать pdf417 barcode в C# – полное руководство по программированию

Если вам нужно **сгенерировать pdf417 barcode** в .NET приложении, это руководство покажет, как сделать это несколькими строками кода. Вы увидите практический пример, который настраивает количество столбцов и строк, а затем сохраняет результат в виде PNG‑изображения. Такой же подход работает с любым текстом, который вы хотите закодировать, поэтому его можно адаптировать для счетов‑фактур, билетов или удостоверений личности.

Создание **pdf417 barcode** часто ощущается как отдельная задача от остального кода. К концу этого руководства вы поймёте, почему параметры макета важны, как контролировать качество изображения и какие вызовы библиотеки необходимы для **сгенерировать pdf417 barcode** надёжно.

## Что понадобится

* .NET 6.0 SDK или более поздняя версия, установленная  
* IDE, совместимая с C# (Visual Studio, VS Code, Rider и др.)  
* Пакет NuGet **Aspose.BarCode for .NET** (или любая совместимая библиотека штрих‑кодов)  

Вы можете добавить библиотеку с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

Библиотека предоставляет класс `BarcodeGenerator`, используемый на протяжении всего руководства.

## Шаг 1: Создать экземпляр генератора штрих‑кода

Первая строка создаёт объект, который умеет **сгенерировать pdf417 barcode**. Необходимо указать тип кодирования (`EncodeTypes.Pdf417`) и текст, который вы хотите закодировать.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Почему этот шаг важен* – `BarcodeGenerator` инкапсулирует все настройки штрих‑кода. Создание его с правильным `EncodeTypes` указывает движку использовать символьный набор PDF417 вместо QR, Code128 или других форматов.

## Шаг 2: Настроить макет PDF417

PDF417 позволяет управлять количеством столбцов и строк, что напрямую влияет на размер и плотность штрих‑кода. Настройка этих значений является сутью **как сгенерировать pdf417 barcode** с пользовательским макетом.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Почему вы можете изменить эти значения* – Большее количество столбцов уменьшает высоту штрих‑кода, а большее количество строк увеличивает ширину. Выбирайте значения, подходящие для целевого сканера и доступной области печати.

> **Совет:** Если вы опустите строки, библиотека автоматически вычислит оптимальное количество на основе длины данных. Явное указание строк полезно, когда нужен фиксированный размер изображения для UI‑макетов.

## Шаг 3: Выбрать формат изображения и сохранить файл

После настройки макета вы можете отрисовать штрих‑код в виде изображения. Пример ниже сохраняет штрих‑код как PNG‑файл, но вы также можете выбрать JPEG, BMP или TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Когда код выполнится, `CustomLayout.png` будет содержать чёткий **pdf417 barcode**, соответствующий указанным вами настройкам столбцов/строк.

### Ожидаемый результат

Открывая `CustomLayout.png`, вы увидите прямоугольный штрих‑код с четырьмя столбцами данных и девятью строками. Сканирование изображения любым PDF417‑ридером возвращает исходный текст **«Sample Text»**.

![Пример сгенерированного PDF417 barcode](generated-pdf417.png){: .center-image alt="Сгенерированный pdf417 barcode, сохранённый как PNG‑файл"}

## Шаг 4: Полный, исполняемый пример

Ниже представлено автономное консольное приложение, которое объединяет все части. Скопируйте код в новый проект `.csproj` и запустите его — дополнительные файлы не требуются.

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
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Запуск программы выводит строку подтверждения и создаёт PNG‑файл в подпапке `output`. Изображение можно встраивать в отчёты, печатать на этикетках или отправлять на мобильное устройство для сканирования.

## Распространённые варианты и граничные случаи

| Сценарий | Что изменить | Почему это важно |
|----------|----------------|----------------|
| **Закодировать длинную строку** | Увеличьте `Rows` или позвольте библиотеке автоматически вычислить, опустив присваивание `Rows` | PDF417 может хранить до 1 850 символов; недостаточное количество строк приводит к усечению |
| **Более высокое визуальное качество** | Установите `generator.Parameters.ImageResolution` в 600 DPI | Полезно при печати на принтерах с высоким разрешением |
| **Другой формат изображения** | Замените `BarCodeImageFormat.Png` на `Jpeg` или `Tiff` | JPEG уменьшает размер файла; TIFF сохраняет данные без потерь для архивирования |
| **Добавить тихую зону** | `generator.Parameters.Barcode.XDimension = 2;` (или скорректировать `Margins`) | Тихие зоны повышают надёжность сканера в шумных условиях |
| **Динамический текст из ввода пользователя** | Замените жёстко закодированную строку на `Console.ReadLine()` | Позволяет генерировать в реальном времени на основе данных пользователя |

### Как сгенерировать pdf417 barcode в веб‑API

Если вам нужно предоставить генерацию штрих‑кода через конечную точку ASP.NET Core, верните изображение в виде массива байтов:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Этот фрагмент кода отвечает на вопрос **как сгенерировать pdf417 barcode** «на лету» без записи на диск, что идеально подходит для микросервисов или мобильных бэкендов.

## Тестирование сгенерированного штрих‑кода

Чтобы убедиться, что штрих‑код создан корректно:

1. Откройте PNG‑файл в любом просмотрщике изображений.  
2. Используйте бесплатное приложение‑сканер PDF417 (например, ZXing, PDF417 Decoder) для сканирования изображения.  
3. Убедитесь, что декодированный текст соответствует исходному вводу.

Если сканер сообщает об ошибках, дважды проверьте значения столбцов/строк и убедитесь, что разрешение изображения достаточно высоко для вашего устройства.

## Заключение

Теперь вы знаете, как **сгенерировать pdf417 barcode** в C# с полным контролем над столбцами, строками и форматом вывода. Полный пример демонстрирует весь процесс — от создания `BarcodeGenerator` до сохранения PNG‑файла — чтобы вы могли интегрировать создание штрих‑кодов в любой проект .NET.

Далее изучайте связанные темы, такие как оптимизация **pdf417 barcode layout**, встраивание штрих‑кодов в PDF‑отчёты или декодирование штрих‑кодов на мобильных устройствах. Настройка уровней коррекции ошибок и эксперименты с различными разрешениями изображений помогут точно настроить решение под ваш конкретный случай. Приятного кодирования!

## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать PDF417 barcode в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Как сохранить штрих‑код в C# – генерация PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Как сгенерировать PDF417 Barcode – полное руководство по программированию](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}