---
category: general
date: 2026-07-18
description: Создавайте PNG‑изображения штрихкода на C# быстро. Узнайте, как настроить
  столбцы, включить ссылки и генерировать PDF417 с помощью генератора штрихкодов на
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to adjust columns
- c# barcode generator
- how to generate pdf417
- how to enable linking
language: ru
lastmod: 2026-07-18
og_description: Создайте PNG‑штрихкод в C# и освоите, как настраивать столбцы, включать
  ссылки и генерировать PDF417 с помощью генератора штрихкодов на C#. Следуйте этому
  краткому руководству.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Создание PNG‑штрихкода в C# – Полный программный обзор
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create barcode PNG in C# quickly. Learn how to adjust columns, enable
    linking, and generate PDF417 with a C# barcode generator.
  headline: Create barcode PNG in C# – Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Создание PNG‑штрихкода в C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать PNG штрих‑кода в C# – Полное пошаговое руководство

Когда‑нибудь задавались вопросом, как **создать PNG штрих‑кода** файлы из C# без лишних усилий? Вы не одиноки. Независимо от того, нужен ли вам GS1‑Micro‑PDF417 для транспортной этикетки или простой QR‑код для рекламного листовки, освоение **c# barcode generator** делает весь процесс простым как раз.

В этом руководстве мы пройдем всё, что нужно для **создания PNG штрих‑кода** изображений, от установки нужного пакета NuGet до настройки количества столбцов и включения связывания. К концу вы будете знать **how to adjust columns**, **how to enable linking** и **how to generate PDF417** всего в нескольких строках кода.

## Что вы узнаете

- Настроить проект C# с библиотекой генерации штрих‑кодов.  
- Использовать **c# barcode generator** для создания штрих‑кода GS1‑Micro‑PDF417.  
- Применить **how to adjust columns** для управления плотностью штрих‑кода.  
- Включить специальную функцию связывания (**how to enable linking**).  
- Сохранить результат в виде высококачественного файла **создать PNG штрих‑кода**.  

## Предварительные требования

- .NET 6.0 SDK или новее (код работает на .NET Core и .NET Framework).  
- Базовое знакомство с синтаксисом C# — если вы умеете писать `foreach`, всё в порядке.  
- Visual Studio 2022, VS Code или любой предпочитаемый IDE.  
- Доступ в интернет для загрузки библиотеки штрих‑кодов из NuGet (в примере мы используем *Aspose.BarCode*).

Внешние файлы конфигурации не требуются; всё находится в коде, который мы напишем вместе.

## Шаг 1: Добавить библиотеку штрих‑кодов (c# barcode generator)

Откройте терминал (или консоль диспетчера пакетов) и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта единственная команда добавит надёжный **c# barcode generator**, способный работать с PDF417, QR, Code128 и многим другим. Библиотека активно поддерживается (v24.9 на июль 2026) и кросс‑платформенна, поэтому вы не будете привязаны к Windows.

## Шаг 2: Определить папку вывода

Прежде чем генерировать что‑либо, нам нужен каталог для сохранения изображения. Жёстко заданный путь подходит для демонстрации, но позже его можно заменить значением из конфигурации.

```csharp
// Step 2: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

Обратите внимание, что мы используем `Path.Combine` для надёжности — без «магических» строк, которые ломаются в Linux. Этот шаг важен, потому что попытка **создать PNG штрих‑кода** без существующей папки вызывает исключение во время выполнения.

## Шаг 3: Инициализировать генератор GS1‑Micro‑PDF417 (how to generate pdf417)

Теперь самая интересная часть. Мы создадим экземпляр **c# barcode generator** и передадим ему исходную строку данных.

```csharp
// Step 3: Initialise the GS1‑Micro‑PDF417 generator
var generator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

`EncodeTypes.GS1MicroPdf417` указывает библиотеке, что нам нужен вариант PDF417, соответствующий стандартам GS1. Строка данных следует формату идентификаторов приложений: `(01)` для GTIN и `(240)` для внутреннего кода компании. Если нужен обычный PDF417, просто замените перечисление на `EncodeTypes.Pdf417` — это **how to generate pdf417** в другой форме.

## Шаг 4: Настроить макет штрих‑кода (how to adjust columns & how to enable linking)

Два параметра часто вызывают путаницу: количество столбцов и флаг связывания. Давайте разберём их.

```csharp
// Step 4a: Adjust the number of columns – this is how to adjust columns
generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns gives a compact barcode

// Step 4b: Enable linking between macro and micro PDF417 – this is how to enable linking
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

- **How to adjust columns**: Свойство `Columns` управляет горизонтальной плотностью. Меньшее количество столбцов делает штрих‑код выше, но шире; больше столбцов сжимает его по вертикали. Мы выбрали `4`, потому что это балансирует читаемость на 2‑дюймовой этикетке и умеренный размер файла.  
- **How to enable linking**: Установка `IsLinked = true` соединяет макро (полный размер) и микро (маленький) версии, что требуется некоторым сканерам для иерархического извлечения данных.

Если пропустить эти две строки, штрих‑код всё равно будет сгенерирован, но может не соответствовать требованиям. Поверьте, я провёл часы, отлаживая несоответствия в количестве столбцов.

## Шаг 5: Точно настроить ширину модуля (X‑Dimension)

Хотя это не основной ключевой термин, настройка ширины модуля часто сочетается с изменением количества столбцов.

```csharp
// Step 5: Set X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Модуль шириной `2` пикселя даёт чёткое изображение, которое хорошо масштабируется при вставке в PDF или печати на термопринтерах.

## Шаг 6: Сохранить изображение – наконец **создать PNG штрих‑кода**

Вся эта подготовка завершается одной строкой, которая действительно записывает файл на диск.

```csharp
// Step 6: Save the generated barcode as a PNG – the core of create barcode png
string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
generator.Save(filePath, BarCodeImageFormat.Png);
Console.WriteLine($"✅ Barcode PNG saved to: {filePath}");
```

`BarCodeImageFormat.Png` гарантирует сжатие без потерь, идеально подходит для последующей обработки (например, вставки PNG в PDF или HTML‑тег `<img>`). Эта строка — сердце **создания PNG штрих‑кода** — без неё вы никогда не увидите результат.

## Полный рабочий пример

Объединив всё вместе, представляем автономное консольное приложение, которое можно скопировать и запустить:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Define the output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // 2️⃣ Create a GS1‑Micro‑PDF417 barcode generator (how to generate pdf417)
        var generator = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(01)12345678901231(240)ABCD123456789012345");

        // 3️⃣ Adjust X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 4️⃣ How to adjust columns – set column count
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 5️⃣ How to enable linking – link macro and micro versions
        generator.Parameters.Barcode.Pdf417.IsLinked = true;

        // 6️⃣ Save as PNG – the moment we finally create barcode png
        string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Successfully created barcode PNG at: {filePath}");
    }
}
```

### Ожидаемый вывод

При запуске программы консоль выводит примерно следующее:

```
✅ Successfully created barcode PNG at: C:\YourProject\Barcodes\GS1MicroPdf417_906_907.png
```

Откройте файл, и вы увидите чистое, считываемое изображение GS1‑Micro‑PDF417 — именно то, что нужно для **создания PNG штрих‑кода** в вашем логистическом процессе.

## Распространённые ошибки и профессиональные советы

- **Pitfall:** Забыли вызвать `Directory.CreateDirectory`. Приложение упадёт с `DirectoryNotFoundException`.  
  **Tip:** Всегда проверяйте, что папка вывода существует перед сохранением.

- **Pitfall:** Использование неверного `EncodeTypes`. `EncodeTypes.Pdf417` даёт обычный PDF417, *не* микровариант.  
  **Tip:** Тщательно проверяйте перечисление, когда нужен GS1‑Micro штрих‑код.

- **Pitfall:** Установка `Columns` в значение вне допустимого диапазона (1‑30).  
  **Tip:** Оставайтесь в диапазоне 2‑10 для большинства размеров этикеток; иначе библиотека бросит `ArgumentOutOfRangeException`.

- **Pro tip:** Если нужен прозрачный фон, добавьте  
  ```csharp
  generator.Parameters.Barcode.BackgroundColor = Color.Transparent;
  ```  
  перед сохранением. Это позволит PNG плавно вписаться в элементы UI.

- **Pro tip:** Для пакетной обработки оберните логику генерации в цикл `foreach` и меняйте строку данных на каждой итерации. Это простой способ **создать PNG штрих‑кода** файлов массово.

## Расширение примера

Теперь, когда вы освоили основы, рассмотрите изучение следующих связанных тем:

- **How to generate QR codes** с тем же `BarcodeGenerator` (просто замените `EncodeTypes.QR`).  
- **Adding human‑readable text** под штрих‑кодом через `generator.Parameters.Barcode.BarHeight`.  
- **Exporting to SVG** (`BarCodeImageFormat.Svg`) для векторной веб‑графики.  
- **Integrating with ASP.NET Core** для динамической отдачи изображений штрих‑кодов (`FileStreamResult`).  

Все эти сценарии используют основной шаблон, который мы рассмотрели: инициализировать генератор, настроить параметры и **создать PNG штрих‑кода** (или другой формат) одним вызовом `Save`.

## Заключение

Мы прошли полный, готовый к продакшн способ **создания PNG штрих‑кода** файлов в C#. Следуя шагам, вы теперь знаете **how to adjust columns**, **how to enable linking** и **how to generate PDF

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}