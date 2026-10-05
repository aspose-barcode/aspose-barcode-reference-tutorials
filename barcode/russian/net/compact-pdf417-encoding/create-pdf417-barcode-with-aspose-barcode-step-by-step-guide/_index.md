---
category: general
date: 2026-08-25
description: Создайте штрих‑код PDF417 с помощью Aspose.BarCode в C#. Этот учебник
  объясняет, как быстро генерировать штрих‑код PDF417 с понятными примерами кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: ru
lastmod: 2026-08-25
og_description: Создайте штрих‑код PDF417 с помощью Aspose.BarCode в C#. Узнайте,
  как сгенерировать штрих‑код PDF417 с полным, готовым к запуску примером.
og_image_alt: Screenshot of a generated PDF417 barcode created with Aspose.BarCode
og_title: Создание штрих‑кода PDF417 с помощью Aspose.BarCode – краткое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create PDF417 barcode using Aspose.BarCode in C#. This tutorial explains
    how to generate PDF417 barcode quickly with clear code examples.
  headline: Create PDF417 barcode with Aspose.BarCode – step-by-step guide
  type: TechArticle
tags:
- Aspose.BarCode
- PDF417
- C#
title: Создание штрихкода PDF417 с помощью Aspose.BarCode – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 с Aspose.BarCode – пошаговое руководство

Если вам нужно **создать штрих‑код PDF417** в .NET‑приложении, это руководство покажет, как генерировать штрих‑код PDF417 с помощью Aspose.BarCode. Вы увидите полностью готовый к запуску пример, поймёте, почему важна каждая настройка, и научитесь адаптировать код под разные сценарии.

В руководстве рассматривается:

* Добавление пакета Aspose.BarCode в ваш проект  
* Настройка генератора штрих‑кода (текст, X‑dimension, columns)  
* Сохранение штрих‑кода в файл PNG  
* Работа с Unicode‑символами и типичные подводные камни  

Внешняя документация не требуется — всё необходимое включено ниже.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+)  
* Последняя версия пакета **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* IDE или редактор по вашему выбору (Visual Studio, VS Code, Rider и т.д.)

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новый консольный проект и импортируйте необходимые пространства имён Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts here.
```

*`Aspose.BarCode`* содержит основные классы, а *`Aspose.BarCode.Generation`* предоставляет `BarcodeGenerator`, используемый для создания штрих‑кодов.

## Шаг 2: Создание генератора штрих‑кода PDF417 с нужным текстом

Первая строка создаёт `BarcodeGenerator` для символьного набора PDF417 и задаёт данные, которые вы хотите закодировать.

```csharp
            // Step 2: Create a PDF417 barcode generator with the desired text
            // Unicode characters such as Å, ó, and © are supported out of the box.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Почему это важно:**  
PDF417 может хранить до 1 850 символов, что делает его подходящим для документов, билетов или удостоверений. Передача текста напрямую в конструктор гарантирует правильное кодирование данных до применения любых визуальных настроек.

## Шаг 3: Настройка визуальных параметров (X‑dimension и columns)

Тонкая настройка внешнего вида повышает надёжность сканирования и соответствует требованиям макета.

```csharp
            // Step 3: Set the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 4: Define the number of columns for the PDF417 barcode
            // Fewer columns produce a taller barcode; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
```

* **X‑dimension** – управляет шириной отдельного модуля штрих‑кода. Значение `2` пикселя обычно обеспечивает хороший баланс между читаемостью и размером файла на большинстве экранов.  
* **Columns** – определяет количество столбцов данных в штрих‑коде. Регулируйте это значение в зависимости от объёма данных и доступного пространства на целевом носителе.

## Шаг 4: Сохранение изображения штрих‑кода

Выберите формат изображения, соответствующий вашему последующему рабочему процессу. PNG сохраняет без потерь, что идеально для дальнейшей обработки или печати.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

Метод `Save` записывает изображение по указанному пути. Если нужен другой формат (JPEG, BMP, SVG), замените `BarCodeImageFormat.Png` на соответствующее значение перечисления.

## Полный, исполняемый пример

Скопируйте весь блок кода ниже в файл `Program.cs` нового консольного проекта, выполните `dotnet run`, и вы найдёте `Pdf417Basic.png` в папке проекта.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with Unicode text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Save as PNG
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Ожидаемый результат

Запуск программы создаёт PNG‑файл, похожий на иллюстрацию ниже.

![Пример создания штрих‑кода PDF417](https://example.com/images/pdf417-sample.png "Пример создания штрих‑кода PDF417")

*Изображение показывает чёткий штрих‑код PDF417 с тремя колонками и шириной модуля 2 px.*

## Как генерировать штрих‑код PDF417 с пользовательской длиной данных

Если ваши данные превышают стандартную ёмкость, возможно, потребуется настроить дополнительные параметры:

| Параметр | Рекомендуемая настройка | Причина |
|-----------|--------------------|--------|
| `Pdf417.Rows` | `0` (auto) | Позволить Aspose вычислить оптимальное количество строк. |
| `Pdf417.ErrorLevel` | `2` (default) | Более высокий уровень увеличивает избыточность, улучшая надёжность сканирования повреждённого носителя. |
| `Pdf417.SecurityLevel` | `0`–`8` | Использовать только при необходимости коррекции ошибок сверх значения по умолчанию. |

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 0;          // Auto‑calculate rows
generator.Parameters.Barcode.Pdf417.ErrorLevel = 2;   // Standard error correction
generator.Parameters.Barcode.Pdf417.SecurityLevel = 5; // Optional extra security
```

**Подсказка:** Всегда тестируйте сгенерированный штрих‑код на целевом сканере. Более высокие уровни ошибки могут увеличить размер изображения, что может влиять на ограничения макета.

## Распространённые подводные камни и как их избежать

| Проблема | Причина | Решение |
|-------|-------|-----|
| Штрих‑код выглядит размытым | Сохранение в PNG низкого разрешения | Увеличьте `XDimension.Pixels` или экспортируйте в SVG (`BarCodeImageFormat.Svg`) |
| Символы заменяются на � | Входная строка не закодирована как UTF‑8 | Убедитесь, что исходный файл сохранён в кодировке UTF‑8 (большинство IDE по умолчанию используют её) |
| Сканер не может прочитать штрих‑код | Слишком мало колонок для объёма данных | Увеличьте `Pdf417.Columns` или позвольте Aspose автоматически определить количество колонок, не задавая параметр |

## Создание штрих‑кода с Aspose – за пределами PDF417

Aspose.BarCode поддерживает множество символьных наборов (QR, Code128, DataMatrix и др.). Переход к другому типу требует лишь изменения значения перечисления `EncodeTypes`:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
qrGenerator.Save("QRCode.png", BarCodeImageFormat.Png);
```

Это демонстрирует шаблон **create barcode with Aspose**: создайте `BarcodeGenerator` с нужным значением `EncodeTypes`, настройте параметры и вызовите `Save`.

## Заключение

Теперь вы знаете, как **создать штрих‑код PDF417** на C# с использованием Aspose.BarCode, от настройки проекта до тонкой настройки визуальных параметров и работы с Unicode‑данными. Полный, исполняемый пример можно адаптировать для больших наборов данных, разных форматов изображений или альтернативных символьных наборов.

Следующие шаги, которые вы можете изучить:

* **Как генерировать штрих‑код PDF417** в веб‑API (ASP.NET Core) – полезно для генерации по запросу.  
* Встраивание штрих‑кода в PDF‑документ с помощью Aspose.PDF.  
* Использование `Pdf417.Rows` и `Pdf417.ErrorLevel` для соответствия конкретным стандартам сканирования.

Не стесняйтесь экспериментировать с количеством колонок, значениями X‑dimension и форматами вывода, чтобы подобрать оптимальное решение для вашего случая. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать штрих‑код – Compact PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑код PDF417 – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Как считывать штрих‑код из PDF на Java с помощью Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}