---
category: general
date: 2026-07-18
description: Создайте штрих‑код PDF417 в C# с помощью генератора штрих‑кодов PDF417
  для C#. Следуйте пошаговому руководству, чтобы сформировать расширенный код текста,
  настроить внешний вид и сохранить изображение.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: ru
lastmod: 2026-07-18
og_description: Создайте штрих‑код PDF417 на C# мгновенно. Это руководство показывает,
  как использовать генератор штрих‑кода PDF417 в C#, настроить расширенный режим и
  экспортировать PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Создание штрихкода PDF417 на C# – Полное руководство по генератору
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Создание штрихкода PDF417 в C# — руководство по генератору штрихкодов
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрихкода PDF417 в C# – Руководство по генератору штрихкодов

Когда‑то вам нужно **создать штрихкод PDF417** в приложении C#, но вы не знаете, с чего начать? Вы не одиноки — многие разработчики сталкиваются с тем же самым, когда впервые берутся за двумерные штрихкоды. Хорошая новость? С помощью встроенного **C# PDF417 barcode generator** вы можете создать полностью функциональный штрихкод всего в несколько строк кода.

В этом руководстве мы пройдем весь процесс: построим расширенный codetext, комбинирующий разные наборы символов, настроим генератор для нужного визуального стиля и, наконец, сохраним штрихкод в файл PNG. К концу вы получите готовый фрагмент кода, который можно вставить в любой .NET‑проект, а также советы по работе с краевыми случаями, такими как Unicode‑символы или пользовательские ширины модулей.

---

## Что понадобится

Прежде чем начать, убедитесь, что на вашем компьютере установлено следующее:

- **.NET 6.0** или новее (пример также работает с .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (или любая совместимая библиотека, предоставляющая `BarcodeGenerator`, `EncodeTypes.Pdf417` и т.д.)
- Редактор кода — Visual Studio, Rider или даже VS Code подойдут
- Папка, в которую можно записывать файлы, так как генератор сохранит PNG туда

Это всё — никаких дополнительных пакетов NuGet, кроме самой библиотеки штрихкодов, не требуется.

---

## Пошаговое руководство по **созданию штрихкода PDF417**

### 1. Установите библиотеку штрихкодов

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Пакет добавит пространство имён `Aspose.BarCode`, в котором находится класс `BarcodeGenerator`, который мы будем использовать дальше.

### 2. Постройте расширенный codetext

PDF417 поддерживает **расширенное кодирование**, позволяя смешивать разные наборы символов в одном штрихкоде. Ниже мы создаём три сегмента:

- Сегмент Windows‑1251 (кириллица)
- Сегмент UTF‑8, содержащий Unicode‑символы (японские кандзи «собака» и «право»)
- Сегмент обычного текста

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Почему это важно:**  
Если использовать только обычный текст, вы ограничены набором ASCII по умолчанию. Явно объявляя сегменты ECI (Extended Channel Interpretation), вы гарантируете, что сканеры правильно интерпретируют каждую часть, независимо от языка или символов.

### 3. Инициализируйте **C# PDF417 barcode generator**

Теперь, когда у нас есть корректная строка codetext, передаём её генератору. Оператор `using` гарантирует автоматическое освобождение ресурсов.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Настройте внешний вид и режим кодирования

Настройки по умолчанию дают крошечный штрихкод, который может быть трудно читаемым. Давайте подправим несколько параметров:

- **X‑Dimension** — контролирует ширину каждого модуля (размер в пикселях)
- **EncodeMode** — указывает движку обрабатывать ввод в расширенном режиме
- **TwoDDisplayText** — необязательный человекочитаемый текст под штрихкодом

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Совет профессионала:** Если печатаете штрихкод на этикеточном принтере, увеличьте `XDimension` до 20 px и более; большинству сканеров нравится немного дополнительного пространства.

### 5. Сохраните изображение штрихкода

Наконец, запишите изображение на диск. Библиотека поддерживает PNG, JPEG, BMP и несколько векторных форматов — PNG является безопасным выбором, так как сохраняет чёткие границы.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Убедитесь, что `YOUR_DIRECTORY` существует и доступен для записи. После запуска программы вы должны увидеть файл, похожий на скриншот ниже.

![Созданный штрихкод PDF417 с помощью C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "Созданный штрихкод PDF417 с помощью C# PDF417 barcode generator")

---

## Использование **C# PDF417 barcode generator** – более глубокий взгляд

### Работа с Unicode и специальными символами

Если передать Unicode‑символы напрямую в обычный штрихкод, генератор может переключиться на резервное кодирование, что приводит к искажённому выводу. Используя `AddECICodetext`, вы явно указываете кодеку, какой набор символов применять, устраняя догадки. Если понадобится поддержка **Arabic**, **Hebrew** или **emoji**, просто выберите соответствующее значение `ECIEncodings`.

### Регулировка уровня коррекции ошибок

PDF417 предлагает четыре уровня коррекции ошибок (0‑8). Более высокие уровни повышают устойчивость, но также увеличивают размер штрихкода. Настроить их можно так:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Масштабирование для печати и экрана

Для отображения на экране можно оставить значение по умолчанию — 96 dpi. Для печати высокого разрешения (300 dpi и выше) задайте:

```csharp
generator.Parameters.ImageResolution = 300;
```

Это гарантирует, что сохранённый PNG сохранит достаточную детализацию для лазерных принтеров.

### Распространённые подводные камни

- **Отсутствует директива `using`** — забыв `using Aspose.BarCode.Encoding;` вы получите ошибку, что `ECIEncodings` не определён.
- **Папка не найдена** — метод `Save` не создаёт промежуточные каталоги; создайте их заранее или используйте `Path.Combine` с `Environment.CurrentDirectory`.
- **Неправильный режим кодирования** — если оставить `EncodeMode` как `Pdf417EncodeMode.Auto`, библиотека может трактовать ваш расширенный codetext как обычный текст, удаляя маркеры ECI.

---

## Полный готовый к запуску пример

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}