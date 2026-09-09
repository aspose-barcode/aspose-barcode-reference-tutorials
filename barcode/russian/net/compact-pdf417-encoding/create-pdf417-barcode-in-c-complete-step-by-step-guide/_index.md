---
category: general
date: 2026-07-18
description: Быстро создавайте штрих‑код PDF417 с помощью C#. Узнайте, как генерировать
  штрих‑код, задавать параметры и сохранять изображения – включена обработка AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: ru
lastmod: 2026-07-18
og_description: Создайте штрих‑код PDF417 на C# с полным пошаговым руководством. Узнайте,
  как генерировать штрих‑код, настраивать параметры и сохранять изображения, обрабатывая
  AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Создание штрих‑кода PDF417 на C# – быстрый, гибкий, полностью готовый пример
  кода
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Создание штрих‑кода PDF417 на C# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# – Полное пошаговое руководство

Когда‑то вам нужно **создать pdf417 barcode**, но вы не знали, какую библиотеку или настройки выбрать? Вы не одиноки — многие разработчики сталкиваются с этим, когда впервые пробуют GS1‑Micro‑PDF417. Хорошая новость в том, что несколькими строками C# можно быстро сгенерировать правильно отформатированный штрих‑код, настроить его внешний вид и сохранить изображение сразу на диск.

В этом руководстве мы пройдём **как генерировать barcode** с помощью библиотеки Aspose.BarCode, покажем **как задать параметры** такие как X‑dimension и количество колонок, а также продемонстрируем **как сохранить изображение** для вариантов AI 10 и AI 21. К концу вы получите переиспользуемый фрагмент кода, который можно вставить в любой .NET‑проект.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- .NET 6+ или .NET Framework 4.7.2 (подойдёт любой современный рантайм)
- Visual Studio 2022 или ваш любимый редактор C#
- NuGet‑пакет **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Папка с правом записи, куда будут сохраняться PNG‑файлы

И всё — никаких дополнительных инструментов, никакой сложной конфигурации. Готовы? Поехали.

## Шаг 1: Создание PDF417 Barcode в формате GS1‑Micro

Первое, что мы делаем, — **create pdf417 barcode** объект и передаём ему начальные данные AI. В GS1‑Micro‑PDF417 AI 10 (номер партии) часто используется в качестве отправной точки, поэтому закодируем его сразу.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Почему это важно:** `EncodeTypes.GS1MicroPdf417` указывает библиотеке следовать спецификации GS1‑Micro, автоматически добавляя скобки AI. Если пропустить этот параметр, вы получите обычный PDF417, который может быть не считываем в розничных условиях.

## Шаг 2: Как задать параметры для штрих‑кода

Теперь, когда у нас есть экземпляр штрих‑кода, нужно точно настроить его визуальные характеристики. Здесь и вступает в действие **how to set parameters**. Мы изменим три часто используемых свойства:

1. **X‑dimension** — контролирует ширину самой маленькой полоски (в пикселях)
2. **Column count** — влияет на общую форму; меньше колонок = высокий штрих‑код
3. **IsLinked** — включает опциональный модуль ссылки, связывающий штрих‑код со строкой данных

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Совет профессионала:** Если вы ориентируетесь на мобильные сканеры, увеличьте X‑dimension до 3‑4 пикселей; более крупные модули лучше выдерживают низкое разрешение камер.

## Шаг 3: Как сохранить изображение – первая версия (AI 10)

После настройки генератора мы наконец **how to save image**. Метод `Save` записывает штрих‑код в файл в указанном формате. Здесь мы используем PNG, потому что он сохраняет чёткие края без артефактов сжатия.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

На данный момент в вашей `outputDir` должен появиться файл `GS1MicroPdf417_AI10.png`. Откройте его в любом просмотрщике — вы увидите чистый, контрастный PDF417, готовый к печати.

## Шаг 4: Переключаемся на другой AI (AI 21) и сохраняем снова

Часто требуется закодировать другой идентификатор приложения, например AI 21 (серийный номер). Достаточно изменить свойство `CodeText`. Это демонстрирует **barcode ai 10** против **barcode ai 21** в одном примере.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **А если нужно больше AI?** Просто конкатенируйте их в одной строке, например `"(10)ABCD(21)12345(240)XYZ"`. Библиотека автоматически распознаёт скобки.

## Полный рабочий пример

Объединив всё вместе, получаем самостоятельную программу, которую можно скопировать в консольное приложение:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Ожидаемый результат:** В `C:\Barcodes\` появятся два PNG‑файла — `GS1MicroPdf417_AI10.png` и `GS1MicroPdf417_AI21.png`. Оба содержат сканируемый PDF417; первый кодирует AI 10, второй — AI 21.

## Распространённые ошибки и как их избежать

- **Отсутствие прав к папке:** Если `Save` бросает `UnauthorizedAccessException`, проверьте, что путь существует и у приложения есть права на запись.
- **Неправильный формат AI:** Пропуск скобок (`(10)`) приведёт к тому, что штрих‑код будет воспринят как обычные данные, нарушив проверку GS1.
- **Слишком маленький X‑dimension:** Полоски тоньше 1 пикселя могут исчезнуть при изменении размера изображения. Для экранного отображения используйте минимум 2 пикселя.

## Следующие шаги и смежные темы

Теперь, когда вы знаете **how to generate barcode**, **how to set parameters** и **how to save image**, вы можете изучить:

- Добавление **human‑readable text** под штрих‑кодом (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Экспорт в **PDF** вместо PNG (`BarCodeImageFormat.Pdf`)
- Интеграцию генерации штрих‑кода в **ASP.NET Core API** для создания изображений «на лету»

Каждая из этих тем опирается на фундамент, заложенный в этом руководстве.

---

### Краткое резюме

- **Create pdf417 barcode** с помощью `BarcodeGenerator` и `EncodeTypes.GS1MicroPdf417`
- **How to set parameters**: X‑dimension, количество колонок и включение ссылки
- **How to save image** в PNG для вариантов AI 10 и AI 21
- Обработали **barcode ai 10** и переключились на **barcode ai 21** изменив одно свойство

Попробуйте, поиграйте с настройками, и у вас будет надёжный движок штрих‑кодов, готовый к продакшну. Есть вопросы или нужен более глубокий разбор? Оставляйте комментарий ниже — приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом гиде. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}