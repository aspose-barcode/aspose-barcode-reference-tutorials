---
category: general
date: 2026-10-21
description: Быстро создавайте штрих‑код Databar Stacked с помощью C#. Узнайте, как
  задать X‑размер, отрегулировать соотношение сторон и сохранять изображения PNG в
  этом полном руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: ru
lastmod: 2026-10-21
og_description: Создайте штрих‑код Databar Stacked в C# с помощью Aspose.BarCode.
  Следуйте этому руководству, чтобы настроить X‑размер, изменить соотношение сторон
  и экспортировать файлы PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Создание штрих‑кода Databar Stacked в C# — полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Как создать штрих‑код Databar Stacked в C# – пошаговое руководство
url: /ru/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать databar stacked barcode в C# – пошаговое руководство

Если вам нужно **create databar stacked barcode** в .NET приложении, это руководство покажет вам точно как. Вы увидите, как настроить X‑dimension, изменить соотношение сторон и сохранить штрих‑код в виде PNG‑файлов.

Создание DataBar stacked barcode не требует сложного конвейера сборки. Этот учебник охватывает всё, что вам нужно: необходимые пакеты, пошаговое объяснение кода и советы по распространённым подводным камням. К концу вы сможете создавать несколько изображений штрих‑кода с разными соотношениями сторон в одном методе.

## Что вам понадобится

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любая IDE, поддерживающая C#)  
* **Aspose.BarCode for .NET** NuGet package – библиотека, предоставляющая `BarcodeGenerator` и `EncodeTypes`  

Вы можете добавить пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новый консольный проект или добавьте код в существующий. Импортируйте необходимые пространства имён, чтобы компилятор распознавал классы штрих‑кода.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти инструкции `using` предоставляют `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`, используемые позже в примере.

## Шаг 2: Определение папки вывода

Выберите папку, в которую будут записываться сгенерированные PNG‑файлы. Использование абсолютного или относительного пути работает одинаково; в примере используется относительная папка с именем `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Создание папки программно предотвращает ошибки выполнения, когда каталог отсутствует.

## Шаг 3: Инициализация генератора **create databar stacked barcode**

Создайте экземпляр `BarcodeGenerator` с `EncodeTypes.DatabarStackedOmniDirectional`. Пример данных `(01)12345678901231` соответствует формату GS1‑128, требуемому для DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Объект генератора хранит все параметры, влияющие на визуальное отображение штрих‑кода.

## Шаг 4: Установка X‑dimension (ширина в пикселях самого маленького штриха)

X‑dimension контролирует общий размер штрих‑кода без изменения закодированных данных. Значение `2` пикселя обеспечивает чёткое, сканируемое изображение для большинства экранных разрешений.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Отрегулируйте это значение, если нужен более большой или более маленький штрих‑код; сохраняйте соотношение между шириной и высотой.

## Шаг 5: Настройка соотношения сторон и сохранение первого изображения

Соотношение сторон определяет соотношение высоты к ширине DataBar stacked barcode. Соотношение `15` является распространённым значением по умолчанию, дающим компактный вид.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Метод `Save` записывает PNG‑файл в ранее определённую папку. Имя файла явно указывает использованное соотношение сторон.

### Ожидаемый результат для соотношения сторон 15

Сгенерированный `DatabarAspectRatio15.png` выглядит аналогично иллюстрации ниже.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Текст alt:* `create databar stacked barcode image saved with aspect ratio 15`

## Шаг 6: Изменение соотношения сторон и сохранение второго изображения

Вы можете повторно использовать тот же экземпляр `BarcodeGenerator` для создания вариантов. Изменение `AspectRatio` на `30` удваивает высоту каждой стопки штрихов, что может потребоваться для печати высокого разрешения.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Ожидаемый результат для соотношения сторон 30

Изображение `DatabarAspectRatio30.png` выше, сохраняет ту же ширину, одновременно повышая читаемость для сканеров на расстоянии.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Текст alt:* `create databar stacked barcode image saved with aspect ratio 30`

## Полный исходный код

Объединение всех шагов приводит к автономной программе, которую можно запустить сразу.

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
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Скомпилируйте и запустите программу. После выполнения каталог `Barcodes` будет содержать два PNG‑файла, каждый из которых представляет **create databar stacked barcode** с разным соотношением сторон.

## Профессиональные советы и распространённые подводные камни

* **Pro tip:** Держите X‑dimension в диапазоне от 1 px до 4 px для большинства сценариев использования на экране. Большие значения увеличивают размер файла без улучшения надёжности сканирования.  
* **Pitfall:** Изменение значения `EncodeTypes` после создания генератора не обновляет внутреннее кодирование. Всегда указывайте правильный `EncodeTypes` в конструкторе.  
* **Pro tip:** Когда требуется более двух соотношений сторон, выполните цикл по массиву целочисленных значений и вызывайте `Save` внутри цикла. Это уменьшает дублирование кода.  
* **Pitfall:** Сохранение в путь без прав на запись вызывает `UnauthorizedAccessException`. Убедитесь, что приложение работает с соответствующими правами файловой системы.  

## Заключение

Теперь вы знаете, как **create databar stacked barcode** в C# с использованием Aspose.BarCode. Руководство охватило настройку окружения, конфигурацию X‑dimension, корректировку соотношения сторон и сохранение PNG‑файлов. С этой базой вы можете генерировать дополнительные варианты, интегрировать создание штрих‑кода в веб‑API или встраивать изображения в PDF‑отчёты.

Далее изучайте связанные темы, такие как лучшие практики сканирования **DataBar Stacked Omnidirectional**, встраивание штрих‑кодов в ответы **ASP.NET Core** или генерация **QR codes** той же библиотекой. Экспериментируйте с различными `EncodeTypes` и форматами изображений, чтобы соответствовать потребностям вашего приложения.

Удачной разработки!

## Что стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать изображения databar PNG с C# и Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Как задать столбцы для Databar Expanded Stacked barcode – полное руководство на C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode в C# – Полное руководство](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}