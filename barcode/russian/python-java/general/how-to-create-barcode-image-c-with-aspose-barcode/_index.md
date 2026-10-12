---
category: general
date: 2026-10-12
description: Создайте изображение штрихкода на C# с помощью Aspose.BarCode за считанные
  минуты. Этот пошаговый пример генератора штрихкодов на C# показывает, как установить
  соотношения сторон и сохранить файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: ru
lastmod: 2026-10-12
og_description: Создайте изображение штрих‑кода на C# мгновенно. Следуйте этому примеру
  генератора штрих‑кодов на C#, чтобы получать PNG‑изображения штрих‑кодов высокого
  качества с пользовательскими соотношениями сторон.
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: Создание изображения штрихкода в C# – быстрое руководство с Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Как создать изображение штрихкода в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрихкода c# с Aspose.BarCode

Если вам нужно **быстро создать изображение штрихкода c#**, это руководство проведет вас через полный, исполняемый пример. Независимо от того, разрабатываете ли вы систему печати транспортных этикеток или сканер инвентаря, нижеуказанные шаги показывают, как точно настроить штрихкод DataBar Stacked Omnidirectional, скорректировать его визуальные параметры и сохранить результат в файл PNG.

Вы также увидите **пример генератора штрихкода c#**, демонстрирующий изменение соотношения сторон «на лету», позволяющий создавать несколько вариантов без переписывания кода. Внешняя документация не требуется — просто скопируйте, вставьте и запустите.

## Что вам понадобится

Перед началом убедитесь, что у вас есть:

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
* Пакет **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Папка, в которую будут записываться сгенерированные PNG‑файлы (замените `YOUR_DIRECTORY` в коде)

Эти предварительные условия гарантируют, что **пример генератора штрихкода c#** будет работать на любой современной машине разработки под Windows, Linux или macOS.

## Как создать изображение штрихкода c# с помощью Aspose.BarCode

Процесс состоит из четырёх коротких шагов: создать генератор, задать размер модуля, настроить соотношение сторон и, наконец, сохранить изображение. Каждый шаг объясняется, чтобы вы понимали *почему* это важно, а не только *что* нужно ввести.

### Шаг 1 – Инициализация генератора штрихкода

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**Почему это важно:** Конструктор `BarcodeGenerator` принимает два аргумента: тип штрихкода (`EncodeTypes.DatabarStackedOmniDirectional`) и строку исходных данных. Префикс `(01)` сообщает сканеру, что последующие 14 цифр представляют идентификатор GTIN‑14, что является распространённым требованием в розничной торговле и логистике.

### Шаг 2 – Установить размер модуля (X‑dimension)

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Почему это важно:** X‑dimension управляет шириной самого маленького штриха («модуля»). Значение `2` пикселя дает чёткий, высоко‑разрешающий штрихкод, остающийся читаемым после масштабирования. Если нужен более крупный штрихкод для плаката, увеличьте это значение пропорционально.

### Шаг 3 – Сохранить первое изображение с соотношением сторон 15

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Почему это важно:** Символы DataBar поддерживают *соотношение сторон*, влияющее на соотношение высоты к ширине. Соотношение `15` является значением по умолчанию для многих розничных приложений и создаёт компактный, почти квадратный штрихкод, который легко помещается на небольших этикетках.

### Шаг 4 – Изменить соотношение сторон на 30 и сохранить второе изображение

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**Почему это важно:** Увеличение соотношения сторон до `30` растягивает штрихкод по вертикали, улучшая читаемость на сканерах с низким разрешением или на этикетках, которые выше, чем шире. Поскольку используется тот же экземпляр `BarcodeGenerator`, вы избегаете создания нового объекта для каждой вариации — эффективный подход для пакетной обработки.

## Полный, исполняемый пример

Ниже приведена полная программа, которую вы можете скопировать в консольное приложение. Она включает необходимые директивы `using`, обработку ошибок и комментарии, объясняющие каждую строку.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### Ожидаемый результат

Запуск программы создаёт два PNG‑файла:

| Имя файла | Соотношение сторон | Типичное применение |
|-----------|--------------------|---------------------|
| `DatabarAspectRatio15.png` | 15 | Стандартная розничная этикетка |
| `DatabarAspectRatio30.png` | 30 | Высокая этикетка или сканер с низким разрешением |

Оба изображения содержат чёткий штрихкод DataBar Stacked Omnidirectional, кодирующий значение GTIN‑14 `12345678901231`. Вы можете открыть PNG‑файлы в любом просмотрщике изображений, чтобы проверить визуальное качество.

![Sample barcode image created with C# using Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="Пример изображения штрихкода, созданного на C# с помощью Aspose.BarCode"}

*Текст alt выше включает основной ключевой запрос, помогая как поисковым системам, так и программам чтения с экрана.*

## Дополнительные соображения и рекомендации по лучшим практикам

* **Поддерживаемые форматы** – `BarCodeImageFormat` поддерживает PNG, JPEG, BMP, GIF и TIFF. PNG является без потерь, что делает его самым надёжным выбором для последующего сканирования.
* **Настройка цветов** – Вы можете изменить цвета переднего/фонового плана через `generator.Parameters.Barcode.ForegroundColor` и `BackgroundColor`. Это полезно при печати на цветных носителях.
* **Пакетная генерация** – Для больших инвентарей оберните логику сохранения в цикл `foreach`, который читает данные о продуктах из CSV‑файла. Повторное использование того же экземпляра `BarcodeGenerator` снижает нагрузку на память.
* **Обработка ошибок** – Блок `try/catch` в полном примере перехватывает такие проблемы, как неверные строки данных или ошибки прав записи, которые часто возникают, когда целевая директория не существует.
* **Производительность** – Установка `XDimension.Pixels` до первого вызова `Save` гарантирует, что рендерер вычислит размер bitmap только один раз при изменении соотношения сторон.

## Заключение

Теперь вы знаете, как **создать изображение штрихкода c#** с помощью Aspose.BarCode, настроить X‑dimension, переключать соотношения сторон и сохранять PNG‑файлы в одном переиспользуемом блоке кода. Этот **пример генератора штрихкода c#** охватывает наиболее распространённые варианты, с которыми вы столкнётесь при генерации символов DataBar Stacked Omnidirectional для розничных или логистических приложений.

## Что дальше?

* Изучите другие символьные наборы, такие как `EncodeTypes.Code128` или `EncodeTypes.QR`, чтобы расширить ваше решение.
* Поэкспериментируйте с `generator.Parameters.Barcode.ImageMargin`, чтобы добавить пустое пространство вокруг штрихкода.
* Интегрируйте сгенерированные PNG‑файлы в PDF‑счета с помощью Aspose.PDF или внедрите их напрямую в HTML‑отчёты.

Не стесняйтесь адаптировать код под ваш конкретный рабочий процесс — независимо от того, нужен ли вам один образец на продукт или массовый экспорт тысяч штрихкодов, показанный здесь шаблон масштабируется эффективно.

---

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать изображение штрихкода с Aspose.Barcode в C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Пример генератора штрихкода в C# – Установка столбцов, строк и экспорт изображения](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Как создать почтовый штрихкод в C# с помощью Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}