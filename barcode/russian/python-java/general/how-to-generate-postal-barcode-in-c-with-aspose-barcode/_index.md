---
category: general
date: 2026-08-19
description: Узнайте, как генерировать почтовый штрих‑код в C# с помощью Aspere.BarCode.
  Это пошаговое руководство показывает, как создавать штрих‑коды форматов Planet и
  RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: ru
lastmod: 2026-08-19
og_description: Создайте почтовый штрих‑код на C# с помощью Aspose.BarCode. Следуйте
  этому руководству, чтобы узнать, как генерировать штрих‑код для Planet и RM4SCC
  с пользовательскими размерами.
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: Создание почтового штрихкода в C# – полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: Как сгенерировать почтовый штрих‑код в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать почтовый штрих‑код в C# с помощью Aspose.BarCode

Если вам нужно **генерировать почтовый штрих‑код** для почтовых приложений, это руководство покажет, как именно генерировать штрих‑код с использованием библиотеки Aspose.BarCode. Вы увидите полный, исполняемый пример, который создает как штрих‑код Planet (высота рассчитывается автоматически), так и штрих‑код RM4SCC с явно заданной высотой полосы.

Генерация почтового штрих‑кода — распространённое требование для логистического программного обеспечения, автоматических принтеров этикеток и систем массовой рассылки. К концу этого урока вы сможете интегрировать генерацию штрих‑кода в любой проект .NET, настроить X‑размер и управлять высотой полосы, если стандартный формат это позволяет.

**Что вы узнаете**

* Как настроить Aspose.BarCode в проекте C#.  
* Как генерировать почтовые штрих‑коды Planet и RM4SCC.  
* Как регулировать X‑размер (ширину модуля) и высоту полосы.  
* Как сохранить результат в виде PNG‑изображения.  

Внешние сервисы не требуются — всё работает локально после подключения пакета Aspose.BarCode через NuGet.

## Предварительные требования

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).  
* Visual Studio 2022, Visual Studio Code или любой другой IDE для C#.  
* Пакет Aspose.BarCode for .NET – установите его через NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Генерировать почтовый штрих‑код с помощью Aspose.BarCode

В следующих разделах мы пошагово пройдём весь процесс: от создания объектов‑генераторов до сохранения окончательных PNG‑файлов.

### Шаг 1: Создать штрих‑код Planet (автоматическая высота)

Planet — почтовый штрих‑код, используемый во многих странах для сортировки почты. При создании штрих‑кода Planet библиотека автоматически определяет оптимальную высоту полосы на основе закодированных данных.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**Почему это работает** – `EncodeTypes.Planet` указывает Aspose.BarCode использовать символьную систему Planet. Свойство `XDimension` задаёт ширину самой маленькой полосы (модуля). Поскольку Planet не требует фиксированной высоты полосы, библиотека автоматически вычисляет подходящую высоту, что упрощает код.

### Шаг 2: Создать штрих‑код RM4SCC с явной высотой

RM4SCC — другая почтовая символьная система, часто требующая конкретной высоты полосы для совместимости со сканерами. Ниже показано, как задать эту высоту вручную.

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Почему вы задаёте высоту** – Некоторые почтовые сканеры ожидают минимальную высоту полосы. Установив `BarHeight.Pixels = 100`, вы гарантируете, что сгенерированное изображение удовлетворяет этим требованиям. X‑размер остаётся одинаковым с штрих‑кодом Planet, чтобы оба изображения имели одинаковую визуальную плотность.

### Шаг 3: Проверить результат

После запуска программы откройте два PNG‑файла, находящиеся в `YOUR_DIRECTORY`. Вы должны увидеть два разных штрих‑кода:

* `PostalPlanetBarHeightNone.png` – штрих‑код Planet с автоматически рассчитанной высотой.  
* `PostalRM4SCCBarHeight100Pixels.png` – штрих‑код RM4SCC с высотой 100 пикселей.

Оба изображения можно напрямую отправлять на принтеры этикеток или отображать в веб‑приложении.

![Generated postal barcode image using Aspose.BarCode](generated-postal-barcode.png)

*Текст альтернативы изображения:* **Сгенерированный почтовый штрих‑код** с помощью Aspose.BarCode (демонстрирует, как генерировать почтовый штрих‑код).

## Как генерировать штрих‑код с пользовательскими размерами (расширенный)

Если необходимо точно настроить другие параметры — такие как отступы, расположение текста или цвет — Aspose.BarCode предоставляет богатый объект `Parameters`. Ниже быстрый пример, который добавляет белый фон и отключает читаемый человеком текст.

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**Когда использовать это** – Отключение читаемого человеком текста часто применяется в автоматической сортировке, где важен только машинно‑читаемый шаблон. Установка цвета фона гарантирует корректную печать штрих‑кода на прозрачных носителях.

## Распространённые ошибки и профессиональные советы

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Штрих‑код выглядит растянутым | X‑размер слишком велик относительно размера изображения | Держите `XDimension.Pixels` в диапазоне от 2 до 5 для большинства почтовых штрих‑кодов |
| Сканер отклоняет изображение | Высота полосы ниже минимального требования почтовой службы | Используйте `BarHeight.Pixels` ≥ 80 для RM4SCC, если спецификация не указывает иначе |
| Размер PNG‑файла большой | Разрешение изображения выше необходимого | Сохраняйте как PNG‑8 (`BarCodeImageFormat.Png8`) или уменьшайте пиксельные размеры |

**Профессиональный совет:** Всегда проверяйте сгенерированный штрих‑код на реальном сканере перед выпуском в продакшн. Небольшие визуальные различия могут влиять на читаемость.

## Полный исходный код

Скопируйте весь блок ниже в новое консольное приложение (`Program.cs`). При необходимости измените пути вывода на папку, в которую ваш процесс имеет право записи.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

Запуск программы выводит *“Barcodes generated successfully.”* и создаёт два PNG‑файла в рабочем каталоге исполняемого файла.

## Заключение

Теперь вы знаете, как **генерировать почтовый штрих‑код** в C# с помощью Aspose.BarCode, охватывая как штрих‑коды Planet с автоматической высотой, так и штрих‑коды RM4SCC с фиксированной высотой. Руководство также показало, **как генерировать штрих‑код** с пользовательским X‑размером, высотой полосы и визуальными параметрами, предоставляя надёжную основу для любого проекта автоматизации рассылки.

Дальнейшие шаги, которые вы можете изучить:

* Интегрировать сгенерированные PNG‑файлы в PDF‑счёт с помощью Aspose.PDF.  
* Переключить формат вывода на SVG для масштабируемой векторной графики.  
* Использовать класс `BarcodeReader` для программной проверки закодированных данных.

Не стесняйтесь экспериментировать с различными символьными системами (например, `EncodeTypes.Postnet`) и делиться результатами с сообществом. Приятного кодинга!

## Что вам стоит изучить дальше?

Следующие учебные материалы охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}