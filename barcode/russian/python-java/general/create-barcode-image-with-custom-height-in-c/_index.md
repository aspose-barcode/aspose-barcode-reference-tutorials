---
category: general
date: 2026-10-28
description: Создайте изображение штрих‑кода в C# и узнайте, как настроить высоту
  с помощью API BarcodeGenerator. Пошаговое руководство по настройке пользовательской
  высоты штрих‑кода и изменению высоты полос.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: ru
lastmod: 2026-10-28
og_description: Создайте изображение штрих‑кода в C# и мгновенно посмотрите, как настроить
  высоту. Следуйте этому полному примеру, чтобы задать пользовательскую высоту штрих‑кода
  с помощью BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Создание изображения штрихкода с пользовательской высотой в C# – полное
  руководство
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Создать изображение штрихкода с пользовательской высотой в C#
url: /ru/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода с пользовательской высотой в C#

Если вам нужно **создать изображение штрих‑кода** и контролировать его размеры, это руководство покажет вам, как это сделать. С помощью библиотеки Aspose.BarCode .NET вы можете сгенерировать штрих‑код GS1‑Databar Omni‑Directional, а затем **как настроить высоту**, чтобы соответствовать любым требованиям макета.

Вы пройдёте через полностью готовую к запуску программу, демонстрирующую **c# barcode generator**, объясняющую каждое установленное свойство и показывающую два разных результата — один с высотой полосы 30 пикселей, другой с высотой 60 пикселей. К концу вы сможете **изменять высоту штрих‑кода** программно для любого типа штрих‑кода, поддерживаемого библиотекой.

## Предварительные требования

- .NET 6.0 SDK или новее (код также работает с .NET Framework 4.6+)
- Visual Studio 2022 или любой редактор, способный собирать проекты C#
- NuGet‑пакет Aspose.BarCode для .NET (`Install-Package Aspose.BarCode`)
- Базовое знакомство с синтаксисом C#

> **Совет:** Если вы используете CI‑конвейер, добавьте NuGet‑пакет в ваш файл `csproj`, чтобы сборка восстанавливала его автоматически.

## Шаг 1: Настройте проект и импортируйте пространства имён

Создайте новый консольный проект и добавьте необходимые директивы `using`. Пространства имён предоставляют доступ к `BarcodeGenerator`, `EncodeTypes` и вспомогательным средствам работы с форматами изображений.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Почему это важно:** Импорт правильных пространств имён предотвращает ошибки компиляции и делает API доступным в IntelliSense.

## Шаг 2: Инициализируйте **c# barcode generator** для кода GS1‑Databar Omni‑Directional

Конструктор принимает два аргумента: тип штрих‑кода (`EncodeTypes.DatabarOmniDirectional`) и строку данных. Строка данных должна соответствовать формату идентификатора приложения GS1, например, `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Объяснение:** Объект `BarcodeGenerator` является точкой входа для всех настроек, связанных со штрих‑кодом. После получения этого экземпляра вы можете менять размеры, цвета и формат вывода.

## Шаг 3: Определите общую X‑dimension (ширина в пикселях самой узкой полосы)

X‑dimension в 2 пикселя — хороший старт для большинства сценариев отображения на экране.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Зачем задавать X‑dimension?** Она контролирует общую ширину штрих‑кода. Сохранение её постоянной гарантирует, что изменение высоты полосы не исказит визуальный баланс.

## Шаг 4: **Создайте изображение штрих‑кода** с высотой полосы 30 пикселей

Теперь мы настраиваем высоту полосы, сохраняем первое изображение, а затем меняем высоту для второго.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Результат:** Вы получаете PNG‑файл, где каждая вертикальная полоса имеет высоту 30 пикселей. X‑dimension остаётся 2 пикселя, поэтому общая ширина не меняется.

## Шаг 5: **Как изменить высоту** — изменить высоту полосы до 60 пикселей

Чтобы продемонстрировать **пользовательскую высоту штрих‑кода**, просто присвойте новое значение тому же свойству и сохраните снова.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Ключевой вывод:** Свойство `BarHeight` изменяемо; вам не нужно заново создавать экземпляр `BarcodeGenerator`. Это упрощает генерацию нескольких размеров в цикле или пакетном процессе.

## Шаг 6: Проверьте результат

Запустите консольную программу (`dotnet run`). После выполнения вы должны увидеть два PNG‑файла в папке вывода проекта:

- `DatabarBarHeight30Pixels.png` – короткие полосы (30 px)
- `DatabarBarHeight60Pixels.png` – длинные полосы (60 px)

Оба изображения содержат одинаковые закодированные данные, но визуальная высота отличается, что полезно при интеграции штрих‑кодов в формы, этикетки продуктов или UI‑компоненты с различными ограничениями по пространству.

![Создание изображения штрих‑кода с пользовательской высотой](barcode-example.png){.align-center width="600" alt="Создание изображения штрих‑кода с пользовательской высотой"}

> **Совет:** Откройте PNG‑файлы в любом просмотрщике изображений. Более высокий штрих‑код должен быть ровно вдвое выше по вертикали, чем короткий, при этом горизонтальное расстояние остаётся одинаковым.

## Шаг 7: Распространённые варианты и граничные случаи

| Situation | Recommended setting |
|-----------|---------------------|
| **Печать на высоко‑разрешающем принтере этикеток** | Используйте большую X‑dimension (например, 4 px) и увеличьте `BarHeight` пропорционально. |
| **Отображение на экране с низким DPI** | Оставьте `XDimension` равным 1 px и задайте `BarHeight` от 20 до 40 px для читаемости. |
| **Генерация QR‑кодов или 2‑D штрих‑кодов** | Свойство `BarHeight` игнорируется; используйте `EncodeTypes.QR` и вместо этого настройте `ImageHeight`. |
| **Пакетная генерация множества высот** | Итерируйте массив высот и вызывайте `Save` внутри цикла; нет необходимости воссоздавать генератор на каждой итерации. |

### Обработка недопустимых высот

Библиотека бросает `ArgumentOutOfRangeException`, если вы задаёте `BarHeight` не положительным значением. Защититесь от этого простой проверкой:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Полный исходный код (готов к копированию)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Почему это работает:** Все необходимые настройки (`EncodeTypes`, `XDimension`, `BarHeight`) применяются перед каждым вызовом `Save`. Один и тот же экземпляр `BarcodeGenerator` переиспользуется, что экономит память и упрощает чтение.

## Заключение

Теперь вы знаете, как **создавать файлы изображений штрих‑кода** в C# и точно **изменять высоту штрих‑кода** с помощью API `BarcodeGenerator`. Регулируя `BarHeight.Pixels`, вы получаете **пользовательскую высоту штрих‑кода** без пересоздания генератора, что делает решение идеальным для динамического создания этикеток, рендеринга UI или пакетных конвейеров обработки.

Далее изучайте связанные темы, такие как **как настроить ширину**, **добавление читаемого человеком текста** или **экспорт в SVG для масштабируемого веб‑использования**. Тот же шаблон — установить свойство, вызвать `Save` — применим к этим сценариям, позволяя уверенно расширять данный пример.

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как изменить высоту штрих‑кода в C# – Полное руководство](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Пример генератора штрих‑кодов — создание штрих‑кодов Planet и RM4SCC с пользовательской высотой](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Как создать штрих‑код rm4scc и контролировать его высоту в C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}