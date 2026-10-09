---
category: general
date: 2026-10-08
description: Генерируйте штрих‑код PDF417 на C# и узнайте, как эффективно создавать
  изображения PDF417 с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: ru
lastmod: 2026-10-08
og_description: Создайте штрих‑код PDF417 на C# с пошаговым руководством. Узнайте,
  как генерировать PDF417 и сохранять изображение штрих‑кода в формате PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Создать штрих‑код PDF417 и изображение штрих‑кода в C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Генерировать штрих‑код PDF417 и создавать изображение штрих‑кода C#
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 и создание изображения штрих‑кода C#

Если вам нужно **generate PDF417 barcode** в приложении .NET, этот учебник покажет, как это сделать. Вы увидите полный, исполняемый пример, который создает штрих‑код, настраивает его макет и сохраняет результат в виде PNG‑изображения.

Создание PDF417 barcode является распространенной потребностью для транспортных этикеток, посадочных талонов и систем инвентаризации. К концу этого руководства вы сможете **how to generate PDF417** с тонким контролем над размером и макетом, а также узнаете, как **create barcode image C#** файлы, которые можно отображать в пользовательском интерфейсе или отправлять на принтер.

## Предварительные требования

- .NET 6.0 или новее (код также работает с .NET Framework 4.7.2+)
- Visual Studio 2022 или любой совместимый с C# IDE
- Aspose.BarCode for .NET (бесплатная пробная версия или лицензированная)  
  Установите её через NuGet:

```bash
dotnet add package Aspose.BarCode
```

Дополнительная конфигурация не требуется; библиотека обрабатывает PNG‑кодирование внутри.

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новый консольный проект и добавьте необходимые директивы `using`. Этот блок содержит всё, что нужно для компиляции примера.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Почему этот шаг важен*: импорт пространства имён `Aspose.BarCode.Generation` предоставляет доступ к `BarcodeGenerator`, `EncodeTypes` и объектам параметров, используемым для настройки штрих‑кода.

## Шаг 2: Генерация PDF417 barcode с нужным текстом

Внутри `Main` создайте экземпляр `BarcodeGenerator` с `EncodeTypes.Pdf417`. Конструктор принимает тип штрих‑кода и текст, который вы хотите закодировать.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Объяснение*: `EncodeTypes.Pdf417` указывает библиотеке создавать символьную схему PDF417. Строка `"Layout demo"` становится данными, закодированными в штрих‑коде.

## Шаг 3: Точная настройка размера штрих‑кода с помощью X‑dimension

X‑dimension управляет шириной отдельного модуля (самого маленького черно‑белого квадрата). Установка в пикселях дает точный контроль над окончательным размером изображения.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Почему это важно*: меньший X‑dimension приводит к более компактному штрих‑коду, что полезно при ограниченном пространстве на этикетке или элементе интерфейса.

## Шаг 4: Настройка макета PDF417 (колонки и строки)

PDF417 позволяет задавать количество колонок и строк. Изменение этих значений меняет соотношение сторон штрих‑кода.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Объяснение*: При 4 колонках и 9 строках штрих‑код становится выше, чем шире, что соответствует многим форматам печати билетов.

## Шаг 5: Сохранение сгенерированного штрих‑кода как PNG‑изображения

Наконец, запишите штрих‑код в файл. Перечисление `BarCodeImageFormat.Png` обеспечивает сжатие без потерь.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Что происходит*: `Save` создаёт файл изображения на диске. При необходимости вы можете заменить `BarCodeImageFormat.Png` на `Jpeg` или `Bmp`.

### Полный пример в одном блоке

Ниже приведена полная, готовая к запуску программа. Замените `YOUR_DIRECTORY` реальным путём к папке на вашем компьютере.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Запустите программу (`dotnet run`) и откройте полученный файл `LayoutPdf417.png`. Вы должны увидеть чистый PDF417 barcode, который кодирует текст *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Сгенерированный PDF417 barcode, сохранённый как PNG"}

*Ожидаемый результат*: PNG‑файл размером примерно 150 × 300 пикселей (размер зависит от X‑dimension), содержащий сканируемый PDF417 barcode.

## Общие варианты и граничные случаи

| Сценарий | Как адаптировать код |
|----------|----------------------|
| **Разный набор данных** | Измените второй аргумент `BarcodeGenerator` (`"Layout demo"` → любую строку, до 1 800 символов). |
| **Более высокое разрешение** | Увеличьте `XDimension.Pixels` (например, `4`) или задайте `Resolution` через `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Прозрачный фон** | Используйте `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Встраивание в Windows Forms PictureBox** | Вместо `Save` вызовите `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Обработка ошибок** | Обёрните код генерации в блок `try…catch`, чтобы перехватывать `BarCodeException` для неподдерживаемых символов. |

## Полезные советы

- **Validate the barcode**: После сохранения вы можете загрузить PNG с помощью SDK сканера штрих‑кодов, чтобы убедиться, что данные соответствуют исходной строке.
- **Performance**: Повторное использование одного экземпляра `BarcodeGenerator` для нескольких штрих‑кодов уменьшает накладные расходы на выделение памяти.
- **Security**: Если закодированные данные содержат конфиденциальную информацию, рассмотрите возможность их шифрования перед передачей в генератор.

## Заключение

Теперь вы знаете, как **generate PDF417 barcode** в C# и **create barcode image C#** файлы, отвечающие требованиям пользовательского макета. Полный пример демонстрирует инициализацию генератора, настройку размера и макета, а также сохранение результата в PNG. Отсюда вы можете изучать дополнительные возможности, такие как настройка цвета, встраивание логотипов или пакетная генерация нескольких штрих‑кодов для массовой печати.

---

*Следующие шаги*:  
- Экспериментируйте с другими символьными схемами (Code128, QR), используя тот же класс `BarcodeGenerator`.  
- Узнайте, как считывать PDF417 штрих‑коды с помощью `BarCodeReader` из Aspose.BarCode.  
- Интегрируйте сгенерированный PNG в представления ASP.NET Core MVC для динамического отображения штрих‑кода.

## Что следует изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сохранить штрих‑код и сгенерировать PDF417 с помощью Aspose в C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Как сгенерировать PDF417 Barcode с Aspose – Полное руководство](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Как сгенерировать PDF417 barcode в C# с пользовательскими размерами](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}