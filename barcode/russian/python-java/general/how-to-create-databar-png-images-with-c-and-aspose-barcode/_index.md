---
category: general
date: 2026-08-19
description: Создавайте PNG‑файлы Databar в C# с помощью Aspose.BarCode. Узнайте,
  как генерировать изображения Databar, настраивать параметры Databar и сохранять
  результат в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: ru
lastmod: 2026-08-19
og_description: Создавайте PNG‑файлы Databar в C# с помощью Aspose.BarCode. Этот учебник
  пошагово покажет, как генерировать изображения Databar, настраивать параметры Databar,
  такие как X‑размер и соотношение сторон, и сохранять PNG‑файлы высокого качества
  для печати или использования в вебе.
og_image_alt: create databar PNG example
og_title: Создание PNG‑изображений databar в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Как создать PNG‑изображения databar с помощью C# и Aspose.BarCode
url: /ru/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создавать PNG‑изображения DataBar с C# и Aspose.BarCode

Если вам нужно **создавать PNG‑DataBar** файлы в .NET‑приложении, это руководство покажет вам, как это сделать. Вы увидите полностью готовый, исполняемый пример, который генерирует stacked omnidirectional DataBar коды, настраивает ключевые параметры и сохраняет два PNG‑файла с разными соотношениями сторон.

Создание изображения DataBar — это не просто вызов одной функции. Вам также нужно **настраивать параметры DataBar**, такие как X‑dimension (ширина модуля) и соотношение сторон, чтобы соответствовать требованиям печати или сканирования. К концу этого руководства вы поймёте, **как генерировать графику DataBar**, которая надёжно работает в реальных сценариях.

## Предварительные требования

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Visual Studio 2022 или любой IDE, совместимый с C#
- Действительная лицензия для **Aspose.BarCode for .NET** (бесплатная оценочная версия подходит для тестирования)
- Базовое знакомство с синтаксисом C#

> **Совет:** Если у вас ещё нет лицензии, вы можете запросить временный оценочный ключ на портале Aspose. API работает так же; меняется только водяной знак.

## Шаг 1: Установите пакет Aspose.BarCode NuGet

Откройте ваш проект в Visual Studio, щёлкните правой кнопкой мыши по решению и выберите **Manage NuGet Packages**. Найдите `Aspose.BarCode` и установите последнюю стабильную версию.

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавляет сборку `Aspose.BarCode` в ваш проект и делает класс `BarcodeGenerator` доступным.

## Шаг 2: Инициализируйте генератор штрихкода для stacked omnidirectional DataBar

Конструктор `BarcodeGenerator` принимает два аргумента: тип штрихкода и строку исходных данных. Для stacked omnidirectional DataBar используйте `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Почему это важно:** Константа `EncodeTypes.DatabarStackedOmniDirectional` указывает библиотеке создавать штрихкод, который может быть считан в любой ориентации, что идеально подходит для этикеток на полках розничных магазинов.

## Шаг 3: Настройте X‑dimension (ширину модуля) в пикселях

X‑dimension управляет размером самого маленького элемента полосы. Установка её в пикселях даёт точный контроль над конечным размером изображения.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Значение **2 пикселя** обеспечивает хороший баланс между читаемостью и компактностью для большинства принтеров этикеток. При необходимости измените это значение для более крупных или более мелких модулей.

## Шаг 4: Установите первое соотношение сторон и сохраните PNG

Соотношение сторон влияет на высоту stacked DataBar. Соотношение **15** создаёт относительно короткий штрихкод, тогда как **30** делает его выше.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Метод `Save` записывает сгенерированный штрихкод в PNG‑файл. PNG — без потерь, что сохраняет чёткие края, необходимые сканерам штрихкодов.

## Шаг 5: Измените соотношение сторон и сохраните второй PNG

Вы можете повторно использовать тот же экземпляр `BarcodeGenerator` для создания вариантов, просто изменив соотношение сторон.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Теперь у вас есть два PNG‑файла — `DatabarAspectRatio15.png` и `DatabarAspectRatio30.png` — каждый с разной визуальной плотностью.

## Шаг 6: Проверьте результат

Откройте сгенерированные PNG‑файлы в любом просмотрщике изображений. Вы должны увидеть чистый, высококонтрастный штрихкод DataBar. Сканирование изображений с помощью сканера штрихкодов на смартфоне подтверждает, что оба соотношения сторон декодируются в исходное значение GTIN `12345678901231`.

![create databar PNG example](databar_example.png)

*На изображении выше показаны два PNG‑файла рядом. Левый файл использует соотношение сторон 15, правый — соотношение сторон 30.*

## Распространённые варианты и граничные случаи

| Сценарий | Что изменить | Причина |
|----------|----------------|--------|
| **Другие данные** | Замените строку `(01)12345678901231` любой допустимой GS1 Application Identifier и данными | Позволяет кодировать идентификаторы продуктов, серийные номера и т.д. |
| **Более высокое разрешение** | Увеличьте `XDimension.Pixels` до 3 или 4 | Требуется, когда штрихкод будет печататься в больших размерах или сканироваться с расстояния. |
| **Другие типы DataBar** | Используйте `EncodeTypes.DatabarStacked` или `EncodeTypes.DatabarExpanded` | Выберите тип, который лучше подходит для макета вашей этикетки. |
| **Прозрачный фон** | Передайте `BarCodeImageFormat.Png` с `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Полезно для наложения штрихкода на цветные этикетки. |

> **Осторожно:** Установка X‑dimension слишком маленькой (< 1 pixel) может привести к тому, что штрихкод будет выглядеть размытым после

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как генерировать и настраивать высоту штрихкода для One-Dimensional Databar с помощью Aspose.BarCode для .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Создание One-Dimensional Databar GS1 кодирования с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Генерация Databar штрихкода Aspose.BarCode с использованием .NET API – конфигурация строк и столбцов](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}