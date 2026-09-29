---
category: general
date: 2026-08-06
description: Создайте изображение штрихкода в C# с помощью Aspose.BarCode. Узнайте,
  как генерировать Databar, настраивать пользовательский размер штрихкода и изменять
  высоту штрихкода простым кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: ru
lastmod: 2026-08-06
og_description: Создайте изображение штрихкода на C# с помощью Aspose.BarCode. Это
  руководство показывает, как создать штрихкод Databar Omnidirectional, настроить
  его размер и эффективно изменить высоту штрихкода.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Создание изображения штрихкода в C# – полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание изображения штрихкода в C# с помощью Aspose.BarCode
url: /ru/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода в C# с помощью Aspose.BarCode

Если вам нужно **генерировать изображение штрих‑кода** программно, это руководство покажет вам, как это сделать. Независимо от того, создаёте ли вы систему учёта розничных товаров или портал отслеживания логистики, вы увидите полный рабочий процесс создания штрих‑кода Databar Omnidirectional, настройки его размеров и сохранения результата в файл PNG.

Генерация изображения штрих‑кода — распространённая задача, но разработчики часто задаются вопросом **как сгенерировать Databar** с точными нужными размерами. В этом учебнике вы научитесь создавать штрих‑код Databar, настраивать его ширину и высоту, а также менять высоту штрих‑кода без переписывания всего генератора.

## Prerequisites

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код работает с .NET Core и .NET Framework)
* Visual Studio 2022 (или любая IDE, поддерживающая C#)
* Действительная лицензия Aspose.BarCode for .NET (бесплатная оценочная версия подходит для тестирования)
* Базовое знакомство с синтаксисом C#

## Step 1: Install Aspose.BarCode

Добавьте пакет Aspose.BarCode NuGet в ваш проект:

```bash
dotnet add package Aspose.BarCode
```

Пакет содержит класс `BarcodeGenerator`, используемый на протяжении всего руководства. После установки восстановите проект, чтобы подтянуть зависимости.

## Step 2: Create a basic barcode generator

Первая строка кода создаёт **генератор штрих‑кода**, который будет генерировать символ Databar Omnidirectional. Перечисление `EncodeTypes.DatabarOmniDirectional` указывает библиотеке, какую символьную схему использовать, а строка данных следует синтаксису GS1 Application Identifier.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Почему это важно:** Объект `BarcodeGenerator` является точкой входа для любой операции со штрих‑кодом. Выбирая `DatabarOmniDirectional`, вы гарантируете, что вывод соответствует стандарту GS1 для розничного сканирования.

## Step 3: Set a custom X‑dimension (module width)

X‑dimension управляет шириной самого узкого штриха. Установка небольшого значения в пикселях даёт компактный штрих‑код, а большие значения увеличивают общую ширину.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Объяснение:** X‑dimension в 2 пикселя — распространённый выбор для экранов с высоким разрешением. При необходимости измените это значение, если вам требуется более плотная или более рыхлая визуальная плотность.

## Step 4: Generate the first barcode image with a specific height

Высота штрих‑кода независима от X‑dimension. Здесь мы задаём высоту штриха **30 px**, а затем сохраняем изображение в формате PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Результат:** Теперь у вас есть файл `DatabarBarHeight30Pixels.png`, показывающий штрих‑код Databar высотой 30 px. Это демонстрирует возможность **настройки размера штрих‑кода** для конкретного случая, например, небольшой этикетки.

## Step 5: Change barcode height for a larger version

Если тот же штрих‑код должен отображаться на более крупной этикетке, достаточно изменить свойство высоты и переиспользовать тот же экземпляр генератора.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Почему генератор можно переиспользовать:** Изменение `BarHeight.Pixels` обновляет внутреннюю раскладку без создания нового объекта, что экономит память и сохраняет строку данных неизменной. Это рекомендуемый способ **изменения высоты штрих‑кода** «на лету».

## Step 6: Verify the output

Откройте оба PNG‑файла в любом просмотрщике изображений. Вы должны увидеть два штрих‑кода Databar Omnidirectional, кодирующих один и тот же GTIN, но различающихся по вертикальному размеру:

* `DatabarBarHeight30Pixels.png` – 30 px в высоту, подходит для компактных чеков.
* `DatabarBarHeight60Pixels.png` – 60 px в высоту, идеален для более крупных этикеток на полках.

Оба изображения сохраняют одинаковый X‑dimension, поэтому соотношение штрих‑пробел остаётся постоянным, а общая высота масштабируется.

## Common variations and edge cases

| Situation | How to handle it |
|-----------|------------------|
| **Different barcode symbology** | Replace `EncodeTypes.DatabarOmniDirectional` with another enum value (e.g., `EncodeTypes.Code128`). The rest of the code remains unchanged. |
| **Non‑pixel dimensions** | Use `generator.Parameters.Barcode.XDimension.Millimeters` or `BarHeight.Millimeters` if you need physical measurements for print‑ready output. |
| **Transparent background** | Set `generator.Parameters.ImageBackgroundColor = Color.Transparent;` before calling `Save`. |
| **High‑resolution output** | Increase both `XDimension.Pixels` and `BarHeight.Pixels` proportionally, or save as `BarCodeImageFormat.Tiff` for lossless quality. |
| **Multiple barcodes in one image** | Create separate `BarcodeGenerator` instances, render each to a `Bitmap`, then compose them using `Graphics.DrawImage`. |

**Pro tip:** Always test the generated barcode with a real scanner before deploying to production. Scanners may interpret very thin bars differently depending on lighting and sensor quality.

## Full source code for reference

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Скопируйте код в новый консольный проект, запустите его, и вы увидите два PNG‑файла в папке вывода.

## Frequently asked questions

**Q: Can I generate a barcode without installing a license?**  
A: The evaluation version of Aspose.BarCode works without a license but adds a small watermark. For production use, apply a purchased license using `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: Does changing the X‑dimension affect readability?**  
A: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution printers. A minimum of 1 px for screen rendering is recommended; for print, use at least 0.25 mm.

**Q: What if I need to generate a barcode in JPEG format?**  
A: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You may also set `generator.Parameters.ImageQuality` to control compression.

## Conclusion

Теперь вы знаете, как **генерировать изображение штрих‑кода** в C# с помощью Aspose.BarCode, как **создавать Databar штрих‑код**, настраивать **пользовательский размер штрих‑кода** и **изменять высоту штрих‑кода** по требованию. Полный пример демонстрирует наиболее распространённый рабочий процесс, а таблица вариантов помогает справиться с реальными краевыми случаями.

Далее изучайте связанные темы, такие как **встраивание штрих‑кодов в PDF‑документы**, **массовая генерация нескольких штрих‑кодов** и **использование QR‑кодов для мобильных платежей**. Каждый из этих сценариев опирается на те же принципы, изложенные здесь, так что вы сможете уверенно расширять свои знания.

Happy coding, and may your barcodes scan flawlessly!

## What Should You Learn Next?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Создание изображения штрих‑кода – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Как сгенерировать Aztec‑штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как сгенерировать штрих‑код – конфигурация Code 39 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}