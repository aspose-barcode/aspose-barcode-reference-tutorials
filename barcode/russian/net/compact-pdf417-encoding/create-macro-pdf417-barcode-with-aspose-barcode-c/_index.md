---
category: general
date: 2026-09-22
description: Создайте макро‑штрих‑код PDF417 с помощью Aspose.BarCode в C#. Узнайте
  пошагово, как генерировать штрих‑код с Aspose, настраивать метаданные и сохранять
  его в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: ru
lastmod: 2026-09-22
og_description: Создайте макро‑штрихкод PDF417 с помощью Aspose.BarCode в C#. Это
  руководство показывает, как сгенерировать штрихкод с Aspose, установить метаданные
  макроса и экспортировать изображение.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Создание макро‑штрихкода PDF417 с помощью Aspose.BarCode (C#) – пошаговое
  руководство
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Создание макро‑PDF417 штрихкода с Aspose.BarCode (C#)
url: /ru/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание макро‑PDF417 штрих‑кода с Aspose.BarCode (C#)

Если вам нужно **создать макро‑PDF417 штрих‑код** в .NET‑приложении, этот учебник покажет, как сделать это с помощью Aspose.BarCode. Вы увидите полностью готовый, исполняемый пример, который **генерирует штрих‑код с Aspose**, настраивает все макро‑специфичные поля и сохраняет результат в виде PNG‑изображения.

Штрих‑коды часто используются для учёта, доставки или отслеживания документов, а вариант Macro PDF417 позволяет внедрять дополнительныe метаданные уровня файла непосредственно в штрих‑код. К концу этого руководства вы сможете генерировать полностью функциональный макро‑PDF417 штрих‑код, соответствующий стандарту ISO/IEC 15438.

## Что понадобится

* .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
* Visual Studio 2022 (или любой IDE для C#)
* Интернет‑соединение, совместимое с NuGet, для загрузки пакета Aspose.BarCode
* Базовые знания синтаксиса C#

Эти предварительные условия гарантируют, что код компилируется без дополнительной настройки.

## Шаг 1: Установите пакет Aspose.BarCode NuGet

Библиотека Aspose.BarCode предоставляет класс `BarcodeGenerator`, используемый на протяжении всего учебника.

```bash
dotnet add package Aspose.BarCode
```

Выполнение команды добавит последнюю стабильную версию в файл проекта (`*.csproj`). Пакет включает поддержку PDF417, Macro PDF417 и многих других символогий.

## Шаг 2: Создайте новый консольный проект (по желанию)

Если вы предпочитаете чистый старт, создайте консольное приложение:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Сгенерированный `Program.cs` будет содержать код генерации штрих‑кода.

## Шаг 3: Инициализируйте генератор штрих‑кода

Генератор создаётся с использованием значения перечисления `EncodeTypes.MacroPdf417` и текста, который вы хотите закодировать. Aspose.BarCode автоматически обрабатывает Unicode‑символы, поэтому вы можете напрямую включать буквы с диакритическими знаками или символы.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Почему это важно

`EncodeTypes.MacroPdf417` указывает библиотеке использовать макроверсию PDF417, что добавляет возможность внедрять метаданные уровня файла (ID файла, количество сегментов и т.д.). Текст `"Åspóse.Barcóde©"` демонстрирует, что генератор правильно кодирует UTF‑8 символы.

## Шаг 4: Установите базовые размеры штрих‑кода

PDF417 позволяет управлять количеством колонок и X‑размером (шириной отдельного модуля). Настройка этих параметров влияет на физический размер штрих‑кода и надёжность сканирования.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Меньшие значения дают более плотный штрих‑код; большие значения упрощают считывание сканерами с низким разрешением.
* **Columns** – Управляет количеством колонок данных; типичные значения от 1 до 30.

## Шаг 5: Настройте метаданные Macro PDF417

Macro PDF417 содержит дополнительные поля, описывающие файл, который представляет штрих‑код. Каждое поле необязательно, но их заполнение улучшает совместимость со сканерами, поддерживающими макро‑формат.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Описание каждого поля

| Property | Purpose | Typical range |
|----------|---------|---------------|
| **MacroPdf417FileID** | Уникальный идентификатор логического файла, который может быть разбит на несколько штрих‑кодов. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Индекс текущего сегмента (начинается с 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Общее количество сегментов, составляющих полный файл. | 1‑99 |
| **MacroPdf417FileName** | Читаемое человеком имя файла. | До 255 символов |
| **MacroPdf417Checksum** | Необязательная контрольная сумма для обнаружения ошибок. | 0‑65535 |
| **MacroPdf417FileSize** | Размер исходного файла в байтах. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Метка времени создания или изменения файла. | Любой `DateTime` |
| **MacroPdf417Addressee** | Идентификатор получателя (например, отдел или устройство). | Произвольная строка |
| **MacroPdf417Sender** | Идентификатор отправителя (например, название компании). | Произвольная строка |
| **MacroPdf417Terminator** | Указывает, является ли этот сегмент последним. | `Set` или `Unset` |

**Совет:** Если вы разбиваете большой файл на несколько штрих‑кодов, убедитесь, что `SegmentID` каждого сегмента последовательный и что `SegmentsCount` остаётся одинаковым для всех сегментов. Сканеры используют эти значения для восстановления оригинального файла.

## Шаг 6: Сохраните изображение штрих‑кода

Aspose.BarCode поддерживает множество форматов вывода (PNG, JPEG, BMP, SVG и др.). PNG обеспечивает без потерь качество, что идеально подходит для тестирования и документации.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Запуск программы создаст файл с именем `ExtPDF417Meta.png` в выходном каталоге проекта (`bin/Debug/net6.0/`). Откройте изображение в любом просмотрщике, чтобы убедиться, что штрих‑код отрисован корректно.

## Шаг 7: Проверьте сгенерированный штрих‑код (по желанию)

Если у вас есть приложение‑сканер PDF417 (мобильное или настольное), отсканируйте сохранённый PNG. Сканер должен вернуть:

* Закодированный текст `"Åspóse.Barcóde©"`
* Все макро‑поля, которые вы настроили (ID файла, ID сегмента и т.д.)

Для автоматической проверки Aspose.BarCode также предоставляет класс `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Этот фрагмент демонстрирует, как программно считать обратно макро‑метаданные, подтверждая, что **генерация штрих‑кода с Aspose** работает от начала до конца.

## Пограничные случаи и лучшие практики

| Situation | Recommended handling |
|-----------|----------------------|
| **Unicode‑символы** | Убедитесь, что исходная строка в UTF‑8 (по умолчанию в .NET). Aspose.BarCode автоматически кодирует Unicode, но проверьте набор символов сканера. |
| **Большой размер файла** | Macro PDF417 разбивает файлы на до 99 сегментов. Если файл превышает 400 KB, увеличьте `SegmentsCount` и создайте несколько штрих‑кодов, каждый с последовательным `SegmentID`. |
| **Точность метки времени** | Используйте `DateTime.UtcNow` для универсального времени; некоторые сканеры ожидают UTC. |
| **Проверка контрольной суммы** | Укажите корректную контрольную сумму, если планируете проверять целостность на стороне получателя. |
| **Разные форматы изображений** | Используйте `BarCodeImageFormat.Svg` для векторной графики, когда нужны бесконечно масштабируемые штрих‑коды. |
| **Производительность** | Повторно используйте один экземпляр `BarcodeGenerator` при генерации множества штрих‑кодов; меняйте только `Parameters` между итерациями. |

## Полный, исполняемый пример

Ниже приведена полная программа, которую вы можете скопировать, вставить и запустить без изменений (при условии, что пакет NuGet установлен).



## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Пример штрих‑кода Aspose: генерация Macro PDF417 на C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Создание метаданных PDF417 штрих‑кода в C# – Полное пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Как сгенерировать изображение PDF417 штрих‑кода в C# с помощью Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}