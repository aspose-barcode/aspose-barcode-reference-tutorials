---
category: general
date: 2026-10-15
description: Быстро создавайте PNG‑изображения штрихкодов с помощью C#. Узнайте, как
  генерировать штрихкоды, изменять строки, настраивать параметры штрихкода и создавать
  штрихкод PDF417 в одном руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: ru
lastmod: 2026-10-15
og_description: Быстро создавайте PNG‑изображения штрихкодов на C#. В этом руководстве
  показано, как генерировать штрихкоды, изменять строки, настраивать штрихкод и генерировать
  штрихкод PDF417 с чистым кодом.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Создайте PNG‑изображение штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Создание PNG‑штрихкода PDF417 на C# – полное руководство
url: /ru/net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание PNG штрихкода PDF417 на C# – полное руководство

Если вам нужно **create barcode PNG** из кода C#, это руководство покажет, как это сделать. Мы пройдем процесс генерации штрихкода PDF417, изменения строк и настройки всех ключевых параметров перед сохранением результата в виде PNG‑изображения.

Вы узнаете, как программно **generate barcode** изображения, настроить макет в соответствии с вашим дизайном и понять параметры настройки внешнего вида штрихкода. Внешние инструменты не требуются — только библиотека Aspose.BarCode (или любой совместимый .NET пакет для штрихкодов) и несколько строк кода.

## Что понадобится

- .NET 6.0 или новее (в примере используется .NET 6, но подойдёт любая современная версия .NET)
- Ссылка на пакет NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)
- Базовые знания C# и Visual Studio (или вашей предпочтительной IDE)

> **Pro tip:** Если вы предпочитаете бесплатную альтернативу, тот же набор API доступен в открытой библиотеке `ZXing.Net`; однако приведённые ниже фрагменты кода ориентированы на Aspose.BarCode, поскольку она предоставляет прямой контроль над макетом PDF417.

## Шаг 1: Настройте проект и добавьте библиотеку штрихкодов

Создайте новое консольное приложение и добавьте пакет NuGet:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Затем откройте `Program.cs` и добавьте необходимые директивы `using`:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Эти пространства имён предоставляют класс `BarcodeGenerator` и перечисление `EncodeTypes`, которые вы будете использовать для **generate PDF417 barcode** изображений.

## Шаг 2: Создание PNG штрихкода – базовый генератор

Первая исполняемая строка создаёт экземпляр `BarcodeGenerator`, настроенный для кодирования PDF417. Это основа **how to generate barcode** изображений.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Why this matters:** Флаг `EncodeTypes.Pdf417` указывает библиотеке, какую символьную схему использовать. Второй аргумент (`"Layout test"`) — это исходный текст, который будет закодирован в штрихкод.

## Шаг 3: Как настроить штрихкод – задать размер модуля

Модуль (или измерение X) определяет наименьший печатаемый элемент штрихкода. Его настройка меняет общий размер изображения, не влияя на плотность данных.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Установка `Pixels = 2` даёт компактный, высоко‑разрешённый результат **create barcode PNG**, который хорошо подходит для веб‑миниатюр и печати.

## Шаг 4: Как изменить строки – настройка макета PDF417

PDF417 позволяет явно управлять количеством столбцов и строк. Этот шаг отвечает на вопрос **how to change rows** в штрихкоде.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Edge case:** Если запросить больше строк, чем требуется данным, библиотека автоматически добавит строки‑заполнители. Наоборот, запрос слишком малого количества строк может вызвать исключение, поскольку данные не помещаются.

## Шаг 5: Сохраните сгенерированный штрихкод в файл PNG

Наконец, запишите изображение на диск. Это завершает процесс **create barcode PNG**.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

При запуске программы вы увидите файл `Pdf417_4x9.png` в папке проекта. Изображение содержит штрихкод PDF417 с ровно 4 столбцами и 9 строками, отрисованный с модулями по 2 пикселя.

### Полный рабочий пример

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Ожидаемый вывод** (консоль):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Откройте PNG‑файл, и вы увидите чистый штрихкод PDF417, готовый к сканированию.

## Как сгенерировать штрихкод с другими данными

Если вам нужно **generate barcode** для другой строки, просто замените второй аргумент конструктора `BarcodeGenerator`:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

Те же шаги настройки (размер модуля, строки, столбцы) применимы, позволяя переиспользовать код для разных полезных нагрузок.

## Как динамически изменять строки в зависимости от длины содержимого

Иногда количество строк должно адаптироваться к длине кодируемого текста. Вы можете вычислить безопасное количество строк перед созданием генератора:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

Этот фрагмент гарантирует, что вы никогда не запросите менее трёх строк (минимум библиотеки), одновременно увеличивая их количество для более длинных данных.

## Как настроить штрихкод для разных форматов изображений

Хотя руководство сосредоточено на PNG, вы можете переключиться на JPEG, BMP или TIFF, изменив перечисление `BarCodeImageFormat`:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG остаётся лучшим выбором для без потерь качества, особенно когда штрихкод будет печататься.

## Распространённые ошибки и их устранение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|--------|
| Штрихкод выглядит размытым | Слишком большое измерение X или масштабирование изображения после сохранения | Держите `XDimension.Pixels` ≤ 3 для экранного использования, либо увеличьте разрешение с помощью векторного формата (PDF) |
| Сканер не может прочитать штрихкод | Слишком мало строк для длины данных | Увеличьте `Pdf417.Rows` или позвольте библиотеке автоматически подобрать размер, убрав явную настройку строк |
| `ArgumentOutOfRangeException` при сохранении | Каталог вывода не существует | Убедитесь, что `outputPath` указывает на существующую папку, или создайте её с помощью `Directory.CreateDirectory` |

## Итоги

В этом руководстве показано, как **create barcode PNG** файлы в C# с использованием символьной схемы PDF417. Вы узнали:

- **How to generate barcode** с помощью класса `BarcodeGenerator`  
- **How to change rows** и столбцы для управления макетом  
- **How to configure barcode** параметры, такие как размер модуля и формат изображения  
- Как **generate PDF417 barcode** и сохранить его как PNG‑изображение

Теперь у вас есть переиспользуемый блок кода, который можно адаптировать под разные данные, форматы изображений или требования к макету.

## Следующие шаги

- Поэкспериментируйте с `Pdf417.ErrorCorrectionLevel` для повышения надёжности сканирования при низкокачественной печати.  
- Объедините несколько штрихкодов в один PDF с помощью Aspose.PDF для пакетной генерации этикеток.  
- Исследуйте другие символьные схемы (`EncodeTypes.Code128`, `EncodeTypes.QR`), меняя значение перечисления — это соответствует второму ключевому слову **generate pdf417 barcode**, демонстрируя более широкие возможности.

Удачной разработки и наслаждайтесь созданием чётких PNG‑штрихкодов для любых приложений!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрихкод PDF417 и экспортировать PNG в C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [Как генерировать штрихкоды PDF417 в C# с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Как создать PNG штрихкода с пользовательским соотношением сторон в C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}