---
category: general
date: 2026-08-25
description: Узнайте, как генерировать штрих‑код PDF417 в C# с помощью библиотеки‑генератора
  штрих‑кодов PDF417 для C# — пошаговые примеры кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: ru
lastmod: 2026-08-25
og_description: Создайте штрих‑код PDF417 на C# с помощью генератора штрих‑кодов PDF417
  библиотеки для C#. Следуйте этому лаконичному руководству для полного кода и лучших
  практик.
og_image_alt: Generated PDF417 barcode example
og_title: Создание штрихкода PDF417 на C# – полное руководство
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Как сгенерировать штрих‑код PDF417 в C# с помощью Barcode Generator
url: /ru/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать PDF417 штрих‑код в C# с помощью Barcode Generator

Если вам нужно **сгенерировать PDF417 штрих‑код** в приложении .NET, это руководство покажет готовое решение. С помощью библиотеки **barcode generator C# PDF417** вы можете управлять размерами, столбцами, строками и форматом изображения всего несколькими строками кода.

Вы узнаете, как создавать штрих‑коды высокого разрешения, настраивать макет и сохранять результат в виде PNG‑файлов — не выходя из вашей IDE.

## Что понадобится

- .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
- Пакет Aspose.BarCode for .NET (установить через NuGet: `Install-Package Aspose.BarCode`)
- Папка, в которой будут сохраняться сгенерированные PNG‑изображения
- Базовое знакомство с синтаксисом C#

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новое консольное приложение (или добавьте код в существующий проект) и добавьте необходимые директивы using:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Пространство имён `Aspose.BarCode.Generation` предоставляет `BarcodeGenerator`, а `Aspose.BarCode` содержит перечисление `BarCodeImageFormat`.

## Шаг 2: Инициализируйте генератор штрих‑кода PDF417

Создайте экземпляр `BarcodeGenerator`, указав тип кодирования PDF417 и текст, который нужно закодировать. В примере используется строка с не‑ASCII символами для демонстрации поддержки Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Почему это важно:**  
`EncodeTypes.Pdf417` указывает библиотеке генерировать штрих‑код PDF417, который представляет собой многослойный линейный штрих‑код, идеальный для хранения больших объёмов данных. Передача текста при создании гарантирует, что генератор готов к немедленному рендерингу.

## Шаг 3: Улучшите разрешение с помощью X‑dimension

X‑dimension (ширина модуля) определяет, сколько пикселей занимает каждый маленький бар. Большее значение даёт более чёткое изображение, особенно при печати.

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Установка `Pixels = 2` обеспечивает хороший баланс между размером и читаемостью. Вы можете увеличить это значение для вывода с высоким DPI, но учитывайте рост размеров файлов.

## Шаг 4: Сгенерировать штрих‑код с фиксированным количеством столбцов

Штрих‑код PDF417 может быть размещён в определённом количестве столбцов. Здесь мы запрашиваем **2 столбца** и позволяем библиотеке автоматически определить количество строк.

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**Результат:** `Pdf417Columns2.png` содержит компактный штрих‑код с двумя вертикальными столбцами.

## Шаг 5: Позвольте генератору определить столбцы и задайте фиксированное количество строк

Когда требуется определённое количество строк — например, чтобы вписать высоту этикетки — вы можете задать строки, оставив столбцы в режиме *auto*.

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

Библиотека вычисляет оптимальное количество столбцов, чтобы разместить данные в шести строках.

## Шаг 6: Укажите и столбцы, и строки для пользовательского макета

Иногда у вас есть строгие ограничения макета (например, предварительно напечатанная форма). Вы можете явно задать оба измерения:

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

Это создаёт штрих‑код, точно соответствующий сетке 4 × 9, что удобно для выравнивания с физическими шаблонами.

## Полный исполняемый пример

Ниже приведена полная программа, последовательно выполняющая все пять шагов. Скопируйте её в `Program.cs` и запустите проект.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**Ожидаемый результат**

Запуск программы создаёт три PNG‑файла в папке вывода проекта:

- `Pdf417Columns2.png` – штрих‑код с двумя вертикальными столбцами.
- `Pdf417Rows6.png` – штрих‑код, растянутый до шести строк.
- `Pdf417Rows9Columns4.png` – штрих‑код, расположенный в сетке 4 × 9.

Вы можете открыть любое из изображений в стандартном просмотрщике, чтобы убедиться, что штрих‑код корректно считывается приложением‑сканером PDF417.

## Профессиональные советы и распространённые подводные камни

- **Unicode handling**: Генератор автоматически кодирует Unicode‑символы, но убедитесь, что целевой сканер поддерживает используемый набор символов.
- **Image format**: PNG сохраняет без потерь. Если нужен векторный формат (например, SVG) для масштабирования, замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Svg`.
- **Performance**: Повторное использование одного экземпляра `BarcodeGenerator` (как показано) эффективнее, чем создание нового для каждого макета.
- **Error handling**: Оберните вызовы `Save` в `try/catch`, чтобы отлавливать ошибки ввода‑вывода, особенно при записи в защищённые каталоги.
- **Printing considerations**: Для печатных этикеток увеличьте `XDimension.Pixels` до 3 или 4, чтобы избежать пикселизации при типичном DPI (300 dpi).

## Заключение

Теперь вы знаете, как **сгенерировать PDF417 штрих‑код** в C# с помощью библиотеки **barcode generator C# PDF417**. В руководстве рассмотрены настройка разрешения, управление

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать PDF417 штрих‑код – Компактное кодирование PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Как создать штрих‑код – Компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Библиотека штрих‑кодов Java – Добавление штрих‑кода в PDF с помощью Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}