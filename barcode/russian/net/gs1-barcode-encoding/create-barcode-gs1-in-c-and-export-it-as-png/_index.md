---
category: general
date: 2026-09-29
description: Создайте штрих‑код GS1 на C# и генерируйте PNG‑изображения штрих‑кода
  с помощью BarcodeGenerator. Следуйте пошаговому руководству, чтобы эффективно экспортировать
  изображение штрих‑кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: ru
lastmod: 2026-09-29
og_description: Создайте штрих‑код GS1 на C# и генерируйте PNG‑файлы штрих‑кода с
  помощью BarcodeGenerator. Следуйте этому полному руководству, чтобы быстро экспортировать
  изображение штрих‑кода.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Создайте штрих‑код GS1 в C# – экспорт в PNG за несколько минут
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Создать штрих‑код GS1 на C# и экспортировать его в PNG
url: /ru/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать штрих-код GS1 в C# и экспортировать его как PNG

Если вам нужно **создать штрих-код GS1** в .NET‑приложении, это руководство покажет, как это сделать. Вы увидите лаконичное решение, которое генерирует PNG‑изображение штрих‑кода и экспортирует его на диск, используя класс Aspose.BarCode `BarcodeGenerator`.

Создание штрих‑кода GS1 является распространённой задачей для систем учёта, доставки и точек продаж. К концу этого руководства вы сможете написать небольшую программу на C#, которая создаёт совместимый с GS1 штрих‑код MicroPDF417 и сохраняет его в виде PNG‑файла высокого качества.

## Требования

* **.NET 6** (или более поздняя версия .NET) установлен.
* **Visual Studio 2022** или любая IDE, поддерживающая C#.
* Пакет NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – он предоставляет API `BarcodeGenerator`, используемый в примерах.
* Базовое знакомство с синтаксисом C#.

> **Совет:** Используйте бесплатную community‑edition Aspose.BarCode для экспериментов; полная версия удаляет любые водяные знаки оценки.

## Шаг 1 – Создать штрих‑код GS1 с помощью BarcodeGenerator

Первое, что нужно сделать, — создать экземпляр `BarcodeGenerator` для формата *MicroPDF417* и передать ему строку данных GS1. Идентификаторы приложений GS1 (AI) заключаются в круглые скобки, например `(01)` для GTIN‑14 и `(21)` для серийного номера.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Почему это важно:**  
`EncodeTypes.MicroPdf417` автоматически рассматривает ввод как данные GS1, если строка содержит корректные AI. Это гарантирует, что сгенерированный штрих‑код соответствует спецификации GS1 без дополнительной настройки.

## Шаг 2 – Установить размеры штрих‑кода для оптимального размера

Визуальный размер штрих‑кода контролируется его **X‑размером** (ширина одного модуля). Регулировка `XDimension.Pixels` позволяет точно настроить конечный размер изображения, сохраняя читаемость.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Как сгенерировать PNG‑штрих‑код** – X‑размер не влияет на закодированные данные; он меняет только физические размеры сгенерированного изображения. Если нужен более крупный штрих‑код для печати с высоким разрешением, увеличьте это значение (например, `3` или `4`).

## Шаг 3 – Сгенерировать PNG‑штрих‑код и экспортировать изображение штрих‑кода

Теперь вы можете отрисовать штрих‑код и записать его в PNG‑файл. Метод `Save` принимает путь назначения и желаемый формат изображения.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Что происходит под капотом:**  
`BarcodeGenerator.Save` растеризует штрих‑код в bitmap, применяет установленный ранее X‑размер и кодирует bitmap в PNG‑файл. Полученный файл можно использовать напрямую в веб‑страницах, печатать на этикетках или встраивать в PDF‑документы.

## Полный пример исходного кода

Ниже представлено полное, автономное консольное приложение, которое вы можете скопировать, вставить и запустить. Оно демонстрирует **как генерировать PNG‑файлы штрих‑кода**, **экспортировать изображение штрих‑кода**, и включает базовую обработку ошибок.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Ожидаемый вывод

При запуске программы вы должны увидеть:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Открытие PNG‑файла показывает чёткий штрих‑код **GS1 MicroPDF417**, который кодирует GTIN‑14 `12345678901234` и серийный номер `ABC123`. Сканирование его любым совместимым с GS1 сканером вернёт исходную строку данных.

## Распространённые ошибки и лучшие практики

| Проблема | Почему происходит | Как избежать |
|----------|-------------------|--------------|
| **Неправильное форматирование AI** | Отсутствие скобок или неправильный порядок делает штрих‑код не‑GS1. | Всегда заключайте каждый AI в скобки, например, `(01)`. |
| **Слишком маленький X‑размер** | Штрих‑код становится нечитаемым на устройствах с низким разрешением. | Сохраняйте `XDimension.Pixels` ≥ 2 для большинства принтеров; увеличивайте для вывода с высоким DPI. |
| **Папка вывода не существует** | `Save` генерирует `DirectoryNotFoundException`. | Вызовите `Directory.CreateDirectory` перед вызовом `Save`. |
| **Использование неправильного EncodeType** | Некоторые типы (например, `Code128`) не поддерживают данные GS1 из коробки. | Выбирайте `EncodeTypes.MicroPdf417` или любой совместимый с GS1 тип. |
| **Отсутствует ссылка NuGet** | Ошибки компиляции, например `The type or namespace name 'Aspose' could not be found`. | Установите пакет `Aspose.BarCode` через NuGet. |

## Расширение примера

* **Разные форматы изображений** – замените `BarCodeImageFormat.Png` на `Jpeg`, `Gif` или `Bmp`, если нужен другой формат.
* **Вывод с более высоким разрешением** – задайте `generator.Parameters.ImageResolution.DpiX` и `DpiY` перед сохранением.
* **Встраивание в PDF** – используйте `Aspose.Pdf`, чтобы разместить PNG в PDF‑счете или этикетке.

## Заключение

Теперь вы знаете, как **создать штрих‑код GS1** в C# с помощью Aspose.BarCode `BarcodeGenerator`, **генерировать PNG‑штрих‑код** и **экспортировать изображение штрих‑кода** в файловую систему. Руководство охватило каждый шаг — от инициализации генератора данными GS1, настройки X‑размера до сохранения финального PNG‑файла — при этом рассмотрены распространённые ошибки и предложены идеи для расширения.

Не стесняйтесь экспериментировать с другими идентификаторами приложений GS1, различными символьными системами штрих‑кодов или изображениями более высокого разрешения. Когда вы освоите эти основы, генерация соответствующих штрих‑кодов для учёта, доставки или розничной торговли станет рутинной частью вашего .NET‑инструментария.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в своих проектах.

- [Создать изображения штрих‑кода GS1 в C# – Как быстро генерировать штрих‑код C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Создать PNG‑штрих‑код в C# – пошаговое руководство](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Создать изображение штрих‑кода в C# – полное программное руководство](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}