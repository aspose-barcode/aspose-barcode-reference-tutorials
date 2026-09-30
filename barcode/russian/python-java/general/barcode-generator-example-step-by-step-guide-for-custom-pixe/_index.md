---
category: general
date: 2026-08-12
description: пример генератора штрихкодов, показывающий, как генерировать штрихкод
  с точным размером пикселя. Узнайте, как задать ширину модуля, высоту полосы и создавать
  штрихкоды Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: ru
lastmod: 2026-08-12
og_description: Пример генератора штрихкодов демонстрирует, как создавать штрихкоды
  с точными пиксельными размерами. Следуйте этому руководству, чтобы управлять шириной
  модуля и высотой полосы для кодов Planet и RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: пример генератора штрихкода – настройка размера пикселя в C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: пример генератора штрихкода — пошаговое руководство по пользовательским размерам
  пикселей
url: /ru/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример генератора штрихкода – пошаговое руководство по пользовательским размерам пикселей

Если вам нужен **barcode generator example**, позволяющий контролировать каждый пиксель, это руководство покажет, как это сделать. Вы научитесь задавать ширину модуля, определять фиксированную высоту полосы и генерировать штрихкоды Planet и RM4SCC с предсказуемыми размерами.

Большинство разработчиков сталкиваются с проблемой «как сгенерировать штрихкод», когда изображения выглядят по‑разному на разных экранах или принтерах. Приведённые ниже фрагменты кода решают эту проблему, раскрывая параметры уровня пикселей библиотеки Aspose.BarCode for .NET, чтобы вы могли получать согласованный результат без догадок.

## Что вы узнаете

* Как установить требуемый пакет NuGet.  
* Как сгенерировать штрихкод Planet с автоматически вычисляемой высотой.  
* Как сгенерировать штрихкод Planet с явно заданной высотой 100 пикселей.  
* Как сгенерировать штрихкод RM4SCC, используя ту же явно заданную высоту.  
* Почему **barcode pixel size** важен для надёжности сканирования.  
* Советы по устранению распространённых проблем при генерации изображений штрихкода Planet.  

Вам понадобится только .NET 6 или новее, базовая среда разработки C# и подключение к интернету для загрузки пакета NuGet.

---

## barcode generator example – настройка среды разработки

Прежде чем писать код, убедитесь, что библиотека Aspose.BarCode доступна вашему проекту.

### Установите пакет Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Команда добавит последнюю стабильную версию **Aspose.BarCode** в ваш `csproj`. После завершения восстановления вы сможете начать использовать класс `BarcodeGenerator`.

> **Pro tip:** Нацельтесь на .NET 6 или .NET 7, чтобы воспользоваться последними улучшениями производительности и обработкой UTF‑8 по умолчанию.

### Добавьте необходимые директивы `using`

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Эти пространства имён предоставляют класс `BarcodeGenerator` и перечисление `BarCodeImageFormat`, используемые далее в руководстве.

## Как сгенерировать штрихкод с пользовательским размером пикселей

Ниже представлены три шага, иллюстрирующие полный **barcode generator example**. Каждый шаг опирается на предыдущий, поэтому вы можете скопировать‑вставить весь блок в консольное приложение и запустить его без изменений.

### Шаг 1 – сгенерировать штрихкод Planet с автоматически вычисляемой высотой

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Почему это работает:**  
*Свойство `XDimension` определяет ширину одного модуля штрихкода (самого маленького чёрного или белого элемента). Когда вы опускаете `BarHeight`, библиотека рассчитывает высоту, сохраняющую стандартное соотношение сторон для кодов Planet.*

**Ожидаемый результат:** PNG‑файл `PlanetAuto.png` с чистым штрихкодом Planet. Его высота адаптируется к ширине модуля 4 пикселя, обычно около 60 пикселей для шестизначного полезного сообщения.

### Шаг 2 – сгенерировать штрихкод Planet с явно заданной высотой 100 пикселей

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Зачем это может понадобиться:**  
Иногда оборудование сканирования требует минимальную высоту полосы для надёжного обнаружения. Установив `BarHeight.Pixels`, вы гарантируете, что каждое сгенерированное изображение удовлетворяет этому требованию, независимо от длины кодируемых данных.

**Ожидаемый результат:** `PlanetHeight100.png` показывает те же данные, что и раньше, но полосы имеют ровно 100 пикселей в высоту, давая вам полный контроль над визуальным размером.

### Шаг 3 – сгенерировать штрихкод RM4SCC с той же явно заданной высотой

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Почему это важно:**  
`EncodeTypes.RM4SCC` – это штабелированный линейный штрихкод, используемый в логистике. Выравнивание его высоты с высотой штрихкода Planet упрощает пакетную обработку, когда обе символьные системы появляются на одной этикетке.

**Ожидаемый результат:** `RM4SCCHeight100.png` отображает идеально размерный штрихкод RM4SCC, соответствующий высоте 100 пикселей, установленной для кода Planet.

> **Проверка результата:** Откройте каждый PNG в просмотрщике изображений и убедитесь, что чёрные полосы ровно 4 пикселя в ширину и, где указано, 100 пикселей в высоту. Вы также можете загрузить файлы в приложение‑сканер, чтобы убедиться, что они декодируются в «123456».

## Понимание размера пикселя штрихкода и высоты полосы

### Что такое **barcode pixel size**?

*Размер пикселя* — это физическое количество пикселей экрана или принтера, представляющих один модуль (`XDimension`). Больший размер пикселя даёт более крупный штрихкод, который может быть легче считывать сканерам низкого разрешения, но занимает больше места на этикетке.

### Как `BarHeight` влияет на читаемость?

Свойство `BarHeight` управляет вертикальной длиной полос. Стандарты большинства 1‑D штрихкодов (включая Planet и RM4SCC) рекомендуют минимальную высоту 10 мм при печати с 300 dpi, что примерно соответствует 118 пикселям. Установка высоты ниже этой может вызвать ошибки чтения, особенно на мобильных камерах.

### Когда следует позволить библиотеке автоматически рассчитывать высоту?

Если вы генерируете штрихкоды только для отображения на экране, автоматический расчёт сохраняет соотношение сторон и уменьшает необходимость ручной настройки. Для печатных этикеток, которым необходимо соответствовать строгим требованиям ISO, следует **явно задавать высоту полосы**.

## Распространённые подводные камни и лучшие практики при генерации штрихкода Planet

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| Полосы выглядят слишком тонкими или толстыми | `XDimension` оставлен по умолчанию (1 пиксель) на дисплеях с высоким разрешением | Установите `XDimension.Pixels` минимум 3‑4 для визуальной чёткости |
| Сканер не может прочитать код | `BarHeight` слишком мал для фокусного расстояния сканера | Используйте `BarHeight.Pixels` ≥ 100 для большинства мобильных сканеров |
| Изображение размыто после масштабирования | Сохранение в JPEG добавляет артефакты сжатия | Сохраняйте как PNG (`BarCodeImageFormat.Png`) для без потерь |
| Неожиданный тип штрихкода | Неправильное значение перечисления `EncodeTypes` | Проверьте, что используете `EncodeTypes.Planet` для символьной системы Planet |

### Pro tip по производительности

При генерации тысяч штрихкодов в пакетной задаче переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только `CodeText` и параметры размера между сохранениями. Это избавляет от повторного выделения внутренних объектов рендеринга и может сократить время выполнения до 30 %.

## Полный рабочий пример – собрать всё вместе

Создайте новый консольный проект (`dotnet new console -n BarcodeDemo`) и замените содержимое `Program.cs` следующим кодом:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Запустите программу командой `dotnet run`. После выполнения вы найдёте три PNG‑файла в папке проекта, каждый из которых иллюстрирует отдельный сценарий **barcode generator example**.

## Следующие шаги и связанные темы

* **Как генерировать штрихкоды в других форматах** – изучите `EncodeTypes.Code128`, `EncodeTypes.QR` и `EncodeTypes.DataMatrix` для 2‑D потребностей.  
* **Встраивание штрихкодов в PDF** – комбинируйте Aspose.BarCode с Aspose.PDF, чтобы размещать штрихкоды непосредственно в шаблонах счетов.  
* **Динамический размер штрихкода на основе ввода пользователя** – вычисляйте  

## Что следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как генерировать штрихкод Java: создать точное изображение штрихкода](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Как генерировать штрихкод в Java: создать и задать размер для полного изображения штрихкода](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [Как создать штрихкод Code128 в Java и задать высоту полос](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}