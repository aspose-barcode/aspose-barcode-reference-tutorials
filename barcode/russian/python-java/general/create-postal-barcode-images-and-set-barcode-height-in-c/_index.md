---
category: general
date: 2026-09-07
description: Создавайте изображения почтовых штрихкодов на C# и узнайте, как изменить
  высоту штрихкода с помощью лаконичного примера генератора штрихкодов в учебнике
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode images
- barcode generator example c#
- change barcode height
language: ru
lastmod: 2026-09-07
og_description: Создавайте изображения почтовых штрихкодов на C# и откройте самый
  простой способ изменить высоту штрихкода, используя понятный пример генератора штрихкодов
  на C#.
og_image_alt: Screenshot showing created postal barcode images with custom height
og_title: Создайте изображения почтовых штрихкодов – задайте высоту штрихкода в C#
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create postal barcode images in C# and learn how to change barcode
    height with a concise barcode generator example C# tutorial.
  headline: Create postal barcode images and set barcode height in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание изображений почтовых штрихкодов и установка высоты штрихкода в C#
url: /ru/python-java/general/create-postal-barcode-images-and-set-barcode-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображений почтовых штрих‑кодов и установка высоты штрих‑кода в C#

Если вам нужно **создавать изображения почтовых штрих‑кодов** для почтовых приложений, это руководство покажет полностью готовое решение, которое можно сразу запустить. Вы увидите **пример генератора штрих‑кодов на C#**, который генерирует как Planet, так и RM4SCC штрих‑коды, и узнаете, как **изменить высоту штрих‑кода** без выхода из кода.

В руководстве покрыты все необходимые шаги для мгновенного начала генерации почтовых штрих‑кодов: требуемые пакеты NuGet, подготовка папки, генерация с высотой по умолчанию, настройка фиксированной высоты и типичные подводные камни, которых следует избегать.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 SDK или более поздняя версия, установленная  
- Visual Studio 2022 (или любая IDE для C#)  
- Пакет NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Эти компоненты дают доступ к классу `BarcodeGenerator`, используемому во всех примерах.

## Шаг 1: Подготовьте папку вывода

Генератор записывает PNG‑файлы на диск, поэтому папка должна существовать и быть доступной для записи.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define where the barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
Console.WriteLine($"Images will be saved to: {outputFolder}");
```

*Почему это важно*: попытка сохранить файл по несуществующему пути вызывает `DirectoryNotFoundException`. `Directory.CreateDirectory` безопасен, так как ничего не делает, если папка уже существует.

## Шаг 2: Сгенерировать штрих‑коды Planet и RM4SCC с высотой по умолчанию

Если не указывать свойство `BarHeight`, библиотека автоматически выбирает оптимальную высоту (режим auto). Это удобно для быстрых прототипов.

```csharp
// Planet barcode – auto height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // Set module width (X dimension) to 4 pixels for readability
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode – auto height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                BarCodeImageFormat.Png);
```

**Результат**: два PNG‑файла появляются в `Barcodes/` с высотой, выбранной библиотекой.

## Шаг 3: Установить явную высоту штрих‑кода (100 пикселей)

Иногда почтовые спецификации требуют фиксированную высоту штрих‑кода. Её можно задать через свойство `BarHeight.Pixels`.

```csharp
// Planet barcode – fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },   // module width
            BarHeight = { Pixels = 100 }   // explicit height
        }
    }
};
planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode – fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 }
        }
    }
};
rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Зачем это может понадобиться**: почтовые службы часто определяют минимальную высоту штрих‑кода для надёжного сканирования. Установка фиксированной высоты гарантирует соответствие всем сгенерированным изображениям.

## Шаг 4: Проверка сгенерированных изображений

Откройте PNG‑файлы в любом просмотрщике изображений. Визуальная разница проявляется в длине штрихов:

- **Файлы с авто‑высотой**: высота штрихов адаптируется к длине данных.  
- **Файлы с фиксированной высотой**: штрихи ровно 100 пикселей, независимо от содержимого.

Если нужно программно подтвердить высоту, загрузите изображение с помощью `System.Drawing` и проверьте `Bitmap.Height`.

```csharp
using System.Drawing;

void PrintBarHeight(string filePath)
{
    using var bmp = new Bitmap(filePath);
    Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
}

PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
```

## Совет профессионала: настройка DPI для печати высокого разрешения

Когда штрих‑код будет печататься на этикеточном принтере, может потребоваться более высокое значение DPI. Свойство `Resolution` позволяет управлять им без изменения размеров в пикселях.

```csharp
planetFixed.Parameters.Resolution = 300; // 300 dpi for crisp prints
planetFixed.Save(Path.Combine(outputFolder, "Planet_300dpi.png"),
                 BarCodeImageFormat.Png);
```

## Распространённые ошибки и как их избежать

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Изображение не создано** | Отсутствует папка вывода или нет прав на запись | Вызовите `Directory.CreateDirectory` и запустите приложение с достаточными привилегиями |
| **Штрих‑код нечитаем** | Слишком маленькое X‑измерение (например, 1 пиксель) | Используйте минимум 2 пикселя; 4 пикселя хорошо подходят для большинства сканеров |
| **Неправильный тип штрих‑кода** | Неправильное значение `EncodeTypes` | Проверьте почтовую спецификацию (Planet vs. RM4SCC) и используйте соответствующий enum |

## Полный исходный код (готов к копированию)

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // Step 1 – Prepare output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);
        Console.WriteLine($"Saving images to: {outputFolder}");

        // -------------------------------------------------
        // Step 2 – Auto‑height barcodes
        // -------------------------------------------------
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 3 – Fixed 100‑pixel height barcodes
        // -------------------------------------------------
        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 4 – Verify heights (optional)
        // -------------------------------------------------
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
    }

    static void PrintBarHeight(string filePath)
    {
        using var bmp = new Bitmap(filePath);
        Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
    }
}
```

Запуск программы создаёт четыре PNG‑файла:

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Each


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)
- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}