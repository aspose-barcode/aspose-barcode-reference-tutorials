---
category: general
date: 2026-08-25
description: Создайте штрих‑код RM4SCC на C# с пошаговым кодом и узнайте, как задать
  высоту штрих‑кода для точного размера.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: ru
lastmod: 2026-08-25
og_description: Создайте штрих‑код RM4SCC на C# с помощью Aspose.BarCode и узнайте,
  как установить высоту штрих‑кода для точного контроля в ваших .NET‑приложениях.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Создание штрих‑кода RM4SCC на C# – руководство по настройке высоты штрих‑кода
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Создать штрих‑код RM4SCC в C# и задать высоту штрих‑кода
url: /ru/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода RM4SCC на C# и установка высоты штрих‑кода

Создайте штрих‑код RM4SCC на C# быстро с помощью библиотеки Aspose.BarCode. В этом руководстве показано, **как установить высоту штрих‑кода** и настроить другие визуальные свойства, чтобы штрих‑код точно вписывался в ваш макет.

Вы увидите полностью готовую консольную программу, которая генерирует три PNG‑файла:

* штрих‑код Planet стандартной высоты (для сравнения)  
* штрих‑код RM4SCC с вручную заданной высотой 100 px  
* штрих‑код Planet с пустыми (не заполненными) полосами  

Пример предполагает наличие Visual Studio 2022 (или любой IDE для .NET 6+) и действующей лицензии Aspose.BarCode for .NET или оценочной копии.

## Требования

| Требование | Причина |
|-------------|--------|
| .NET 6 SDK (или новее) | Предоставляет среду выполнения для консольного приложения |
| Aspose.BarCode for .NET пакет NuGet | Содержит `BarcodeGenerator`, `EncodeTypes` и API экспорта изображений |
| Базовые знания C# | Необходимы для понимания потока кода |

Установите пакет NuGet с помощью:

```bash
dotnet add package Aspose.BarCode
```

> **Полезный совет:** Если запустить код без лицензии, сгенерированные изображения будут содержать небольшую водяную метку Aspose.

## Шаг 1: Настройка структуры проекта

Создайте новый консольный проект и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Операторы `using` дают доступ к классам генератора штрих‑кодов и перечислению форматов PNG.

## Шаг 2: Определите папку вывода

Выберите папку, в которой будут сохраняться PNG‑файлы. Папка должна существовать до вызова `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Создание директории программно избавляет от *FileNotFoundException* при запуске кода на новой машине.

## Шаг 3: Сгенерировать штрих‑код Planet со стандартной высотой (базовая линия)

Штрих‑код Planet не является основной темой данного руководства, но он предоставляет визуальную базовую линию для сравнения с вручную масштабированным штрих‑кодом RM4SCC.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Почему это важно:*  
`XDimension` определяет ширину отдельной полосы. При постоянном значении `XDimension` и изменении `BarHeight` можно изолировать влияние высоты.

## Шаг 4: **Создание штрих‑кода RM4SCC C#** – установка ручной высоты

Теперь решаем основную задачу: **создать штрих‑код RM4SCC C#** и явно управлять его высотой.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Как установить высоту штрих‑кода

Свойство `BarHeight` находится в `Parameters.Barcode`. Оно принимает значение `float`, выраженное в **пикселях**, **точках** или **миллиметрах** в зависимости от выбранной единицы измерения (`Pixels`, `Points`, `Millimeters`). В примере используется `Pixels`, потому что формат вывода — PNG.

Если нужна высота в миллиметрах, сначала переключите единицу измерения:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Шаг 5: Сгенерировать штрих‑код Planet с пустыми (не заполненными) полосами

Этот шаг демонстрирует ещё одно полезное свойство — `FilledBars`. Установка его в `false` создаёт «полый» штрих‑код, что может быть удобно для дизайнерских целей.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Полностью готовая программа

Скопируйте следующий код в файл `Program.cs`. Скомпилируйте и запустите проект; три PNG‑файла появятся в папке `GeneratedBarcodes`.



## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}