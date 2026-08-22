---
category: general
date: 2026-08-22
description: Как генерировать штрих‑код в C# с помощью Aspose.BarCode. Узнайте, как
  пошагово создавать изображение штрих‑кода в C#, отключать 2‑D‑компонент и сохранять
  файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: ru
lastmod: 2026-08-22
og_description: Как генерировать штрих‑код в C# с помощью Aspose.BarCode. Этот учебник
  показывает, как создать изображение штрих‑кода в C# с использованием DataBar Expanded,
  переключить 2‑D‑компонент и сохранить файлы PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Как генерировать штрих‑код в C# – полное руководство по созданию изображения
  штрих‑кода в C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Как сгенерировать штрих‑код в C# – создать изображение штрих‑кода в C# с DataBar
  Expanded
url: /ru/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрих‑код в C# – создание изображения штрих‑кода c# с DataBar Expanded

Генерация штрих‑кода в C# часто требуется, когда необходимо внедрить машинно‑читаемые данные в ваши приложения. В этом руководстве показано, как создать изображение штрих‑кода c# с помощью библиотеки Aspose.BarCode, отключить 2‑D‑компонент и сохранить результат в виде PNG‑файлов.

Вы увидите полностью готовую, исполняемую программу, объяснение каждой опции конфигурации и советы по настройке вывода. Внешняя документация не нужна — только код ниже и среда разработки .NET.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия  
* Visual Studio 2022 (или любая IDE, поддерживающая .NET)  
* NuGet‑пакет Aspose.BarCode for .NET (`Aspose.BarCode`)  

Пакет можно добавить следующей командой:

```bash
dotnet add package Aspose.BarCode
```

Библиотека предоставляет класс `BarcodeGenerator`, используемый во всём этом руководстве.

## Шаг 1: Создание проекта и импорт пространств имён

Создайте новое консольное приложение и импортируйте необходимые пространства имён:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Пространство имён `Aspose.BarCode.Generation` содержит все классы, необходимые для настройки и рендеринга штрих‑кодов.

## Шаг 2: Инициализация генератора штрих‑кода DataBar Expanded

Первая рабочая строка создаёт `BarcodeGenerator` для символьной системы **DataBar Expanded** и передаёт исходную строку данных. Строка данных следует формату GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Создание генератора выделяет внутренний bitmap‑канвас, поэтому вы можете изменить размер и внешний вид до рендеринга.

## Шаг 3: Определение ширины модуля (X‑dimension)

X‑dimension управляет шириной самого маленького элемента штрих‑кода. Установка её в пикселях даёт точный контроль над конечным размером изображения.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение `2` пикселя хорошо подходит для отображения на экране; увеличьте его для печати с более высоким разрешением.

## Шаг 4: Отключение 2‑D‑композитного компонента

DataBar Expanded может включать 2‑D‑компонент, содержащий дополнительную информацию. Чтобы сгенерировать штрих‑код **без** этого компонента, установите флаг в `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Отключение компонента уменьшает визуальную сложность и приводит к меньшему PNG‑файлу.

## Шаг 5: Сохранение изображения штрих‑кода без 2‑D‑компонента

Выберите каталог вывода и запишите изображение на диск. Перечисление `BarCodeImageFormat.Png` гарантирует безпотерьный PNG‑файл.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

После этого вызова `Databar2DComponentDisabled.png` будет содержать чистый штрих‑код DataBar Expanded.

## Шаг 6: Включение 2‑D‑композитного компонента

Если нужен дополнительный слой данных, снова включите флаг. Один и тот же экземпляр генератора можно переиспользовать, что избавляет от создания второго объекта.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Шаг 7: Сохранение изображения штрих‑кода с включённым 2‑D‑компонентом

Сгенерируйте второе изображение, используя те же настройки, кроме флага 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Теперь `Databar2DComponentEnabled.png` показывает штрих‑код с дополнительным 2‑D‑шаблоном.

## Полный исходный код

Скопируйте весь фрагмент ниже в `Program.cs` и запустите проект. Программа создаст оба PNG‑файла в указанной папке.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Ожидаемый вывод

При запуске программа выводит:

```
Barcode images generated successfully.
```

и создаёт два файла:

* `Databar2DComponentDisabled.png` — штрих‑код без 2‑D‑компонента  
* `Databar2DComponentEnabled.png` — штрих‑код с 2‑D‑компонентом  

Откройте PNG‑файлы в любом просмотрщике изображений, чтобы увидеть визуальную разницу.

## Распространённые варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Другая символьная система** | Замените `EncodeTypes.DatabarExpanded` на другое значение, например `EncodeTypes.Code128`. |
| **Большее разрешение** | Увеличьте `XDimension.Pixels` до 4 или 5, либо задайте `Resolution` в `barcodeGenerator.Parameters.Image`. |
| **Другие форматы изображений** | Используйте `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` или `BarCodeImageFormat.Svg`. |
| **Запуск в веб‑приложении** | Передавайте байты изображения напрямую в HTTP‑ответ вместо сохранения на диск. |
| **Управление памятью** | Оберните генератор в блок `using`, если вы целитесь в .NET Framework, чтобы гарантировать освобождение неуправляемых ресурсов. |

## Профессиональные советы

* **Переиспользуйте генератор** — изменение только 2‑D‑флага избавляет от повторного создания объекта, экономя процессорные циклы.  
* **Проверяйте данные** — данные GS1 должны точно соответствовать требованиям по длине и контрольной сумме; неверный ввод вызывает `ArgumentException`.  
* **Пакетная обработка** — пройдитесь по коллекции строк данных, переключайте 2‑D‑флаг по необходимости и сохраняйте каждое изображение под уникальным именем.  

## Заключение

Теперь вы знаете, как генерировать штрих‑код в C# и создавать изображение штрих‑кода c# с полным контролем над 2‑D‑композитным компонентом. Пример демонстрирует инициализацию генератора, настройку X‑dimension, переключение компонента и сохранение PNG‑файлов. Дальше вы можете исследовать другие символьные системы, встраивать изображения в PDF или интегрировать генерацию штрих‑кодов в сервисы ASP.NET Core.

--- 

*Следующие шаги*: попробуйте генерировать QR‑коды, поэкспериментируйте с различными разрешениями изображений или внедрите полученные PNG‑файлы в PDF с помощью Aspose.PDF. Эти расширения используют тот же API `BarcodeGenerator` и сохраняют согласованность вашего рабочего процесса.


## Что изучать дальше?


В следующих руководствах рассматриваются тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}