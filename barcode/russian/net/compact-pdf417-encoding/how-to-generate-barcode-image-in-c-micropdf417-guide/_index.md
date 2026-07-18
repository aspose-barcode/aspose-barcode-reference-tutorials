---
category: general
date: 2026-07-18
description: Узнайте, как генерировать изображение штрихкода в C# с использованием
  формата MicroPdf417. Пошаговая настройка размеров и сохранение в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- micro pdf417 barcode
- BarcodeGenerator class
- set barcode dimensions
- save barcode as png
language: ru
lastmod: 2026-07-18
og_description: Как сгенерировать изображение штрихкода в C#? Следуйте этому руководству,
  чтобы создать штрихкод MicroPdf417, настроить его размер и экспортировать его в
  файл PNG.
og_image_alt: Screenshot of a MicroPdf417 barcode image generated in C#
og_title: Как сгенерировать изображение штрихкода в C# – Полный учебник по MicroPdf417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  headline: How to Generate Barcode Image in C# – MicroPdf417 Guide
  type: TechArticle
- description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  name: How to Generate Barcode Image in C# – MicroPdf417 Guide
  steps:
  - name: Change Image Format
    text: 'You aren’t limited to PNG. Switch to JPEG or BMP by adjusting the second
      argument of `Save`:'
  - name: Increase DPI for Print
    text: 'For high‑resolution prints, bump the `Resolution` property:'
  - name: Add Quiet Zone (Margin)
    text: 'A quiet zone helps scanners differentiate the barcode from surrounding
      graphics:'
  - name: Encode Different Data Types
    text: 'MicroPdf417 works with numeric, alphanumeric, and binary data. If you need
      to embed a URL, just replace the text:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Как создать изображение штрихкода в C# – руководство MicroPdf417
url: /ru/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрихкода в C# – Руководство по MicroPdf417

Вы когда‑нибудь задавались вопросом **как создать изображение штрихкода** в C# без бесконечного поиска в документации? Вы не одиноки. Независимо от того, создаёте ли вы систему билетов, каталог товаров или просто нужен быстрый QR‑подобный код, освоение создания штрихкодов может сэкономить вам время и избавить от головной боли.

В этом руководстве мы пройдем точные шаги по созданию **изображения штрихкода MicroPdf417** с помощью класса `BarcodeGenerator`, настроим его размеры и сохраним результат в формате PNG. Без лишних слов — только полностью готовый пример, который вы можете скопировать и вставить в свой проект уже сегодня.

## Что вы узнаете

- Настроить `BarcodeGenerator` для формата MicroPdf417  
- **Установить размеры штрихкода**: ширина модуля и количество колонок  
- **Сохранить штрихкод как PNG** в выбранную вами папку  
- Дополнительные настройки для вывода в высоком разрешении и обработки ошибок  

К концу вы сможете уверенно ответить на вопрос *«как создать изображение штрихкода»* и получите прочную основу для создания и других типов штрихкодов.

---

## Необходимые условия

Перед тем как начать, убедитесь, что у вас есть:

1. **.NET 6.0 или новее** (код также работает на .NET Framework 4.5+)  
2. Ссылка на библиотеку **Aspose.BarCode** (или любую другую, предоставляющую `BarcodeGenerator`). Вы можете получить её через NuGet:  

   ```bash
   dotnet add package Aspose.BarCode
   ```

3. Надёжная IDE — Visual Studio, Rider или VS Code подойдёт.  
4. Права на запись в каталог, куда будет сохраняться PNG‑файл.

> **Совет:** Если вы используете другую библиотеку штрихкодов, имена классов могут отличаться, но общий процесс остаётся тем же.

---

## Шаг 1: Создать генератор штрихкода MicroPdf417

Первое, что вам нужно, — это экземпляр `BarcodeGenerator`, настроенный для формата **штрихкода MicroPdf417**. Этот объект является движком, который преобразует ваш текст в визуальный код.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // Choose the MicroPdf417 format
    "Åspóse.Barcóde©");               // The data you want to encode
```

**Почему это важно:**  
`EncodeTypes.MicroPdf417` указывает библиотеке использовать компактный вариант PDF417, который идеально подходит для коротких строк и ограниченного пространства. Текст может содержать Unicode‑символы, как показано выше, поэтому вы не ограничены обычным ASCII.

---

## Шаг 2: Установить размеры штрихкода

Теперь, когда генератор существует, вы, вероятно, захотите контролировать размер каждого модуля (маленького квадратика) и количество колонок, которые охватывает штрихкод. Здесь в дело вступает ключевое слово **set barcode dimensions**.

```csharp
// Step 2: Adjust appearance – module width and column count
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels
generator.Parameters.Barcode.Pdf417.Columns = 4;    // Number of columns (affects height)
```

- **`XDimension.Pixels`** — Большие значения упрощают сканирование штрихкода, но увеличивают размер файла.  
- **`Pdf417.Columns`** — Меньшее количество колонок сжимает штрихкод по вертикали; больше колонок растягивают его по горизонтали.

> **Внимание:** Установка слишком маленькой ширины модуля (например, 1 пиксель) может привести к размытию изображения на экранах с высоким DPI. Значение от 2 до 4 пикселей обычно хорошо подходит для большинства принтеров.

---

## Шаг 3: Сохранить изображение штрихкода в PNG

После настройки генератора последний шаг — записать графику на диск. Это удовлетворяет требование **save barcode as png**.

```csharp
// Step 3: Export the barcode to a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Что происходит под капотом?**  
`Save` рендерит штрихкод в bitmap, кодирует его как PNG (без потерь) и записывает байты в указанное место. Если каталог не существует, `Save` выбросит исключение — поэтому в продакшн‑коде стоит обернуть это в блок `try/catch`.

---

## Полный рабочий пример

Объединив всё вместе, представляем автономное консольное приложение, которое можно запустить сразу:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set dimensions
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 3️⃣ Define output path
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        // 4️⃣ Save as PNG
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

**Ожидаемый результат:** Чёткий файл `MicroPdf417.png` на вашем рабочем столе, отображающий закодированную строку `Åspóse.Barcóde©`. Откройте его в любом просмотрщике изображений, чтобы убедиться, что штрихкод ясен и сканируем.

---

## Расширенные опции (необязательно)

Если вы хотите расширить базовый процесс, рассмотрите следующие настройки — каждая из них соответствует вторичному ключевому слову из нашего списка.

### Изменить формат изображения

Вы не ограничены PNG. Переключитесь на JPEG или BMP, изменив второй аргумент метода `Save`:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

### Увеличить DPI для печати

Для печати в высоком разрешении увеличьте свойство `Resolution`:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

### Добавить тихую зону (отступ)

Тихая зона помогает сканерам отличать штрихкод от окружающих графических элементов:

```csharp
generator.Parameters.Barcode.QR.QrQuietZone = 4; // 4 modules of margin
```

### Кодировать разные типы данных

MicroPdf417 работает с числовыми, буквенно-цифровыми и бинарными данными. Если нужно встроить URL, просто замените текст:

```csharp
generator.CodeText = "https://example.com";
```

---

## Распространённые ошибки и как их избежать

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Штрихкод выглядит размытым | `XDimension.Pixels` установлен в 1 или изображение изменено после сохранения | Используйте минимум 2 пикселя и избегайте масштабирования после обработки |
| Сканер не может прочитать код | Слишком много колонок для данной длины данных | Уменьшите `Pdf417.Columns` или позвольте библиотеке автоматически подобрать размер (`Columns = 0`) |
| Unicode‑символы отображаются как � | Устаревшая версия библиотеки или отсутствие поддержки шрифтов | Обновите Aspose.BarCode до последней версии и обеспечьте правильную кодировку |
| `Save` бросает `DirectoryNotFoundException` | Папка вывода не существует | Создайте каталог заранее или используйте `Path.Combine` с известными папками |

---

## Тестирование вашего штрихкода

После создания изображения вы можете проверить его с помощью любого приложения для сканирования штрихкодов (большинство смартфонов теперь имеют встроенные сканеры). Наведите камеру на PNG‑файл на экране или распечатайте его — если приложение считывает `Åspóse.Barcóde©`, вы успешно ответили на вопрос **how to generate barcode image**.

---

## Заключение

Мы рассмотрели всё, что нужно знать, чтобы **how to generate barcode image** с помощью C# и формата MicroPdf417:

1. **Создать** `BarcodeGenerator` с вашими данными.  
2. **Установить размеры штрихкода** для контроля размера и читаемости.  
3. **Сохранить штрихкод как PNG** (или в любом другом поддерживаемом формате).  

Отсюда вы можете экспериментировать с различными типами штрихкодов, регулировать DPI для печати или встраивать изображение напрямую в PDF‑файлы или отчёты. Основные элементы одинаковы, поэтому смело заменяйте `EncodeTypes.MicroPdf417` на `EncodeTypes.QR` или `EncodeTypes.Code128` и повторяйте шаги.

Есть вопросы о других стандартах штрихкодов или нужна помощь с настройкой внешнего вида? Оставьте комментарий ниже, и удачной разработки!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать Aztec‑штрихкод с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как генерировать штрихкоды — одноразмерные типы штрихкодов](/barcode/english/net/one-dimensional-barcode-types/)
- [Как генерировать DataMatrix‑штрихкоды (ECC 200) с Aspose.BarCode для .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}