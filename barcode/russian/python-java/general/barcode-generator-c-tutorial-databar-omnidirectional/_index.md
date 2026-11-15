---
category: general
date: 2026-11-14
description: Учебник по генерации штрихкодов на C#, показывающий, как создавать штрихкоды
  DataBar Omnidirectional, задавать X‑размер и регулировать высоту штриха в пикселях.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: ru
lastmod: 2026-11-14
og_description: Учебник по генерации штрихкодов на C# пошагово объясняет, как создать
  штрих‑код DataBar Omnidirectional, задать XDimension в пикселях и изменить высоту
  полосы для вывода в PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 'Генератор штрих‑кодов на C# – учебник: создание штрих‑кодов DataBar'
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Генератор штрихкодов C#: учебник по DataBar Omnidirectional'
url: /ru/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Руководство по генератору штрихкодов C# – создание штрихкодов DataBar Omnidirectional

Если вы ищете **barcode generator C# tutorial**, вы попали в нужное место. Это руководство проведёт вас через процесс создания штрихкода DataBar Omnidirectional, настройки XDimension в пикселях и регулировки высоты полос для получения PNG‑изображений.

Вы увидите полностью готовый, исполняемый пример, охватывающий всё—from инициализации генератора до сохранения нескольких изображений с разными высотами полос. Внешняя документация не требуется — просто скопируйте код, запустите его, и у вас будет два готовых файла штрихкода.

## Prerequisites

Перед началом убедитесь, что у вас есть:

* .NET 6.0 или более поздняя версия  
* Ссылка на библиотеку штрихкодов, предоставляющую `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat` (например, Aspose.BarCode for .NET)  
* Базовое знакомство с синтаксисом C# и Visual Studio или вашей любимой IDE  

> **Pro tip:** Если вы используете Aspose.BarCode, добавьте в проект NuGet‑пакет `Aspose.BarCode`.

## Barcode generator C# tutorial – step 1: create the generator

Первый шаг — создать экземпляр `BarcodeGenerator` с типом кодирования `DatabarOmniDirectional` и данными, которые нужно закодировать.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` сообщает библиотеке генерировать штрихкод, читаемый из любого направления, что идеально подходит для розничной упаковки и логистики.

## Set XDimension pixels for the barcode

X‑dimension определяет ширину самого маленького модуля («пикселя») в штрихкоде. Установка её в пикселях даёт точный контроль над визуальной плотностью штрихкода.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* Значение `2` пикселя даёт штрихкод, достаточно чёткий для большинства сканеров, при этом размер файла остаётся умеренным.

## Adjust bar height and save images

Высота полос определяет, насколько высокими будут полосы. Вы можете генерировать несколько изображений с разными высотами, изменяя свойство `BarHeight.Pixels` и вызывая `Save` повторно.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Значение перечисления `BarCodeImageFormat.Png` гарантирует, что результат будет без потерь в формате PNG, который рекомендуется для графики штрихкодов, поскольку сохраняет точные размеры.

## Change bar height to create multiple images

Часто требуется один и тот же штрихкод разных размеров — например, один для небольшой этикетки и другой для большого плаката. Измените высоту полос и повторно используйте тот же экземпляр генератора:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* Если высота полос установлена слишком низко (например, ниже 10 px), некоторые сканеры могут испытывать трудности с чтением кода. Всегда тестируйте сгенерированные изображения на целевом сканирующем оборудовании.

## Full source code

Ниже приведена полная программа, которую можно скопировать и вставить в новый консольный проект. В ней указаны все необходимые директивы `using` и продемонстрированы варианты высоты полос.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Запустите программу, замените `YOUR_DIRECTORY` на действительный путь к папке, и вы найдёте два PNG‑файла:

* `DatabarBarHeight30Pixels.png` — полосы высотой 30 px  
* `DatabarBarHeight60Pixels.png` — полосы высотой 60 px  

![вывод руководства по генератору штрихкодов C#](images/databar-example.png "Руководство по генератору штрихкодов C# показывает два изображения DataBar")

## Common questions

| Question | Answer |
|----------|--------|
| **Можно ли изменить формат изображения?** | Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` по необходимости. PNG предпочтителен для безпотерьного качества. |
| **Что делать, если нужна другая XDimension?** | Отрегулируйте `generator.Parameters.Barcode.XDimension.Pixels` до любого целого числа. Большие значения увеличивают общую ширину штрихкода. |
| **Подходит ли DataBar Omnidirectional для мобильного сканирования?** | Да, при условии, что напечатанный размер соответствует минимальному размеру модуля сканера (обычно 0.33 mm). Пиксель‑ориентированная XDimension помогает выполнить это требование. |
| **Как встроить штрихкод в PDF?** | После сохранения PNG используйте библиотеку для работы с PDF (например, iTextSharp), чтобы вставить изображение в страницу PDF. |

## Conclusion

Это **barcode generator C# tutorial** показало, как создать штрихкод DataBar Omnidirectional, задать XDimension в пикселях и сгенерировать PNG‑файлы с разными высотами полос. Теперь у вас есть переиспользуемый фрагмент кода, который можно адаптировать для любого C#‑проекта, требующего создания штрихкодов.

### What’s next?

* Исследуйте другие `EncodeTypes`, такие как `Code128` или `QR`, чтобы расширить свой набор штрихкодов.  
* Скомбинируйте сгенерированные PNG с библиотекой создания PDF, чтобы получать печатные счета.  
* Поэкспериментируйте с `generator.Parameters.Barcode.Color`, чтобы добавить пользовательские цвета, оставаясь в рамках спецификаций сканеров.

Не стесняйтесь модифицировать пример, пробовать дополнительные высоты полос или менять формат вывода. Приятного кодинга!

## What Should You Learn Next?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}