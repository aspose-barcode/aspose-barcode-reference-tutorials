---
category: general
date: 2026-07-18
description: Узнайте, как генерировать изображения штрих‑кодов с помощью .NET‑генератора
  штрих‑кодов и легко менять высоту штрих‑кода для символов GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: ru
lastmod: 2026-07-18
og_description: .NET‑генератор штрихкодов позволяет быстро создавать изображения штрихкодов.
  Это руководство показывает, как генерировать штрихкоды, регулировать высоту полос
  и сохранять файлы PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Измените высоту штрихкода с помощью .NET‑генератора штрихкодов
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET‑генератор штрихкодов – изменить высоту штрихкода
url: /ru/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – изменение высоты штрих‑кода

Когда‑нибудь задумывались **как генерировать штрих‑коды** без необходимости использовать десятки сторонних инструментов? В мире .NET существует удивительно простой способ сделать это, и ключевым элементом является **.net barcode generator**. Всего несколькими строками C# вы можете создать символ GS1‑Databar Omni‑Directional, отрегулировать высоту полос и сохранить результат в файл PNG.

Если вы разрабатываете систему учёта, принтер этикеток для доставки или любое приложение, которому нужен сканируемый код, этот учебник поможет перейти от нуля к работающему штрих‑коду за несколько минут. Мы пройдёмся по полному коду, объясним, почему каждая настройка важна, и покажем, как **изменить высоту штрих‑кода** без нарушения спецификации.

## Что вам понадобится

- .NET 6.0 или новее (API работает одинаково на .NET Framework 4.7+)
- Ссылка на библиотеку штрих‑кодов (например, Aspose.BarCode for .NET – те же классы используются во многих коммерческих наборах)
- Среда разработки (Visual Studio, Rider или VS Code с расширением C#)
- Папка, в которой у вас есть права на запись — в ней учебник сохранит файлы PNG

Вот и всё. Нет дополнительных пакетов NuGet, кроме самой библиотеки штрих‑кодов.

## Использование .net barcode generator для изменения высоты штрих‑кода

Ниже представлен **полный, исполняемый консольный пример**. Вставьте его в новый C#‑проект, укажите папку вывода и нажмите F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Почему каждая строка важна

| Строка | Причина |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Создаёт экземпляр **.net barcode generator** с нужной символикой и данными. Перечисление `EncodeTypes.DatabarOmniDirectional` указывает библиотеке использовать формат GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimension — это ширина самой тонкой полосы. Установка значения *2 пикселя* даёт чёткое изображение на большинстве мониторов при небольшом размере файла. |
| `BarHeight.Pixels = 30;` | Это шаг **изменения высоты штрих‑кода**, определяющий высоту каждой полосы. Высота 30 пикселей — хороший вариант по умолчанию для небольших этикеток. |
| `generator.Save(...);` | Сохраняет штрих‑код в файл PNG. PNG — без потерь, что означает, что сканеры видят точно сгенерированный шаблон. |
| `BarHeight.Pixels = 60;` | Здесь мы **изменяем высоту штрих‑кода** ещё раз — на этот раз до 60 пикселей. Библиотека автоматически перерисовывает символ с новой размерностью при повторном вызове `Save`. |
| `Console.WriteLine(...);` | Выводит быстрый отзыв о том, что процесс завершён без исключений. |

> **Pro tip:** Если вам нужен вывод более высокого разрешения для печати, замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Tiff` и увеличьте свойство `Resolution` (например, `generator.Parameters.ImageResolution = 300;`). Высота полос останется учтённой, только будет отрисована с более тонким DPI.

## Как генерировать изображения штрих‑кодов с различными настройками

Приведённый выше фрагмент покрывает основы, но в реальных сценариях часто требуются дополнительные настройки:

### Регулировка X‑dimension для больших печатей
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Увеличение X‑dimension делает весь штрих‑код больше, не меняя закодированных данных. Это удобно, когда печатаете на больших этикетках.

### Переключение форматов вывода
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG масштабируется бесконечно, что идеально подходит для веб‑сканеров, которым нужны чёткие векторные изображения.

### Добавление читаемого человеком текста
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Включение `CodeTextVisible` добавляет исходные данные под штрих‑кодом, что полезно для проверки во время тестирования.

## Распространённые подводные камни при **изменении высоты штрих‑кода**

1. **Слишком маленькая высота** – Некоторые сканеры требуют минимальную высоту полос (часто 10 мм в физических единицах). Если задать `BarHeight.Pixels` слишком низко, полученное изображение может быть нечитаемым реальным сканером. Всегда тестируйте с целевым оборудованием.  
2. **Несоответствие X‑dimension и высоты** – Огромная высота полос при крошечной X‑dimension выглядит растянутой и может вызвать ошибки декодирования. Стремитесь к сбалансированному соотношению (примерно 3:1‑5:1), если только спецификация не предписывает иначе.  
3. **Забыли сбросить параметры** – Генератор сохраняет состояние между сохранениями. Если изменить `BarHeight` для одного изображения и затем использовать тот же экземпляр для другого штрих‑кода, прежняя высота останется. Сбросьте свойство или создайте новый `BarcodeGenerator` для каждого отдельного штрих‑кода.

## Полный пример от начала до конца (включая установку NuGet)

Если вы начинаете с нуля, выполните следующие шаги, чтобы запустить проект:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Замените автоматически сгенерированный `Program.cs` кодом из блока выше, **не забудьте заменить `YOUR_DIRECTORY`** на что‑то вроде `Path.Combine(Environment.CurrentDirectory, "output")`. Затем:

```bash
dotnet run
```

Вы должны увидеть два PNG‑файла в папке `output`:

- `DatabarBarHeight30Pixels.png` – компактный штрих‑код высотой 30 пикселей.  
- `DatabarBarHeight60Pixels.png` – более высокий вариант высотой 60 пикселей.

Оба изображения выглядят схоже, но второе имеет заметно более длинные полосы, что облегчает чтение сканерами низкого разрешения.

![Barcode height example](/images/barcode-height.png){alt="Вывод .net barcode generator, показывающий разные высоты полос"}

## Итоги и дальнейшие шаги

Мы рассмотрели, как **генерировать штрих‑коды** с помощью **.net barcode generator**, точно настроили свойство **изменения высоты штрих‑кода** и сохранили результаты в формате PNG. Ключевые выводы:

- Создайте генератор с правильным `EncodeTypes`.  
- Управляйте визуальными размерами через `XDimension` и `BarHeight`.  
- Вызывайте `Save` после каждого изменения, чтобы сохранить новое изображение.  
- Настройте разрешение, формат,  

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как сгенерировать Aztec‑barcode с пользовательским соотношением сторон, используя Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как создать расширенный код текста dotcode с помощью Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Как генерировать DataMatrix штрих‑коды (ECC 200) с помощью Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}