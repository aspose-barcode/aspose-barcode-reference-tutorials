---
category: general
date: 2026-09-19
description: Создайте штрих‑код PDF417 на C# и узнайте, как сгенерировать изображение
  штрих‑кода, задать его размеры и сохранить в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: ru
lastmod: 2026-09-19
og_description: Создайте штрих‑код PDF417 на C# и узнайте, как сгенерировать изображение
  штрих‑кода, задать его размеры и сохранить в формате PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Создание штрих‑кода PDF417 и экспорт PNG в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Как создать штрих‑код PDF417 и экспортировать PNG в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код PDF417 и экспортировать PNG в C#

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как сгенерировать изображение штрих‑кода, настроить его размеры и сохранить в файл PNG. Вы увидите полностью готовый, исполняемый пример, использующий библиотеку Aspose.BarCode, который можно скопировать прямо в свой проект.

Генерация изображения штрих‑кода — частая задача для систем билетов, учёта запасов и мобильных посадочных талонов. К концу этого урока вы поймёте, **как генерировать изображение штрих‑кода**, **как задавать размеры штрих‑кода** и **как создавать PNG‑файлы штрих‑кода**, отвечающие вашим требованиям к визуальному качеству.

## Требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).
* Среда разработки, например Visual Studio 2022 или VS Code.
* Действующая лицензия на библиотеку **Aspose.BarCode for .NET** (бесплатная пробная версия подходит для этого примера).
* Базовые знания синтаксиса C#.

Установите пакет NuGet с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новое консольное приложение или добавьте код в существующий проект. Импортируйте необходимые пространства имён в начале файла:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Эти пространства имён дают доступ к классу `BarcodeGenerator` и перечислению `EncodeTypes`.

## Шаг 2: Как создать штрих‑код PDF417 – базовая конфигурация генератора

Первой операцией является создание экземпляра `BarcodeGenerator` с типом кодирования `Pdf417` и текстом, который вы хотите закодировать. Этот объект представляет штрих‑код, который будет отрисован позже.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Почему это важно*: `EncodeTypes.Pdf417` указывает библиотеке использовать символьную систему PDF417, представляющую собой многослойный линейный штрих‑код, способный хранить большие объёмы данных. Второй аргумент («Sample») — это полезная нагрузка, которая будет отображаться при сканировании штрих‑кода.

## Шаг 3: Как задать размеры штрих‑кода – тонкая настройка плотности и макета

Штрих‑код PDF417 состоит из строк и столбцов модулей. Регулирование X‑размера (ширины модуля) и количества строк/столбцов позволяет контролировать визуальную плотность и общий размер изображения.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Почему это важно*:  
* **X‑dimension** определяет, насколько широк каждый крошечный квадрат (модуль). Меньшее значение делает штрих‑код более компактным, но может усложнить чтение сканерами низкого разрешения.  
* **Columns** и **Rows** влияют на ёмкость данных и физическую форму. Увеличение количества столбцов делает штрих‑код шире; увеличение количества строк — выше. Вы можете экспериментировать со значениями до пределов, указанных в комментариях.

**Совет**: Если штрих‑код выглядит слишком плотным на экране с высоким DPI, увеличьте `XDimension.Pixels` до 3 или 4. И наоборот, для небольшой этикетки можно установить 1 пиксель и уменьшить количество столбцов.

## Шаг 4: Как сгенерировать изображение штрих‑кода – рендеринг в bitmap в памяти

После настройки генератора вы можете отрисовать штрих‑код в объект изображения. Этот шаг необязателен, если вам нужно сразу сохранить файл, но доступ к bitmap позволяет выполнить дополнительную обработку (например, добавить логотип или нарисовать рамку).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` возвращает объект `System.Drawing.Image`, которым можно управлять через GDI+, если требуется.

## Шаг 5: Как создать PNG‑файл штрих‑кода – сохранение готового изображения

Наконец, запишите изображение на диск в формате PNG. PNG сохраняет качество без потерь, что идеально для сканирующих приложений.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Почему это важно*: Метод `Save` самостоятельно обрабатывает кодирование и ввод‑вывод файлов. Использование `BarCodeImageFormat.Png` гарантирует, что результат будет портативным без потерь изображением, совместимым с браузерами и мобильными устройствами.

### Полный исполняемый пример

Ниже представлен полный код программы, который можно вставить в `Program.cs` и запустить. Замените `YOUR_DIRECTORY` на существующую папку на вашем компьютере.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Запуск программы создаст PNG‑файл, выглядящий так:

![Сгенерированный пример штрих‑кода PDF417](https://example.com/placeholder-image.png "Штрих‑код PDF417, сгенерированный с пользовательскими размерами и сохранённый как PNG")

*Alt text*: **Пример штрих‑кода PDF417, сгенерированный на C# с пользовательскими размерами и сохранённый как PNG** — это удовлетворяет требованию **create PDF417 barcode** для доступности изображения.

## Распространённые варианты и граничные случаи

| Ситуация | Рекомендованная настройка |
|-----------|------------------------|
| **Очень маленькая этикетка** (например, 1 см × 2 см) | Установите `XDimension.Pixels = 1` и уменьшите `Columns` до 2‑3. Проверьте читаемость сканером. |
| **Печать с высоким разрешением** (300 dpi и выше) | Увеличьте `XDimension.Pixels` до 3‑4 и при необходимости добавьте больше `Rows` для большей ёмкости данных. |
| **Необходим другой формат изображения** (JPEG, BMP) | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp`. |
| **Встраивание в PDF** | Используйте `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` вместо PNG. |
| **Динамические данные** (ввод пользователя) | Замените статическую строку `"Sample"` на переменную, например `userInput`. Убедитесь, что длина текста не превышает ограничения PDF417 (≈ 1800 символов). |

## Список проверки устранения неполадок

* **Пустое изображение** – Убедитесь, что целевая папка существует и приложение имеет права записи.  
* **Штрих‑код не сканируется** – Увеличьте `XDimension.Pixels` или добавьте больше столбцов/строк; низкоконтрастный фон также может вызывать ошибки.  
* **Неожиданный размер** – Проверьте значения `Columns` и `Rows`; библиотека соблюдает максимальные ограничения, указанные в комментариях.  

## Следующие шаги

Теперь, когда вы умеете **create PDF417 barcode**, рассмотрите изучение связанных тем:

* **How to generate barcode image** в других форматах, например SVG для масштабируемой веб‑графики.  
* **How to set barcode dimensions** для QR‑кодов и символьных систем DataMatrix.  
* **How to create barcode PNG** с пользовательскими цветами или встроенными логотипами с помощью `System.Drawing`.  

Эти расширения позволят построить полноценный сервис генерации штрих‑кодов, обслуживающий мобильные приложения, веб‑порталы и настольные утилиты.

---

*Вы научились создавать штрих‑код PDF417, настраивать его размеры, рендерить изображение штрих‑кода и сохранять его как PNG‑файл с помощью C#. Применяйте показанные шаблоны к другим типам штрих‑кодов и форматам изображений, чтобы расширить возможности автоматизации.*

## Что изучать дальше?

Следующие учебные материалы охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}