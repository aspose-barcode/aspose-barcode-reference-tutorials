---
category: general
date: 2026-11-20
description: Узнайте, как быстро считывать макро‑PDF417 штрих‑код в C#. Это руководство
  покажет, как считывать штрих‑коды с изображения в C# с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read macro PDF417 barcode
- read barcodes from image C#
- Aspose.BarCode C#
- PDF417 extended data
- barcode decoding .NET
language: ru
lastmod: 2026-11-20
og_description: Считайте макро‑PDF417 штрих‑код в C# с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы считывать штрих‑коды с изображения в C# и извлекать полную
  информацию о макро‑PDF417.
og_image_alt: Screenshot showing a Macro PDF417 barcode being read in a C# console
  application
og_title: Чтение макро‑штрихкода PDF417 в C# – полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  headline: How to read macro PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  name: How to read macro PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
    text: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
  - name: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
    text: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
  - name: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
    text: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
  - name: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
    text: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- Aspose
title: Как считать макро‑PDF417 штрих‑код в C# с помощью Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать macro PDF417 barcode в C# с Aspose.BarCode

Если вам нужно **читать macro PDF417 barcode** в приложении .NET, этот учебник покажет вам полное готовое решение. Вы увидите, как **читать barcodes from image C#** с помощью библиотеки Aspose.BarCode, извлечь каждое расширенное поле Macro PDF417 и обработать распространённые граничные случаи.

В руководстве покрыты все необходимые темы: настройка проекта, разбор кода, советы по устранению неполадок и идеи для дальнейших шагов в более продвинутых сценариях.

## Что вам понадобится

- **.NET 6.0** или новее (код также работает с .NET Framework 4.6+)
- **Visual Studio 2022** (или любой IDE, поддерживающий .NET)
- Пакет NuGet **Aspose.BarCode for .NET** (бесплатная пробная версия или лицензированная)
- Файл изображения, содержащий Macro PDF417 barcode (например, `ExtPDF417Meta.png`)

> **Pro tip:** Если у вас нет образца изображения штрих‑кода, вы можете сгенерировать его с помощью класса `BarcodeGenerator` из Aspose.BarCode и установить `EncodeMode = EncodeMode.MacroPdf417`.

## Шаг 1: Установить Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последние DLL‑файлы Aspose.BarCode и обновит ваш файл `.csproj`. Дополнительные нативные зависимости не требуются.

## Шаг 2: Создать каркас консольного приложения

Создайте новый консольный проект (если у вас его ещё нет):

```bash
dotnet new console -n MacroPdf417Reader
cd MacroPdf417Reader
```

Замените сгенерированный `Program.cs` полным примером ниже. Код автономный и компилируется без изменений после установки пакета NuGet.

## Шаг 3: Полный пример кода – чтение macro PDF417 barcode

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace MacroPdf417Reader
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that holds the Macro PDF417 barcode.
            // Use an absolute path or place the image in the project folder and set
            // "Copy to Output Directory" = "Copy always" in Visual Studio.
            string imagePath = "ExtPDF417Meta.png";

            // Initialize the BarCodeReader for MacroPdf417 decoding.
            // DecodeType.MacroPdf417 tells the library to look for the extended
            // Macro PDF417 fields (FileID, SegmentID, FileName, etc.).
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Read all barcodes found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // The Extended property contains PDF417‑specific information.
                    var pdf417Info = result.Extended?.Pdf417;

                    if (pdf417Info != null)
                    {
                        Console.WriteLine($"Pdf417MacroFileID   : {pdf417Info.MacroPdf417FileID}");
                        Console.WriteLine($"Pdf417MacroSegmentID: {pdf417Info.MacroPdf417SegmentID}");
                        Console.WriteLine($"Pdf417MacroFileName : {pdf417Info.MacroPdf417FileName}");
                        Console.WriteLine($"Pdf417MacroFileSize : {pdf417Info.MacroPdf417FileSize}");
                        Console.WriteLine($"Pdf417MacroChecksum : {pdf417Info.MacroPdf417Checksum}");
                        // Add any other fields you need here.
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 information was found in this barcode.");
                    }
                }
            }

            Console.WriteLine("\nFinished reading macro PDF417 barcode.");
        }
    }
}
```

### Как работает код

1. **Конструктор `BarCodeReader`** – Передавая `DecodeType.MacroPdf417`, мы сообщаем Aspose.BarCode искать именно символы Macro PDF417 и заполнять объект `Extended.Pdf417`.
2. **`ReadBarCodes()`** – Возвращает коллекцию, так как изображение может содержать более одного штрих‑кода. Цикл обрабатывает каждый результат независимо.
3. **`result.Extended.Pdf417`** – Содержит расширенные поля, определённые спецификацией Macro PDF417:
   - `MacroPdf417FileID` – Идентификатор всего файла (полезно, когда данные разбиты на несколько символов).
   - `MacroPdf417SegmentID` – Индекс данного сегмента.
   - `MacroPdf417FileName` – Необязательное имя файла, встроенное в штрих‑код.
   - `MacroPdf417FileSize` – Общий размер исходного файла в байтах.
   - `MacroPdf417Checksum` – Значение контрольной суммы.
4. **Вывод в консоль** – Показывает каждое поле, упрощая проверку корректного чтения штрих‑кода.

> **Почему использовать `MacroPdf417` вместо обычного `Pdf417`?**  
> Macro PDF417 добавляет метаданные, позволяющие разбивать большие объёмы данных на несколько символов. Если декодировать только обычный `Pdf417`, эти дополнительные поля игнорируются, и вы теряете информацию, необходимую для восстановления оригинального файла.

## Шаг 4: Проверить вывод

Запустите программу:

```bash
dotnet run
```

Типичный вывод в консоль выглядит так:

```
Pdf417MacroFileID   : 12
Pdf417MacroSegmentID: 3
Pdf417MacroFileName : invoice_2026_11.pdf
Pdf417MacroFileSize : 45231
Pdf417MacroChecksum : 0x1A2B3C4D

Finished reading macro PDF417 barcode.
```

Если изображение не содержит символ Macro PDF417, программа выводит *«No Macro PDF417 information was found in this barcode.»*. Это сообщение помогает отличить неподдерживаемый штрих‑код от ошибки декодирования.

## Шаг 5: Распространённые подводные камни при **read barcodes from image C#**

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| `reader.ReadBarCodes()` возвращает пустую коллекцию | Неправильный путь к изображению или файл не скопирован в папку вывода. | Используйте абсолютный путь или установите свойство файла изображения **Copy to Output Directory** в **Copy always**. |
| `result.Extended.Pdf417` равно `null` | Штрих‑код не является символом Macro PDF417 (например, обычный PDF417 или другой формат). | Убедитесь, что штрих‑код был сгенерирован с `EncodeMode = EncodeMode.MacroPdf417`. |
| Декодирование не удаётся на изображениях низкого разрешения | Штрих‑код размытый или слишком маленький для настроек библиотеки по умолчанию. | Увеличьте разрешение изображения или включите `reader.Parameters.BarcodeReaderOptions`, такие как `AutoRotate` и настройки `Quality`. |
| Несоответствие контрольной суммы | Изображение было повреждено при передаче или сохранении. | Сгенерируйте штрих‑код заново или проверьте целостность исходного файла. |

Решение этих проблем на ранних этапах экономит время при **read barcodes from image C#** в производственных системах.

## Шаг 6: Расширенные параметры и дальнейшие шаги

- **Batch processing** – Оберните логику чтения в метод, принимающий путь к папке и автоматически обрабатывающий каждый файл PNG/JPG.
- **Asynchronous decoding** – Используйте `Task.Run` для декодирования больших пакетов без блокировки UI‑потока в настольных или веб‑приложениях.
- **Saving extracted data** – Запишите макрополя в JSON‑файл для последующей обработки:

  ```csharp
  var json = System.Text.Json.JsonSerializer.Serialize(pdf417Info);
  File.WriteAllText($"metadata_{pdf417Info.MacroPdf417SegmentID}.json", json);
  ```

- **Integration with other Aspose products** – Скомбинируйте декодированные данные с Aspose.PDF для восстановления оригинального документа из его макросегментов.

## Заключение

Теперь вы знаете, как **read macro PDF417 barcode** в C# с помощью Aspose.BarCode, и понимаете, как **read barcodes from image C#**, извлекая каждое расширенное поле Macro PDF417. Полный, готовый к запуску пример демонстрирует настройку проекта, выполнение кода и советы по устранению неполадок.

Отсюда вы можете исследовать пакетное декодирование, асинхронную обработку или интегрировать извлечённые метаданные с другими библиотеками работы с документами. Экспериментируйте с различным качеством изображений, многосегментными файлами и пользовательской обработкой ошибок, чтобы адаптировать решение под ваш конкретный случай.

--- 

*Готовы попробовать сами? Клонируйте репозиторий, замените `ExtPDF417Meta.png` своим изображением штрих‑кода и запустите программу. Если возникнут проблемы, таблица устранения неполадок выше подскажет, как действовать.*

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Чтение штрих‑кода из изображения C# – полное руководство с Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Как создать macro PDF417 barcode в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Как читать PDF417 barcode в C# с Aspose – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}