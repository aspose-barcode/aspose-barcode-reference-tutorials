---
category: general
date: 2026-11-23
description: Создайте почтовый планетарный штрих‑код в C# с помощью Aspose.BarCode.
  Узнайте, как генерировать планетарный штрих‑код, установить X‑размер и сохранить
  заполненные или пустые штрихи.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: ru
lastmod: 2026-11-23
og_description: Создайте почтовый планетарный штрих‑код на C# и узнайте, как генерировать
  планетарный штрих‑код с помощью Aspose.BarCode. Следуйте полному примеру, чтобы
  получить заполненные и пустые полосы.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Как создать штрих‑код Postal Planet в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Как создать штрих‑код Postal Planet в C#
url: /ru/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать почтовый планетарный штрих‑код в C#

Если вам нужно **создать почтовый планетарный штрих‑код** в приложении .NET, это руководство покажет вам точно **как генерировать планетарный штрих‑код** с использованием библиотеки Aspose.BarCode. Вы увидите, как настроить X‑dimension, переключаться между заполненными и пустыми полосами и сохранять изображения в формате PNG.

Создание планетарного штрих‑кода часто требуется для почтовых служб, которым нужны высокоплотные, машинно‑читаемые символы. К концу этого руководства у вас будет два PNG‑файла — один с сплошными полосами, другой с полыми полосами — готовые к интеграции в любой почтовый процесс.

## Требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия.
* Visual Studio 2022 (или любой редактор C#), настроенный для разработки под .NET.
* Действующая лицензия NuGet для **Aspose.BarCode for .NET**. Установите пакет с помощью:

```bash
dotnet add package Aspose.BarCode
```

Дополнительные внешние сервисы не требуются; библиотека выполняет всё кодирование локально.

## Шаг 1 – создать почтовый планетарный штрих‑код

Первая операция — создать экземпляр `BarcodeGenerator` для символьного набора **Planet** и передать данные для кодирования. Строка данных должна быть числовой и содержать не более 12 цифр согласно почтовой спецификации.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Создание генератора выделяет все внутренние структуры, необходимые для отрисовки. Значение перечисления `EncodeTypes.Planet` выбирает правильный алгоритм кодирования для почтового формата.

## Шаг 2 – установить X‑dimension для лучшей видимости

X‑dimension определяет ширину одного модуля (самого маленького элемента полосы). Значение 4 пикселя обеспечивает чёткое визуальное представление без увеличения общего размера изображения.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Настройка X‑dimension важна, когда штрих‑код будет печататься на низкокачественных носителях. То же значение будет использовано для версии с пустыми полосами, чтобы обе картинки были согласованы.

## Шаг 3 – сохранить штрих‑код со сплошными полосами

По умолчанию генератор отрисовывает **filled bars** (сплошные чёрные модули). Сохранение изображения выполняется одним вызовом метода, который записывает PNG‑файл на диск.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Замените `YOUR_DIRECTORY` фактическим путём, где вы хотите разместить выходные файлы. Перечисление `BarCodeImageFormat.Png` гарантирует сжатие без потерь, что идеально для последующей обработки.

## Шаг 4 – создать ещё один генератор Planet‑штрих‑кода для пустых полос

Чтобы получить версию с **empty bars** (белыми модулями на чёрном фоне), понадобится второй экземпляр `BarcodeGenerator`. Повторное использование той же строки данных гарантирует, что оба изображения представляют один и тот же почтовый код.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Создание отдельного генератора изолирует свойство `FilledBars`, позволяя переключать визуальный стиль без влияния на первое изображение.

## Шаг 5 – настроить генератор для отрисовки пустых полос

Флаг `FilledBars` меняет режим отрисовки. Установка его в `false` сообщает библиотеке рисовать полосы как пустые (прозрачные), оставляя фон сплошным.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Сохранение одинакового X‑dimension, как и в версии со сплошными полосами, гарантирует одинаковые размеры PNG‑файлов, что упрощает расчёты разметки в шаблонах печати.

## Шаг 6 – сохранить штрих‑код, отрисованный пустыми полосами

Наконец, запишите изображение с пустыми полосами на диск. Используется тот же формат PNG, но при желании можно переключиться на JPEG или BMP, изменив значение `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

На данный момент у вас есть два файла:

* `PostalPlanetFilledBars.png` — сплошные чёрные полосы.
* `PostalPlanetEmptyBars.png` — полые полосы на чёрном фоне.

Оба соответствуют почтовой спецификации для символьного набора Planet.

## Полный исходный код

Собрав все шаги вместе, получаем компактное консольное приложение, которое можно запустить сразу.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Скомпилируйте и запустите программу:

```bash
dotnet run
```

Консоль выводит *Barcodes generated successfully.* и два PNG‑файла появляются в папке проекта.

## Ожидаемый результат

Ниже показано визуальное представление изображения со сплошными полосами. Версия с пустыми полосами выглядит идентично, за исключением того, что полосы прозрачные.

![Пример созданного почтового планетарного штрих‑кода с заполненными полосами](postal-planet-filled.png)

*Image alt text:* **Пример созданного почтового планетарного штрих‑кода с заполненными полосами** (contains the primary keyword).

Оба изображения по умолчанию имеют размер 150 × 150 пикселей, но вы можете управлять общим размером с помощью параметров `ImageWidth` и `ImageHeight`, если требуется другое разрешение.

## Дополнительные варианты

### Изменение формата изображения

Если ваша downstream‑система предпочитает JPEG, замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`. JPEG вводит артефакты сжатия, поэтому используйте его только когда размер файла критичен.

### Масштабирование штрих‑кода

Можно увеличить штрих‑код, сохранив ширину модуля, изменив свойство `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Более высокие значения DPI улучшают качество печати на лазерных принтерах.

### Использование пользовательского цвета фона

Фон можно задать так:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Это удобно для визуального тестирования, но в производственных почтовых этикетках, требующих белого фона, следует избегать.

## Часто задаваемые вопросы

**Работает ли это с .NET Core?**  
Да. Библиотека Aspose.BarCode ориентирована на .NET Standard 2.0, что совместимо с .NET 5, .NET 6 и .NET Core 3.1.

**Что если строка данных содержит нечисловые символы?**  
Planet‑штрих‑коды принимают только числовой ввод. Передача букв или символов вызывает `BarcodeException`. Проверьте ввод перед созданием генератора.

**Можно ли сгенерировать штрих‑код в памяти без записи на диск?**  
Используйте метод `GenerateBarCodeImage`, чтобы получить объект `System.Drawing.Image`, а затем передайте его напрямую в ответ или в базу данных.

## Заключение

Теперь вы знаете, как **создать почтовый планетарный штрих‑код** в C# и понимаете **как генерировать планетарный штрих‑код** как со сплошными, так и с пустыми полосами. Руководство охватило весь процесс — от инициализации генератора, настройки X‑dimension, переключения флага `FilledBars` до сохранения PNG‑файлов. Экспериментируйте с форматами изображений, настройками DPI и цветами фона, чтобы адаптировать штрих‑код к вашей системе рассылки.

Для следующего шага изучите другие почтовые символьные наборы, такие как **POSTNET** или **Intelligent Mail**, используя тот же API Aspose.BarCode. Параметры вроде `EncodeTypes.Postnet` настраиваются по той же схеме, продемонстрированной здесь, позволяя построить полноценный набор генерации штрих‑кодов в единой кодовой базе.

## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создать пустой планетарный штрих‑код, сгенерировать почтовый штрих‑код в C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Как задать ширину и сгенерировать планетарный штрих‑код в C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Генерация почтового штрих‑кода в C# — полный гид с планетарным штрих‑кодом](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}