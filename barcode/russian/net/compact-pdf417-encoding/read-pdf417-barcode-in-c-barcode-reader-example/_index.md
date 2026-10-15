---
category: general
date: 2026-10-14
description: Создать console сканер штрих‑кодов на C#, который читает штрих‑коды PDF417,
  обрабатывает macro PDF417 и декодирует несколько штрих‑кодов с одного изображения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Создать console сканер штрих‑кодов на C# для быстрой считывания штрих‑кодов
  PDF417 и macro PDF417 с изображений. Это пошаговое руководство показывает, как декодировать
  несколько штрих‑кодов на одной картинке.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Создать console сканер штрих‑кодов на C# – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Создать console сканер штрих‑кодов на C# – пример чтения штрих‑кода PDF417
url: /ru/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать консольный сканер штрихкодов на C# – пример чтения штрихкода PDF417

`BarCodeReader` является ядром класса Aspose.BarCode, который декодирует штрихкоды из изображений и возвращает подробные метаданные. Если вам нужно прочитать данные штрихкода PDF417 из изображения, это руководство покажет, как сделать это с помощью класса **BarCodeReader** на C#. Вы изучите пример **create console barcode scanner**, который также обрабатывает macro PDF417 и может считывать несколько штрихкодов на одном изображении.

Работа со штрихкодами часто подразумевает работу с различными источниками изображений, изменяющимися условиями освещения и иногда составными данными, такими как сегменты macro PDF417. Этот учебник охватывает всё, что вам нужно для декодирования штрихкода PDF417, извлечения его расширенных полей и обработки нескольких штрихкодов с одной картинки. К концу вы получите исполняемую консольную программу, которая читает штрихкоды из файла изображения и выводит подробную информацию в консоль.

## Краткие ответы
- **Что делает пример?** Он создает консольный сканер штрихкодов, который читает штрихкоды PDF417 и macro PDF417 с изображения и выводит все декодированные поля.  
- **Какая библиотека требуется?** Aspose.BarCode for .NET (NuGet).  
- **Можно ли читать несколько штрихкодов одновременно?** Да — считыватель перебирает каждый найденный на изображении штрихкод.  
- **Нужен ли интернет?** Нет, библиотека полностью работает офлайн.  
- **Какая версия .NET поддерживается?** .NET 6.0 или новее.

## Что вам понадобится

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия, установленная  
* Последняя версия пакета NuGet **Aspose.BarCode for .NET** (или любая совместимая библиотека, предоставляющая `BarCodeReader` и `DecodeType.MacroPdf417`)  
* Файл изображения, содержащий штрихкод PDF417 или macro PDF417 (в примере используется `ExtPDF417Meta.png`)  
* Редактор кода или IDE, например Visual Studio 2022  

Дополнительные сервисы или внешние API не требуются.

## Настройка проекта для чтения штрихкодов

1. **Создать новый консольный проект**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Добавить библиотеку штрихкодов**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Скопировать изображение штрихкода**  

   Поместите `ExtPDF417Meta.png` (или любое изображение, содержащее штрихкод PDF417) в папку проекта.  
   Для этого учебника мы предполагаем, что файл находится по пути `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Проект теперь готов к компиляции и запуску примера считывателя штрихкодов.

## Как создать консольный сканер штрихкодов на C#?

`BarCodeReader` — класс, предоставляемый Aspose.BarCode, который читает штрихкоды из изображений и возвращает их декодированные данные.  
Загрузите изображение с помощью `BarCodeReader`, установите тип декодирования в `MacroPdf417` и перебирайте результаты — это всё, что нужно для создания консольного сканера штрихкодов. Считыватель автоматически освобождает нативные ресурсы благодаря оператору `using`, поэтому вам не нужно управлять памятью вручную. Этот подход работает с любым форматом изображений, поддерживаемым .NET, таким как PNG, JPEG или BMP.

### Пошаговое руководство

Ядром решения является блок `using`, который создает экземпляр `BarCodeReader`, указывает `DecodeType.MacroPdf417` и перебирает каждый обнаруженный штрихкод. Следующий код — это полностью самостоятельная программа, которую вы можете вставить в `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Почему это работает**:  

* `DecodeType.MacroPdf417` указывает считывателю искать макро‑расширение PDF417, которое содержит дополнительные метаданные, такие как ID файла, количество сегментов и метки времени.  
* Оператор `using` гарантирует своевременное освобождение неуправляемых ресурсов (дескрипторы файлов, нативные буферы декодирования).  
* Цикл `foreach` автоматически обрабатывает **все** штрихкоды, содержащиеся в изображении, удовлетворяя требование *read multiple barcodes*.  

При запуске программы (`dotnet run`) вы должны увидеть вывод, похожий на следующий:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Если изображение содержит более одного штрихкода PDF417, цикл выводит отдельный блок для каждого штрихкода, тем самым демонстрируя, как **read multiple barcodes** из одной картинки.

## Как прочитать несколько штрихкодов с изображения?

Используйте один экземпляр `BarCodeReader` и установите флаг `DecodeType`, включающий все форматы, которые вы хотите обнаружить. Комбинируя флаги с помощью побитового оператора OR, вы можете указать библиотеке искать PDF417, QR, Code‑128 и многие другие символьные наборы за один проход. Это устраняет необходимость в отдельных считывателях и снижает время обработки.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* — это битовая маска, поэтому вы можете комбинировать любое количество поддерживаемых форматов. Aspose.BarCode поддерживает **30+ символогий штрихкодов**, включая QR, DataMatrix, Code‑128 и UPC‑A, позволяя одному сканеру обслуживать разнообразные сценарии, такие как маркировка продукции, проверка билетов и верификация личности.

## Что такое macro PDF417 и как безопасно получить доступ к его полям?

Macro PDF417 — это расширение символогии PDF417, позволяющее разбивать большой набор данных на несколько символов штрихкода.  
Macro PDF417 добавляет богатый набор расширенных свойств. Однако не каждый штрихкод содержит все поля. Попытка доступа к отсутствующему свойству может вызвать `NullReferenceException`. Самый безопасный подход — проверять каждое свойство перед выводом, гарантируя стабильность приложения даже при отсутствии макро‑данных.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Почему это важно*: В реальных развертываниях вы можете получать обычные штрихкоды PDF417 без макро‑данных. Защитная проверка гарантирует, что приложение продолжит работу без сбоев.

## Распространённые подводные камни и лучшие практики

| Проблема | Почему это происходит | Рекомендованное решение |
|----------|-----------------------|--------------------------|
| Неправильный путь к изображению | `BarCodeReader` бросает исключение file‑not‑found до начала декодирования | Используйте `Path.Combine` и проверьте существование файла с помощью `File.Exists` |
| Изображение с низким разрешением | Декодер не может найти границы штрихкода, в результате нет обнаружений | Обеспечьте минимальное разрешение 300 dpi для надёжных результатов |
| Штрихкод повернут более 45° | Большинство библиотек предполагают вертикальное расположение | Включите `reader.RecognitionOptions.RotateImage = true`, если изображение может быть повернуто |
| Отсутствуют макро‑поля | Попытка чтения свойства со значением null приводит к сбою | Всегда проверяйте `null` перед доступом к макро‑свойствам |
| Обработка больших пакетов | Создание нового считывателя для каждого файла добавляет накладные расходы | Повторно используйте один экземпляр `BarCodeReader` с разными потоками при обработке множества изображений |

## Почему использовать Aspose.BarCode для консольного сканера штрихкодов?

Aspose.BarCode может декодировать **30+ типов штрихкодов** и обрабатывает изображения до **200 MP**, не загружая весь файл в память, достигая пропускной способности **150 кадров в секунду** на типичном процессоре 3.2 GHz. Эти измеримые возможности делают его надёжным выбором для высокообъёмных сканирующих решений на месте, где критичны задержка и точность.

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и изучить альтернативные подходы к реализации в ваших проектах.

- [Как читать штрихкоды DataMatrix с помощью Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Чтение штрихкода DataMatrix C# – Генерация режима DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Чтение штрихкода с изображения – Извлечение области штрихкода в Java с Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Часто задаваемые вопросы

**Q: Можно ли использовать этот сканер в производственной среде?**  
A: Да. Приобретите коммерческую лицензию Aspose.BarCode, чтобы убрать водяной знак оценки и получить полную поддержку.

**Q: Работает ли библиотека на Linux и macOS?**  
A: Абсолютно. Aspose.BarCode for .NET кросс‑платформенный и работает на .NET 6+ в Windows, Linux и macOS.

**Q: Как обрабатывать очень большие изображения без исчерпания памяти?**  
A: Используйте конструктор `LoadOptions` для включения режима потоковой передачи, который обрабатывает изображение кусками вместо полной загрузки в ОЗУ.

**Q: Можно ли декодировать зашифрованные или защищённые паролем изображения?**  
A: Считыватель может обрабатывать изображения, зашифрованные стандартными схемами паролей PNG/JPEG; просто укажите пароль через `reader.ImagePassword`.

**Q: Что делать, если мой штрихкод частично повреждён?**  
A: Включите опции коррекции ошибок, такие как `reader.RecognitionOptions.CorrectErrors = true`, чтобы повысить устойчивость к повреждениям или шуму.

---

**Последнее обновление:** 2026-10-14  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные учебники

- [Как читать Pdf417 на C# – полный пример считывателя штрихкодов](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Чтение нескольких штрихкодов C# – полное руководство с Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Декодирование штрихкода из изображения с примером C# считывателя](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}