---
category: general
date: 2026-10-05
description: Создайте PNG‑штрих‑код в C# и узнайте, как задать соотношение сторон
  15 для многослойных DataBar всенаправленных штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: ru
lastmod: 2026-10-05
og_description: Создайте PNG‑изображение штрихкода на C# и узнайте, как установить
  соотношение сторон 15 для многослойных всенаправленных штрихкодов DataBar за несколько
  шагов.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Создание PNG‑штрихкода в C# – установка соотношения сторон 15, учебник
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Как создать PNG‑изображение штрихкода с пользовательским соотношением сторон
  в C#
url: /ru/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PNG штрихкода с пользовательским соотношением сторон в C#

Если вам нужно **создать PNG штрихкода** в C#, это руководство покажет, **как установить соотношение сторон** 15 для стека DataBar омнидирекционного штрихкода. Мы пройдем каждый вызов API, объясним, почему соотношение сторон важно, и предоставим полностью готовый пример, который можно вставить в любой проект .NET.

Генерация изображения штрихкода — распространённая задача для систем учёта, транспортных этикеток и розничных POS‑приложений. К концу этого руководства у вас будет PNG‑файл, полностью соответствующий визуальным требованиям вашего бизнес‑партнёра. Без внешних инструментов, без ручного редактирования изображений — только код.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 или новее (пример использует .NET 6, но работает с .NET 5+)
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)
* Пакет **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Права записи в папку, куда вы хотите сохранить PNG‑файл

Эти требования минимальны; тот же код работает в .NET Core, .NET Framework или консольном приложении.

## Создание PNG штрихкода с помощью Aspose.BarCode

Первый шаг — создать экземпляр класса `BarcodeGenerator` с нужным типом штрихкода. В данном случае мы используем `EncodeTypes.DatabarStackedOmniDirectional`, который генерирует стековый DataBar, читаемый из любого направления.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Почему это важно:* Конструктор принимает два аргумента — **символику штрихкода** и **строку данных**. Формат DataBar ожидает идентификатор приложения GS1, поэтому пример данных начинается с `(01)`.

## Как установить соотношение сторон для стека DataBar

Визуальная ширина DataBar управляется свойством **aspect ratio**. Более высокое значение делает полосы шире, что может повысить надёжность сканирования на принтерах с низким разрешением.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` определяет размер одного модуля (самой маленькой полосы или пробела). При значении 2 px изображение получается чётким и плотным, что подходит большинству этикеточных принтеров.

## Установка соотношения сторон 15 – разбор кода

Теперь применим требование **set aspect ratio 15**. Это ядро руководства, демонстрирующее точный вызов API, который вам нужен.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Почему 15?* Значение соотношения сторон по умолчанию для стекового DataBar равно 12. Увеличение до 15 расширяет ширину каждой полосы на 25 %, что часто соответствует спецификациям логистических провайдеров, требующих более широкого штрихкода для ускоренного сканирования.

## Сохранить штрихкод как PNG

После настройки генератора последний шаг — записать изображение на диск. Метод `Save` принимает путь к файлу и перечисление формата изображения.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Формат PNG сохраняет без потерь, гарантируя, что штрихкод будет отображён точно так же, как задумано, на любом дисплее или принтере.

## Полный пример и ожидаемый результат

Ниже представлен полный код программы, который можно скопировать в метод `Main` консольного приложения. Он включает все описанные выше шаги и небольшое сообщение‑проверку.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Ожидаемый результат**

Запуск программы создаёт файл `DatabarAspectRatio15.png` с чётким, широким стековым DataBar штрихкодом. При открытии PNG‑файла вы увидите горизонтально растянутый штрихкод, который всё ещё соответствует спецификациям GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Текст альтернативного изображения:* **создать PNG штрихкода, показывающий стек DataBar с соотношением сторон 15**

### Советы и распространённые подводные камни

| Ситуация | Рекомендация |
|-----------|----------------|
| **Изображение выглядит размытым** | Увеличьте `XDimension.Pixels` до 3 px или более, но держите общий размер изображения ниже 500 px, чтобы избежать слишком больших файлов. |
| **Сканер не может считать код** | Убедитесь, что строка данных соответствует формату GS1 (префикс `(01)`). Также проверьте, что разрешение принтера не менее 300 dpi. |
| **Нужен другой формат файла** | Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` — API поддерживает все основные растровые форматы. |
| **Запуск в веб‑приложении** | Используйте `generator.Save(Stream, BarCodeImageFormat.Png)`, чтобы записать напрямую в HTTP‑ответ без обращения к файловой системе. |

### Расширение примера

* **Несколько штрихкодов в одном изображении:** Создайте дополнительные экземпляры `BarcodeGenerator` и отрисуйте их на одном `Bitmap`, используя `Graphics`.  
* **Добавление читаемого человеком текста:** Установите `generator.Parameters.Caption.Visible = true` и настройте шрифт через `generator.Parameters.Caption.Font`.  
* **Динамическое соотношение сторон:** Получайте значение соотношения из конфигурационного файла или базы данных, чтобы генерировать штрихкоды с разной шириной «на лету».

## Заключение

В этом руководстве вы узнали, как **создать PNG штрихкода** в C# и точно **установить соотношение сторон** 15 для стекового DataBar омнидирекционного штрихкода. Полный, готовый к запуску код демонстрирует каждый необходимый вызов API, объясняет, почему важна каждая настройка, и предоставляет практические советы для реальных внедрений.  

Далее вы можете изучить **как установить соотношение сторон** для других типов штрихкодов (например, QR Code или Code 128) или интегрировать генератор в сервис ASP .NET Core, который по запросу возвращает изображения штрихкодов. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как создать PNG‑изображения DataBar с C# и Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Как создать стековый DataBar штрихкод в C# с Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Настройка соотношения сторон стекового омнидирекционного DataBar в .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}