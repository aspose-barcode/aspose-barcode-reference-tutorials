---
category: general
date: 2026-09-29
description: Узнайте, как быстро генерировать штрих‑код PDF417 на C#. Этот пошаговый
  учебник охватывает настройки штрих‑кода, вывод изображения и распространённые подводные
  камни.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- PDF417 barcode settings
- C# barcode library
- barcode image export
language: ru
lastmod: 2026-09-29
og_description: Создайте штрих‑код PDF417 на C# с помощью этого подробного руководства.
  Следуйте полному примеру, чтобы создать и экспортировать изображение штрих‑кода.
og_image_alt: Screenshot showing generated PDF417 barcode saved as PNG
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  headline: How to generate PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# quickly. This step‑by‑step
    tutorial covers barcode settings, image output, and common pitfalls.
  name: How to generate PDF417 barcode in C# – complete programming guide
  steps:
  - name: Adjusting error correction level
    text: PDF417 supports five error‑correction levels (0‑8). Higher levels increase
      robustness at the cost of size.
  - name: Changing image format
    text: 'If you need a vector format for scaling, export as SVG instead of PNG:'
  - name: Handling very long strings
    text: 'When the input exceeds the default capacity, increase the number of rows:'
  - name: Using a different library
    text: If you prefer an open‑source alternative, the `ZXing.Net` package also supports
      PDF417. The API differs, but the overall flow—create a writer, set options,
      render to bitmap—remains the same.
  - name: Next steps
    text: '* Explore **PDF417 barcode settings** such as row count and aspect ratio
      for custom layouts. * Integrate the barcode generation into an ASP.NET Core
      API to serve images on demand. * Combine this code with a QR‑code generator
      for multi‑symbology documents.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Как сгенерировать штрих‑код PDF417 в C# – полное руководство по программированию
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-programming-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 в C# – полное руководство по программированию

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как это сделать. Вы увидите полностью готовый пример, который генерирует штрих‑код PDF417, настраивает его размеры и сохраняет как PNG‑изображение.

Создание штрих‑кода – распространённая задача для систем учёта, платформ билетирования и автоматизации документооборота. К концу этого урока вы сможете интегрировать генерацию штрих‑кодов в любой проект на C# без поиска дополнительных фрагментов кода.

## Что вы узнаете

* Как создать генератор штрих‑кода PDF417 с пользовательским текстом  
* Какие параметры управляют X‑размером и количеством колонок  
* Как экспортировать штрих‑код в PNG‑файл высокого качества  
* Советы по работе с Unicode‑символами и настройке размера изображения  

**Предварительные требования**  
* .NET 6.0 или новее (код также работает с .NET Framework 4.6+)  
* Ссылка на пакет NuGet `Aspose.BarCode` (или любую совместимую библиотеку штрих‑кодов)  
* Базовое знакомство с синтаксисом C# и Visual Studio или вашей любимой IDE  

Если вы задаётесь вопросом **как сгенерировать штрих‑код PDF417** в первый раз, читайте дальше – шаги расположены в логическом порядке от настройки до проверки.

## Шаг 1: Установите библиотеку штрих‑кодов

Прежде чем писать код, добавьте SDK штрих‑кодов в ваш проект. Наиболее широко используемая библиотека для PDF417 в C# – **Aspose.BarCode for .NET**.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Используйте последнюю стабильную версию (в данный момент 24.5), чтобы получить улучшения производительности и полную поддержку Unicode.

## Шаг 2: Создайте генератор штрих‑кода PDF417

Суть процесса – создать экземпляр `BarcodeGenerator` с перечислением `EncodeTypes.Pdf417`. Конструктор также принимает текст, который нужно закодировать.

```csharp
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,               // PDF417 symbology
    "Åspóse.Barcóde©");               // Text includes Unicode characters
```

*Почему это важно*: Флаг `EncodeTypes.Pdf417` указывает библиотеке использовать стандарт PDF417, поддерживающий большие блоки данных и коррекцию ошибок. Передача Unicode‑строки демонстрирует, что генератор корректно обрабатывает символы вне ASCII.

## Шаг 3: Настройте X‑размер (ширина модуля)

X‑размер определяет ширину одного модуля штрих‑кода (самой маленькой чёрной или белой полоски). Указание его в пикселях даёт точный контроль над конечным размером изображения.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение `2` пикселя даёт компактный штрих‑код, который всё ещё легко читается большинством сканеров. Если нужен более крупный штрих‑код для печати на плакате, увеличьте это значение пропорционально.

## Шаг 4: Задайте количество колонок

PDF417 позволяет указать количество колонок, что влияет на соотношение сторон штрих‑кода. Меньшее количество колонок делает штрих‑код выше; больше колонок – шире.

```csharp
// Step 4: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Три колонки создают сбалансированную форму, подходящую для большинства экранных приложений. Для плотных данных можно увеличить число до 5 или 7.

## Шаг 5: Сохраните штрих‑код как PNG‑изображение

Наконец, экспортируйте сгенерированный штрих‑код в файл. PNG сохраняет резкие края и поддерживает прозрачность, что делает его идеальным для отображения в UI.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Pdf417Basic.png");

barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

При выполнении кода вы найдёте `Pdf417Basic.png` на рабочем столе. Открытие файла покажет чёткий штрих‑код PDF417, кодирующий строку **Åspóse.Barcóde©**.

## Проверка результата

Чтобы убедиться, что штрих‑код содержит нужные данные, можно воспользоваться любой бесплатной программой‑сканером PDF417 (например, приложением ZXing для Android) или онлайн‑декодером. Сканируйте сохранённый PNG; декодированный текст должен точно совпадать с исходным вводом, включая специальные символы.

**Ожидаемый результат** – PNG‑изображение, похожее на это (для иллюстрации):

![Сгенерированный штрих‑код PDF417, сохранённый как PNG – пример генерации pdf417 штрих‑кода](https://example.com/assets/pdf417-sample.png "пример генерации pdf417 штрих‑кода")

*Текст alt выше удовлетворяет требованию alt‑текста изображения для основного ключевого слова.*

## Распространённые варианты и граничные случаи

### Настройка уровня коррекции ошибок

PDF417 поддерживает пять уровней коррекции ошибок (0‑8). Более высокие уровни повышают надёжность за счёт увеличения размера.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // medium protection
```

### Смена формата изображения

Если нужен векторный формат для масштабирования, экспортируйте в SVG вместо PNG:

```csharp
barcodeGenerator.Save("Pdf417Basic.svg", BarCodeImageFormat.Svg);
```

### Обработка очень длинных строк

Когда ввод превышает стандартную ёмкость, увеличьте количество строк:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 10;
```

### Использование другой библиотеки

Если вы предпочитаете открытое решение, пакет `ZXing.Net` также поддерживает PDF417. API отличается, но общий процесс – создать writer, задать параметры, отрисовать в bitmap – остаётся тем же.

## Полный, готовый к запуску пример

Ниже представлен полный код программы, который можно скопировать в консольное приложение и сразу запустить.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize the generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose a compact column count
        generator.Parameters.Barcode.Pdf417.Columns = 3;

        // Optional: increase error correction for noisy environments
        generator.Parameters.Barcode.Pdf417.ErrorLevel = 5;

        // 4️⃣ Determine output path (desktop for easy access)
        string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
        string filePath = Path.Combine(desktop, "Pdf417Basic.png");

        // 5️⃣ Export as PNG
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to: {filePath}");
    }
}
```

Запустите программу (`dotnet run`), затем откройте сгенерированный файл, чтобы увидеть штрих‑код. Консоль выведет путь к сохранённому изображению.

## Заключение

Теперь вы знаете **как сгенерировать штрих‑код PDF417** в C# от начала до конца. Создав `BarcodeGenerator`, настроив X‑размер и количество колонок и экспортировав в PNG, вы сможете внедрить генерацию штрих‑кодов в любое решение на .NET. Поэкспериментируйте с уровнями коррекции ошибок, различными форматами изображений или большими объёмами данных, чтобы адаптировать штрих‑код под свои задачи.

### Следующие шаги

* Изучите **настройки штрих‑кода PDF417**, такие как количество строк и соотношение сторон, для создания пользовательских макетов.  
* Интегрируйте генерацию штрих‑кода в API ASP.NET Core, чтобы обслуживать изображения по запросу.  
* Скомбинируйте этот код с генератором QR‑кодов для документов с несколькими симболами.

Не стесняйтесь адаптировать пример, делиться результатами или задавать вопросы в комментариях. Приятного кодинга!


## Что изучать дальше?


Ниже представлены руководства, охватывающие смежные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}