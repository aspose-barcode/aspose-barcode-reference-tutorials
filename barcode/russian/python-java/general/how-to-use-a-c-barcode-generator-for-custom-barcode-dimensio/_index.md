---
category: general
date: 2026-08-22
description: Узнайте, как генератор штрихкодов на C# может изменять размер штрихкода,
  настраивать его параметры и создавать несколько строк в штрихкоде DataBar Expanded
  Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: ru
lastmod: 2026-08-22
og_description: Учебник по генерации штрихкодов на C#, показывающий, как изменить
  размер штрихкода, настроить размеры и генерировать несколько строк штрихкода с пользовательскими
  настройками.
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: Руководство по генератору штрихкодов на C# – изменение размера, строк и
  столбцов
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Как использовать генератор штрихкодов на C# для пользовательских размеров штрихкода
url: /ru/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для пользовательских размеров штрих‑кода

Если вам нужен **c# barcode generator**, позволяющий **изменять размер штрих‑кода** «на лету», это руководство покажет, как это сделать. Мы сгенерируем штрих‑код DataBar Expanded Stacked, изменим его ширину и высоту, задав пользовательские столбцы и строки, и сохраним три примерных изображения.

В конце урока у вас будет полностью готовая, исполняемая консольная программа, демонстрирующая **пользовательские размеры штрих‑кода**, **генерацию штрих‑кода в нескольких строках** и **регулировку размеров штрих‑кода** без выхода из IDE.

## Что понадобится

| Требование | Почему это важно |
|------------|------------------|
| .NET 6.0 SDK или новее | Предоставляет среду выполнения для консольного приложения |
| Visual Studio 2022 (или VS Code) | Предоставляет редактор с IntelliSense |
| NuGet‑пакет Aspose.Barcode for .NET | Содержит класс `BarcodeGenerator`, используемый в примерах |
| Права записи в папку на диске | Генератор сохраняет PNG‑файлы в этом месте |

Установите библиотеку через NuGet CLI:

```bash
dotnet add package Aspose.Barcode
```

Или используйте менеджер пакетов Visual Studio:

```powershell
Install-Package Aspose.Barcode
```

## Шаг 1: Создание базового генератора штрих‑кодов C#

Создайте новый консольный проект и добавьте необходимые директивы `using`. Этот шаг создаёт минимальный **c# barcode generator**, способный выводить простой штрих‑код DataBar Expanded Stacked.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**Почему это работает:** `EncodeTypes.DatabarExpandedStacked` указывает генератору, какой символьный набор использовать. Метод `Save` записывает PNG‑файл на диск. На данном этапе штрих‑код использует размер по умолчанию, заданный библиотекой.

## Шаг 2: Изменение ширины штрих‑кода путём настройки столбцов

Ширина штрих‑кода DataBar Expanded Stacked управляется свойством **columns**. Установка этого свойства позволяет **c# barcode generator** создавать более широкий или более узкий штрих‑код.

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**Объяснение:** Столбцы влияют на количество горизонтальных модулей. Больше столбцов — более широкая полоса, что полезно, когда требуется дополнительное место для более длинного читаемого человеком текста или при печати на широких этикетках.

## Шаг 3: Генерация штрих‑кода в нескольких строках для управления высотой

Высота регулируется свойством **rows**. Увеличивая количество строк, вы **generate barcode multiple rows** и делаете символ выше — идеально для сканирования высокого разрешения.

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**Почему строки важны:** Строки добавляют вертикальные модули. Более высокий штрих‑код может улучшить читаемость на фонах с низким контрастом или когда расстояние фокусировки сканера меняется.

## Шаг 4: Комбинация пользовательских столбцов и строк для полного контроля

Теперь, когда вы знаете, как **adjust barcode dimensions**, вы можете задать оба свойства одновременно. Этот шаг создаёт штрих‑код с шестью столбцами и десятью строками, демонстрируя полную гибкость **c# barcode generator**.

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**Результат:** Файл `DatabarCols6Rows10.png` содержит штрих‑код, который шире и выше стандартных размеров, подтверждая, что вы можете **adjust barcode dimensions** под любые требования макета.

## Полный исполняемый пример

Ниже представлена полная программа, включающая все четыре шага. Скопируйте её в `Program.cs`, выполните `dotnet run` и проверьте папку `C:\Temp\Barcodes\` — там появятся четыре PNG‑файла.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### Ожидаемый результат

Запуск программы создаёт четыре PNG‑файла:

| Имя файла                | Описание |
|--------------------------|----------|
| `DefaultDatabar.png`     | Стандартная ширина и высота |
| `DatabarCols4.png`       | Широкий штрих‑код (4 столбца) |
| `DatabarRows3.png`       | Высокий штрих‑код (3 строки) |
| `DatabarCols6Rows10.png` | И шире, и выше (6 столбцов, 10 строк) |

Откройте любой PNG в просмотрщике изображений — вы увидите шаблон DataBar Expanded Stacked, изменённый точно в соответствии с указанными параметрами.

## Распространённые ошибки и профессиональные советы

- **Недопустимые значения столбцов/строк** — библиотека бросает `ArgumentException`, если задать значение вне поддерживаемого диапазона (1‑12 для столбцов, 1‑10 для строк). Проверяйте ввод перед присвоением.
- **Разрешения каталога** — если целевая папка защищена, `Save` завершится с ошибкой. Используйте `System.IO.Directory.CreateDirectory`, как показано, чтобы гарантировать существование пути.
- **Производительность** — создание большого количества штрих‑кодов в цикле может сильно нагружать CPU. Переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только `Columns`/`Rows` между сохранениями, чтобы сократить накладные расходы на создание объектов.
- **Особенности сканирования** — слишком высокие или широкие штрих‑коды могут выйти за пределы поля зрения сканера. После изменения размеров тестируйте работу с вашим оборудованием.

## Заключение

Теперь у вас есть надёжный пример **c# barcode generator**, позволяющий **change barcode size**, **custom barcode dimensions**, **generate barcode multiple rows** и **adjust barcode dimensions** под любые задачи. Путём изменения свойств `Columns` и `Rows` вы получаете точный контроль над визуальным размером штрих‑кода DataBar Expanded Stacked.

Не стесняйтесь экспериментировать с другими символьными наборами (`EncodeTypes.QR`, `EncodeTypes.Code128`) или форматами вывода (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`). Один и тот же шаблон — создать `BarcodeGenerator`, задать свойства размеров, затем вызвать `Save` — применим ко всему API Aspose.Barcode.

**Следующие шаги**

- Исследуйте **уровни коррекции ошибок** для QR‑кодов.
- Сочетайте **пользовательские цвета** и **фоновое изображение**, чтобы брендировать ваши штрих‑коды.
- Интегрируйте генератор в веб‑службу ASP.NET Core для создания штрих‑кодов «по запросу».

Счастливого кодинга!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}