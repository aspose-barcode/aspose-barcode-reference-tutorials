---
category: general
date: 2026-09-23
description: Как изменить размер штрихкода в C# с помощью Aspose.BarCode. Узнайте,
  как генерировать штрихкод в C#, настраивать размер и эффективно экспортировать изображение
  штрихкода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: ru
lastmod: 2026-09-23
og_description: Как изменить размер штрихкода в C# с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы сгенерировать код штрихкода на C#, настроить размеры и
  экспортировать изображение штрихкода.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Как изменить размер штрихкода в C# – полный учебник по Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Как изменить размер штрих‑кода в C# с помощью Aspose.BarCode – пошаговое руководство
url: /ru/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить размер штрих‑кода в C# с помощью Aspose.BarCode – пошаговое руководство

Если вам нужно **изменить размер штрих‑кода** в приложении .NET, это руководство показывает точный код, который вы можете скопировать‑вставить и запустить уже сегодня. Вы узнаете, как **генерировать штрих‑код C#**, регулировать высоту полос и **экспортировать изображения штрих‑кода** без выхода из IDE.

Создание штрих‑кодов часто требуется в системах учёта, транспортных этикетках и POS‑терминалах. К концу этого руководства вы сможете **создавать изображения Databar штрих‑кода** любой необходимой высоты и поймёте ключевые свойства, управляющие размером, разрешением и форматом файла.

## Требования

- .NET 6 или новее (пример также работает с .NET Framework 4.6+)  
- NuGet‑пакет Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)  
- Базовые знания синтаксиса C# и Visual Studio (или любой другой C# IDE)  

Дополнительные библиотеки не требуются; Aspose.BarCode самостоятельно обрабатывает рендеринг, масштабирование и экспорт изображений.

## Шаг 1: Создайте проект и подключите Aspose.BarCode

Создайте новый консольный проект (или добавьте в существующий) и подключите пространство имён Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Совет:** Используйте последнюю версию Aspose.BarCode (по состоянию на сентябрь 2026), чтобы получить исправления ошибок и новые символьные наборы штрих‑кодов.

## Шаг 2: Инициализируйте генератор штрих‑кода DataBar Omni‑directional

**Пример генератора штрих‑кода** начинается с указания символьного набора (`EncodeTypes.DatabarOmniDirectional`) и данных. Данные оформлены в формате GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Этот объект хранит все параметры, которые вы позже будете изменять, такие как X‑dimension, высота полос и формат изображения.

## Шаг 3: Задайте общие параметры размера

Перед экспортом установите X‑dimension (ширина самой тонкой полосы) и начальную высоту полос. X‑dimension задаётся в пикселях; значение `2` хорошо подходит для большинства экранных разрешений.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Почему это важно:** Свойство `BarHeight` напрямую влияет на визуальный размер штрих‑кода. Его изменение — основа **изменения размера штрих‑кода** в Aspose.BarCode.

## Шаг 4: Экспортируйте первое изображение штрих‑кода (высота 30 px)

Теперь вы можете **экспортировать изображение штрих‑кода** в файл PNG. Метод `Save` автоматически рендерит штрих‑код с текущими параметрами.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Полученный файл выглядит так:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Пример изменения размера штрих‑кода – высота 30 пикселей"}

## Шаг 5: Измените высоту полос для создания более крупного штрих‑кода

Чтобы продемонстрировать **динамическое изменение размера штрих‑кода**, измените свойство `BarHeight` и сохраните заново. Это **не требует** создания нового экземпляра `BarcodeGenerator`; достаточно изменить существующий объект.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Шаг 6: Экспортируйте изменённое изображение штрих‑кода (высота 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла — один высотой 30 px, другой 60 px — показывающие, как одни и те же данные могут быть отрисованы в разных размерах.

### Ожидаемый результат

| Имя файла | Высота полос (px) | Визуальный результат |
|-------------------------------|----------------|-----------------------|
| `DatabarBarHeight30Pixels.png`| 30 | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="30‑пиксельный DataBar Omni‑directional штрих‑код"} |
| `DatabarBarHeight60Pixels.png`| 60 | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="60‑пиксельный DataBar Omni‑directional штрих‑код"} |

Оба изображения являются корректными штрих‑кодами GS1‑128 DataBar, готовыми к сканированию.

## Шаг 7: Дополнительно — настройка визуальных параметров

Хотя основной задачей является **изменение размера штрих‑кода**, вы также можете настроить:

| Свойство | Описание | Типичные значения |
|----------|----------|-------------------|
| `XDimension.Pixels` | Ширина самой тонкой полосы | 1–4 |
| `BarHeight.Pixels`  | Высота всего штрих‑кода | 20–200 |
| `Resolution` | DPI для растрового вывода | 72, 150, 300 |
| `ForeColor` / `BackColor` | Цвета переднего и фонового плана | `Color.Black`, `Color.White` |

Пример:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Эти настройки не влияют на логику **изменения размера**, но дают полный контроль над качеством конечного изображения.

## Распространённые ошибки и как их избежать

| Проблема | Симптом | Решение |
|----------|---------|---------|
| Высота полос не меняется | Сохранённые изображения выглядят одинаково | Убедитесь, что изменяете `barcode.Parameters.Barcode.BarHeight.Pixels` *до* каждого вызова `Save`. |
| Штрих‑код становится нечитаемым | Сканер сообщает «cannot read» | Держите `XDimension` ≥ 2 px для DataBar Omni‑directional; слишком тонкие полосы могут нарушить сканирование. |
| PNG‑файл размытый | Экспорт с низким DPI | Установите `barcode.Parameters.ImageResolution.DpiX/Y` минимум 150 для печати высокого качества. |
| Файл перезаписан случайно | Новое изображение заменило старое | Используйте уникальные имена файлов или включайте значение высоты в имя, как показано выше. |

## Полный, готовый к запуску пример

Скопируйте весь блок ниже в новый консольный проект (`Program.cs`). Код компилируется и работает «из коробки», создавая два PNG‑файла в папке вывода проекта.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

Запуск программы выдаёт:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Проверьте папку вывода — там два PNG‑файла. Оба готовы к печати, встраиванию в PDF или отправке на удалённое устройство.

## Заключение

В этом руководстве мы рассмотрели **изменение размера штрих‑кода** в C# с помощью Aspose.BarCode, продемонстрировали полный **пример генератора штрих‑кода** и показали, как **экспортировать изображения штрих‑кода** разных высот. Теперь вы знаете, как:

1. **Создавать объекты Databar штрих‑кода** с пользовательскими данными.  
2. Регулировать `BarHeight` (ключ к изменению размера).  
3. Экспортировать PNG‑файлы любого требуемого размера.  

Далее вы можете исследовать дополнительные настройки — другие символьные наборы, цветовые схемы или векторные форматы, такие как SVG. Та же схема (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) работает для любого типа штрих‑кода, поддерживаемого Aspose.BarCode, так что вы смело применяете знания **изменения размера штрих‑кода** во всём приложении.

---

**Следующие шаги**

- Попробуйте менять размер других символьных наборов (QR, Code128), чтобы увидеть, как взаимодействуют высота и ширина.  
- Используйте `BarCodeImageFormat.Svg` для генерации масштабируемой векторной графики для веб‑страниц.  
- Интегрируйте полученные изображения в PDF‑отчёты с помощью Aspose.PDF или iTextSharp.  

Счастливого кодинга и наслаждайтесь гибкостью программной генерации штрих‑кодов!

## Что следует изучить дальше?

Следующие учебные материалы охватывают смежные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}