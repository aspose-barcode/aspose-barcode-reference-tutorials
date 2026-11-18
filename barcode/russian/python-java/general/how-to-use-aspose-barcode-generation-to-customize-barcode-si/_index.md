---
category: general
date: 2026-11-17
description: Изучите генерацию штрих‑кодов Aspose с пошаговым руководством по настройке
  размера штрих‑кода, установке ширины модуля и корректировке размеров штрих‑кода
  для идеальных результатов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generation
- customize barcode size
- barcode with module width
- adjust barcode dimensions
language: ru
lastmod: 2026-11-17
og_description: Генерация штрихкодов Aspose позволяет настраивать размер штрихкода,
  задавать ширину модуля и регулировать размеры. Следуйте этому руководству для получения
  полного, готового к запуску решения.
og_image_alt: Screenshot of a barcode created with Aspose barcode generation showing
  customized size
og_title: 'Генерация штрихкодов Aspose: настройка размера и ширины модуля в C#'
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn Aspose barcode generation with step‑by‑step guide to customize
    barcode size, set module width, and adjust barcode dimensions for perfect results.
  headline: How to use Aspose barcode generation to customize barcode size in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- barcode customization
title: Как использовать генерацию штрихкодов Aspose для настройки размера штрихкода
  в C#
url: /ru/python-java/general/how-to-use-aspose-barcode-generation-to-customize-barcode-si/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генерацию штрих‑кодов Aspose для настройки размера штрих‑кода в C#

Если вам нужно выполнить генерацию штрих‑кода Aspose и точно контролировать размер результата, это руководство покажет полный процесс. Вы увидите, как задать ширину модуля, изменить высоту полосы и сохранить результат в виде PNG‑изображения — всё в нескольких лаконичных шагах.

Настройка размеров штрих‑кода важна, когда изображение должно вписаться в определённую этикетку, UI‑элемент или шаблон печати. В этом учебнике вы научитесь генерировать штрих‑код GS1 DataBar Omni‑Directional, регулировать его размер и проверять полученный результат.

## Prerequisites

Перед началом убедитесь, что у вас есть:

- .NET 6.0 или новее
- Лицензия **Aspose.BarCode** (бесплатная пробная версия подходит для оценки)
- Visual Studio 2022 или любой другой предпочитаемый IDE для C#
- Базовые знания консольных приложений C#

## Step 1: Set up Aspose barcode generation in a C# project

Создайте новый консольный проект и добавьте пакет Aspose.BarCode через NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Библиотека `Aspose.BarCode` предоставляет класс `BarcodeGenerator`, который является ядром генерации штрих‑кодов Aspose. Добавление пакета делает API доступным для последующих шагов.

## Step 2: Initialize the barcode generator and choose a symbology

Первый блок кода создаёт генератор для штрих‑кода GS1 DataBar Omni‑Directional. Эта символьность идеальна для розничных приложений, требующих компактных числовых данных.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

// Step 1: Create a barcode generator for GS1 DataBar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Почему это важно:** Значение перечисления `EncodeTypes.DatabarOmniDirectional` сообщает генератору Aspose, какие правила кодирования применять. Строка данных `"(01)12345678901231"` соответствует формату идентификатора приложения GS1, обеспечивая сканируемость штрих‑кода стандартными розничными сканерами.

## Step 3: Customize barcode size with module width and bar height

Генерация штрих‑кодов Aspose позволяет независимо управлять **шириной модуля** (самый маленький бар или пробел) и **высотой полосы**. Регулирование этих параметров напрямую влияет на визуальный размер штрих‑кода.

```csharp
// Step 2: Set visual parameters – X dimension (module width) and bar height
generator.Parameters.Barcode.XDimension.Pixels = 2;      // 2 px module width
generator.Parameters.Barcode.BarHeight.Pixels = 30;    // 30 px bar height
```

- **barcode with module width** – Установка `XDimension.Pixels` определяет, сколько пикселей представляет один модуль. Меньшие значения дают более плотный штрих‑код, большие — увеличивают общую ширину.
- **adjust barcode dimensions** – `BarHeight.Pixels` контролирует вертикальный размер полос. Увеличение этого значения делает штрих‑код выше, не затрагивая ширину.

Эти два параметра вместе позволяют **настраивать размер штрих‑кода** под любые требования макета.

## Step 4: Save the barcode as an image file

После настройки размеров экспортируйте штрих‑код в PNG‑файл. PNG сохраняет точные пиксельные размеры, которые вы задали.

```csharp
// Step 3: Save the barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY/DatabarBarHeight30Pixels.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Метод `Save` записывает изображение, используя ранее установленные размеры. Полученный файл будет иметь ширину, определяемую длиной закодированных данных, умноженной на ширину модуля, и высоту 30 px, как указано.

## Full, runnable example

Ниже приведена полная программа, которую можно скопировать, вставить и запустить. В ней включены все необходимые директивы `using` и продемонстрирован весь процесс от инициализации до сохранения.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Customize size: set module width and bar height
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // barcode with module width = 2 px
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // adjust barcode dimensions (height)

            // Save the barcode image
            string outputPath = @"DatabarBarHeight30Pixels.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode generated and saved to {outputPath}");
        }
    }
}
```

**Ожидаемый результат:** После выполнения программы в папке проекта появится файл `DatabarBarHeight30Pixels.png`. На изображении будет чёткий штрих‑код GS1 DataBar Omni‑Directional с шириной, пропорциональной длине данных, и высотой 30 px. Откройте файл в любом просмотрщике изображений, чтобы подтвердить размеры.

![пример генерации штрих‑кода Aspose с настройкой размера штрих‑кода](https://example.com/placeholder.png "пример генерации штрих‑кода Aspose с настройкой размера штрих‑кода")

*Image alt text:* *пример генерации штрих‑кода Aspose с настройкой размера штрих‑кода* – это описание визуального результата учебника.

## Practical tips and common pitfalls

- **Pro tip:** Если вы нацелены на принтеры высокого разрешения, увеличьте ширину модуля минимум до 3 px, чтобы избежать пикселизации.
- **Watch out for:** Слишком маленькая ширина модуля может сделать штрих‑код нечитаемым на сканерах низкого качества. Протестируйте на реальном сканере перед окончательной фиксацией размера.
- **Edge case:** При кодировании длинных числовых строк общая ширина может превысить типичные размеры этикеток. В таких случаях рассмотрите возможность уменьшения ширины модуля или перехода к компактной символьности, например `DatabarLimited`.
- **Compatibility note:** Код работает с .NET 6.0, .NET 7.0 и .NET Framework 4.8. Убедитесь, что вы ссылаетесь на правильную версию `Aspose.BarCode.dll`, если используете полную платформу .NET Framework.

## Conclusion

Теперь у вас есть полное руководство по генерации штрих‑кодов Aspose, охватывающее **настройку размера штрих‑кода**, задание конкретной **ширины модуля** и **регулирование размеров** для любого проекта на C#. Следуя этим шагам, вы сможете создавать штрих‑коды, которые идеально вписываются в ваш UI, этикетки или печатные материалы.

Готовы исследовать дальше? Попробуйте изменить `EncodeTypes` для создания QR‑кодов или поэкспериментировать с цветами фона и отступами, используя объект `Parameters`. API Aspose.BarCode предоставляет обширные возможности для тонкой настройки каждого визуального аспекта штрих‑кода. Приятного кодинга!

## What Should You Learn Next?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как настроить размеры штрих‑кода в Java с Aspose](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Как задать пользовательский размер штрих‑кода в Java с Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/configuring-custom-size-barcode/)
- [Установка отступов штрих‑кода в Java – регулировка расстояния изображения штрих‑кода с Aspose](/barcode/english/java/image-manipulation/setting-margins-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}