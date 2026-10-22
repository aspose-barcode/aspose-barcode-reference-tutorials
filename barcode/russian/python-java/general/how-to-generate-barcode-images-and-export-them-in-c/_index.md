---
category: general
date: 2026-10-21
description: Узнайте, как генерировать изображения штрихкодов в C# и как экспортировать
  файлы штрихкодов в PNG с помощью Aspose.BarCode для быстрых и надёжных результатов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: ru
lastmod: 2026-10-21
og_description: Как генерировать изображения штрихкодов в C# и экспортировать файлы
  штрихкодов в PNG. Следуйте этому полному руководству, чтобы создать штрихкоды Planet
  и RM4SCC с помощью Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Как генерировать изображения штрих‑кодов и экспортировать их в C# – пошаговое
  руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Как генерировать изображения штрихкодов и экспортировать их в C#
url: /ru/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать изображения штрих‑кодов и экспортировать их в C#

Если вам нужно **как генерировать штрих‑коды** в приложении .NET, это руководство покажет точные шаги по созданию штрих‑кодов Planet и RM4SCC, а затем **как экспортировать файлы штрих‑кода** в формате PNG. Вы получите готовый к запуску пример кода, описание каждой настройки и советы по типичным ошибкам.

В руководстве рассматривается:

* Добавление пакета NuGet Aspose.BarCode
* Настройка ширины модуля и необязательной высоты штриха
* Сохранение сгенерированных штрих‑кодов на диск
* Проверка полученных файлов

> **Prerequisite** – .NET 6+ SDK, Visual Studio 2022 (или любой IDE) и подключение к интернету для загрузки пакета Aspose.BarCode.

## Что вы сможете сделать

К концу этой статьи вы сможете:

* Сгенерировать штрих‑код **Planet** с автоматической высотой штриха.
* Сгенерировать штрих‑код **RM4SCC** с автоматической высотой штриха.
* Переопределить высоту по умолчанию и получить штрих‑код высотой 100 пикселей.
* Экспортировать каждый штрих‑код в файл PNG в выбранную вами папку.

## Шаг 1: Установить Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет предоставляет класс `BarcodeGenerator` и перечисление `EncodeTypes`, используемые в дальнейшем коде.

## Шаг 2: Настроить папку вывода

Создайте папку, в которой будут храниться файлы PNG. Папка может быть указана абсолютным или относительным путём от корня проекта.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Tip:** Использование `Path.Combine` избавляет от жёстко заданных разделителей пути и работает в Windows, macOS и Linux.

## Шаг 3: Генерировать штрих‑коды с автоматической высотой штриха

Если высота штриха не указана, Aspose.BarCode выбирает размер, подходящий для закодированных данных. Следующий код создаёт два штрих‑кода — Planet и RM4SCC — с шириной модуля 4 пикселя.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Почему это работает:**  
* `EncodeTypes.Planet` и `EncodeTypes.RM4SCC` указывают генератору, какую символьную систему использовать.  
* `XDimension.Pixels` задаёт ширину одного модуля штрих‑кода; значение 4 px даёт чёткое, сканируемое изображение.  
* Поскольку `BarHeight` не установлен, библиотека автоматически рассчитывает оптимальную высоту.

## Шаг 4: Генерировать штрих‑коды с фиксированной высотой 100 пикселей

Если ваш дизайн требует конкретной высоты штриха, можно переопределить автоматический расчёт:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Зачем может понадобиться фиксированная высота:**  
Технические требования к этикеткам часто диктуют точные размеры штрих‑кода для совместимости со сканерами. Установка `BarHeight.Pixels` гарантирует одинаковую высоту всех генерируемых изображений.

## Шаг 5: Проверить экспортированные файлы

После выполнения программы в папке `Barcodes` появятся четыре файла PNG:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Откройте любой из них в просмотрщике изображений или вставьте в PDF, чтобы убедиться, что они отображаются корректно. Если сканер не считывает штрих‑код, увеличьте значение `XDimension.Pixels` или проверьте длину входной строки.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Вы должны увидеть вывод, похожий на:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Часто задаваемые вопросы и особые случаи

| Question | Answer |
|----------|--------|
| **Can I export to formats other than PNG?** | Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp`, `Gif` или `Tiff`. |
| **What if my data contains characters not allowed by the symbology?** | Генератор бросит `ArgumentException`. Проверьте входные данные или переключитесь на символьную систему, поддерживающую данный набор символов. |
| **How do I change the foreground/background colors?** | Установите `Parameters.Barcode.ForeColor` и `Parameters.Barcode.BackColor` перед вызовом `Save`. |
| **Is there a way to generate barcodes in memory instead of saving to disk?** | Вызовите `GenerateBarCodeImage()`, чтобы получить объект `System.Drawing.Image`, затем работайте с ним в памяти или передайте по потоку. |

## Pro tip: пакетная обработка

Когда требуется создать множество штрих‑кодов (например, для списка рассылки), оберните логику генерации в цикл `foreach`:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Такой подход масштабируется до тысяч штрих‑кодов, оставаясь лаконичным.

## Заключение

Теперь вы знаете **как генерировать изображения штрих‑кодов** в C# и **как экспортировать файлы штрих‑кода** в PNG с помощью Aspose.BarCode. Полный пример демонстрирует как автоматическую, так и фиксированную генерацию высоты для символьных систем Planet и RM4SCC, предоставляя надёжную основу для любого проекта, связанного со штрих‑кодами.

**Следующие шаги**

* Исследуйте другие символьные системы, такие как Code128, QR или DataMatrix.  
* Поэкспериментируйте с настройкой цветов (`ForeColor`, `BackColor`).  
* Интегрируйте сгенерированные PNG в PDF‑счета или этикетки с помощью PDF‑библиотеки.  

Счастливого кодинга, и пусть ваши штрих‑коды сканируются без проблем!

## Что вам стоит изучить дальше?

Следующие руководства охватывают смежные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [how to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}