---
category: general
date: 2026-07-21
description: Быстро генерируйте штрих‑коды на C# с помощью Aspose.BarCode. Узнайте,
  как создать штрих‑код DataBar, настроить его размер и экспортировать изображение
  штрих‑кода за несколько шагов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: ru
lastmod: 2026-07-21
og_description: Создавайте штрих‑коды на C# с помощью Aspose.BarCode. Создавайте штрих‑код
  DataBar, настраивайте его размер и мгновенно экспортируйте изображение.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Генерация штрихкода C# – Создание штрихкодов DataBar с пользовательским
  размером
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Генерация штрихкода C# – Создание штрихкода DataBar
url: /ru/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode C# – Create DataBar barcode

Хотите **generate barcode C#** без бесконечного изучения документации? Вы попали по адресу. В этом руководстве мы пройдем процесс создания **DataBar barcode**, настройки его размеров и, наконец, **exporting the barcode image** — всё это с помощью нескольких строк кода C#.

Представьте, что вам нужен компактный ярлык продукта, который помещается на крошечной бирке. Символика DataBar Expanded Stacked решает задачу, а с помощью Aspose.BarCode вы можете точно управлять количеством столбцов или строк. Готовы? Погрузимся.

## Что вы сможете сделать

- **Create a DataBar barcode** (вариант “expanded stacked”) с нуля.  
- **Customize barcode size** путем прямой установки столбцов или строк.  
- **Change barcode dimensions** «на лету», не пересоздавая генератор.  
- **Export barcode image** в PNG (или любой формат, поддерживаемый Aspose).  

## Требования

- .NET 6.0 или новее (код также работает на .NET Framework 4.7+).  
- Действительная лицензия Aspose.BarCode for .NET (или можно использовать пробный режим).  
- Любая удобная IDE — Visual Studio, Rider или VS Code подойдут.  

Если вы ещё не установили пакет NuGet, выполните:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — никаких дополнительных зависимостей.

## Шаг 1: Настройка генератора штрих‑кода (Как **generate barcode C#**)

Сначала нам нужен экземпляр `BarcodeGenerator`, указывающий на символогию **DataBar Expanded Stacked**. Этот объект является движком, который позже создаст изображение.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Почему это важно*: перечисление `EncodeTypes.DatabarExpandedStacked` сообщает Aspose, что нам нужна stacked‑версия, что идеально подходит для узких пространств. Текст, который мы передаём, становится закодированным значением; вы можете заменить его любой числовой строкой, необходимой вашему приложению.

## Шаг 2: **Customize barcode size** – установка столбцов

Штрих‑коды DataBar позволяют влиять на визуальную плотность, указывая количество **columns** *или* **rows**. Начнём со столбцов. Количество строк будет рассчитано автоматически, чтобы штрих‑код оставался валидным.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Полезный совет*: столбцы влияют на ширину штрих‑кода. Больше столбцов → шире штрих‑код, что может повысить надёжность сканирования на принтерах с низким разрешением.

## Шаг 3: **Export barcode image** с настройкой столбцов

Теперь сохраняем изображение на диск. Вы можете выбрать PNG, JPEG, BMP или даже SVG. Здесь используется PNG для чёткого, без потерь вывода.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Expected result** – Откройте `DatabarCols4.png`, и вы увидите аккуратно сложенный DataBar с четырьмя столбцами. Он выглядит как плотный набор вертикальных полос, идеально подходящий для небольшого ярлыка.

## Шаг 4: **Change barcode dimensions** – установка строк вместо столбцов

Иногда нужен более высокий штрих‑код, а не более широкий. Переключаемся на управление строками; Aspose автоматически пересчитает столбцы.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Почему переключаться?* Строки влияют на высоту штрих‑кода. Больше строк делают символ выше, что удобно, когда есть вертикальное пространство, но ограничена ширина.

## Шаг 5: **Export barcode image** с настройкой строк

Сохраните вторую вариацию. Обратите внимание, что имя файла отражает изменение; вы также можете оставить оба изображения для сравнения.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Result** – `DatabarRows3.png` теперь отображает более высо́кую версию тех же данных, всё ещё полностью сканируемую.

## Полный рабочий пример

Объединив всё вместе, представляем самостоятельное консольное приложение, которое вы можете скопировать и запустить сразу:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Запустите программу, затем откройте два PNG‑файла. Теперь вы **generated barcode C#**, **customized barcode size**, **changed barcode dimensions** и **exported the barcode image** — всё за менее чем минуту.

## Часто задаваемые вопросы и особые случаи

- **What if I need a different image format?**  
  Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp`, `Gif` или `Svg`. API автоматически выполнит конвертацию.

- **Can I change both rows and columns simultaneously?**  
  Технически можно задать оба параметра, но Aspose отдаст приоритет последнему изменённому свойству. Безопаснее установить *одну* измерение и позволить библиотеке вычислить другое для валидного DataBar.

- **How do I apply a foreground/background color?**  
  Используйте `barcodeGen.Parameters.Barcode.ForegroundColor` и `BackgroundColor`. Пример:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked поддерживает до 74 числовых символов (или 30 буквенно‑цифровых). Превышение этого лимита вызывает исключение.

## Следующие шаги

Теперь, когда вы освоили основы **create databar barcode**, рассмотрите:

- Добавление **text annotations** под штрих‑кодом (`barcodeGen.Parameters.CaptionAbove.Text`).
- Встраивание PNG напрямую в PDF с помощью Aspose.PDF.
- Генерацию штрих‑кодов пакетно, перебирая CSV‑файл с идентификаторами продуктов.

Каждая из этих тем опирается на тот же объект `BarcodeGenerator`, поэтому не придётся начинать с нуля.

---

**Bottom line**: теперь вы знаете, как **generate barcode C#**, **customize barcode size**, **change barcode dimensions** и **export barcode image** с помощью Aspose.BarCode. Поэкспериментируйте с значениями столбцов/строк, меняйте форматы изображений и интегрируйте код в вашу систему учёта или POS. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}