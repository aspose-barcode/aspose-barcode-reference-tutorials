---
category: general
date: 2026-07-15
description: Быстро генерируйте штрих‑код PDF417 с помощью C#. Узнайте, как создать
  штрих‑код из текста, настроить его размер и задать пользовательские размеры штрих‑кода
  за считанные минуты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- generate barcode from text
- adjust barcode size
- custom barcode dimensions
language: ru
lastmod: 2026-07-15
og_description: Генерируйте штрих‑код PDF417 в C# мгновенно. Это руководство показывает,
  как создать штрих‑код из текста, настроить размер штрих‑кода и задать пользовательские
  размеры штрих‑кода.
og_image_alt: Screenshot of a PDF417 barcode generated with custom dimensions using
  C# code
og_title: Генерация штрих‑кода PDF417 в C# – Полный учебник по программированию
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly with C#. Learn how to generate barcode
    from text, adjust barcode size, and set custom barcode dimensions in minutes.
  headline: Generate PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Генерация штрихкода PDF417 в C# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих‑кода PDF417 на C# – Полное пошаговое руководство

Когда‑то вам нужно было **создать штрих‑код PDF417**, но вы не знали, какие параметры менять? Вы не одиноки — многие разработчики сталкиваются с тем же самым, когда впервые работают с 2‑D штрих‑кодами. Хорошая новость? Пара строк кода на C# позволяют превратить любую строку в сканируемое изображение PDF417, точно задать его размер и даже определить пользовательскую раскладку столбцов‑строк.

В этом руководстве мы пройдёмся по тому, как **создать штрих‑код из текста**, настроить его размер и задать пользовательские размеры штрих‑кода — всё с помощью популярной библиотеки Aspose.BarCode. К концу вы получите готовый пример, который можно сразу вставить в любой .NET‑проект.

![Создать пример штрих‑кода PDF417](https://example.com/og-image.png "Создать пример штрих‑кода PDF417")

## Что вы создадите

- Штрих‑код PDF417, кодирующий строку `Åspóse.Barcóde©`.
- Точный контроль над X‑размером (ширина в пикселях каждого модуля).
- Пользовательскую раскладку из 4 столбцов и 9 строк.
- PNG‑файл, сохранённый на диск.

Никаких внешних сервисов, никаких волшебных палочек — только чистый C#‑код, который можно сразу скомпилировать.

## Требования

- .NET 6.0 или новее (код также работает на .NET Framework 4.8).
- Visual Studio 2022 или любой IDE, поддерживающий C#.
- Aspose.BarCode for .NET (бесплатная пробная версия или лицензия). Установите через NuGet:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — как только пакет подключён, можно начинать.

## Шаг 1 – Генерация штрих‑кода PDF417 из текстовых данных

Первым делом нам нужен экземпляр `BarcodeGenerator`, который знает, что мы работаем с символьностью PDF417 и с тем текстом, который хотим закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Почему это важно:**  
> `EncodeTypes.Pdf417` указывает библиотеке использовать 2‑D формат PDF417, а второй аргумент — это **генерация штрих‑кода из текста**. Всё, что вы передаёте сюда, становится данными, хранящимися в матрице штрих‑кода.

## Шаг 2 – Регулировка размера штрих‑кода (X‑размер)

Если вы когда‑либо печатали штрих‑код, который получался слишком крошечным на чеке, знаете, как раздражает, когда сканер его не видит. Свойство `XDimension` управляет шириной одного модуля (самого маленького чёрного или белого квадратика) в пикселях.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Совет профессионала:**  
> Значение 2 px хорошо подходит для большинства сценариев отображения на экране. Для печати высокого разрешения можно увеличить его до 3 или 4 px. Помните, что больший X‑размер увеличивает общий размер изображения.

## Шаг 3 – Задание пользовательских размеров штрих‑кода (Столбцы и строки)

PDF417 позволяет задать, сколько столбцов и строк будет занимать штрих‑код. Здесь вступают в действие **пользовательские размеры штрих‑кода**. Изменение этих параметров помогает разместить штрих‑код в ограниченном пространстве UI или соответствовать конкретному размеру этикетки.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Что происходит под капотом?**  
> Библиотека перераспределяет закодированные данные по указанной сетке. Меньшее количество столбцов делает штрих‑код выше; больше строк — короче. Поэкспериментируйте с числами, пока визуальный баланс не будет выглядеть правильно для вашего приложения.

## Шаг 4 – Сохранение изображения штрих‑кода

После настройки всех параметров просто просим генератор записать PNG‑файл. PNG — это формат без потерь, поэтому чёткость модулей сохраняется.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

Запустив программу, вы увидите файл `C:\Barcodes\CustomLayout.png`, похожий на скриншот выше. Сканирование его любой программой, поддерживающей PDF417, вернёт исходную строку `Åspóse.Barcóde©`.

## Полный рабочий пример

Ниже представлен полностью готовый код, который можно скопировать в консольное приложение. В нём присутствуют все директивы `using` и обработка ошибок, ожидаемая в продакшн‑коде.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Ожидаемый вывод

При запуске код выводит:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…и создаёт PNG, который открывается в любой программе просмотра изображений. Если просканировать его мобильным приложением (например, «Barcode Scanner» на iOS/Android), декодированный текст будет точно **Åspóse.Barcóde©**.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| **Можно ли использовать другой формат изображения?** | Да — поддерживаются `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` и `Svg`. Просто измените второй аргумент метода `Save`. |
| **Что если мой текст содержит Unicode‑символы?** | Aspose.BarCode полностью поддерживает UTF‑8, поэтому пример с `Å` и `©` работает «из коробки». |
| **Как изменить уровень коррекции ошибок?** | Используйте `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (уровни 0‑8). Более высокий уровень повышает избыточность, но и размер. |
| **Мне нужен прозрачный фон — это возможно?** | Установите `generator.Parameters.Barcode.Image.TransparentBackground = true;` перед сохранением. |
| **Можно ли встроить штрих‑код напрямую в PDF?** | Конечно. Замените вызов `Save` на `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` — вы получите одностраничный PDF с штрих‑кодом. |

## Заключение

Теперь вы знаете, как **генерировать штрих‑код PDF417** на C# из любой строки, **регулировать размер штрих‑кода** и применять **пользовательские размеры** для соответствия вашим требованиям к макету. Четырёхшаговый процесс — инициализация, размер, раскладка, сохранение — охватывает основной рабочий поток для большинства сценариев 2‑D штрих‑кодов.

Что дальше? Попробуйте заменить `EncodeTypes.Pdf417` на `EncodeTypes.QR` или `EncodeTypes.Code128`, чтобы увидеть, как API адаптируется. Поэкспериментируйте с различными значениями `XDimension`, меняйте матрицу столбцов/строк или внедряйте изображение в PDF‑отчёт. Возможности практически безграничны, и теперь у вас есть прочный фундамент для дальнейшего развития.

Есть вопросы или вы нашли интересный приём, работая с PDF417? Оставляйте комментарий ниже — давайте поддерживать обсуждение. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}