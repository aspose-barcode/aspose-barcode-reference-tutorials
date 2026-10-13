---
category: general
date: 2026-09-26
description: Узнайте, как быстро создать планетарный штрих‑код в C#. Это руководство
  охватывает заполненные и пустые планетарные штрих‑коды, настройки X‑размера и экспорт
  изображений.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: ru
lastmod: 2026-09-26
og_description: Создайте штрих‑код Planet на C# с полным примером кода. Генерируйте
  как заполненные, так и пустые штрих‑коды Planet, задавайте ширину полосы и сохраняйте
  в PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Создайте изображения штрихкода планеты на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать изображения штрихкодов планет в C# с помощью BarcodeGenerator
url: /ru/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображения штрихкода Planet в C# с помощью BarcodeGenerator

Если вам нужно **создать штрихкод Planet** изображения в .NET‑приложении, этот учебник покажет вам точные шаги. Вы узнаете, как генерировать как заполненный, так и пустой штрихкод Planet, настроить ширину полосы и экспортировать результаты в файлы PNG — всё с помощью библиотеки Aspose.BarCode for .NET.

Создание решения **Planet barcode C#** довольно просто, как только вы поймете ключевые **barcode generator parameters**. В последующих разделах мы пройдемся по полному, исполняемому коду, объясним, почему каждый параметр важен, и укажем распространенные подводные камни, чтобы вы могли избежать их с первого раза.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия, установленная.
* Visual Studio 2022 (или любой предпочитаемый вами IDE для C#).
* Пакет NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`), добавленный в ваш проект.

Вы можете добавить пакет через консоль NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Настройка BarcodeGenerator

Класс `BarcodeGenerator` является точкой входа для всех задач по созданию штрихкодов. Он требует два аргумента: тип штрихкода (`EncodeTypes.Planet`) и данные для кодирования.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Почему это важно:* Создание экземпляра генератора с `EncodeTypes.Planet` указывает библиотеке использовать символьную схему **Planet barcode**, которая часто применяется в почтовых службах некоторых стран. Строка `"123456"` — это полезная нагрузка, которая появится в штрихкоде.

## Шаг 2: Настройка X‑dimension (ширина полосы)

X‑dimension управляет физической шириной каждой полосы. Типичное значение для отображения на экране — 4 пикселя, но вы можете изменить его в соответствии с требованиями печати.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Почему это важно:* Установка `XDimension.Pixels` гарантирует, что сгенерированный штрихкод будет не слишком тонким (что может привести к ошибкам сканирования) и не слишком толстым (что тратит место). То же значение будет использовано для пустого штрихкода.

## Шаг 3: Сохранение заполненного штрихкода Planet

Экспортируйте штрихкод в файл PNG с помощью метода `Save`. Перечисление `BarCodeImageFormat.Png` указывает библиотеке создавать без потерь изображение, подходящее для дальнейшей обработки.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

После запуска программы вы найдете файл `PostalPlanetFilledBars.png` в папке вывода. Откройте его, чтобы убедиться, что полосы сплошные (заполненные).

## Шаг 4: Создание генератора для пустого штрихкода Planet

**Пустой штрихкод planet** отображает те же данные, но с незаполненными (белыми) полосами. Это полезно для визуальных дизайнов, где штрихкод накладывается на цветные фоны.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Вызов конструктора идентичен версии с заполнением; различие заключается в параметре, который мы изменим дальше.

## Шаг 5: Повторное использование того же X‑dimension

Чтобы сохранить визуальный размер одинаковым, примените ту же ширину полосы к пустому штрихкоду.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Повторное использование **barcode generator parameters** гарантирует, что оба изображения будут идеально совпадать при размещении рядом.

## Шаг 6: Переключение на незаполненные полосы

Флаг `FilledBars` определяет, будут ли полосы отрисованы как сплошные черные (по умолчанию) или прозрачные белые.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Почему это важно:* Установка `FilledBars = false` меняет режим отрисовки, что является ключевым различием между заполненным и пустым штрихкодом Planet.

## Шаг 7: Сохранение пустого штрихкода Planet

Наконец, экспортируйте пустую версию в PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

При запуске программы появятся два файла:

* `PostalPlanetFilledBars.png` — сплошные черные полосы.
* `PostalPlanetEmptyBars.png` — прозрачные (незаполненные) полосы.

Оба изображения содержат одинаковые данные (`123456`) и используют одну и ту же X‑dimension, что делает их взаимозаменяемыми в большинстве сценариев пользовательского интерфейса.

## Полный, исполняемый пример

Объединив всё вместе, представляем полный исходный файл, который вы можете скопировать и вставить в новый консольный проект:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Ожидаемый результат**

Запуск программы создаёт два PNG‑файла в рабочем каталоге исполняемого файла. Откройте их в любом просмотрщике изображений:

* **Заполненная версия** — тёмные, сплошные полосы, которые легко читаются стандартными сканерами.
* **Пустая версия** — полосы выглядят как белые пробелы на чёрном фоне, что полезно для наложения.

## Распространённые ошибки и профессиональные советы

| Проблема | Почему это происходит | Как исправить |
|----------|-----------------------|---------------|
| Полосы выглядят слишком тонкими | X‑dimension оставлен по умолчанию (1 пиксель) | Установите `XDimension.Pixels` в диапазон 3‑5 пикселей для отображения на экране; увеличьте значение для печати высокого разрешения. |
| Пустой штрихкод отображается полностью чёрным | `FilledBars` не установлен в `false` | Убедитесь, что `emptyPlanet.Parameters.Barcode.FilledBars = false;` выполняется **после** установки X‑dimension. |
| Отсутствует PNG‑файл | Путь вывода неверный или каталог не существует | Укажите полный путь (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) или создайте каталог заранее с помощью `Directory.CreateDirectory`. |
| Штрихкод не сканируется | Строка данных содержит недопустимые символы для символьной схемы Planet | Штрихкоды Planet принимают только числовую нагрузку; проверьте ввод с помощью `int.TryParse`. |

**Совет:** Если вам нужно встроить штрихкод в PDF, вы можете загрузить сгенерированный PNG в `PdfDocument` с помощью Aspose.PDF, либо напрямую добавить штрихкод как поток изображения без записи на диск.

## Следующие шаги

Теперь, когда вы можете **создавать изображения штрихкода planet**, рассмотрите возможность изучения следующих связанных тем:

* **Planet barcode C#** — настройка цветов, добавление читаемого человеком текста или встраивание штрихкода в PDF.
* **Barcode generator parameters** — настройка уровня коррекции ошибок, зоны тишины (quiet zone) или вращения.
* **Batch generation** — перебор списка почтовых кодов для создания zip‑файла с PNG‑изображениями.
* **Alternative formats** — экспорт в SVG или JPEG для веб‑дружелюбной доставки.

Экспериментируйте с различными значениями `XDimension` и флагом `FilledBars`, чтобы увидеть, как они влияют на надёжность сканирования и визуальный стиль. Когда будете готовы, интегрируйте код генерации в ваш веб‑API или настольное приложение, чтобы автоматизировать создание почтовых штрихкодов в реальном времени.

---

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать Planet Barcode в C# – Полное пошаговое руководство](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – пример создания Planet barcode и RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Генерация почтового штрихкода в C# – Полное руководство с Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}