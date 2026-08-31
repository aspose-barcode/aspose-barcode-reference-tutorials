---
category: general
date: 2026-07-15
description: Создавайте изображение штрихкода планеты быстро с помощью C#. Узнайте,
  как генерировать почтовый штрихкод и как сохранять изображение штрихкода в формате
  PNG с использованием Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate postal barcode
- how to save barcode image
language: ru
lastmod: 2026-07-15
og_description: Создайте изображение штрихкода планеты на C#. Это руководство объясняет,
  как сгенерировать почтовый штрихкод и как сохранить изображение штрихкода с понятными
  примерами кода.
og_image_alt: Screenshot showing a generated Planet barcode image saved as PNG
og_title: Создайте изображение штрихкода Planet в C# – быстрое руководство по почтовым
  штрихкодам
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  headline: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  type: TechArticle
- description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  name: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  steps:
  - name: Why This Structure Works
    text: '- **Separate generators**: We instantiate two `BarcodeGenerator` objects
      because the `FilledBars` property is immutable once an image is rendered. Keeping
      them independent avoids side‑effects. - **X‑dimension choice**: A value of 4
      pixels balances readability and file size. If you need a higher‑reso'
  - name: Changing the Data Payload
    text: 'The `EncodeTypes.Planet` symbology expects numeric data up to 16 digits.
      To encode a different tracking number, just replace `"123456"` with your actual
      string:'
  - name: Adjusting Image Format
    text: If you need a JPEG for web delivery, swap `BarCodeImageFormat.Png` with
      `BarCodeImageFormat.Jpeg`. Remember JPEG introduces compression artifacts—avoid
      it for high‑precision scanning.
  - name: Handling Errors Gracefully
    text: 'When dealing with user‑supplied data, wrap the generation in a try‑catch
      block:'
  type: HowTo
- questions:
  - answer: Yes. Aspose.BarCode supports .NET Framework 4.5 and higher. Just change
      the target framework in your `.csproj` file.
    question: Does this work with .NET Framework 4.5?
  - answer: Replace `EncodeTypes.Planet` with any other enum value (e.g., `EncodeTypes.Code128`).
      The rest of the code stays the same.
    question: What if I need a different barcode symbology?
  - answer: 'Absolutely. Use `generator.Parameters.Barcode.BarColor = Color.Blue;`
      before saving. ## Conclusion You now know **how to create planet barcode image**
      in C#, **how to generate postal barcode** with the Aspose.BarCode library, and
      **how to save barcode image** as PNG files. The full example covered i'
    question: Can I change the bar color?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание изображения штрихкода Planet в C# – Как сгенерировать почтовый штрихкод
url: /ru/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрихкода Planet в C# – Как сгенерировать почтовый штрихкод

Когда‑нибудь вам нужно было **создать изображение штрихкода Planet** в проекте .NET, но вы не знали, с чего начать? Вы не одиноки. В этом руководстве мы пройдемся по **генерации почтового штрихкода** с использованием Aspose.BarCode, а затем покажем, **как сохранить изображение штрихкода** на диск в виде PNG‑файла.  

Представьте, что вы создаёте систему рассылки, которая печатает почтовые ярлыки «на лету» — надёжный генератор штрихкодов экономит часы ручной работы. К концу этого урока у вас будет готовое консольное приложение, которое выводит два PNG‑файла: один с заполненными полосами и другой только с контурами.

## Необходимые условия

Перед тем как перейти к коду, убедитесь, что у вас есть:

- .NET 6 SDK (или любая свежая версия .NET) установлен.
- Visual Studio 2022 или VS Code с расширениями C#.
- Пакет **Aspose.BarCode for .NET** NuGet. Вы можете добавить его через CLI:

```bash
dotnet add package Aspose.BarCode
```

Других внешних зависимостей не требуется.

## Шаг 1: Настройка каркаса проекта

Сначала создайте новый консольный проект и подключите библиотеку штрихкодов.

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

В папке теперь находится файл `Program.cs`, куда мы разместим всю нашу логику.

## Шаг 2: Написание полного кода – Создание изображения штрихкода Planet

Ниже приведена полная, автономная программа. Скопируйте её в `Program.cs` (заменив шаблон, сгенерированный `dotnet new`).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Namespace and class are optional in a top‑level program (C# 9+), but we keep them for clarity.
namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Create a Planet barcode generator with the desired data.
            // -----------------------------------------------------------------
            // The "Planet" symbology is used by many postal services for
            // tracking and sorting. Here we encode a simple numeric string.
            var generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // ---------------------------------------------------------------
            // 2️⃣  Set the X‑dimension (width of a single bar) to 4 pixels.
            // ---------------------------------------------------------------
            // XDimension controls the visual density of the barcode.
            // 4 px is a common default that works well on most printers.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 3️⃣  Save the barcode using the default *filled‑bars* appearance.
            // ---------------------------------------------------------------
            // BarCodeImageFormat.Png ensures a lossless image, perfect for
            // later processing or printing.
            string filledPath = "PlanetFilledBars.png";
            generator.Save(filledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Filled bars saved to {filledPath}");

            // -----------------------------------------------------------------
            // 4️⃣  Create another generator for the same data to show empty bars.
            // -----------------------------------------------------------------
            var emptyBarsGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyBarsGenerator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 5️⃣  Disable filled bars so only the outlines are drawn.
            // ---------------------------------------------------------------
            emptyBarsGenerator.Parameters.Barcode.FilledBars = false;

            // ---------------------------------------------------------------
            // 6️⃣  Save the barcode with empty bars.
            // ---------------------------------------------------------------
            string emptyPath = "PlanetEmptyBars.png";
            emptyBarsGenerator.Save(emptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Empty bars saved to {emptyPath}");

            // -----------------------------------------------------------------
            // 7️⃣  Quick verification – open the files if you’re on Windows.
            // -----------------------------------------------------------------
            // This is optional but handy when you run the demo locally.
            if (OperatingSystem.IsWindows())
            {
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = filledPath,
                    UseShellExecute = true
                });
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = emptyPath,
                    UseShellExecute = true
                });
            }
        }
    }
}
```

### Почему такая структура работает

- **Отдельные генераторы**: Мы создаём два объекта `BarcodeGenerator`, потому что свойство `FilledBars` становится неизменяемым после рендеринга изображения. Их независимое использование предотвращает побочные эффекты.
- **Выбор X‑размера**: Значение 4 пикселя обеспечивает баланс между читаемостью и размером файла. Если требуется печать более высокого разрешения, увеличьте до 6 или 8.
- **Сохранение в PNG**: PNG сохраняет чёткие границы штрихкода, что критично для оптических сканеров, используемых почтовыми службами.

## Шаг 3: Запуск демо и проверка результата

Скомпилируйте и выполните программу:

```bash
dotnet run
```

Вы должны увидеть сообщения в консоли, подтверждающие сохранение двух файлов. В папке проекта вы найдете:

- `PlanetFilledBars.png` – штрихкод с полностью заполненными полосами.
- `PlanetEmptyBars.png` – только контуры полос.

Ниже представлена визуальная иллюстрация того, как выглядит заполненная версия (изображение только для примера; ваш реальный вывод может немного отличаться в зависимости от настроек DPI).

![create planet barcode image example](https://example.com/planet-filled.png)

*Alt text: пример создания изображения штрихкода Planet, показывающий PNG штрихкода Planet с заполненными полосами.*

## Шаг 4: Настройка штрихкода – Распространённые варианты

### Изменение полезных данных

`EncodeTypes.Planet` символьный набор ожидает числовые данные длиной до 16 цифр. Чтобы закодировать другой номер отслеживания, просто замените `"123456"` на вашу строку:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Planet, "9876543210123456");
```

### Настройка формата изображения

Если нужен JPEG для веб‑доставки, замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. Учтите, что JPEG вводит артефакты сжатия — избегайте его для сканирования высокой точности.

### Обработка ошибок без сбоев

При работе с данными, предоставленными пользователем, оберните генерацию в блок try‑catch:

```csharp
try
{
    generator.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

Это гарантирует, что приложение не упадёт при недопустимом вводе.

## Шаг 5: Интеграция в более крупное приложение

В реальной системе рассылки вы, вероятно, будете генерировать штрихкод «на лету» и встраивать его в PDF или шаблон этикетки. Ниже короткий фрагмент, показывающий, как получить штрихкод как `byte[]` для дальнейшей обработки:

```csharp
using System.IO;

// Generate the image in memory
using (MemoryStream ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    byte[] barcodeBytes = ms.ToArray();

    // Pass barcodeBytes to a PDF library, send over a network, etc.
}
```

Теперь вы можете передать массив байтов в iTextSharp, QuestPDF или любой другой генератор документов, не обращаясь к файловой системе.

## Часто задаваемые вопросы (FAQ)

**В: Работает ли это с .NET Framework 4.5?**  
О: Да. Aspose.BarCode поддерживает .NET Framework 4.5 и выше. Просто измените целевую платформу в файле `.csproj`.

**В: Что делать, если нужен другой тип штрихкода?**  
О: Замените `EncodeTypes.Planet` на любое другое значение перечисления (например, `EncodeTypes.Code128`). Остальная часть кода остаётся без изменений.

**В: Можно ли изменить цвет полос?**  
О: Конечно. Используйте `generator.Parameters.Barcode.BarColor = Color.Blue;` перед сохранением.

## Заключение

Теперь вы знаете **как создать изображение штрихкода Planet** в C#, **как сгенерировать почтовый штрихкод** с помощью библиотеки Aspose.BarCode и **как сохранить изображение штрихкода** в виде PNG‑файлов. Полный пример охватывает инициализацию, настройку X‑размера, переключение заполнения полос и сохранение на диск — плюс несколько полезных советов для реальной интеграции.

Готовы к следующему шагу? Попробуйте внедрить сгенерированный PNG в PDF‑ярлык, поэкспериментировать с разными цветами или перейти к формату изображения более высокого разрешения. Возможности безграничны, когда вы комбинируете генерацию штрихкодов с современными инструментами .NET.

Если вы столкнулись с проблемами или у вас есть идеи для расширений, оставьте комментарий ниже. Счастливого кодинга!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как сохранить PNG, используя DataMatrix C40 с Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Как создать тихую зону штрихкода для Code 16K с использованием Aspose.BarCode для .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Генерация изображения штрихкода – Code 93 с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}