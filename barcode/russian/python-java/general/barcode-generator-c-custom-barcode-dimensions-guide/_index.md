---
category: general
date: 2026-07-21
description: Учебник по генератору штрихкодов на C#, показывающий, как установить
  пользовательские размеры штрихкода, отрегулировать высоту пикселей штрихкода и быстро
  изменить высоту изображения штрихкода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- custom barcode dimensions
- barcode pixel height
- barcode image height
- change barcode height
language: ru
lastmod: 2026-07-21
og_description: Генератор штрихкодов c# позволяет вам контролировать каждый пиксель.
  Узнайте, как задавать пользовательские размеры штрихкода, настраивать высоту пикселя
  и легко изменять высоту штрихкода.
og_image_alt: Screenshot of barcode generator c# output with custom dimensions
og_title: Генератор штрихкодов C# – Освойте пользовательские размеры за считанные
  минуты
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  headline: Barcode generator c# – Custom barcode dimensions guide
  type: TechArticle
- description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  name: Barcode generator c# – Custom barcode dimensions guide
  steps:
  - name: What if I need a different **barcode image height** than the default?
    text: 'You can control the overall canvas size via `GeneratorParameters.ImageHeight.Pixels`.
      For example:'
  - name: How does `XDimension` affect scanning reliability?
    text: A smaller `XDimension` creates thinner bars, which can look sharper but
      may be harder for low‑resolution scanners. As a rule of thumb, keep `XDimension`
      ≥ 2 px for 300 dpi printing and ≥ 3 px for 200 dpi.
  - name: Can I switch from PNG to another format without changing code?
    text: 'Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`,
      `Bmp`, etc. Just replace the enum value:'
  - name: What if I need to generate dozens of barcodes with varying heights?
    text: 'Wrap the height‑changing logic in a loop:'
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Генератор штрихкодов C# – Руководство по пользовательским размерам штрихкода
url: /ru/python-java/general/barcode-generator-c-custom-barcode-dimensions-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генератор штрих‑кодов c# – Руководство по пользовательским размерам штрих‑кода

Когда‑нибудь задумывались, как заставить **barcode generator c#** создавать точно тот размер, который вам нужен? Вы не одиноки. Будь то печать этикеток на производственной линии или генерация QR‑подобных меток для системы учёта, правильные размеры имеют решающее значение.

В этом руководстве мы пройдём через полностью готовый к запуску пример, показывающий, как задать **custom barcode dimensions**, отрегулировать **barcode pixel height** и, наконец, **change barcode height** «на лету». Никаких расплывчатых ссылок — только код, который вы можете скопировать, вставить и запустить уже сегодня.

## Что вы узнаете

- Как создать **barcode generator c#** для символьного набора DataBar Omnidirectional.  
- Разницу между **barcode pixel height** и общей **barcode image height**.  
- Два практических способа **change barcode height** без пересоздания генератора.  
- Советы по сохранению изображения с точными требуемыми размерами.

Вам понадобится лишь современная среда .NET (4.7+ или .NET 6) и библиотека Aspose.BarCode for .NET (или любой совместимый API). Если они уже установлены, приступаем.

## Шаг 1: Настройка проекта и импорт библиотеки

Сначала создайте новое консольное приложение (или добавьте код в существующее). Затем установите пакет NuGet:

```bash
dotnet add package Aspose.BarCode
```

Теперь подключите необходимые пространства имён:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing;   // only if you manipulate the bitmap later
```

> **Pro tip:** Если вы используете Visual Studio, менеджер NuGet автоматически добавит ссылку — вручную искать DLL не придётся.

## Шаг 2: Создать экземпляр barcode generator c# с кодом DataBar Omnidirectional

Класс **barcode generator c#** — ваша точка входа. Закодируем простое значение GTIN‑14:

```csharp
// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

На данном этапе генератор знает, *что* кодировать, но не *как* велики должны быть полосы. Здесь вступают в силу **custom barcode dimensions**.

## Шаг 3: Определить пользовательские размеры штрих‑кода – фокус на barcode pixel height

Два свойства управляют вертикальным размером:

| Property | What it does | Typical range |
|----------|--------------|---------------|
| `XDimension.Pixels` | Width of a single bar (the “module”) | 1‑5 px is common |
| `BarHeight.Pixels` | Height of the bars themselves | 30‑100 px depending on printing DPI |

Установим скромную ширину в 2 пикселя и **barcode pixel height** в 30 px:

```csharp
// Step 3: Apply custom barcode dimensions
generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel tall bars
```

Почему именно 30 px? На принтере с разрешением 300 dpi 30 px≈0,1 дюйма — идеальный размер для большинства розничных этикеток. При необходимости увеличьте значение для более выразительного визуального эффекта.

## Шаг 4: Сохранить изображение штрих‑кода с нужной barcode image height

При вызове `Save` библиотека автоматически добавляет отступы, чтобы учесть **barcode image height** (общую высоту bitmap). Финальное изображение будет выше 30 px из‑за зон тишины и любой подписи, которую вы можете включить. Пример записи первого PNG:

```csharp
// Step 4: Export the first image (30‑pixel bar height)
string output30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
generator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 30‑pixel barcode to {output30}");
```

Откройте полученный файл — вы увидите чёткий DataBar с **barcode image height**, слегка превышающим 30 px, что соответствует ожиданиям большинства сканеров.

## Шаг 5: Изменить высоту штрих‑кода без пересоздания генератора

Изменить высоту полосы так же просто, как поправить одно свойство. Пересоздавать объект `BarcodeGenerator` не требуется:

```csharp
// Step 5: Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
generator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 60‑pixel barcode to {output60}");
```

Обратите внимание, что мы изменили только `BarHeight.Pixels`. Это демонстрирует возможность **change barcode height** — быстро, экономно по памяти и идеально для пакетной обработки, когда каждая этикетка может требовать разного размера.

## Ожидаемый результат

Запуск полной программы создаёт два PNG‑файла:

- `DatabarBarHeight30Pixels.png` – полосы высотой 30 px, общая высота изображения около 40 px (включая зоны тишины).  
- `DatabarBarHeight60Pixels.png` – полосы высотой 60 px, общая высота изображения около 70 px.

Оба изображения содержат одинаковые закодированные данные, поэтому любой сканер, читающий первое, без проблем прочитает и второе без изменения настроек.

## Полный исходный код – копировать, вставлять, запускать

```csharp
// ------------------------------------------------------------
// Barcode generator c# – Custom dimensions demo
// ------------------------------------------------------------
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Omnidirectional
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set custom barcode dimensions (X‑dimension & bar height)
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
        generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel bars

        // 3️⃣ Save first image – demonstrates barcode pixel height = 30
        string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(path30, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 30‑pixel barcode to {path30}");

        // 4️⃣ Change barcode height – now 60 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Save second image – demonstrates change barcode height
        string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(path60, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 60‑pixel barcode to {path60}");
    }
}
```

> **Note:** Замените `YOUR_DIRECTORY` реальным путём к папке, в которую ваше приложение может записывать файлы. В Windows, например, `@"C:\Temp"` подойдёт.

## Часто задаваемые вопросы и обработка граничных случаев

### Что делать, если нужен иной **barcode image height**, отличный от значения по умолчанию?

Общий размер холста можно задать через `GeneratorParameters.ImageHeight.Pixels`. Например:

```csharp
generator.Parameters.ImageHeight.Pixels = 120; // forces total image height
```

Это удобно, когда нужно вписать штрих‑код в заранее подготовленный шаблон этикетки.

### Как `XDimension` влияет на надёжность сканирования?

Меньшее значение `XDimension` создаёт более тонкие полосы, которые выглядят острее, но могут быть труднее распознаваемы сканерами низкого разрешения. Как правило, держите `XDimension` ≥ 2 px при печати 300 dpi и ≥ 3 px при 200 dpi.

### Можно ли переключить формат с PNG на другой без изменения кода?

Конечно. Метод `Save` принимает `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp` и т.д. Достаточно заменить значение перечисления:

```csharp
generator.Save(@"path\barcode.jpg", BarCodeImageFormat.Jpeg);
```

### Как генерировать десятки штрих‑кодов с разными высотами?

Обёрните логику изменения высоты в цикл:

```csharp
int[] heights = {30, 45, 60, 75};
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($@"YOUR_DIRECTORY\BarHeight{h}.png", BarCodeImageFormat.Png);
}
```

Таким образом вы **change barcode height** программно для каждой итерации без повторного создания генератора.

## Итоги

Мы рассмотрели, как **barcode generator c#** можно настроить для получения **custom barcode dimensions**, управлять **barcode pixel height** и **change barcode height** «на лету». Полный пример демонстрирует инициализацию, изменение свойств и два сохранения, показывающие визуальную разницу.

Готовы к следующему шагу? Попробуйте сочетать эти настройки с текстовыми подписями, фоновыми цветами или даже внедрить штрих‑код в PDF с помощью Aspose.PDF. Принципы те же — меняйте только нужные параметры.

Если руководство оказалось полезным, поставьте звёздочку на GitHub, поделитесь им с коллегами или оставьте комментарий ниже с вашими экспериментами. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}