---
category: general
date: 2026-07-30
description: Чтение нескольких штрихкодов C# с помощью Aspose.BarCode. Узнайте пошагово,
  как декодировать PDF417, обнаруживать компактный режим и обрабатывать множество
  штрихкодов на одном изображении.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read multiple barcodes c#
- BarCodeReader C#
- PDF417 decoding
- barcode compact mode
- C# barcode library
language: ru
lastmod: 2026-07-30
og_description: Чтение нескольких штрихкодов C# с помощью Aspose.BarCode. Это руководство
  показывает, как декодировать все штрихкоды на изображении, проверить компактный
  режим и интегрировать в приложения .NET.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Чтение нескольких штрихкодов C# – Полный учебник по PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  headline: Read Multiple Barcodes C# – Complete Guide with PDF417
  type: TechArticle
- description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  name: Read Multiple Barcodes C# – Complete Guide with PDF417
  steps:
  - name: Why This Code Works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No Barcodes Detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely Large Images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑Safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Чтение нескольких штрихкодов C# – Полное руководство с PDF417
url: /ru/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение нескольких штрихкодов C# – Полное руководство с PDF417

Когда‑нибудь задумывались, как **read multiple barcodes C#** из одного изображения? Возможно, у вас есть партия транспортных этикеток, коллаж билетов или документ PDF417, в котором несколько кодов упакованы в одну картинку. В моей повседневной работе я столкнулся именно с такой проблемой — пока не открыл для себя `BarCodeReader` из Aspose.BarCode. В этом руководстве мы пройдемся по декодированию каждого штрихкода на изображении, определим, находится ли каждый PDF417 в компактном (усечённом) режиме, и корректно обработаем результаты.

Мы также добавим несколько полезных советов — например, что делать, когда изображение содержит разные типы штрихкодов, или когда сканирование не возвращает результатов. К концу вы получите готовое к запуску консольное приложение, которое **reads multiple barcodes C#** как профессионал.

## Что понадобится

Прежде чем погрузиться в детали, убедитесь, что на вашем компьютере установлено следующее:

- **.NET 6.0** SDK или новее (код также работает с .NET Framework 4.6+, но .NET 6 — оптимальный вариант).
- NuGet‑пакет **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`).
- Пример изображения, содержащего **PDF417** штрихкоды — желательно, чтобы в нём были как компактные, так и полноразмерные символы. В руководстве используется `CompactPdf417.png`, но подойдёт любой PNG/JPEG.
- Любая удобная IDE (Visual Studio, Rider или VS Code).  

И всё — никаких дополнительных DLL, никаких нативных зависимостей. Aspose.BarCode написан полностью на управляемом коде, поэтому его можно подключить к любому .NET‑проекту.

![Вывод консоли чтения нескольких штрихкодов C#](image.png "Вывод консоли чтения нескольких штрихкодов C#")

*Текст альтернативного описания изображения: Чтение нескольких штрихкодов C# — скриншот консоли, показывающий статус компактного режима для штрихкодов PDF417.*

## Шаг 1 – Установка и подключение библиотеки BarCodeReader C#

Первым делом вам нужна **BarCodeReader C#**‑класс, который осуществляет декодирование. Откройте терминал (или консоль диспетчера пакетов) и выполните:

```powershell
dotnet add package Aspose.BarCode
```

Или, если вы используете менеджер NuGet в Visual Studio, просто найдите *Aspose.BarCode* и нажмите **Install**. Будет загружена последняя стабильная версия (на июль 2026 года — 23.9), поддерживающая PDF417, QR, DataMatrix и десятки других символогий.

Почему это важно: библиотека берёт на себя тяжёлую работу по обработке изображений, коррекции ошибок и распознаванию символов. Вы могли бы написать собственный сканер, но это заняло бы недели на отладку краевых случаев. Aspose предоставляет проверенную **C# barcode library**, уже адаптированную под современные .NET‑рантаймы.

## Шаг 2 – Создание минимального консольного проекта

Создайте новое консольное приложение, чтобы сосредоточиться только на логике работы со штрихкодами без лишних UI‑шумов:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Замените сгенерированный `Program.cs` полным примером ниже. Можно оставить пространство имён по умолчанию или переименовать — ничего особенного не требуется.

## Шаг 3 – Реализация полной функции “Read Multiple Barcodes C#”

Ниже представлен **полный, готовый к запуску** образец кода. Он охватывает все четыре шага из оригинального фрагмента, добавляет обработку ошибок и выводит полезную диагностику.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Почему этот код работает

- **`BarCodeReader`** — основной класс из **BarCodeReader C#** API. Он открывает изображение, применяет предобработку и ищет символы указанного типа.
- **`ReadBarCodes()`** возвращает массив, а не один результат. Именно это позволяет **reading multiple barcodes C#** — метод автоматически собирает все найденные совпадения.
- **`result.Extended.Pdf417.IsTruncated`** сообщает, находится ли PDF417 в *compact* (также известном как truncated) режиме. Этот флаг существует только для PDF417, поэтому мы используем оператор условного доступа (`?.`), чтобы избежать исключений, если в изображении появятся другие символогии.
- Цикл `foreach` выводит как декодированный текст, так и статус компактности, предоставляя быстрый контроль качества.

## Шаг 4 – Обработка разных типов штрихкодов (опционально)

Если ваше изображение может содержать не только PDF417, просто замените второй аргумент `BarCodeReader` на `DecodeType.AllSupported`. Цикл останется тем же, но потребуется проверять, что `result.Extended` не равен `null` для символов, отличных от PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

Это небольшое изменение превращает вашу **C# barcode library** в универсальный сканер, идеальный для пакетов со смешанными символогиями.

## Шаг 5 – Крайние случаи и рекомендации по лучшим практикам

### 1️⃣ Не обнаружено штрихкодов  
Если `ReadBarCodes()` возвращает пустой массив, чаще всего виноваты:

- Неправильный путь к файлу или отсутствие прав на чтение.
- Слишком низкое качество изображения (размытие, низкий контраст). Рассмотрите предобработку через `reader.ImagePreprocessingOptions` (например, `reader.ImagePreprocessingOptions.Denoise = true;`).

### 2️⃣ Очень большие изображения  
Обработка фотографии в 10 МП может потребовать много памяти. Можно ограничить область сканирования:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Потокобезопасность  
`BarCodeReader` реализует `IDisposable` и **не** является потокобезопасным. Создавайте отдельные экземпляры для каждого потока, если требуется параллельная обработка.

### 4️⃣ Лицензирование  
Aspose.BarCode работает в режиме триала «из коробки», но на выходном изображении будет водяной знак. Для продакшна установите лицензию как можно раньше:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Логирование  
При интеграции в более крупный сервис замените `Console.WriteLine` на структурированный логгер (Serilog, NLog). Так вы сможете фиксировать `CodeText`, `CodeType` и `IsTruncated` как отдельные поля для последующего анализа.

## Полный рабочий пример

Объединив всё вместе, получаем *полный* код программы, который можно скопировать в `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            const string imagePath = "YOUR_DIRECTORY


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом гайде. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}