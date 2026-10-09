---
category: general
date: 2026-09-29
description: Создайте штрих‑код RM4SCC на C# с полным примером кода и узнайте, как
  генерировать штрих‑код Planet, используя ту же библиотеку. Включает варианты автоматической
  и фиксированной высоты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- barcode generator example c#
- how to generate planet barcode
language: ru
lastmod: 2026-09-29
og_description: Создайте штрих‑код RM4SCC на C# с готовым к запуску примером. Руководство
  также показывает, как генерировать штрих‑код Planet, охватывая автоматическую и
  фиксированную высоту полос.
og_image_alt: Screenshot showing a generated RM4SCC barcode created with C#
og_title: Создание штрих‑кода RM4SCC на C# – полный учебник генератора
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create RM4SCC barcode C# with a full code example and learn how to
    generate Planet barcode using the same library. Includes auto and fixed height
    options.
  headline: Create RM4SCC barcode C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
title: Создание штрих‑кода RM4SCC на C# – пошаговое руководство
url: /ru/python-java/general/create-rm4scc-barcode-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода RM4SCC на C# – пошаговое руководство

Если вам нужно **быстро создать штрих‑код RM4SCC C#**, это руководство покажет полностью готовый, исполняемый пример. Вы также увидите **пример генератора штрих‑кода C#**, который демонстрирует **как сгенерировать штрих‑код Planet** в том же проекте.  

Код использует библиотеку Aspose.BarCode for .NET, поддерживающую как почтовые стандарты (RM4SCC, Planet), так и широкий набор линейных и 2‑D символогий. К концу этого урока вы сможете:

* Сгенерировать штрих‑код RM4SCC с автоматическим расчётом высоты.  
* Сгенерировать тот же штрих‑код с фиксированной высотой полос.  
* Создать штрих‑код Planet, используя те же шаги конфигурации.  

Никакие внешние сервисы не требуются — всё работает локально в любой среде .NET 6+.

## Требования

| Требование | Почему это важно |
|------------|-------------------|
| .NET 6 SDK или новее | Библиотека нацелена на .NET Standard 2.0+, поэтому .NET 6 гарантирует совместимость. |
| Visual Studio 2022 (или любой IDE) | Обеспечивает IntelliSense и удобное управление проектом. |
| Aspose.BarCode for .NET NuGet‑пакет | Содержит `BarcodeGenerator`, `EncodeTypes` и поддержку форматов изображений. |

Установите NuGet‑пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создание проекта и импортов

Создайте новый консольный проект и добавьте необходимые директивы `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The tutorial code starts here.
```

Эти пространства имён предоставляют `BarcodeGenerator`, `EncodeTypes` и перечисление `BarCodeImageFormat`, используемые далее.

## Шаг 2: Создание штрих‑кода RM4SCC – автоматическая высота

Первый пример показывает, как **создать штрих‑код RM4SCC C#** без указания высоты полос. Библиотека автоматически определяет оптимальную высоту на основе X‑размера.

```csharp
            // Create a Planet (postal) barcode generator – auto height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // Define the module width (X‑dimension) in pixels
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Optional: comment out the next line to keep automatic height
            // rm4sccAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image as PNG
            rm4sccAuto.Save("RM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

**Почему это работает:**  
* `EncodeTypes.RM4SCC` указывает генератору использовать почтовую символогию RM4SCC.  
* `XDimension.Pixels` задаёт ширину узкой полосы; 4 px — обычный выбор для отображения на экране.  
* Когда `BarHeight.Pixels` опущен, Aspose вычисляет высоту, удовлетворяющую спецификации RM4SCC, обеспечивая читаемость для почтовых сканеров.

## Шаг 3: Создание штрих‑кода RM4SCC – фиксированная высота

Иногда система дизайна требует конкретной высоты полос. Следующий код фиксирует высоту в 100 px:

```csharp
            // Create a RM4SCC barcode generator – fixed height
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // X‑dimension stays the same
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

            // Explicitly set the bar height to 100 px
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image
            rm4sccFixed.Save("RM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

**Почему может понадобиться фиксированная высота:**  
Руководства по дизайну часто предписывают одинаковый визуальный вес разных штрих‑кодов. Устанавливая `BarHeight.Pixels`, вы гарантируете одинаковый внешний вид независимо от используемой символогии.

## Шаг 4: Создание штрих‑кода Planet – автоматическая высота

**Пример генератора штрих‑кода C#** работает так же для почтового кода Planet. Поменяйте значение `EncodeTypes` и повторно используйте ту же логику конфигурации:

```csharp
            // Create a Planet barcode generator – auto height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Same X‑dimension as before
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Keep automatic height (comment out the line below if you want auto)
            // planetAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the PNG file
            planetAuto.Save("Planet_AutoHeight.png", BarCodeImageFormat.Png);
```

**Как сгенерировать штрих‑код Planet:**  
Единственное изменение — значение перечисления `EncodeTypes.Planet`. Все остальные параметры (X‑размер, необязательная высота) работают идентично, поэтому это руководство служит **примером генератора штрих‑кода C#** для нескольких почтовых форматов.

## Шаг 5: Создание штрих‑кода Planet – фиксированная высота

Если нужна конкретная высота для штрих‑кода Planet, примените тот же параметр, что использовался для RM4SCC:

```csharp
            // Create a Planet barcode generator – fixed height
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // fixed 100 px

            planetFixed.Save("Planet_FixedHeight.png", BarCodeImageFormat.Png);
```

## Шаг 6: Запуск и проверка результата

Закройте метод `Main` и фигурные скобки класса:

```csharp
        }
    }
}
```

Соберите и запустите проект:

```bash
dotnet run
```

После выполнения вы найдёте четыре PNG‑файла в папке проекта:

* `RM4SCC_AutoHeight.png`
* `RM4SCC_FixedHeight.png`
* `Planet_AutoHeight.png`
* `Planet_FixedHeight.png`

Каждое изображение содержит чёткий, сканируемый штрих‑код. Откройте любой файл, чтобы убедиться, что полосы отрисованы с ожидаемой шириной (4 px) и высотой (авто или 100 px).  

![RM4SCC barcode generated with C#](rm4scc_example.png "Screenshot showing a generated RM4SCC barcode created with C#")

*Текст alt изображения:* **Screenshot showing a generated RM4SCC barcode created with C#** (matches the OG image alt requirement).

## Полезные советы и распространённые подводные камни

| Ситуация | Рекомендация |
|----------|--------------|
| **Неправильный X‑размер** | Держите `XDimension.Pixels` в диапазоне от 2 px до 6 px для большинства принтеров. Меньшие значения могут вызвать размытие. |
| **Игнорируется высота полос** | Убедитесь, что вы *раскомментировали* строку `BarHeight.Pixels`; оставив её закомментированной, будет использована авто‑высота. |
| **Недопустимая строка данных** | RM4SCC и Planet принимают только цифры (0‑9). Передача букв вызывает `ArgumentException`. |
| **Вывод высокого разрешения** | Используйте `BarCodeImageFormat.Tiff` или `Pdf` для без потерь печати. |
| **Производительность** | Переиспользуйте один экземпляр `BarcodeGenerator`, если нужно создать много штрих‑кодов с одинаковыми настройками; меняйте только свойство `CodeText` между сохранениями. |

## Заключение

Теперь вы знаете, как **создать штрих‑код RM4SCC C#** и **как сгенерировать штрих‑код Planet**, используя лаконичный, переиспользуемый шаблон кода. Руководство охватило оба сценария — автоматическая и фиксированная высота, предоставило готовый скелет проекта и выделило лучшие практики надёжного создания штрих‑кодов.

Далее можете изучить другие почтовые символогии, такие как **POSTNET** или **USPS Intelligent Mail** — тот же API `BarcodeGenerator` применяется, так что вы сможете расширить этот **пример генератора штрих‑кода C#** с минимальными изменениями. Приятного кодинга!

## Что изучать дальше?

Следующие уроки охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Create RM4SCC barcode C# and set barcode height](/barcode/english/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}