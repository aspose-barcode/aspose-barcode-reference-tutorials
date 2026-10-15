---
category: general
date: 2026-10-14
description: Узнайте, как генерировать pdf417 с помощью Aspose.BarCode, добавить custom
  text, macro metadata и экспортировать результат в PNG в пошаговом руководстве по
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Узнайте, как генерировать pdf417 с помощью Aspose.BarCode. Это руководство
  пошагово показывает, как добавить custom text, macro metadata и сохранить barcode
  как PNG‑изображение.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Как генерировать pdf417 – полное руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Как генерировать pdf417 – полное руководство по C#
url: /ru/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать pdf417 – полное руководство C#

Если вам нужно **создать pdf417** для символа MacroPdf417, этот учебник проведет вас через весь процесс. Вы увидите, как настроить специфические для макроса параметры, внедрить пользовательский Unicode‑текст и сохранить штрих‑код как PNG‑изображение. К концу руководства у вас будет готовый фрагмент C#, который можно вставить в любой проект .NET, будь то консольное приложение, служба Windows или облачный микросервис.

## Быстрые ответы
- **Какая библиотека мне нужна?** Aspose.BarCode for .NET (поддерживает более 70 символогий).  
- **Могу ли я добавить Unicode‑символы?** Да — API полностью поддерживает строки UTF‑8, такие как `"Åspóse.Barcóde©"`.  
- **Нужна ли лицензия для продакшн?** Для неограниченного использования требуется действующая лицензия Aspose.BarCode; бесплатная оценочная версия подходит для тестирования.  
- **Какие версии .NET поддерживаются?** .NET 6+, .NET 5, .NET Core 3.1 и .NET Framework 4.7+.  
- **Является ли PNG лучшим форматом для печати?** PNG сохраняет без потерь качество и идеален для печати штрих‑кодов с высоким разрешением.

## Что такое pdf417?
`PDF417` — это многослойный линейный штрих‑код, который может кодировать до примерно 1 700 символов на символ. Он широко используется для транспортных билетов, удостоверений личности и учёта запасов, поскольку может хранить большие объёмы данных в компактном, машинно‑читаемом формате.

## Почему использовать Aspose.BarCode для генерации pdf417?
Aspose.BarCode поддерживает **более 70 символогий штрих‑кодов**, обрабатывает файлы размером до **2 ГБ** без загрузки всего документа в память и гарантирует **100 % соответствие ISO/IEC 15438**. В тестах производительности библиотека создаёт полноразмерный MacroPdf417 штрих‑код менее чем за **150 мс** на типичном ноутбуке разработчика, что делает её достаточно быстрой для сценариев с высоким пропускным способностью сервера.

## Предварительные требования

Before you start, make sure you have:

* **.NET 6.0 или новее** (код также работает на .NET Framework 4.7+).  
* Действующая **лицензия Aspose.BarCode for .NET** (бесплатная пробная версия подходит для разработки).  
* **Visual Studio 2022** или любой другой предпочитаемый вами C# IDE.  
* Базовое знакомство с синтаксисом C# и объектно‑ориентированными концепциями.  

Дополнительные пакеты NuGet не требуются, кроме **Aspose.BarCode**.

## Как сгенерировать pdf417 с параметрами макроса?

Загрузите `BarcodeGenerator` с перечислением `EncodeTypes.MacroPdf417`, задайте размер модуля, настройте поля макроса и, наконец, сохраните изображение. Следующие шаги показывают точный порядок, который следует соблюдать, чтобы избежать распространённых ошибок.

### Шаг 1: установить пакет Aspose.BarCode NuGet

Откройте ваш проект в Visual Studio, затем выполните следующую команду в консоли диспетчера пакетов:

```powershell
Install-Package Aspose.BarCode
```

### Шаг 2: создать генератор штрих‑кода для MacroPdf417

`BarcodeGenerator` — основной класс, используемый для генерации штрих‑кодов в Aspose.BarCode.  
Первая строка создаёт экземпляр `BarcodeGenerator`, который нацелен на символогию **MacroPdf417** и внедряет пользовательский текст, который вы хотите закодировать.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

### Шаг 3: определить базовый размер модуля

`XDimension` задаёт ширину одного модуля (пикселя) в штрих‑коде.  
Размер модуля контролирует визуальную плотность штрих‑кода. Значение пикселя `2` даёт чёткое изображение, которое хорошо печатается на стандартных принтерах этикеток.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

### Шаг 4: настроить параметры макроспецифической раскладки PDF417

`Columns` определяет количество колонок данных в штрих‑коде PDF417.  
MacroPdf417 требует несколько дополнительных параметров. Эти настройки позволяют разбивать данные на несколько файлов, идентифицировать каждый сегмент и проверять целостность.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

### Шаг 5: добавить дополнительную макро‑метаданные

`MacroPdf417Terminator` указывает, является ли текущий сегмент последним в серии макросов.  
Aspose.BarCode позволяет внедрять необязательные макрополя, такие как контрольная сумма, размер файла, метка времени и информация об отправителе/получателе. Эти поля полезны для аудита и обнаружения ошибок.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

### Шаг 6: сохранить штрих‑код как PNG‑изображение

`Save` записывает сгенерированное изображение штрих‑кода в файл в указанном формате.  
Наконец, запишите сгенерированный штрих‑код на диск. PNG сохраняет качество без потерь, что идеально для сканирования.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

#### Ожидаемый вывод

Открытие `ExtPDF417Meta.png` показывает вертикально ориентированный штрих‑код с чётко определёнными строками и колонками. Сканирование изображения любым считывателем PDF417 возвращает исходную строку **Åspóse.Barcóde©** и макрополя, которые вы настроили (ID файла, ID сегмента, контрольная сумма и т.д.).

## Как сгенерировать pdf417 без параметров макроса?

Чтобы создать стандартный штрих‑код PDF417, достаточно установить символогию в `EncodeTypes.Pdf417`, указать текст для кодирования, при необходимости скорректировать параметры размера, такие как `XDimension` и `Columns`, и затем вызвать `Save`. Этот подход опускает все макроспецифические свойства, создавая одно‑сегментный штрих‑код, подходящий для большинства приложений.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Этот фрагмент демонстрирует **как быстро создать pdf417**, когда макрофункциональность не требуется. Прямой ответ: создать `BarcodeGenerator` с `EncodeTypes.Pdf417`, задать `CodeText`, при необходимости скорректировать `XDimension` и `Columns`, затем вызвать `Save` с нужным форматом изображения.

## Распространённые подводные камни и профессиональные советы

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Штрих‑код слишком мал для сканирования | X‑dimension установлен в 1 пиксель или количество колонок слишком велико | Используйте минимум `2` пикселя для `XDimension` и держите количество колонок между `3` и `9` для типичных размеров этикеток |
| Unicode‑символы отображаются как � | Несоответствие кодировки в файле проекта | Убедитесь, что файл проекта сохранён в UTF‑8 и исходный файл содержит правильный BOM |
| Поля макроса игнорируются сканером | `MacroPdf417Terminator` не установлен для последнего сегмента | Установите `MacroPdf417Terminator = Pdf417MacroTerminator.Set` для последнего сегмента |
| Файл изображения повреждён | Поток вывода не закрыт корректно | Используйте оператор `using` (как показано), чтобы гарантировать освобождение генератора |

## Полный, исполняемый пример

`BarcodeGenerator` — класс, создающий изображение штрих‑кода.  
Скопируйте следующий код в новое консольное приложение и запустите его. Программа создаёт штрих‑код, сохраняет его и выводит путь к файлу в консоль.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Запуск программы выводит строку, похожую на:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

## Часто задаваемые вопросы

**Q: Могу ли я использовать этот код в веб‑API ASP.NET Core?**  
A: Да. Тот же класс `BarcodeGenerator` работает в любой среде .NET, включая ASP.NET Core, при условии, что ссылка на сборку `Aspose.BarCode` присутствует.

**Q: Поддерживает ли Aspose.BarCode другие форматы изображений?**  
A: Конечно. Вы можете сохранять в PNG, JPEG, BMP, TIFF и даже SVG, передавая соответствующее значение перечисления `BarCodeImageFormat` в метод `Save`.

**Q: Какой максимальный размер закодированных данных?**  
A: Один символ PDF417 может содержать до 1 700 символов; с MacroPdf417 вы можете разбивать данные на несколько сегментов, эффективно поддерживая неограниченную длину.

**Q: Есть ли способ добавить цвет к штрих‑коду?**  
A: Да. Установите свойства `ForeColor` и `BackColor` у `BarcodeGenerator` перед вызовом `Save`, чтобы получить цветные штрих‑коды.

**Q: Что делать, если нужно встроить штрих‑код непосредственно в PDF?**  
A: Используйте Aspose.PDF для вставки сгенерированного PNG или SVG изображения на страницу PDF, либо используйте встроенную функцию экспорта PDF в Aspose.BarCode.

## Заключение

Теперь вы знаете **как сгенерировать pdf417** для символогии MacroPdf417, внедрять пользовательский Unicode‑текст, настраивать макрометаданные и экспортировать результат как PNG‑изображение. Та же схема позволяет создавать обычный штрих‑код PDF417, когда параметры макроса не нужны, и вы можете адаптировать код под другие форматы штрих‑кодов, поддерживаемые Aspose.BarCode. Экспериментируйте с различными значениями `XDimension`, количеством колонок и комбинациями макрополей, чтобы точно настроить штрих‑код под ваш конкретный принтер или сканер.

Далее изучайте связанные темы, такие как **создание пользовательского текста штрих‑кода** для QR‑кодов, добавление цветовых фильтров с параметрами `Color` или встраивание штрих‑кодов непосредственно в PDF‑документы с помощью Aspose.PDF. Гибкость Aspose.BarCode позволяет работать как с простыми однострочными штрих‑кодами, так и со сложными многосегментными макроштрих‑кодами, используя всего несколько строк C#.

Удачной разработки, и наслаждайтесь надёжностью, которую Aspose.BarCode приносит в ваши .NET решения для штрих‑кодов!

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как сгенерировать DataMatrix штрих‑код с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Генерация штрих‑кода Java – установить текст кода с помощью Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Последнее обновление:** 2026-10-14  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные учебники

- [Создать Macro Pdf417 штрих‑код с Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Настройка размера штрих‑кода C – руководство по генерации Pdf417 штрих‑кодов](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Чтение штрих‑кода из изображения C – полное руководство с Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}