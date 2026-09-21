---
category: general
date: 2026-07-30
description: Как сгенерировать изображение штрихкода PDF417 в C# с помощью Aspose.
  Узнайте пошагово, как создать штрихкод с Aspose, установить метаданные MacroPDF417
  и сохранить в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode image c#
- create barcode with aspose
- Aspose.BarCode PDF417
- MacroPdf417 metadata
language: ru
lastmod: 2026-07-30
og_description: Как сгенерировать изображение штрихкода PDF417 в C# с помощью Aspose.
  Следуйте этому полному руководству, чтобы создать штрихкод с Aspose, настроить метаданные
  MacroPDF417 и вывести PNG‑файл.
og_image_alt: Screenshot showing a generated PDF417 barcode image created with Aspose
  in C#
og_title: Как сгенерировать изображение штрихкода PDF417 в C# с помощью Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate PDF417 barcode image in C# with Aspose. Learn step‑by‑step
    how to create barcode with Aspose, set MacroPDF417 metadata, and save as PNG.
  headline: How to Generate PDF417 Barcode Image in C# with Aspose
  type: TechArticle
tags:
- Aspose
- C#
- Barcode
title: Как сгенерировать изображение штрихкода PDF417 в C# с помощью Aspose
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать изображение штрихкода PDF417 в C# с помощью Aspose

Генерация изображения штрихкода PDF417 в C# с помощью Aspose часто представляет собой препятствие для тех, кто работает с кодированием данных высокой плотности. В этом руководстве мы пройдем каждый шаг — настройку генератора, настройку метаданных MacroPDF417 и, наконец, сохранение четкого PNG‑файла.

Если вы когда‑нибудь пытались **generate barcode image c#** и получали пустой холст или нечитаемый скан, вы не одиноки. Хорошая новость в том, что Aspose.BarCode делает весь процесс почти безболезненным, и к концу этой статьи вы сможете **create barcode with Aspose** для любого корпоративного рабочего процесса.

## Что вы узнаете

- Установить и добавить ссылку на библиотеку Aspose.BarCode для .NET.
- Инициализировать генератор PDF417 с пользовательским полезным нагрузкой.
- Применить специфические для MacroPDF417 поля, такие как file ID, segment ID и timestamp.
- Экспортировать результат в PNG‑изображение, которое можно встроить в отчёты или мобильные приложения.
- Советы по устранению распространённых проблем (например, неправильная ширина модуля, отсутствие сегментов).

## Предварительные требования

| Требование | Причина |
|-------------|--------|
| .NET 6.0 или новее | Текущая LTS‑версия, полностью поддерживаемая Aspose |
| Visual Studio 2022 (или любой IDE) | Для компиляции и запуска примера |
| Aspose.BarCode for .NET (NuGet) | Предоставляет `BarcodeGenerator` и поддержку PDF417 |

Библиотеку можно добавить через NuGet:

```bash
dotnet add package Aspose.BarCode
```

Теперь, когда основа готова, давайте погрузимся в код.

## Как сгенерировать изображение штрихкода PDF417 в C# — настройка

Первое, что мы делаем, — создаём экземпляр `BarcodeGenerator` для типа кодирования **MacroPdf417**. Этот объект содержит все параметры конфигурации, от размера модуля до богатых метаданных, которые ожидает MacroPDF417.

```csharp
using Aspose.BarCode.Generation;
using System;

// Step 1: Create the barcode generator with the desired payload.
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Payload"))
{
    // The rest of the configuration goes here.
}
```

> **Почему это важно:** `EncodeTypes.MacroPdf417` указывает Aspose создавать штрихкод PDF417, который может быть разбит на несколько сегментов — необходимая функция для больших файлов или пакетной обработки.

## Настройка базового внешнего вида

Читаемый штрихкод начинается с правильных визуальных настроек. `XDimension` управляет шириной каждого модуля (маленьких чёрных/белых квадратов), а `Columns` определяет количество колонок, которые охватывает штрихкод.

```csharp
// Step 2: Define basic barcode appearance.
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels.
generator.Parameters.Barcode.Pdf417.Columns = 5;    // Number of columns (adjust for size).
```

- **Подсказка:** Если штрихкод выглядит слишком плотным на принтере чеков, увеличьте `XDimension` до `3` или `4`.  
- **Подводный камень:** Установка слишком малого значения `Columns` может привести к выходу штрихкода за границы изображения, делая сканирование нечитаемым.

## Установка специфических метаданных MacroPDF417

MacroPDF417 позволяет внедрять информацию уровня файла непосредственно в штрихкод. Это идеально подходит для отслеживания больших поставок документов или разбивки файла на несколько сканов.

```csharp
// Step 3: Set MacroPDF417 specific metadata.
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 CRC
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Что делает каждое поле:**

| Свойство | Описание |
|----------|----------|
| `MacroPdf417FileID` | Уникальный идентификатор всего файла. |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (начинается с 0). |
| `MacroPdf417SegmentsCount` | Общее количество сегментов, на которые разбит файл. |
| `MacroPdf417FileName` | Читаемое человеком имя, полезное для журналов аудита. |
| `MacroPdf417Checksum` | 16‑битный CRC для проверки целостности данных. |
| `MacroPdf417FileSize` | Исходный размер файла в байтах, помогает получателям выделять буферы. |
| `MacroPdf417TimeStamp` | Дата/время генерации файла. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Необязательные строки для идентификации получателя/отправителя. |
| `MacroPdf417Terminator` | Помечает последний сегмент; требуется для корректного декодирования. |

> **Зачем это нужно?** Без этих полей сканер может прочитать только сырые данные, без контекста. Добавление метаданных позволяет принимающей системе автоматически собрать оригинальный файл.

## Save the Barcode as PNG

Once the generator is fully configured, persisting the image is a one‑liner:

```csharp
// Step 4: Save the generated barcode image.
generator.Save("YOUR_DIRECTORY/MacroPdf417Meta.png", BarCodeImageFormat.Png);
```

- **Формат файла:** PNG — без потерь, гарантирует, что каждый модуль остаётся чётким для сканеров.  
- **Альтернатива:** Используйте `BarCodeImageFormat.Jpeg`, если нужен меньший размер файла, но ожидайте небольшое снижение читаемости.

### Ожидаемый результат

После выполнения фрагмента кода вы найдёте `MacroPdf417Meta.png` в указанной папке. Он должен выглядеть аналогично иллюстрации ниже:

![Штрихкод PDF417, сгенерированный с помощью Aspose](path/to/your/image.png){alt="Как сгенерировать изображение штрихкода PDF417 в C#"}

Изображение содержит плотную сетку чёрных и белых квадратов, в которой закодирована полезная нагрузка и внедрены метаданные MacroPDF417.

## Полный рабочий пример

Ниже представлен полный готовый к копированию пример программы. Он компилируется в любом проекте .NET 6+ и требует только пакет NuGet Aspose.BarCode.



## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрихкод — Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрихкоды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Как генерировать штрихкод Aztec с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}