---
category: general
date: 2026-09-29
description: Руководство по генератору штрихкодов на C# показывает, как создать штрихкод
  MicroPdf417, изменить размеры, задать количество столбцов и настроить размер штрихкода
  всего за несколько строк.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: ru
lastmod: 2026-09-29
og_description: Руководство по генератору штрихкодов C# показывает, как создать штрихкод
  MicroPdf417, изменить размеры, задать количество столбцов и настроить размер штрихкода
  всего за несколько строк.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Руководство по генератору штрихкодов C# – создание и настройка MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Руководство по генератору штрихкодов C#: создание MicroPdf417'
url: /ru/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Руководство по генератору штрихкодов C#: создание MicroPdf417

Если вам нужен **barcode generator C#** для вашего проекта .NET, это руководство проведёт вас через процесс создания штрихкода MicroPdf417 с нуля. Вы узнаете, **как генерировать штрихкод**, менять размеры, задавать количество колонок и **настраивать размер штрихкода** без труда.

MicroPdf417 — компактная 2‑D символьная система, хорошо подходящая для маркировки небольших деталей, билетов или этикеток инвентаря. К концу этого руководства у вас будет полностью готовое консольное приложение, которое сохраняет PNG‑изображение штрихкода, и вы поймёте, как каждый параметр влияет на конечный размер.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)
* IDE, поддерживающая C# (Visual Studio, VS Code, Rider и т.д.)
* NuGet‑пакет **GroupDocs.Barcode** — установите его с помощью  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Дополнительные внешние инструменты не требуются; библиотека сама обрабатывает кодирование, рендеринг и сохранение файлов.

## Barcode generator C#: инициализация генератора

Первый шаг — создать экземпляр `BarcodeGenerator` и указать символьную систему (`EncodeTypes.MicroPdf417`) вместе с данными, которые нужно закодировать.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Почему это важно:**  
`BarcodeGenerator` — точка входа для всех операций со штрихкодами. Конструктор связывает выбранный **EncodeTypes** (MicroPdf417) с исходной строкой данных. Библиотека автоматически обрабатывает Unicode‑символы, такие как «Å» и «©», поэтому дополнительная логика кодирования не нужна.

## Как изменить размеры штрихкода

Читаемость штрихкода сильно зависит от ширины модуля (X‑dimension). Увеличение количества пикселей делает полосы шире и упрощает сканирование, особенно на дисплеях с низким разрешением.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Объяснение:**  
`XDimension.Pixels` управляет шириной одного модуля штрихкода. По умолчанию это 1 пиксель, что может выглядеть тонко на мониторах с высоким DPI. Увеличение до 2 пикселей удваивает общую ширину без изменения закодированных данных.

**Совет:** Если планируете печатать штрихкод с разрешением 300 dpi, значение 3‑4 пикселя обычно обеспечивает лучший баланс между размером и надёжностью сканирования.

## Как задать количество колонок для управления размером

MicroPdf417 позволяет указать количество колонок (до 4). Меньшее количество колонок даёт более высокий штрихкод; больше колонок делает его шире, но короче. Регулирование этого параметра — основной способ **customize barcode size**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Почему это работает:**  
Свойство `Pdf417.Columns` используется во всех символьных системах семейства PDF417, включая MicroPdf417. Установка максимального значения (4) распределяет данные по самой широкой возможной раскладке, уменьшая общую высоту. Если нужен более компактный по высоте штрихкод, уменьшите количество колонок до 2 или 3.

**Особый случай:** При длинной строке данных библиотека может автоматически увеличить количество строк, чтобы вместить содержимое, независимо от выбранного количества колонок. Держите полезную нагрузку менее 50 символов для предсказуемого размера.

## Настройка размера штрихкода для разных выводов

Помимо X‑dimension и колонок, финальный размер изображения можно влиять, выбирая подходящий формат изображения и DPI. PNG — без потерь, идеально подходит для веб‑отображения, тогда как BMP или TIFF могут быть предпочтительнее для печати высокого качества.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Если нужен более высокий DPI, его можно задать явно:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Результат:** Сохранённый PNG‑файл содержит чёткий штрихкод MicroPdf417, соответствующий заданным вами параметрам. Откройте файл в любом просмотрщике изображений, чтобы проверить визуальный размер.

### Ожидаемый результат

Запуск программы создаёт файл с именем **MicroPdf417.png** (или **MicroPdf417_300dpi.png**, если вы задали DPI). Штрихкод будет выглядеть примерно так:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Barcode generator C# output showing a MicroPdf417 PNG*

Сканирование изображения стандартным 2‑D считывателем возвращает исходную строку `Åspóse.Barcóde©`.

## Полный исходный код для быстрого копирования

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Скопируйте код в новый консольный проект, восстановите пакеты NuGet и выполните `dotnet run`. Консоль подтвердит расположение изображения, и вы увидите сгенерированный штрихкод в папке проекта.

## Часто задаваемые вопросы и устранение неполадок

| Вопрос | Ответ |
|----------|--------|
| **Что делать, если штрихкод выглядит размытым?** | Увеличьте `XDimension.Pixels` или DPI (`Parameters.Image.DpiX/Y`). Оба параметра делают модули крупнее и улучшают визуальную чёткость. |
| **Можно ли использовать другой формат изображения?** | Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Tiff`. PNG остаётся самым надёжным выбором для качества без потерь. |
| **Мои данные содержат эмодзи — будут ли они закодированы?** | MicroPdf417 поддерживает UTF‑8, поэтому большинство эмодзи кодируются корректно. Если возникнут ошибки, проверьте, что строка правильно нормализована (`System.Text.Encoding.UTF8`). |
| **Как генерировать другие символьные системы?** | Замените `EncodeTypes.MicroPdf417` на любое другое значение из `EncodeTypes` (


## Что изучать дальше?


Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}