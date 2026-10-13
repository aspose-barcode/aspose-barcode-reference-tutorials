---
category: general
date: 2026-09-28
description: Быстро считывайте PDF417 barcode c# с помощью Aspose.BarCode. Декодируйте
  несколько barcode с одного изображения, извлекайте поля Macro‑PDF417 и обрабатывайте
  вращение или пакетную обработку.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Быстро считывайте PDF417 barcode c# с помощью Aspose.BarCode. Это
  руководство показывает, как декодировать несколько barcode с одного изображения,
  извлекать все свойства Macro‑PDF417 и обрабатывать вращённые или пакетные изображения.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Чтение PDF417 barcode c# – полный пример кода и руководство
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Как читать PDF417 barcode c# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать штрих‑код PDF417 c# – полное пошаговое руководство

Когда‑нибудь задавались вопросом **как читать PDF417** с изображения с помощью C#? Вы не одиноки. Большинство разработчиков сталкиваются с проблемой, когда нужно извлечь расширенные поля Macro‑PDF417 из отсканированного документа. Хорошая новость? Всего несколькими строками кода вы можете **читать штрих‑код PDF417 c#**, декодировать несколько штрих‑кодов на одной картинке и получить все скрытые свойства, предусмотренные спецификацией.

## Быстрые ответы
- **Может ли Aspose.BarCode декодировать Macro‑PDF417?** Да – просто включите `DecodeType.MacroPdf417`, и библиотека вернёт все расширенные поля.  
- **Сколько штрих‑кодов можно прочитать с одного изображения?** Не ограничено; API возвращает коллекцию объектов `BarCodeResult`.  
- **Нужна ли лицензия для продакшна?** Коммерческая лицензия требуется для использования в продакшн‑среде; бесплатная пробная версия подходит для оценки.  
- **Будут ли обнаружены повернутые штрих‑коды?** Встроенная компенсация вращения работает для штрих‑кодов, занимающих как минимум 30 % ширины изображения.  
- **Поддерживается ли пакетная обработка?** Абсолютно – оберните считыватель в цикл `foreach` и освобождайте каждый экземпляр с помощью `using`.

## Что такое read PDF417 barcode c#?
`read pdf417 barcode c#` относится к процессу использования .NET‑библиотеки для декодирования PDF417 (включая Macro‑PDF417) символов из файлов изображений непосредственно в коде C#. SDK Aspose.BarCode предоставляет одно‑вызовное API, которое обрабатывает загрузку изображения, обнаружение штрих‑кода и извлечение всех полей, определённых ISO.

## Почему стоит использовать Aspose.BarCode для декодирования PDF417?
Aspose.BarCode поддерживает **более 30 символогий** и может обрабатывать изображения размером до **5000 × 5000 px** менее чем за **0.1 s** на типичном серверном оборудовании. Он также предлагает готовую поддержку вращения, искажений и инвертированных штрих‑кодов, избавляя от необходимости писать собственную предобработку изображений. Кроме того, библиотека включает встроенную поддержку чтения расширенных полей Macro‑PDF417, делая её универсальным решением для сложных сценариев сканирования.

## Предварительные требования

Прежде чем приступить, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код работает и с .NET Core, и с .NET Framework).  
* Visual Studio 2022 (или любой другой предпочитаемый редактор).  
* Пакет NuGet **Aspose.BarCode for .NET** – это библиотека, которая действительно парсит PDF417.  
* Пример изображения, содержащего штрих‑код Macro‑PDF417 (например `ExtPDF417Meta.png`).  

Дополнительная конфигурация не требуется; библиотека поставляется со всеми необходимыми декодерами.

## Как читать штрих‑код PDF417 c#?

Загрузите изображение с помощью `BarCodeReader`, укажите `DecodeType.MacroPdf417` и пройдитесь по возвращённой коллекции `BarCodeResult` – это полное решение в менее чем десяти строках кода. Считыватель автоматически извлекает как обычные PDF417‑символы, так и расширенные данные Macro‑PDF417, поэтому вы получаете идентификаторы файлов, номера сегментов, метки времени и контрольные суммы без дополнительного парсинга.

### Шаг 1: установить Aspose.BarCode

Откройте папку проекта в терминале и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда загрузит последнюю стабильную версию (на июль 2026 это 23.12). Если вы предпочитаете консоль диспетчера пакетов в Visual Studio, используйте:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** зафиксируйте версию (`23.12.0`) в вашем `.csproj`, чтобы избежать случайных несовместимых изменений позже.

### Шаг 2: создать каркас консольного приложения

Создайте новый консольный проект, если у вас его ещё нет:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Замените автоматически сгенерированный `Program.cs` кодом ниже. Мы разберём каждый блок в следующих разделах.

### Шаг 3: написать полный код «как читать PDF417»

`BarCodeReader` – основной класс, который читает изображение, обнаруживает штрих‑коды и возвращает коллекцию объектов `BarCodeResult`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — основной класс, отвечающий за чтение и декодирование штрих‑кодов из изображений.  
* `DecodeType.MacroPdf417` — флаг, который сообщает SDK обрабатывать Macro‑PDF417 особым образом, одновременно возвращая обычные PDF417‑символы.  
* `Extended.Pdf417.MacroPdf417` — объект, содержащий все необязательные поля, определённые ISO/IEC 15438, такие как `FileID`, `SegmentID` и `Checksum`.

Блок `using` гарантирует освобождение нативных ресурсов, предотвращая утечки памяти в длительно работающих сервисах.

### Шаг 4: запустить приложение и проверить вывод

В терминале:

```bash
dotnet run
```

Вы должны увидеть что‑то вроде:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Если изображение содержит более одного штрих‑кода, цикл выводит разделительную строку (`----------------------------------------`) и переходит к следующему результату — именно так выглядит **чтение нескольких штрих‑кодов** на практике.

## Часто задаваемые вопросы и особые случаи

### Что делать, если изображение содержит как Macro‑PDF417, так и обычные PDF417 символы?

Тот же вызов `BarCodeReader` вернёт оба типа. Их можно различать, проверяя `result.CodeType` (`MacroPdf417` vs `Pdf417`). Расширенные свойства будут `null` для обычного PDF417, поэтому проверка `if (macro != null)` предотвращает `NullReferenceException`.

### Мой штрих‑код повернут или искривлён — будет ли считыватель работать?

Aspose.BarCode включает встроенную компенсацию вращения и искажений. При условии, что штрих‑код занимает минимум 30 % ширины изображения, декодер обычно справляется. Для экстремальных случаев можно включить `reader.Options.AllowInvertedBarcodes = true;` перед вызовом `ReadBarCodes()`.

### Как обрабатывать большие партии изображений?

Обёрните логику чтения в цикл `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Паттерн `using` гарантирует освобождение нативных ресурсов каждого изображения перед следующей итерацией, поддерживая низкое потребление памяти.

## Полный листинг исходного кода (готов к копированию)

Ниже представлен весь программный код в одном блоке для быстрого копирования. Нет скрытых зависимостей — только пакет NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Итоги – что мы рассмотрели

* **Как читать штрих‑код PDF417 c#** с помощью Aspose.BarCode.  
* Точные шаги для **чтения нескольких штрих‑кодов** с одного изображения.  
* Как **читать изображение штрих‑кода c#** и извлекать каждое поле Macro‑PDF417.  
* Советы по вращению, пакетной обработке и работе с отсутствующими расширенными данными.

## Следующие шаги и смежные темы

* **Encode PDF417** – генерируйте свои собственные штрих‑коды Macro‑PDF417 с помощью `BarCodeBuilder`.  
* **Чтение других 2‑D символогий** – QR, DataMatrix, Aztec — используя тот же класс `BarCodeReader`.  
* **Интеграция с ASP.NET Core** – создайте веб‑endpoint, принимающий загруженное изображение и возвращающий JSON с декодированными полями.  

### Полезные ссылки
- [Как читать штрих‑коды DataMatrix с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Чтение штрих‑кода DataMatrix C# – режим автоматической генерации (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Экспериментируйте: меняйте путь к изображению, помещайте обычный PDF417 в ту же папку или меняйте флаги `DecodeType`, чтобы увидеть, как библиотека реагирует. Чем больше вы играете, тем увереннее будете себя чувствовать в сценариях **read barcode image c#**.

Есть сложное изображение, которое отказывается декодироваться? Оставьте комментарий ниже или откройте issue в репозитории GitHub примера проекта. Приятного кодинга!

## Часто задаваемые вопросы

**В: Можно ли использовать это в коммерческом приложении?**  
О: Да, вы можете использовать Aspose.BarCode в коммерческих проектах при наличии действующей лицензии; бесплатная пробная версия доступна для оценки.

**В: Поддерживает ли считыватель изображения, защищённые паролем?**  
О: SDK работает с любыми стандартными форматами изображений; защита паролем применима только к PDF‑файлам, которые обрабатываются отдельным компонентом Aspose.PDF.

**В: Какие версии .NET поддерживаются?**  
О: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, и .NET 6+ полностью поддерживаются текущим выпуском Aspose.BarCode.

**В: Как улучшить производительность при обработке очень больших пакетов изображений?**  
О: Включите `reader.Options.Quality = QualityMode.HighPerformance` и обрабатывайте изображения параллельно с помощью `Parallel.ForEach`, при этом каждый `BarCodeReader` всё равно оборачивается в `using`.

**В: Есть ли способ получить только поля Macro‑PDF417 без перебора всех результатов?**  
О: Да — после вызова `ReadBarCodes()` отфильтруйте коллекцию с помощью `result => result.CodeType == DecodeType.MacroPdf417` и затем обращайтесь к свойству `Extended.Pdf417.MacroPdf417`.

---

**Последнее обновление:** 2026-09-28  
**Тестировано с:** Aspose.BarCode 23.12 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как сгенерировать изображение штрих‑кода Pdf417 в C с Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Создание штрих‑кода Pdf417 с Aspose Barcode пошаговое руководство](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Чтение нескольких штрих‑кодов C Полное руководство с Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}