---
category: general
date: 2026-08-03
description: Учебник по генерации штрихкодов на C# показывает, как создать изображение
  штрихкода с помощью Aspose.BarCode, задать столбцы и строки и сохранить PNG‑файлы
  для DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: ru
lastmod: 2026-08-03
og_description: Учебник по генерации штрихкодов на C# объясняет, как создавать изображение
  штрихкода с помощью Aspose.BarCode, настраивать столбцы и строки DataBar Expanded
  Stacked и сохранять файлы PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Генератор штрихкодов C# – пошаговое руководство по созданию изображения
  штрихкода
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Генератор штрихкодов C# – генерировать изображение штрихкода
url: /ru/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – generate barcode image

Если вам нужен barcode generator C# , способный генерировать изображение штрих‑кода для DataBar Expanded Stacked, это руководство проведёт вас через весь процесс. Вы узнаете, как настроить параметры столбцов и строк, сохранить результат в PNG и адаптировать код для других символогий.

Программная генерация изображений штрих‑кодов устраняет ручные шаги и обеспечивает единообразие в счетах, транспортных этикетках и системах учёта. В этом учебнике рассматривается всё необходимое — от настройки проекта до полного исходного кода, чтобы вы могли сразу запустить пример.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 или более поздняя версия  
* IDE, например Visual Studio 2022 (подойдёт любой редактор, поддерживающий C#)  
* Лицензия на **Aspose.BarCode for .NET** — бесплатная оценочная версия подходит для тестирования  
* Базовые знания синтаксиса C#  

Если чего‑то не хватает, установите .NET SDK с сайта dotnet.microsoft.com и получите пакет Aspose.BarCode NuGet с помощью:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a barcode generator C# project

Создайте новое консольное приложение и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

Класс `BarcodeGenerator` является ядром API barcode generator C#. Он принимает тип символогии и текст для кодирования.

## Step 2: Generate a DataBar Expanded Stacked barcode and set columns

В первом примере создаётся штрих‑код с четырьмя столбцами. Изменение свойства `Columns` меняет визуальную плотность символогии DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Почему это важно:** Количество столбцов влияет на объём данных, которые можно разместить в компактном пространстве. Установка значения 4 даёт более широкий штрих‑код, остающийся читаемым большинством сканеров.

## Step 3: Generate a barcode with custom row count

Во втором примере показано, как управлять вертикальной компоновкой, задавая свойство `Rows`. Конфигурация из трёх строк полезна, когда нужен более высокий штрих‑код при ограниченном горизонтальном пространстве.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Почему это важно:** Регулировка количества строк позволяет разместить штрих‑код в узкой колонке, сохраняя читаемость. barcode generator C# автоматически пересчитывает размер модуля, чтобы соответствовать спецификации.

## Step 4: Full, runnable example

Ниже приведена автономная программа, объединяющая предыдущие шаги. Скопируйте код в `Program.cs`, замените `YOUR_DIRECTORY` на существующий путь к папке и запустите приложение.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Expected output

При запуске программы в целевом каталоге появятся два PNG‑файла:

* **DatabarCols4.png** — штрих‑код DataBar Expanded Stacked с четырьмя столбцами  
* **DatabarRows3.png** — те же данные, закодированные в три строки  

Откройте изображения в любом просмотрщике; они показывают чёткие, сканируемые штрих‑коды, готовые к печати или встраиванию в PDF‑файлы.

## How to generate barcode image with custom dimensions

Если нужен конкретный размер изображения, задайте свойства `ImageHeight` и `ImageWidth` перед вызовом `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Изменение размеров не влияет на закодированные данные; оно лишь масштабирует визуальное представление. Эта техника полезна при интеграции штрих‑кодов в UI‑компоненты с фиксированными ограничениями макета.

## Common pitfalls and pro tips

* **Path separators:** Используйте дословные строки (`@"C:\Path\file.png"`) или `Path.Combine`, чтобы избежать проблем с экранированием символов в Windows.  
* **License enforcement:** Без действующей лицензии сгенерированные изображения содержат водяной знак. Примените лицензию сразу после запуска приложения:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Encoding limits:** DataBar Expanded Stacked поддерживает до 74 цифровых символов. Превышение этого лимита вызывает исключение. Проверяйте длину входных данных перед созданием генератора.  
* **Performance:** Повторное использование одного экземпляра `BarcodeGenerator` для нескольких сохранений снижает расход памяти. Меняйте свойства `Rows` или `Columns` между сохранениями только если закодированный текст остаётся тем же.

## Next steps

Теперь, когда вы умеете генерировать изображения штрих‑кодов с помощью barcode generator C#, можете изучить следующее:

* **Different symbologies** — попробуйте `EncodeTypes.QR`, `EncodeTypes.Code128` или `EncodeTypes.Pdf417`.  
* **Color customization** — задайте `Parameters.Barcode.ForeColor` и `BackColor`, чтобы соответствовать фирменному стилю.  
* **Embedding in PDFs** — объедините сгенерированный PNG с Aspose.PDF для создания печатных документов.  

Эти расширения позволят построить полнофункциональное решение штрих‑кодов для инвентаризации, логистики или розничных приложений.

---


## What Should You Learn Next?

Следующие учебники охватывают близко связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}