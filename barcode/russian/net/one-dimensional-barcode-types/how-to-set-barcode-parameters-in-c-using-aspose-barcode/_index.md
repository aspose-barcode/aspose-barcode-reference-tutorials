---
category: general
date: 2026-09-10
description: Как задать свойства штрихкода в C# с помощью Aspose.BarCode — также посмотрите,
  как создавать штрихкоды и техники генерации штрихкодов на C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to create barcode
- c# barcode generation
language: ru
lastmod: 2026-09-10
og_description: Как задать свойства штрихкода в C# с помощью Aspose.BarCode. Узнайте,
  как создать штрихкод, настроить размеры и генерировать PNG‑изображения для ваших
  приложений.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Как установить параметры штрих‑кода в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode properties in C# with Aspose.BarCode – also see
    how to create barcode and master c# barcode generation techniques.
  headline: How to set barcode parameters in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- csharp
- Aspose
title: Как задать параметры штрихкода в C# с помощью Aspose.BarCode
url: /ru/net/one-dimensional-barcode-types/how-to-set-barcode-parameters-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как задать параметры штрих‑кода в C# с помощью Aspose.BarCode

Если вам нужно **как задать параметры штрих‑кода** в проекте C#, это руководство покажет полный процесс. Вы узнаете, как создать штрих‑код, настроить X‑размер, выбрать количество колонок и сохранить результат в PNG‑файл — всё в одном работающем примере.

Программная генерация штрих‑кодов устраняет ручные шаги и гарантирует одинаковый результат в разных средах. К концу этого урока вы сможете интегрировать генерацию штрих‑кодов в системы выставления счетов, учётные системы или любые .NET‑приложения, требующие машинно‑читаемых данных.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* Действующая лицензия **Aspose.BarCode for .NET** (бесплатная trial‑версия подходит для разработки)  

Также необходимо добавить ссылку на пакет `Aspose.BarCode` через NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создать генератор штрих‑кода — как создать штрих‑код

Первым делом нужно создать объект `BarcodeGenerator` с нужной символьной системой и данными. В примере используется **MicroPdf417**, компактный 2‑D формат, подходящий для небольших этикеток.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a MicroPdf417 barcode generator with the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,      // symbology
    "Micro data");                // data to encode
```

*Почему это важно*: Выбор правильного `EncodeTypes` сообщает библиотеке, какие правила кодирования применять. `MicroPdf417` ограничивает размер штрих‑кода, сохраняя коррекцию ошибок.

## Шаг 2: Задать X‑размер — как задать штрих‑код

X‑размер определяет ширину одного модуля (самого маленького чёрного или белого квадрата). Изменение этого значения напрямую влияет на общий размер изображения и его сканируемость.

```csharp
// Step 2: Set the X‑dimension (module width) of the barcode in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Почему это важно*: Большой X‑размер делает штрих‑код более надёжным, его могут считывать с большего расстояния, но при этом увеличивается площадь изображения. Значение `2` пикселя — сбалансированный вариант для отображения на экране.

## Шаг 3: Выбрать количество колонок — как задать штрих‑код

MicroPdf417 поддерживает 1‑4 колонки. Большее количество колонок сжимает штрих‑код по вертикали, что удобно для узких этикеток.

```csharp
// Step 3: Specify the number of columns (1‑4 are allowed for MicroPdf417)
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Почему это важно*: Количество колонок меняет соотношение сторон штрих‑кода. Выбор максимального значения `4` колонок уменьшает высоту, сохраняя читаемость.

## Шаг 4: Сохранить изображение — генерация штрих‑кода в C#

Наконец, записываем штрих‑код в файл. Формат `BarCodeImageFormat.Png` сохраняет изображение без потери качества, что идеально подходит для дальнейшей обработки.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Ожидаемый результат** — файл `MicroPdf417.png` появится на рабочем столе. При открытии вы увидите компактный штрих‑код MicroPdf417, кодирующий строку «Micro data».

## Полный рабочий пример — генерация штрих‑кода в C#

Объединив все шаги, получаем самостоятельную программу, которую можно скопировать, вставить и запустить:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with MicroPdf417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Micro data");

        // 2. Set module width (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3. Choose 4 columns for a compact layout
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4. Define output path and save as PNG
        string filePath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode generated and saved to: {filePath}");
    }
}
```

Запустите программу командой `dotnet run`. Если в консоли отобразится путь к файлу без ошибок, генерация прошла успешно.

## Распространённые ошибки при **как задать параметры штрих‑кода**

| Проблема | Причина | Решение |
|----------|---------|---------|
| Изображение выглядит размытым | X‑размер слишком мал для требуемого размера | Увеличьте `XDimension.Pixels` до 3 или 4 |
| Штрих‑код не читается сканером | Количество колонок не соответствует длине данных | Уменьшите `Pdf417.Columns` или сократите кодируемый текст |
| Исключение времени выполнения `License not found` | Отсутствует лицензия Aspose в продакшене | Загрузите действующий файл лицензии: `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` |
| PNG‑файл не создан | Папка вывода не существует или нет прав записи | Убедитесь, что каталог существует и приложение имеет достаточные привилегии |

Раннее устранение этих проблем экономит время отладки, особенно при интеграции генерации штрих‑кодов в автоматизированные конвейеры.

## Расширение примера — как создать штрих‑код другого типа

Та же схема работает для любой поддерживаемой символьной системы. Чтобы сгенерировать QR‑code вместо MicroPdf417, замените значение `EncodeTypes`:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR,               // change symbology
    "https://example.com");       // data to encode
qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
```

Также можно настроить уровни коррекции ошибок, цвета и отступы через объект `Parameters`. Документация Aspose.BarCode API перечисляет все настраиваемые свойства.

## Соображения по производительности при генерации штрих‑кодов в C#

* **Пакетная обработка** — переиспользуйте один экземпляр `BarcodeGenerator` при создании множества штрих‑кодов; меняйте только свойство `CodeText` между сохранениями.  
* **Параллелизм** — библиотека потокобезопасна для независимых объектов‑генераторов, поэтому можно генерировать штрих‑коды в нескольких потоках для ускорения больших задач.  
* **Потребление памяти** — PNG‑файлы записываются напрямую на диск, минимизируя выделение кучи. Для сценариев в памяти используйте `MemoryStream` вместо пути к файлу.

## Заключение

Теперь вы знаете **как задать параметры штрих‑кода**: размеры, количество колонок и формат вывода в C#. Полное решение демонстрирует **как создать штрих‑код** с помощью Aspose.BarCode, охватывая каждый шаг от создания объекта до сохранения PNG‑изображения. С этой базой вы сможете генерировать любой поддерживаемый тип штрих‑кода, настраивать его внешний вид и интегрировать процесс в более крупные .NET‑приложения.

**Следующие шаги**  

* Изучите другие символьные системы, такие как `EncodeTypes.Code128` или `EncodeTypes.DataMatrix` (вторичное ключевое слово: *c# barcode generation*).  
* Добавьте пользовательские цвета, задав `generator.Parameters.Barcode.Color` и `BackgroundColor`.  
* Вставьте сгенерированный PNG в PDF‑отчёты с помощью Aspose.PDF или iTextSharp.

Экспериментируйте с различными X‑размерами, количеством колонок и объёмом данных. Генерация штрих‑кодов — мощный инструмент: освоив базовый **как задать параметры штрих‑кода**, вы легко сможете расширять его под любые бизнес‑требования. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}