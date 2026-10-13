---
category: general
date: 2026-10-05
description: Узнайте, как создать штрих‑код PDF417 на C# и сгенерировать PNG‑изображение
  штрих‑кода с пошаговым кодом и советами по лучшим практикам.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: ru
lastmod: 2026-10-05
og_description: Создайте штрих‑код PDF417 на C# и мгновенно генерируйте PNG‑изображение
  штрих‑кода. Следуйте этому полному руководству для готового к производству решения.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Создание штрихкода PDF417 в C# – полное руководство по генерации PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Как создать штрих‑код PDF417 и сохранить его как PNG в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PDF417 barcode и сохранить его как PNG в C#

Если вам нужно **создать PDF417 barcode** в приложении .NET, это руководство покажет вам, как это сделать. Вы получите готовый фрагмент кода C#, который генерирует высококачественный **barcode PNG** файл, и вы поймёте каждую настройку, влияющую на результат.

Создание штрих‑кодов — распространённая потребность для систем билетов, учёта запасов и безопасного кодирования документов. К концу этого руководства вы сможете ответить на вопрос «**how to generate PDF417**» с полным, исполняемым примером.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Среда разработки, например Visual Studio 2022 или VS Code  
* Пакет NuGet **Aspose.BarCode for .NET** (или любая совместимая библиотека, поддерживающая PDF417)  

Вы можете добавить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

Код ниже использует Aspose API, потому что он предоставляет детальный контроль над параметрами PDF417 и поддерживает экспорт в PNG из коробки.

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новый консольный проект и импортируйте необходимые пространства имён:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Пространство имён `Aspose.BarCode.Generation` содержит класс `BarcodeGenerator`, который является точкой входа для **создания PDF417 barcode** изображений.

## Шаг 2: Создайте PDF417 barcode с нужным текстом

Создайте экземпляр генератора, используя перечисление `EncodeTypes.Pdf417` и данные, которые вы хотите закодировать. В примере используется строка, содержащая специальные символы, чтобы продемонстрировать работу с Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Теперь генератор содержит объект штрих‑кода, который вы можете настроить перед отрисовкой.

## Шаг 3: Настройте визуальные параметры

Точная настройка штрих‑кода улучшает читаемость и уменьшает размер изображения. Наиболее часто настраиваемые параметры — **X‑dimension**, **columns** и **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** управляет шириной каждого модуля; значение `2` пикселя даёт компактный, но разборчивый штрих‑код.  
* **Columns** определяют, сколько столбцов данных использует код. Меньшее количество столбцов делает штрих‑код уже, но выше.  
* **Truncate** активирует режим «compact», определённый спецификацией PDF417, который удаляет лишние строки заполнения.

Вы можете поэкспериментировать с `Rows` и `ErrorCorrectionLevel`, если ваш сценарий требует более высокой устойчивости к повреждениям.

## Шаг 4: Сохраните штрих‑код как PNG‑изображение

Наконец, экспортируйте штрих‑код в файл PNG. PNG сохраняет резкие границы и поддерживает прозрачность, что делает его идеальным для веб‑ и печатных сценариев.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Запуск программы создаёт `CompactPdf417.png` в указанном каталоге. Изображение выглядит так:

![Компактный PDF417 barcode, созданный с помощью C#](compact-pdf417.png "Пример компактного PDF417 barcode, созданного с помощью C#")

*Текст альтернативного описания выше содержит основной ключевой запрос, удовлетворяя требования SEO и доступности.*

## Полный, исполняемый пример

Объединив все части, представляем автономную программу, которую вы можете скопировать, вставить и запустить:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Ожидаемый результат

Когда вы откроете `CompactPdf417.png`, вы должны увидеть вертикальный, высокоплотный штрих‑код, который кодирует строку *Åspóse.Barcóde©*. Сканирование изображения любым считывателем PDF417 возвращает исходный текст.

## Почему эти настройки важны

* **X‑dimension** влияет как на физический размер, так и на скорость сканирования. Меньшие модули повышают плотность данных, но могут потребовать сканеров с более высоким разрешением.  
* **Columns** влияют на соотношение сторон. Для мобильных чеков небольшое количество столбцов сохраняет штрих‑код достаточно узким, чтобы поместиться на узкой бумаге.  
* **Truncate** уменьшает количество строк, экономя чернила и место без потери целостности данных, поскольку PDF417 уже включает кодовые слова коррекции ошибок.

Понимание этих параметров позволяет адаптировать штрих‑код под ограничения целевого носителя — будь то принтер этикеток, веб‑страница или мобильное приложение.

## Распространённые варианты и крайние случаи

### Генерация других форматов изображений

Если вы предпочитаете JPEG или BMP, измените перечисление `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG сжимает изображение, но может добавить артефакты, влияющие на сканирование при небольших размерах.

### Настройка коррекции ошибок

Для тяжёлых условий (например, наружные вывески) увеличьте уровень коррекции ошибок:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Более высокие уровни добавляют больше избыточности, делая штрих‑код больше, но надёжнее.

### Кодирование бинарных данных

PDF417 может кодировать бинарные полезные нагрузки. Передайте `byte[]` вместо строки:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Библиотека автоматически переключается в бинарный режим.

### Обработка очень длинных строк

Когда данные превышают стандартную ёмкость, генератор автоматически создаёт дополнительные строки. Вы можете ограничить количество строк, чтобы избежать слишком больших изображений:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Если содержимое всё ещё не помещается, рассмотрите возможность разбить его на несколько штрих‑кодов.

## Профессиональные советы

* **Cache the generator** если вам нужно создавать множество штрих‑кодов с одинаковыми настройками. Повторное использование объекта избегает повторного выделения внутренних ресурсов.  
* **Set `Resolution`** в `ImageOptions`, если требуется конкретное DPI для печати:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output** программно с помощью `BarCodeReader`, чтобы убедиться, что сгенерированный PNG может быть декодирован перед отправкой пользователям.

## Заключение

Теперь вы знаете, как **create PDF417 barcode** в C# и **generate barcode PNG** файлы с полным контролем над размером, столбцами и компактным режимом. Полный пример демонстрирует стандартный подход, объясняет, почему каждая настройка важна, и охватывает варианты, такие как коррекция ошибок, альтернативные форматы и бинарные данные. Используйте приведённые советы, чтобы адаптировать решение к вашему конкретному рабочему процессу, будь то система билетов, генератор логистических этикеток или безопасный кодировщик документов.

---

**Следующие шаги**

* Изучите другие 2D‑символы (DataMatrix, QR), используя тот же класс `BarcodeGenerator`.  
* Интегрируйте создание штрих‑кода в ASP.NET Core API для предоставления PNG‑изображений по запросу.  
* Объедините изображение штрих‑кода с библиотеками генерации PDF, чтобы внедрить его непосредственно в отчёты.

Удачной разработки!

## Что вам следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и изучить альтернативные подходы к реализации в ваших проектах.

- [Как создать pdf417 barcode в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Как сгенерировать micro pdf417 barcode в C# – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Как создать PDF417 barcode в C# с компактным режимом](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}