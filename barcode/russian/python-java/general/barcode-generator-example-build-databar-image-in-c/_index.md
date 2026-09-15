---
category: general
date: 2026-07-18
description: Пример генератора штрихкодов, показывающий, как задать размеры и создать
  изображение штрихкода DataBar Stacked Omni‑Directional на C#. Быстро изучайте типы
  кодирования штрихкодов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: ru
lastmod: 2026-07-18
og_description: Пример генератора штрихкодов пошагово покажет, как задать размеры,
  выбрать типы кодирования и создать проект C# для изображения штрихкода с минимальным
  количеством кода.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Пример генератора штрихкодов — Быстрое создание изображений DataBar на C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Пример генератора штрихкодов – создание изображения DataBar в C#
url: /ru/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример генератора штрихкодов – создание изображения DataBar на C#

Нужен **пример генератора штрихкодов**, который действительно выводит реальный штрихкод, не сводя вас к отчаянию? Вы не одиноки. Большинство разработчиков сталкиваются с проблемой, когда пытаются понять **как задать размеры** для штрихкода DataBar Stacked Omni‑Directional, особенно когда документация завалена жаргоном.

В этом руководстве мы пройдем полностью готовую к запуску программу на C#, которая показывает **как генерировать изображения databar**, выбирает правильные **barcode encode types** и, наконец, **create barcode image c#** файлы, которые можно добавить в любой проект. Без лишних слов — только код, который можно скопировать‑вставить, плюс объяснение каждой строки.

## Что понадобится

- **.NET 6** (или любая современная версия .NET) — API, которое мы используем, ориентировано на .NET Standard, поэтому работает и в .NET Framework.  
- **Aspose.BarCode for .NET** — библиотека, предоставляющая `BarcodeGenerator`. Можно установить её через NuGet командой `Install-Package Aspose.BarCode`.  
- **IDE для C#** — Visual Studio, Rider или VS Code подойдут.  
- Папка на диске, куда будут сохраняться PNG‑файлы (код создаёт `DatabarAspectRatio15.png` и `DatabarAspectRatio30.png`).

Все готово? Отлично — приступим.

## Пример генератора штрихкодов – инициализация генератора

Первым делом нам нужен экземпляр `BarcodeGenerator`, настроенный для символьной системы **DataBar Stacked Omni‑Directional**. Это **barcode encode type**, с которым мы будем работать.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Почему это важно:** `EncodeTypes.DatabarStackedOmniDirectional` сообщает Aspose, какой именно символьный набор отрисовать. Если выбрать неправильный тип, сканер не распознает штрихкод, независимо от того, как красиво выглядит изображение.

## Как задать размеры штрихкода

Читаемость штрихкода зависит от его **X‑dimension** (ширина самой узкой полоски). В большинстве случаев значение 2 пикселя работает отлично, но вы можете изменить его под ваш принтер или экран.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Совет:** Если когда‑нибудь понадобится **как задать размеры** для другой семейства штрихкодов, используйте ту же цепочку свойств (`Parameters.Barcode.XDimension`) — просто измените значение `Pixels`.

## Как сгенерировать DataBar Stacked Omni‑Directional штрихкод

Теперь, когда генератор готов, поиграем со свойством **aspect ratio**. Оно управляет отношением высоты к ширине DataBar, позволяя получить короткий, квадратный символ или высокий, узкий.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Что происходит?** `AspectRatio = 15` заставляет движок делать полосы в 15 раз выше, чем они шире. Полученный PNG сохраняется рядом с исполняемым файлом.

## Create Barcode Image C# – изменение соотношения сторон

Продемонстрируем гибкость, изменив коэффициент на 30 и сохранив второй файл.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

При запуске программы вы получите два PNG‑файла:

| Файл | Соотношение сторон | Приблизительный размер |
|------|--------------------|------------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Откройте их в любом просмотрщике изображений — вы увидите чистые, сканируемые символы DataBar.

## Обзор Barcode Encode Types (Опционально, но полезно)

Если вам интересны другие **barcode encode types**, поддерживаемые Aspose, вот быстрый шпаргалка:

| Enum EncodeTypes | Описание |
|------------------|----------|
| `EncodeTypes.Code128` | Высокоплотный буквенно‑цифровой код |
| `EncodeTypes.QR` | 2‑D матричный код |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar для розничной торговли |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Наш фокус** — компактный, всенаправленный |

Знание правильного enum избавит вас от множества попыток и ошибок при переключении проектов.

## Распространённые подводные камни и как их избежать

- **Отсутствует пакет NuGet** — код не скомпилируется без `Aspose.BarCode`. Сначала выполните `dotnet add package Aspose.BarCode`.  
- **Неправильный путь к файлу** — если используете абсолютный путь, проверьте обратные слеши (`\\`) в Windows. Относительные пути (как в примере) делают проект переносимым.  
- **Слишком экстремальное соотношение** — коэффициенты выше 50 могут сделать штрихкод слишком высоким для типичных сканеров. Оставайтесь в диапазоне 15‑30 для большинства сценариев.

## Полный исходный код (готов к копированию)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Запустите программу (`dotnet run` или нажмите **F5** в Visual Studio) — в консоли появится сообщение, подтверждающее, что файлы созданы на диске.

![Пример вывода генератора штрихкода, показывающий DataBar штрихкод с соотношением сторон 15](placeholder/path/to/image.png){: .align-center alt="Пример вывода генератора штрихкода, показывающий DataBar штрихкод с соотношением сторон 15"}

## Итоги

Мы только что завершили **пример генератора штрихкодов**, который демонстрирует **как задать размеры**, выбирает правильные **barcode encode types** и, наконец, **create barcode image c#** файлы, которые можно внедрить куда угодно. Код небольшой, концепции предельно ясны, и теперь у вас есть прочная база для расширения решения — возможно, добавления подписи, вращения изображения или перехода к другой символьной системе.

### Что дальше?

- Поэкспериментируйте с **разными X‑dimension** и посмотрите, как меняется допуск сканера.  
- Попробуйте другие **EncodeTypes**, такие как `Code128` или `QR`, чтобы расширить набор инструментов.  
- Автоматизируйте пакетную генерацию: пройдитесь по CSV с идентификаторами товаров и создайте PNG для каждого.

Если возникнут проблемы, оставьте комментарий ниже или обратитесь к документации Aspose.BarCode — там полно примеров, дополняющих то, что мы рассмотрели здесь.

Счастливого кодинга, и пусть ваши штрихкоды всегда сканируются с первой попытки!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом пособии. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}