---
category: general
date: 2026-10-28
description: Создайте почтовый штрих‑код в C# с использованием формата Planet. Этот
  пример штрих‑кода Planet показывает, как задать ширину штрих‑кода и сохранить как
  заполненные, так и пустые полосы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: ru
lastmod: 2026-10-28
og_description: Создайте почтовый штрих‑код на C# с полным примером штрих‑кода Planet.
  Узнайте, как задать ширину штрих‑кода, генерировать заполненные полосы и создавать
  изображения пустых полос.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Создание почтового штрихкода на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как сгенерировать почтовый штрих‑код в C# — пример планеты
url: /ru/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать почтовый штрих‑код в C# – пример Planet

Если вам нужно сгенерировать почтовый штрих‑код в C#, это руководство проведёт вас через полное решение. Вы увидите практический пример штрих‑кода Planet, который кодирует числовую строку, позволяет задать ширину штрих‑кода и сохраняет как заполненные, так и пустые изображения полос.

Создание почтового штрих‑кода не требует сложного конвейера сборки. К концу этого руководства вы сможете интегрировать генерацию штрих‑кода в любое приложение .NET, настроить X‑размер и выбрать, будут ли полосы заполненными или пустыми.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более новая версия, установленная  
* Среда разработки C# (Visual Studio, VS Code или Rider)  
* NuGet‑пакет **Aspose.BarCode for .NET** (версия 23.10 или новее)  

Вы можете добавить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

В приведённых ниже фрагментах кода предполагается, что вы добавили `using Aspose.BarCode.Generation;` в начало вашего файла.

## Генерация почтового штрих‑кода с симбологией Planet

Первый шаг — создать экземпляр `BarcodeGenerator`, использующий симбологию Planet. Planet — это формат почтового штрих‑кода, применяемый несколькими национальными почтовыми службами.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Почему это важно:**  
`EncodeTypes.Planet` указывает библиотеке использовать стандарт штрих‑кода Planet, который кодирует числовые данные в серии полос и пробелов. Конструктор принимает строку данных (`"123456"` в данном случае), которую вы хотите закодировать.

Запуск программы создаёт два PNG‑файла в рабочем каталоге исполняемого файла:

* **PostalPlanetFilledBars.png** — полосы отображаются как сплошные чёрные прямоугольники.  
* **PostalPlanetEmptyBars.png** — полосы отображаются как белые прямоугольники с чёрной окантовкой, что удобно для печати на тёмных фонах.

## Установка ширины штрих‑кода (X‑размер) в пикселях

Визуальный размер штрих‑кода контролируется X‑размером, который определяет ширину отдельной полосы. Регулирование этого значения гарантирует корректное сканирование штрих‑кода при заданном разрешении печати.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Почему стоит установить его:**  
Большой X‑размер упрощает сканирование штрих‑кода сканерами низкого разрешения, тогда как меньший размер уменьшает общий размер изображения для печати высокой плотности. Ширина по умолчанию — 2 пикселя; 4 пикселя часто являются хорошим компромиссом для большинства настольных принтеров.

Вы можете экспериментировать с различными значениями:

| Пиксели | Типичный сценарий использования |
|--------|---------------------------------|
| 2      | Метки высокой плотности |
| 4      | Обычная офисная печать |
| 6‑8    | Большие вывески |

**Подсказка:** После изменения X‑размера всегда проверяйте сгенерированный штрих‑код на целевом сканере.

## Пример штрих‑кода Planet — заполненные vs пустые полосы

Штрих‑код Planet может быть отрисован либо сплошными (заполненными) полосами, либо контурными (пустыми) полосами. Свойство `FilledBars` переключает это поведение.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Почему вы можете выбрать пустые полосы:**  
Пустые полосы улучшают контраст на тёмных упаковках, потому что белый внутренний участок каждой полосы выделяется на тёмном фоне. Заполненные полосы являются значением по умолчанию и хорошо работают на светлых носителях.

**Ожидаемый результат:**  

*Оба изображения отображают одни и те же закодированные данные (`123456`).* Единственное визуальное различие — стиль полос. Ниже текстовое описание того, что вы увидите:

* **Изображение с заполненными полосами:** Сплошные чёрные вертикальные полосы на белом фоне.  
* **Изображение с пустыми полосами:** Чёрные контуры, образующие тот же узор, с белыми внутренними областями.

Вы можете открыть PNG‑файлы в любом просмотрщике изображений, чтобы убедиться, что узор соответствует спецификации Planet.

## Настройка дополнительных свойств штрих‑кода (необязательно)

Хотя основные шаги выше покрывают большинство сценариев, вы можете захотеть тонко настроить другие параметры:

| Свойство | Описание | Типичное значение |
|----------|----------|-------------------|
| `Barcode.Color` | Цвет переднего плана полос | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Цвет заливки фона | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Читаемый человеком текст, отображаемый под штрих‑кодом | То же, что закодированные данные, или пользовательская метка |
| `Barcode.ImageFormat` | Формат вывода (PNG, JPEG, BMP и т.д.) | `BarCodeImageFormat.Png` |

Пример установки пользовательского цвета переднего плана:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Эти необязательные настройки помогут вам соответствовать фирменному стилю или удовлетворять специфическим требованиям печати.

## Распространённые ошибки и как их избежать

| Проблема | Причина | Решение |
|----------|---------|---------|
| Штрих‑код нечитаем | X‑размер слишком мал для DPI принтера | Увеличьте `XDimension.Pixels` до 4 или более |
| Файл изображения повреждён | Отсутствуют права записи в целевой папке | Используйте абсолютный путь или убедитесь, что каталог существует |
| Выбрана неправильная симбология | Передан `EncodeTypes.Code128` вместо `EncodeTypes.Planet` | Проверьте, что аргумент `EncodeTypes` соответствует почтовому формату |

**Профессиональный совет:** Всегда генерируйте тестовый штрих‑код и сканируйте его на целевом оборудовании перед выпуском в продакшн.

## Полный, готовый к запуску пример

Ниже представлено автономное консольное приложение, включающее все обсуждённые шаги. Скопируйте код в новый .NET‑консольный проект и запустите его, чтобы увидеть два PNG‑файла в выходном каталоге.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Шаги проверки:**  

1. Сборка проекта (`dotnet build`).  
2. Запуск исполняемого файла (`dotnet run`).  
3. Найдите `PostalPlanetFilledBars.png` и `PostalPlanetEmptyBars.png` в папке `bin/Debug/net6.0`.  
4. Откройте каждое изображение; вы должны увидеть серию вертикальных полос, представляющих числовую строку.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}