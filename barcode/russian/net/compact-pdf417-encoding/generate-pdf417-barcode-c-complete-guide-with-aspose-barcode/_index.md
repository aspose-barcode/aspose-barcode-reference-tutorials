---
category: general
date: 2026-08-03
description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Узнайте пошагово,
  как добавить метаданные Macro PDF417 и сохранить в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: ru
lastmod: 2026-08-03
og_description: Создайте штрих‑код PDF417 на C# с помощью Aspose.BarCode. Этот учебник
  показывает, как внедрить метаданные Macro PDF417 и экспортировать результат в виде
  изображения PNG.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Генерация штрих‑кода PDF417 на C# – пошаговое руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Генерация штрихкода PDF417 на C# – полное руководство с Aspose.BarCode
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация PDF417 штрих‑кода C# – полное руководство

Если вам необходимо **генерировать PDF417 barcode C#** для системы логистики или управления документами, этот учебник покажет, как сделать это с помощью Aspose.BarCode. Вы увидите, как настроить штрих‑код, внедрить метаданные Macro PDF417 и сохранить результат в виде PNG‑изображения всего за несколько строк кода.

Генерация PDF417 штрих‑кода в C# часто подразумевает работу с дополнительной информацией, такой как идентификаторы файлов, номера сегментов или метки времени. Это руководство охватывает эти детали, чтобы вам не пришлось искать их в разрозненной документации. К концу статьи у вас будет готовая к запуску программа, создающая соответствующее спецификации Macro PDF417 изображение штрих‑кода.

## Что вам понадобится

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Aspose.BarCode for .NET (v23.9 или новее) – установить через NuGet `Install-Package Aspose.BarCode`
- Среда разработки, например Visual Studio 2022 или Visual Studio Code
- Базовое знакомство с синтаксисом C#

> **Совет:** Используйте последнюю версию Aspose.BarCode, чтобы получить исправления ошибок и поддержку новейших спецификаций PDF417.

## Как сгенерировать PDF417 штрих‑код C# с помощью Aspose.BarCode

Процесс состоит из четырёх логических шагов. Каждый шаг оформлен в отдельном блоке кода, чтобы вы могли сразу скопировать, вставить и запустить его.

### Шаг 1: Создать генератор Macro PDF417

Сначала создайте экземпляр `BarcodeGenerator` с перечислением `EncodeTypes.MacroPdf417`. Конструктор также принимает текст, который нужно закодировать – в этом примере мы используем строку с Unicode‑символами, чтобы продемонстрировать поддержку полноширинных символов.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Почему это важно*: Тип `MacroPdf417` указывает Aspose.BarCode рассматривать символ как макро‑штрих‑код, способный нести дополнительную метаданные уровня файла. Без этого флага дополнительные поля, которые вы зададите позже, будут проигнорированы.

### Шаг 2: Настроить базовый внешний вид штрих‑кода

Далее задайте визуальный размер штрих‑кода. `XDimension.Pixels` контролирует ширину отдельного модуля (самого маленького чёрно‑белого квадрата), а `Pdf417.Columns` влияет на общую форму, задавая количество столбцов.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Почему это важно*: Меньшее значение `XDimension` даёт изображение более высокого разрешения, что полезно, когда штрих‑код сканируют с экрана. Изменение количества столбцов помогает разместить штрих‑код в ограниченном пространстве без потери ёмкости данных.

### Шаг 3: Заполнить метаданные Macro PDF417

Macro PDF417 позволяет внедрять информацию уровня файла, от которой зависят многие бэк‑офисные системы (например, ID файла, ID сегмента, метка времени). Ниже приведены свойства, иллюстрирующие наиболее часто используемые поля.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Почему это важно*: Каждое поле напрямую сопоставляется с сегментом спецификации макро‑штрих‑кода. Например, `MacroPdf417FileID` уникально идентифицирует логический файл, а `MacroPdf417SegmentsCount` сообщает сканеру, сколько частей следует ожидать. Точные метаданные позволяют downstream‑системам безошибочно воссоздать оригинальный документ.

### Шаг 4: Сохранить изображение штрих‑кода в PNG

Наконец, вызовите `Save`, чтобы записать штрих‑код на диск. PNG – формат без потерь, идеально подходящий для высококачественного сканирования.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Почему это важно*: Перечисление `BarCodeImageFormat.Png` гарантирует, что выходной файл будет содержать точно те пиксельные данные, которые вы настроили. Если нужен векторный формат для масштабирования, замените `Png` на `Svg` – Aspose.BarCode поддерживает его из коробки.

#### Ожидаемый результат

Запуск полной программы создаёт файл с именем **ExtPDF417Meta.png**. На изображении виден плотный, многострочный символ PDF417, включающий текст «Åspóse.Barcóde©» и макро‑метаданные, которые вы задали. Сканирование штрих‑кода совместимым считывателем PDF417 возвращает исходный текст плюс структурированный блок данных, содержащий ID файла, ID сегмента, метку времени и другие поля.

![Screenshot of generated PDF417 barcode](/images/pdf417-example.png){: .center-image alt="Скриншот сгенерированного PDF417 штрих‑кода"}

## Полный исходный код (готов к копированию)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Как проверить результат

1. Откройте `ExtPDF417Meta.png` в любой программе просмотра изображений.  
2. Используйте приложение‑сканер PDF417 (например, *Zebra Scanner* или *BarCode Reader* на Android/iOS).  
3. Убедитесь, что декодированный полезный груз содержит исходный текст и блок, похожий на JSON, с макро‑полями, которые вы задали.

## Часто задаваемые вопросы и обработка граничных случаев

| Вопрос | Ответ |
|----------|--------|
| **Можно ли генерировать векторное изображение вместо PNG?** | Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Svg`. Остальная часть кода остаётся без изменений. |
| **Что делать, если мои данные превышают стандартную ёмкость?** | Увеличьте `Pdf417.Columns` или задайте `Pdf417.Rows` вручную. Большие значения позволяют разместить больше кодовых слов в сегменте. |
| **Поддерживается ли Unicode в кодируемом тексте?** | Абсолютно. В примере используется «Åspóse.Barcóde©». Aspose.BarCode автоматически переключается на кодировку UTF‑8 при необходимости. |
| **Нужно ли лицензировать Aspose.BarCode?** | Для продакшна следует применить лицензию, чтобы избавиться от водяного знака оценки. Вызовите `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` перед созданием генератора. |
| **Как обрабатывать ошибки при сохранении файла?** | Оберните вызов `Save` в блок `try/catch` и логируйте `IOException` или `BarCodeException` для отладки. |

## Заключение

Теперь вы знаете, как **генерировать PDF417 barcode C#** с помощью Aspose.BarCode, внедрять полные метаданные Macro PDF417 и экспортировать результат в виде высококачественного PNG‑изображения. Шаги — создание генератора, настройка внешнего вида, заполнение метаданных и сохранение изображения — образуют переиспользуемый шаблон, который можно адаптировать для счетов‑фактур, транспортных этикеток или любой другой задачи, требующей богатых данных в штрих‑коде.

### Следующие шаги

- Поэкспериментируйте с другими форматами штрих‑кодов (например, QR, Code128), изменив `EncodeTypes`.  
- Исследуйте `Pdf417.ErrorCorrectionLevel`, чтобы повысить надёжность сканирования при плохом освещении.  
- Интегрируйте сгенерированное изображение в PDF‑отчёт с помощью Aspose.PDF для сквозной автоматизации документооборота.  

Не стесняйтесь менять поля метаданных в соответствии с вашими бизнес‑правилами, и пусть генерация штрих‑кодов станет бесшовной частью ваших C#‑приложений. Приятного кодинга!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode (на немецком)](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode library – Добавить штрих‑код в PDF с помощью Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}