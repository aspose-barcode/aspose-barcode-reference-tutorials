---
category: general
date: 2026-10-02
description: Создайте изображение штрих‑кода в C# с помощью генератора штрих‑кодов,
  контролируйте размер пикселя штрих‑кода и регулируйте высоту штрих‑кода для пользовательских
  размеров.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: ru
lastmod: 2026-10-02
og_description: Создайте изображение штрихкода в C# с помощью генератора штрихкодов.
  Узнайте, как установить размер пикселя штрихкода, отрегулировать его высоту и задать
  пользовательские размеры штрихкода.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Создание изображения штрихкода в C# – руководство по генератору штрихкодов
  и пользовательским размерам
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Как создать изображение штрихкода в C# с помощью генератора штрихкодов
url: /ru/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода в C# с помощью barcode generator

Если вам нужно **создавать изображения штрих‑кода** программно, это руководство покажет вам полное, готовое к запуску решение на C#. Используя barcode generator, вы можете управлять **размером пикселя штрих‑кода**, **регулировать высоту штрих‑кода** и задавать **пользовательские размеры штрих‑кода** без выхода из вашей IDE.

Вы узнаете, как сгенерировать два PNG‑файла — один с высотой полосы 30 px, а другой с 60 px — при постоянной ширине модуля. Эти шаги работают с любым типом штрих‑кода, поддерживаемым библиотекой, поэтому вы можете адаптировать их к QR‑коду, Code 128 или другим символогиям.

## Что понадобится

- .NET 6.0 или новее (код также компилируется с .NET Framework 4.8)
- Ссылка на библиотеку штрих‑кодов (например, Aspose.BarCode for .NET или любой совместимый класс `BarcodeGenerator`)
- Базовые знания C#
- Права записи в папку, где будут сохраняться PNG‑файлы

## Шаг 1: Инициализировать barcode generator для **создания изображения штрих‑кода**

Сначала импортируйте необходимые пространства имён и создайте экземпляр `BarcodeGenerator`. Конструктор принимает тип штрих‑кода (`EncodeTypes.DatabarOmniDirectional`) и строку данных, которую вы хотите закодировать.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Создание генератора является основой любого рабочего процесса **barcode generator c#**. Он выделяет внутреннее полотно для рисования и подготавливает данные к рендерингу.

## Шаг 2: Задать **размер пикселя штрих‑кода** и начальную высоту полосы

Визуальное качество конечного изображения зависит от двух параметров:

| Параметр | Значение |
|-----------|---------|
| `XDimension.Pixels` | Ширина одного модуля (самого маленького чёрно‑белого элемента). |
| `BarHeight.Pixels` | Высота полос для текущего изображения. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Сохранение **размера пикселя штрих‑кода** постоянным при изменении высоты позволяет создавать **пользовательские размеры штрих‑кода**, соответствующие требованиям бренда или сканирования.

## Шаг 3: Сохранить первый PNG‑файл (высота 30 px)

Теперь запишите изображение на диск. Метод `Save` принимает путь к файлу и желаемый формат изображения.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

Полученный файл — это **изображение штрих‑кода** с высотой полосы 30 px и шириной модуля 2 px, идеально подходящее для компактных этикеток.

## Шаг 4: **Регулировать высоту штрих‑кода** для более крупной версии

Чтобы сгенерировать второе изображение с другим визуальным размером, нужно изменить только свойство `BarHeight.Pixels`. Это демонстрирует, насколько просто **регулировать высоту штрих‑кода** без повторного создания генератора.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Изменение высоты при сохранении **размера пикселя штрих‑кода** гарантирует чёткость полос и постоянное соотношение сторон.

## Шаг 5: Сохранить второй PNG‑файл (высота 60 px)

Наконец, сохраните более крупную версию.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Теперь у вас есть два **пользовательских размера штрих‑кода**, сохранённые рядом:

- `DatabarBarHeight30Pixels.png` – высота полосы 30 px
- `DatabarBarHeight60Pixels.png` – высота полосы 60 px

Оба изображения имеют одинаковый **размер пикселя штрих‑кода** 2 px, обеспечивая визуальную согласованность при разных размерах.

## Почему эти настройки важны

- **Размер пикселя штрих‑кода** (`XDimension`) влияет на читаемость сканером. Ширина 2 px — распространённый параметр, который балансирует размер файла и надёжность сканирования.
- **Высота полосы** определяет, насколько высоко будет отображаться штрих‑код на этикетке. Некоторые розничные сканеры требуют минимальную высоту; другие допускают более высокие полосы по эстетическим соображениям.
- Сохранение экземпляра генератора активным при изменении только `BarHeight` уменьшает выделения памяти и ускоряет пакетную обработку.

## Пограничные случаи и рекомендации по лучшим практикам

| Ситуация | Рекомендуемый подход |
|-----------|----------------------|
| **Разные форматы изображений** (JPEG, BMP) | Измените `BarCodeImageFormat.Jpeg` или `.Bmp` в вызове `Save`. JPEG меньше по размеру, но может ввести артефакты сжатия. |
| **Вывод высокого разрешения** (например, 300 DPI) | Увеличьте `XDimension.Pixels` пропорционально (например, до 4 px) и скорректируйте `BarHeight.Pixels`, чтобы сохранить тот же физический размер. |
| **Динамические строки данных** | Обёрните создание генератора в метод, принимающий строку данных как параметр, затем переиспользуйте один и тот же экземпляр `barcode` для нескольких сохранений. |
| **Потокобезопасная пакетная генерация** | Создавайте отдельный `BarcodeGenerator` для каждого потока или используйте пул поток‑локальных объектов, чтобы избежать условий гонки. |
| **Ошибки прав доступа к файловой системе** | Убедитесь, что `outputFolder` существует и процесс имеет права записи; обрабатывайте `IOException` корректно. |

## Полный листинг исходного кода

Ниже представлен полный, автономный пример программы, который вы можете скопировать, вставить и запустить.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Ожидаемый результат

После выполнения программы в папке `YOUR_DIRECTORY` появятся два PNG‑файла:

- **DatabarBarHeight30Pixels.png** – компактный штрих‑код, подходящий для небольших этикеток.
- **DatabarBarHeight60Pixels.png** – более крупная версия, идеальная для приложений с высокой видимостью.

Оба файла можно открыть в любом просмотрщике изображений, распечатать или встроить в PDF.

## Заключение

Теперь вы знаете, как **создавать изображения штрих‑кода** в C# с помощью **barcode generator c#**, управлять **размером пикселя штрих‑кода**, **регулировать высоту штрих‑кода** и создавать **пользовательские размеры штрих‑кода**, соответствующие конкретным требованиям сканирования или брендинга. Пример демонстрирует чистый, повторяемый шаблон, который масштабируется для пакетной обработки или различных символогий.

### Что изучать дальше

- [Как создать изображение штрих‑кода в C# с регулируемой высотой](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Как сгенерировать набор штрих‑кодов пользовательского размера и сохранить изображение в C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Создать изображение штрих‑кода в C# с примером barcode generator](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}