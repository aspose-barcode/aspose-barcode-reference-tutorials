---
category: general
date: 2026-08-12
description: Создайте изображение штрихкода в C# с помощью BarCodeGenerator. Узнайте,
  как генерировать DataBar, управлять размером изображения штрихкода и эффективно
  создавать несколько штрихкодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: ru
lastmod: 2026-08-12
og_description: Создайте изображение штрих‑кода в C# с помощью BarCodeGenerator. Этот
  учебник пошагово показывает, как генерировать коды DataBar, регулировать размер
  изображения штрих‑кода и создавать несколько штрих‑кодов.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Создание изображения штрихкода в C# – полное руководство по BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Создать изображение штрихкода в C# с помощью BarCodeGenerator
url: /ru/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода в C# с помощью BarCodeGenerator

Если вам нужно **создать изображение штрих‑кода** в приложении .NET, это руководство покажет, как сделать это с помощью класса `BarCodeGenerator`. Независимо от того, разрабатываете ли вы POS‑систему для розничной торговли или инструмент учёта запасов, вы научитесь генерировать символы DataBar, управлять размером изображения штрих‑кода и создавать несколько штрих‑кодов за один запуск.

Вы также узнаете, как API **barcode generator c#** позволяет настраивать размеры, переключать форматы вывода и обрабатывать граничные случаи, такие как недопустимые строки данных. К концу урока вы сможете уверенно **создавать несколько штрих‑кодов** без написания повторяющегося кода.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6.0 или новее  
- Среда разработки (Visual Studio, Rider или VS Code)  
- NuGet‑пакет Aspose.BarCode for .NET (или любая совместимая библиотека, предоставляющая `BarCodeGenerator`)  

Пакет можно добавить с помощью:

```bash
dotnet add package Aspose.BarCode
```

## Что покрывает это руководство

1. Создание экземпляра **barcode generator c#** для кодирования DataBar Omni‑directional.  
2. Регулировка **barcode image size** путём изменения X‑dimension и высоты штрихов.  
3. Использование цикла для **создания нескольких штрих‑кодов** с разными высотами.  
4. Сохранение изображений в формате PNG и проверка результата.  

Все фрагменты кода полностью готовы к копированию в новый консольный проект.

![Create barcode image example](barcode-example.png){alt="Create barcode image example"}

## Шаг 1: Инициализация генератора — основы создания изображения штрих‑кода

Первый шаг — создать экземпляр `BarCodeGenerator` с нужной символьной системой. Для символа DataBar Omni‑directional используйте `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Почему это важно:** При создании генератора задаются правила кодирования и полезная нагрузка данных. Если указать неверное значение `EncodeTypes`, библиотека сгенерирует неподдерживаемый штрих‑код или выбросит исключение.

## Шаг 2: Настройка X‑dimension и высоты штриха — контроль размера изображения штрих‑кода

Визуальный размер штрих‑кода определяется двумя параметрами:

| Параметр                | Что контролирует                               | Типичный диапазон |
|------------------------|-----------------------------------------------|-------------------|
| `x_dimension.pixels`   | Ширина самого маленького модуля («точки»)      | 1 – 4 px          |
| `bar_height.pixels`    | Высота вертикальных штрихов                    | 30 – 150 px       |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Совет:** Меньшее значение X‑dimension даёт изображение более высокого разрешения, но может быть труднее считать на принтерах низкого качества. Подбирайте значение в зависимости от оборудования сканирования.

## Шаг 3: Сохранение первого штрих‑кода — создание изображения штрих‑кода высотой 30 px

Теперь можно сгенерировать изображение и записать его на диск. Метод `Save` принимает путь к файлу и перечисление формата изображения.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Ожидаемый результат:** В папке `C:\Barcodes` появляется PNG‑файл `Databar30.png`. При открытии файла отображается символ DataBar Omni‑directional с чётким, контрастным узором.

## Шаг 4: Изменение высоты и генерация дополнительных изображений — создание нескольких штрих‑кодов

Чтобы **создать несколько штрих‑кодов** с разными размерами, достаточно изменить свойство `BarHeight` и снова вызвать `Save`. Это избавляет от повторного создания генератора, экономя память и процессорное время.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Почему это работает:** Объект `BarCodeGenerator` хранит всё состояние конфигурации. Изменение одного свойства обновляет движок рендеринга для следующего вызова `Save`, позволяя **создавать несколько штрих‑кодов** эффективно.

## Шаг 5: Продвинутое использование — генерация DataBar с пользовательскими данными

В примере выше используется статический GS1‑payload. В реальных сценариях часто требуется внедрять переменные идентификаторы продукта. Библиотека принимает любую строку, соответствующую спецификации DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Ключевой момент:** Установка `generator.CodeText` обновляет закодированные данные без пересоздания объекта. Это рекомендуемый шаблон **how to generate databar** при работе с большими наборами данных.

## Шаг 6: Проверка и отладка — обеспечение правильного размера изображения штрих‑кода

После генерации изображений вы можете программно убедиться, что их размеры соответствуют ожиданиям. Класс `Image` из `System.Drawing` может прочитать файл и сообщить его размеры.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Если высота не соответствует заданному значению, проверьте:

- **X‑dimension**: Очень маленькое значение может привести к округлению высоты рендерером.  
- **Формат изображения**: Некоторые форматы (например, JPEG) применяют сжатие, которое может изменить пиксельные размеры при сохранении. PNG сохраняет точные размеры.

## Шаг 7: Лучшие практики для размера изображения штрих‑кода и производительности

| Рекомендация                                                   | Причина |
|---------------------------------------------------------------|---------|
| Держите `x_dimension.pixels` в диапазоне 2 – 3 px для большинства сканеров. | Баланс читаемости и размера файла. |
| Используйте PNG для безпотерьного вывода, когда изображение будет печататься. | Гарантирует точные размеры и чёткие края. |
| Переиспользуйте один экземпляр `BarCodeGenerator` при генерации множества штрих‑кодов. | Снижает накладные расходы на создание объектов. |
| Валидируйте входную строку согласно стандарту GS1 перед присвоением `CodeText`. | Предотвращает исключения во время выполнения и некорректные сканы. |
| Храните сгенерированные изображения в отдельной папке с понятным именованием (например, `Databar_{GTIN}.png`). | Упрощает последующую обработку и аудит. |

## Полный рабочий пример

Ниже представлена полная программа, включающая все шаги от инициализации до проверки. Скопируйте код в новый консольный проект и запустите его.



## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}