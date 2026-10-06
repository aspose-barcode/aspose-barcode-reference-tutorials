---
category: general
date: 2026-10-05
description: Считывание штрихкода с изображения в C# с использованием Aspose.BarCode.
  Изучите пошаговое сканирование штрихкодов в C#, декодирование Macro PDF417 и работу
  с расширенными свойствами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- C# barcode scanning
- Macro PDF417 decoding
- Aspose.BarCode for .NET
- decode barcode image C#
language: ru
lastmod: 2026-10-05
og_description: Считайте штрих‑код с изображения на C# с помощью Aspose.BarCode. Этот
  учебник показывает, как сканировать штрих‑код Macro PDF417, извлекать расширенные
  поля и обрабатывать несколько кодов.
og_image_alt: Screenshot of C# console output showing barcode type and Macro PDF417
  properties
og_title: Считывание штрихкода с изображения C# – полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Read barcode from image C# using Aspose.BarCode. Learn step‑by‑step
    C# barcode scanning, decode Macro PDF417 and handle extended properties.
  headline: Read barcode from image C# – complete guide with Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- image-processing
title: Считывание штрихкода с изображения на C# – полное руководство с Macro PDF417
url: /ru/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Считывание штрих‑кода с изображения C# – полное руководство с Macro PDF417

Если вам нужно **считать штрих‑код с изображения C#**, это руководство покажет готовое решение. С помощью библиотеки Aspose.BarCode for .NET вы сможете декодировать штрих‑код Macro PDF417, извлечь его базовые данные и получить все расширенные свойства, которые предоставляет формат.

Считывание штрих‑кодов с изображений — частая задача, будь то система проверки билетов, обработка транспортных этикеток или извлечение метаданных из отсканированных документов. В следующих шагах мы объясним, почему класс `BarCodeReader` является рекомендованным подходом, как настроить его для Macro PDF417 и что делать с полученными результатами.

---

## Что вы узнаете

* Установить и подключить **Aspose.BarCode for .NET** (библиотека, используемая в примере).  
* Создать `BarCodeReader`, сконфигурированный для **декодирования Macro PDF417**.  
* Перебрать все штрих‑коды на изображении и вывести как стандартные, так и расширенные поля.  
* Обрабатывать несколько штрих‑кодов, правильно управлять ресурсами и устранять типичные проблемы.

**Предварительные требования**

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.6+).  
* Базовые знания C# консольных приложений.  
* Файл изображения, содержащий штрих‑код Macro PDF417 (например, `ExtPDF417Meta.png`).  

---

## Шаг 1: Добавьте Aspose.BarCode в ваш проект (сканирование штрих‑кода C#)

1. Откройте терминал в папке решения.  
2. Выполните команду NuGet:

```bash
dotnet add package Aspose.BarCode
```

Пакет содержит класс `BarCodeReader`, перечисление `DecodeType` и объект `BarCodeResult`, используемые в этом руководстве.

> **Pro tip:** Если вы нацелены на .NET Framework, используйте консоль диспетчера пакетов в Visual Studio:  
> `Install-Package Aspose.BarCode`

---

## Шаг 2: Настройте консольное приложение (декодирование изображения штрих‑кода C#)

Создайте новый консольный проект (или добавьте код в существующий):

```csharp
using System;
using Aspose.BarCode;               // Core namespace
using Aspose.BarCode.BarCodeRecognition; // For DecodeType and BarCodeReader

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains a Macro PDF417 barcode.
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 2.1: Initialise the BarCodeReader for Macro PDF417.
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath, DecodeType.MacroPdf417))
            {
                // Step 2.2: Read every barcode present in the image.
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // Step 2.3: Output basic information.
                    Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                    // Step 2.4: Output Macro PDF417 extended properties.
                    PrintMacroPdf417Properties(barcodeResult);
                }
            }

            // Keep console window open for inspection.
            Console.WriteLine("\nPress any key to exit...");
            Console.ReadKey();
        }

        /// <summary>
        /// Writes all Macro PDF417 extended fields to the console.
        /// </summary>
        /// <param name="result">Result object returned by BarCodeReader.</param>
        private static void PrintMacroPdf417Properties(BarCodeResult result)
        {
            // The Extended property is null if the barcode type does not support it.
            if (result?.Extended?.Pdf417 == null)
            {
                Console.WriteLine("No Macro PDF417 extended data available.");
                return;
            }

            var macro = result.Extended.Pdf417;
            Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
            Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
            Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
            Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
            Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
            Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
            Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
            Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
            Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
            Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
        }
    }
}
```

### Почему такая структура?

* **`using`‑оператор** – гарантирует освобождение нативных ресурсов `BarCodeReader` (это важно для больших изображений).  
* **`DecodeType.MacroPdf417`** – указывает библиотеке искать именно Macro PDF417; другие типы (например, QR, Code128) игнорируют расширенные поля.  
* **`ReadBarCodes()`** – возвращает перечисление, позволяя обрабатывать **несколько штрих‑кодов** в одном изображении без дополнительного кода.  
* **Отдельный метод `PrintMacroPdf417Properties`** – изолирует логику работы с расширенными полями, упрощая основной цикл и будущую поддержку.

---

## Шаг 3: Запустите программу и проверьте вывод (декодирование Macro PDF417)

Откройте командную строку, перейдите в папку проекта и выполните:

```bash
dotnet run
```

Вы должны увидеть вывод, похожий на следующий (значения будут отличаться в зависимости от конкретного штрих‑кода):

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B3C4D
Pdf417MacroFileSize: 1048576
Pdf417MacroTimeStamp: 2023-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True

Press any key to exit...
```

Если изображение не содержит штрих‑код Macro PDF417, консоль выведет **«No Macro PDF417 extended data available.»** Такое обработка предотвращает исключения null‑reference.

---

## Шаг 4: Распространённые варианты и граничные случаи (советы по сканированию штрих‑кодов C#)

| Ситуация | Рекомендуемая настройка |
|-----------|------------------------|
| **Несколько типов штрих‑кодов в одном изображении** | Инициализировать ридер с `DecodeType.AllSupported` и проверять `barcodeResult.CodeTypeName`, чтобы выбрать нужную логику. |
| **Большие изображения (≥10 MP)** | Увеличить `barcodeReader.Options.MaxBarCodeCount` или вызвать `barcodeReader.SetResolution(300)` для ускорения обнаружения. |
| **Отсутствуют расширенные поля** | Некоторые сканеры отбрасывают Macro‑данные; проверьте исходное изображение с помощью инструмента инспекции штрих‑кодов перед кодированием. |
| **Запуск на Linux/macOS** | Убедитесь, что нативные бинарники Aspose.BarCode присутствуют (пакет `Aspose.BarCode.Native`), либо задайте `Environment.SetEnvironmentVariable("DOTNET_SYSTEM_GLOBALIZATION_INVARIANT", "1")`, если нужны только ASCII‑данные. |
| **Циклы с критичными требованиями к производительности** | Кешировать экземпляр `BarCodeReader` и переиспользовать его для пакета изображений; освобождать только после завершения пакета. |

---

## Шаг 5: Итоги и дальнейшие шаги (считывание штрих‑кода с изображения C#)

Теперь у вас есть **полное, автономное решение** для чтения штрих‑кода Macro PDF417 с изображения в C#. Пример демонстрирует:

* Правильную **установку** библиотеки Aspose.BarCode.  
* Создание **`BarCodeReader`**, настроенного на **Macro PDF417**.  
* Перебор **всех штрих‑кодов** в предоставленном изображении.  
* Извлечение **стандартных** (`CodeTypeName`, `CodeText`) **и расширенных** метаданных Macro PDF417.  

### Что изучать дальше?

* **Декодировать другие форматы** – замените `DecodeType.MacroPdf417` на `DecodeType.QR`, `DecodeType.Code128` и т.д.  
* **Интеграция с ASP.NET Core** – создайте Web API, принимающий загрузку изображений и возвращающий JSON с данными штрих‑кода.  
* **Сохранение результатов** – сохраняйте извлечённые метаданные в базе данных для последующего анализа.  
* **Комбинация с OCR** – используйте Aspose.OCR для чтения текста, не закодированного в штрих‑коде.

Экспериментируйте с примерным изображением, меняйте путь к файлу или внедряйте логику в более крупное приложение. Класс **`BarCodeReader`** предоставляет надёжную основу для любой **C# задачи сканирования штрих‑кодов**.

--- 

*Удачной разработки! Если возникнут проблемы, проверьте, действительно ли изображение содержит штрих‑код Macro PDF417 и соответствует ли версия Aspose.BarCode вашей среде .NET.*


## Что изучать дальше?


В следующих руководствах рассматриваются тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Read barcode from image in C# – BarCodeReader tutorial](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}