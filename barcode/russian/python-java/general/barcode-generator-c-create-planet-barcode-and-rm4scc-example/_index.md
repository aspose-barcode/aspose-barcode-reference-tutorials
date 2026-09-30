---
category: general
date: 2026-08-03
description: Учебник по генерации штрихкодов на C#, показывающий, как создать штрихкод
  Planet с помощью Aspose.BarCode, установить X‑размер и сохранить в виде PNG‑изображений.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: ru
lastmod: 2026-08-03
og_description: Учебник по генератору штрих‑кодов на C# пошагово покажет, как создать
  штрих‑код Planet, настроить X‑размер и сохранить его в формате PNG с помощью Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Генератор штрих‑кодов C# – создаём штрих‑код Planet шаг за шагом
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Генератор штрихкодов C# – пример создания штрихкода Planet и RM4SCC
url: /ru/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генератор штрих‑кодов C# – пример создания штрих‑кода Planet и RM4SCC

Если вам нужен **barcode generator C#**, способный создавать почтовые символы, это руководство покажет, как **create Planet barcode** изображения с помощью Aspose.BarCode. Вы увидите, как настроить X‑dimension, сгенерировать соответствующий штрих‑код RM4SCC и сохранить оба в виде PNG‑файлов — всё в нескольких лаконичных шагах.

В учебнике описано всё, что необходимо для запуска кода на .NET 6 или новее, объясняется, почему важна каждая настройка, и указаны распространённые подводные камни, такие как неверная ширина модуля или отсутствие прав на запись в каталог. К концу вы получите два готовых к печати изображения штрих‑кодов, соответствующих стандартам Planet и RM4SCC.

## Prerequisites

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6 SDK (или любая версия .NET, поддерживаемая Aspose.BarCode)
* Visual Studio 2022 или любой другой предпочитаемый IDE для C#
* NuGet‑ссылка на **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Права на запись в папку, где планируется сохранять PNG‑файлы

Дополнительные внешние сервисы не требуются; библиотека выполняет всё кодирование локально.

## Step 1: Initialise the barcode generator C# object

Первая задача — создать экземпляр `BarcodeGenerator`. Конструктор принимает тип штрих‑кода (`EncodeTypes.Planet`) и данные для кодирования.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Почему этот шаг?*  
`BarcodeGenerator` — точка входа для любого генерируемого штрих‑кода. Выбор `EncodeTypes.Planet` сообщает библиотеке использовать спецификацию ISO/IEC 24723, применяемую многими почтовыми службами.

## Step 2: Set the X‑dimension (module width) for the Planet barcode

X‑dimension определяет ширину одного модуля штрих‑кода (самой маленькой полоски или пробела). Значение **4 пикселя** хорошо подходит для большинства принтеров этикеток.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Почему это важно*  
Если модуль слишком узкий, штрих‑код может стать нечитаемым; если слишком широкий — размер этикетки будет избыточным. Настройка `Pixels` позволяет точно подобрать ширину штрих‑кода под разрешение вашего принтера.

## Step 3: Save the Planet barcode as a PNG image

Aspose.BarCode автоматически рассчитывает высоту штрих‑кода в зависимости от выбранной символьной системы, поэтому вам нужно указать только путь к файлу и формат.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Подсказка*  
Замените `YOUR_DIRECTORY` на абсолютный или относительный путь, существующий на вашем компьютере. Если каталог не существует, метод `Save` выбросит `DirectoryNotFoundException`.

**Ожидаемый результат** – PNG‑файл, похожий на иллюстрацию ниже (изображение не отображается, но вы увидите классический штрих‑код Planet с числовой нагрузкой `123456`).

## Step 4: Initialise a second generator for the RM4SCC barcode

Во многих почтовых системах требуется наличие одновременно штрих‑кодов Planet и RM4SCC. Создайте новый экземпляр `BarcodeGenerator` для символьной системы RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Почему отдельный экземпляр?*  
Каждая символьная система имеет собственный набор параметров. Повторное использование того же генератора может непреднамеренно перенести настройки (например, X‑dimension), которые не оптимальны для второго штрих‑кода.

## Step 5: Configure the X‑dimension for the RM4SCC barcode

RM4SCC также учитывает настройку X‑dimension, поэтому применяем ту же ширину в пикселях для визуального соответствия.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Если нужен более высокий штрих‑код (например, для больших этикеток), можно также задать `Height.Pixels`. Оставив параметр пустым, библиотека автоматически вычислит оптимальную высоту.

## Step 6: Save the RM4SCC barcode as a PNG image

Наконец, сохраняем штрих‑код RM4SCC на диск.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла — `PostalPlanetBarHeightNone.png` и `PostalRM4SCCBarHeightNone.png` — которые можно вставлять в почтовые ярлыки, печатать на конвертах или отправлять в стороннюю типографию.

## Optional: Adjusting height or using other image formats

Если ваш процесс требует конкретной высоты штрих‑кода или другого формата изображения (например, JPEG или BMP), можно изменить параметры перед вызовом `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – При установке пользовательской высоты убедитесь, что значение соответствует минимальной высоте, требуемой ISO‑стандартом; иначе штрих‑код может не пройти проверку.

## Common pitfalls and how to avoid them

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| `DirectoryNotFoundException` | Целевой каталог не существует или указано неверное имя. | Сначала создайте каталог или используйте `Path.Combine` с `Environment.CurrentDirectory`. |
| Штрих‑код нечитаем на принтерах с низким разрешением | X‑dimension слишком мал для DPI принтера. | Увеличьте `XDimension.Pixels` до 5 – 6 для принтеров 203 dpi, либо протестируйте на образце этикетки. |
| Неправильный тип символьной системы | Передан `EncodeTypes.Code128` вместо `EncodeTypes.Planet`. | Проверьте, что значение `EncodeTypes` соответствует требуемому почтовому стандарту. |
| Null reference на `Parameters` | Используется более старая версия Aspose.BarCode с отличающимся API. | Обновите до последней версии NuGet‑пакета (v23.12 или новее). |

## Full runnable example

Ниже представлена полная программа, которую можно скопировать, вставить и запустить. В ней есть `using`‑директивы, обработка ошибок и комментарии, поясняющие каждую строку.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Запуск программы создаст папку `Barcodes` рядом с исполняемым файлом и поместит в неё два PNG‑файла. Откройте их в любом просмотрщике изображений, чтобы убедиться в корректности вывода.

## Conclusion

Теперь у вас есть **barcode generator C#** решение, которое может **create Planet barcode** изображения, настроить X‑dimension для оптимальной печати и создать соответствующий штрих‑код RM4SCC — всё в паре строк кода. Подход работает с .NET 6+, требует только NuGet‑пакет Aspose.BarCode и может быть расширен другими символьными системами, такими как Code128, QR или DataMatrix, заменой значения `EncodeTypes`.

### What’s next?

* Поэкспериментируйте с различными значениями `XDimension.Pixels`, чтобы подобрать их под DPI вашего принтера.  
* Генерируйте штрих‑коды в других форматах (PDF, SVG), изменив значение перечисления `BarCodeImageFormat`.  
* Объедините два PNG‑файла в один ярлык с помощью графической библиотеки, например **SkiaSharp**.  
* Изучите полный API Aspose.BarCode для продвинутых функций, таких как проверка контрольных сумм или пользовательские шрифты.

Не стесняйтесь адаптировать код для пакетной обработки или интегрировать его в веб‑службу ASP.NET Core, которая будет возвращать изображения штрих‑кодов по запросу. Приятного кодинга!

## What Should You Learn Next?

Следующие учебные материалы охватывают близкие темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}