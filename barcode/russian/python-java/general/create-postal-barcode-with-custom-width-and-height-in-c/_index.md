---
category: general
date: 2026-09-16
description: Создайте почтовый штрих‑код на C# и узнайте, как задать ширину и изменить
  высоту штрих‑кода для идеального сканирования.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: ru
lastmod: 2026-09-16
og_description: Создайте почтовый штрих‑код в C# с помощью этого пошагового руководства,
  показывающего, как установить ширину и изменить высоту штрих‑кода для надёжного
  сканирования почты.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Создайте почтовый штрих‑код с пользовательской шириной и высотой в C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Создать почтовый штрих‑код с пользовательской шириной и высотой в C#
url: /ru/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание почтового штрихкода с пользовательской шириной и высотой в C#

Если вам нужно **создать почтовый штрихкод** изображения в C#, это руководство покажет, как генерировать штрихкоды Planet и RM4SCC с точными размерами. К концу первых двух предложений вы узнаете точные вызовы API для **установки ширины** и **изменения высоты штрихкода**, чтобы создавать сканируемые штрихкоды, соответствующие спецификациям почтовой службы.

Вы узнаете:
* Как создать экземпляр генератора штрихкода для форматов Planet и RM4SCC.  
* Какое свойство использовать для **установки ширины** (X‑dimension) в пикселях.  
* Как **изменить высоту штрихкода** для конкретного типа штрихкода.  
* Где сохраняются сгенерированные PNG‑файлы и как они выглядят.

Единственное требование — ссылка на библиотеку `Aspose.BarCode` (или аналогичную), которая предоставляет класс `BarcodeGenerator`. Дополнительные пакеты NuGet не требуются, кроме самого SDK штрихкодов.

---

## Создание почтового штрихкода с пользовательскими размерами

Сначала добавьте необходимые директивы `using` и создайте простую консольную программу. Полный, готовый к запуску пример представлен после пошагового объяснения.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Почему это работает:**  
* `EncodeTypes.Planet` и `EncodeTypes.RM4SCC` указывают генератору, какому почтовому стандарту следовать.  
* `XDimension.Pixels` контролирует **ширину** каждого модуля штрихкода (самого маленького черного/белого элемента).  
* `BarHeight.Pixels` позволяет **изменить высоту штрихкода** для форматов, которые не рассчитывают высоту автоматически, например RM4SCC.

Запуск программы создаёт два PNG‑файла в рабочем каталоге исполняемого файла:
* `PostalPlanetBarWidth4.png` – штрихкод Planet с шириной модуля 4 px.  
* `PostalRM4SCCHeight100.png` – штрихкод RM4SCC с шириной модуля 4 px и фиксированной высотой 100 px.

---

## Как установить ширину для почтового штрихкода

Шаг **как установить ширину** одинаков для любого поддерживаемого почтового формата:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` — целое число, представляющее размер одного модуля в пикселях.  
* Типичное значение для почтовых штрихкодов — **4 px**, но его можно увеличить для печати с более высоким разрешением.  

**Pro tip:** При печати на принтере с управляемым DPI умножайте ширину в пикселях на коэффициент DPI принтера, чтобы сохранить физические размеры.

---

## Изменение высоты штрихкода для почтового штрихкода RM4SCC

Только часть почтовых символогий (например, RM4SCC) требует явного указания высоты. Используйте свойство **change barcode height**:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` — общая высота изображения штрихкода, а не высота отдельного модуля.  
* Установка `BarHeight` в **100 px** даёт высокий, легко читаемый штрихкод, соответствующий многим рекомендациям почтовых служб.

**Edge case:** Если задать слишком маленькую высоту, штрихкод может стать нечитаемым сканерами. Всегда проверяйте печатный образец перед массовым внедрением.

---

## Полный исходный файл для быстрого копирования

Ниже представлен весь код программы, который можно скопировать в новый консольный проект. Другой код не требуется.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Ожидаемый вывод** (консоль):

```
Both postal barcodes have been saved.
```

И два PNG‑файла появятся в папке вывода, каждый из которых отображает чёткий почтовый штрихкод, готовый к печати или встраиванию.

---

## Часто задаваемые вопросы и устранение неполадок

| Question | Answer |
|----------|--------|
| *What if I need a different X‑dimension for each barcode?* | Create separate `BarcodeGenerator` instances and assign a distinct `XDimension.Pixels` value before calling `Save`. |
| *Why does the Planet barcode ignore `BarHeight`?* | The Planet format automatically calculates height from the X‑dimension, so setting `BarHeight` has no effect. |
| *Can I output SVG instead of PNG?* | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg`. |
| *What if the image is blurry when printed?* | Increase the X‑dimension (e.g., to 6 px) and generate the image at a higher DPI using `Resolution` settings on the generator. |

---

## Заключение

Теперь вы знаете, как **создавать почтовый штрихкод** изображения в C# и точно **устанавливать ширину** и **изменять высоту штрихкода** с помощью API `BarcodeGenerator`. Пример охватывает как автоматически рассчитываемый (Planet), так и вручную задаваемый (RM4SCC) форматы, предоставляя надёжную основу для любого проекта автоматизации почтовых отправлений.

Далее вы можете изучить:
* Добавление читаемого человеком текста под штрихкодом (`CodeTextParameters`).  
* Экспорт в другие форматы, такие как SVG или PDF, для векторной печати.  
* Интеграцию генератора в веб‑API для выдачи штрихкодов по запросу.

Не стесняйтесь экспериментировать с различными размерами, кодировками и форматами вывода, чтобы подобрать оптимальное решение для вашего почтового рабочего процесса. Happy coding!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}