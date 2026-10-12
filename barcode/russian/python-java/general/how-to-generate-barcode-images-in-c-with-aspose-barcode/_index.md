---
category: general
date: 2026-10-12
description: Как быстро генерировать штрих‑код в C#. Узнайте, как создать пустой штрих‑код
  и настроить ширину полос для чётких почтовых штрих‑кодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: ru
lastmod: 2026-10-12
og_description: Как генерировать штрих‑код в C# с помощью Aspose.BarCode. Это руководство
  покажет, как создать пустой штрих‑код и настроить размеры полос для почтовых стандартов.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: Как генерировать изображения штрих‑кодов в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Как генерировать изображения штрихкодов в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать изображения штрих‑кодов в C# с помощью Aspose.BarCode

Если вам нужно **how to generate barcode** изображения из строки в приложении .NET, это руководство предоставляет полное, готовое к запуску решение. Вы увидите, как генерировать стандартные штрих‑коды Planet и RM4SCC, регулировать ширину полос для читаемости и **create empty barcode** варианты, где полосы не заполнены. Код работает с последней версией Aspose.BarCode для .NET (v.24.10) и запускается на .NET 6 или новее.

Генерация штрих‑кодов — распространённая потребность для транспортных этикеток, систем учёта запасов и платформ продажи билетов. К концу этого руководства вы сможете программно создавать как заполненные, так и пустые штрих‑коды, без необходимости во внешних инструментах.

## Предварительные требования

* .NET 6 SDK (или любая более новая версия .NET)
* Visual Studio 2022 или VS Code
* Действительная лицензия Aspose.BarCode для .NET (бесплатная оценочная версия подходит для тестирования)
* Базовое знакомство с консольными приложениями C#

Вы можете установить пакет Aspose.BarCode NuGet с помощью:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создать минимальный консольный проект

Создайте новый консольный проект и добавьте необходимые директивы `using`. Ниже приведён автономный пример; скопируйте его в `Program.cs` и запустите.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Почему этот шаг важен

* **Project scaffolding** гарантирует, что руководство можно запустить без дополнительной конфигурации.
* Пространства имён `using Aspose.BarCode.Generation;` и `using Aspose.BarCode;` предоставляют класс `BarcodeGenerator` и форматы изображений.
* Программное создание папки вывода предотвращает ошибки «каталог не найден» при первом запуске.

## Шаг 2: Сгенерировать заполненный штрих‑код Planet

Первый вызов `GeneratePlanetBarcode` передаёт `filled: true`. Это создаёт стандартный штрих‑код Planet, где каждая полоса отображается как сплошной чёрный прямоугольник.

* **Полученный файл:** `PostalPlanetFilledBars.png`
* **Визуальный индикатор:** Полосы черные, соответствуют почтовым требованиям для печатных отправлений.

### Ожидаемый результат

Запуск программы создаст изображение, похожее на показанное ниже (само изображение здесь не отображается, но при открытии файла вы увидите чёткий 6‑значный штрих‑код).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Шаг 3: Создать пустой штрих‑код (Planet с незаполненными полосами)

Чтобы **create empty barcode**, тот же метод вызывается с `filled: false`. Свойство `FilledBars` указывает Aspose.BarCode рисовать только контуры полос, оставляя внутреннюю часть прозрачной.

* **Полученный файл:** `PostalPlanetEmptyBars.png`
* **Сценарий использования:** Пустые штрих‑коды полезны, когда нужно, чтобы фон отображал логотип или цвет, при этом сохраняя читаемость штрих‑кода.

### Ожидаемый результат

Сгенерированный PNG содержит только контуры полос:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Шаг 4: Сгенерировать заполненный штрих‑код RM4SCC

RM4SCC — голландский почтовый стандарт штрих‑кодов. В примере используется та же X‑dimension (4 пикселя) для визуального соответствия штрих‑кодов Planet.

* **Полученный файл:** `PostalRM4SCCFilledBars.png`
* **Почему RM4SCC?** Он кодирует числовые данные в компактном формате, который принимают многие европейские почтовые службы.

### Ожидаемый результат

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Практические советы и распространённые подводные камни

| Tip | Explanation |
|-----|-------------|
| **Consistent X‑dimension** | Использование одинакового значения `XDimension.Pixels` для разных символогий обеспечивает единообразный внешний вид печатных этикеток. |
| **Do not reuse the same generator instance** | Изменение `FilledBars` в уже существующем генераторе может привести к неожиданным результатам; создавайте новый `BarcodeGenerator` для каждого отдельного штрих‑кода. |
| **Verify image format** | PNG — без потерь и идеален для штрих‑кодов; сжатие JPEG может размыть тонкие полосы, вызывая ошибки сканирования. |
| **License handling** | Если запускать код без лицензии, сгенерированные изображения будут содержать водяной знак. Примените лицензию в начале `Main` с помощью `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Thread safety** | `BarcodeGenerator` **не** является потокобезопасным. Создавайте отдельные экземпляры для каждого потока, если генерируете штрих‑коды параллельно. |

## Пограничные случаи, с которыми вы можете столкнуться

* **Ограничения длины данных** — штрих‑коды Planet принимают до 6 числовых символов. При передаче большего количества символов генерируется `ArgumentException`. Проверьте длину ввода перед вызовом генератора.
* **Ненумерические данные** — RM4SCC также ожидает числовой ввод. Для алфавитно‑цифровых данных нужен другой тип символогии (например, Code128). Тот же подход с установкой `FilledBars` работает для любого штрих‑кода, поддерживающего эту опцию.
* **Печать высокого разрешения** — если нужны штрих‑коды больше, чем отображаются на экране, увеличьте `XDimension.Pixels` (например, до 8 или 10) и при необходимости задайте `Resolution` в `generator.Parameters.Image`. Это сохраняет чёткость полос при печати 300 dpi.

## Полный перечень исходного файла

Ниже снова приведён весь исходный файл для быстрого копирования. Он включает все шаги, комментарии и необязательный фрагмент кода лицензии (закомментирован).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Заключение

Теперь вы знаете **how to generate barcode** изображения в C# с использованием Aspose.BarCode и можете **create empty barcode** варианты, переключая свойство `FilledBars`. В руководстве рассмотрено:

* Настройка консольного проекта и установка пакета Aspose.BarCode
* Генерация заполненных штрих‑кодов Planet и RM4SCC
* Создание пустого (только контур) штрих‑кода Planet
* Регулировка ширины полос для читаемости и обработка распространённых подводных камней

Далее изучайте другие символогии (Code128, QR, DataMatrix) и экспериментируйте с цветом, размером и форматами изображений. Интеграция генерации штрих‑кодов в веб‑API или Windows‑службу следует той же схеме — просто замените метод `Main` консольного приложения на точку входа вашего приложения.

Удачной разработки, и пусть ваши приложения начнут сканировать!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}