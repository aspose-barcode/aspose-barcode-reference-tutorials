---
category: general
date: 2026-08-22
description: Как быстро генерировать штрих‑код и узнать, как изменить размер штрих‑кода
  при экспорте изображения штрих‑кода в формате PNG с использованием Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: ru
lastmod: 2026-08-22
og_description: Как сгенерировать штрих‑код в C# и легко изменить его размер перед
  экспортом изображения штрих‑кода в PNG. Следуйте этому полному руководству.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Как генерировать изображения штрихкодов с пользовательским размером в C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как генерировать изображения штрихкодов с пользовательским размером в C#
url: /ru/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать изображения штрих‑кодов с пользовательским размером в C#

Если вам нужно **как генерировать штрих‑код** для почтовой автоматизации, учёта запасов или билетов на мероприятия, это руководство покажет готовое решение, которое можно сразу запустить в C#. Вы также узнаете, **как изменить размер штрих‑кода** и **экспортировать изображение штрих‑кода** в формате PNG, не покидая IDE.

Мы будем использовать библиотеку Aspose.BarCode, потому что она поддерживает символьную схему OneCode, позволяет управлять размерами пиксель‑за‑пикселем и экспортировать изображение одним вызовом метода. К концу урока у вас будет четыре PNG‑файла — каждый представляет штрих‑код OneCode с разным количеством цифр.

## Предварительные требования

- .NET 6.0 или новее (код также работает с .NET Framework 4.6+)
- Visual Studio 2022 (или любой другой редактор C# по вашему выбору)
- NuGet‑ссылка на **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Базовое знакомство с синтаксисом C#

> **Pro tip:** Если вы оцениваете библиотеку, Aspose предлагает бесплатную 30‑дневную пробную версию, включающую все функции штрих‑кодов.

## Шаг 1: Создайте минимальный консольный проект

Создайте новое консольное приложение и добавьте пакет Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Сгенерированный файл `Program.cs` будет содержать всю логику генерации штрих‑кода.

## Шаг 2: Как генерировать штрих‑код – создаём переиспользуемый метод

Ниже приведён автономный метод, который принимает строку данных, желаемое имя файла и необязательные параметры размера. Этот метод демонстрирует основной шаблон **как генерировать штрих‑код**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Почему важен этот метод

- **Инкапсуляция:** Все настройки, связанные с размером, находятся в одном месте, что упрощает вызов метода с разными размерами.
- **Переиспользуемость:** Вы можете использовать один и тот же метод для любой длины строки OneCode, что важно, поскольку OneCode принимает только 20‑31 цифру.
- **Ясность:** Комментарии с эмодзи помогают читателям пройти через три логические фазы — инициализацию, изменение размера и экспорт.

## Шаг 3: Измените размер штрих‑кода под разные требования

Иногда сканеру нужен более высокий штрих‑код, или макет печати требует более узкого модуля. Свойство `XDimension.Pixels` управляет шириной отдельного модуля штрих‑кода, а `BarHeight.Pixels` задаёт общую высоту.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Ключевые моменты при изменении размера:**

- **Минимальная X‑размерность:** Технически допускается 1 пиксель, но большинству сканеров требуется минимум 2 пикселя для надёжного чтения.
- **Максимальная высота:** Жёсткого ограничения нет, но очень высокие штрих‑коды могут выйти за пределы печатной области стандартных этикеток.
- **Соотношение сторон:** Сохраняйте соотношение высоты к ширине модуля в пределах (≈12‑15 × ширина модуля), чтобы избежать искажений.

## Шаг 4: Экспорт изображения штрих‑кода в другие форматы (по желанию)

Метод `Save` принимает несколько значений `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Если нужен без потерь векторный формат, можно экспортировать в `Svg`.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Экспорт в PNG — самый распространённый выбор, поскольку он сохраняет чёткие границы и широко поддерживается веб‑браузерами и системами печати.

## Ожидаемый результат

Запуск программы создаст четыре PNG‑файла в папке проекта:

- `PostalOneCodeBarcode20Digits.png` – штрих‑код OneCode из 20 цифр
- `PostalOneCodeBarcode25Digits.png` – штрих‑код OneCode из 25 цифр
- `PostalOneCodeBarcode29Digits.png` – штрих‑код OneCode из 29 цифр
- `PostalOneCodeBarcode31Digits.png` – штрих‑код OneCode из 31 цифры

Каждое изображение будет выглядеть примерно так (реальный график зависит от введённых числовых данных).

![Как генерировать пример штрих‑кода](https://example.com/placeholder.png "Как генерировать пример штрих‑кода")

*Текст alt изображения включает основной ключевой запрос для доступности и SEO.*

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| **Что делать, если строка данных короче 20 цифр?** | OneCode требует минимум 20 цифр. Дополните строку ведущими нулями или используйте другую символьную схему (например, Code128). |
| **Можно ли генерировать штрих‑коды в многопоточном окружении?** | Да. `BarcodeGenerator` не является потокобезопасным, поэтому создавайте отдельный генератор для каждого потока. |
| **Как задать цвет фона?** | Используйте `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` перед вызовом `Save`. |
| **Можно ли встроить изображение напрямую в HTML‑страницу?** | Сохраните изображение в `MemoryStream`, преобразуйте в Base64 и вставьте с помощью `<img src="data:image/png;base64,..." />`. |

## Заключение

Теперь вы знаете, **как генерировать изображения штрих‑кодов** в C# с помощью Aspose.BarCode, **как изменить размер штрих‑кода**, регулируя X‑размерность и высоту полос, а также **как экспортировать изображения штрих‑кодов** в PNG (или другие) форматы. Переиспользуемый метод `GenerateOneCode` позволяет создавать любой штрих‑код OneCode от 20 до 31 цифры одной строкой кода.

Дальше вы можете:

- Поэкспериментировать с другими символьными схемами (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Интегрировать генератор в веб‑API, которое будет возвращать изображения штрих‑кодов по запросу.
- Скомбинировать вывод PNG с библиотекой PDF для встраивания штрих‑кодов в транспортные этикетки.

Приятного кодинга, и делитесь своими вариантами в комментариях!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}