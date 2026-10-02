---
category: general
date: 2026-09-07
description: Быстро создавайте PNG‑изображения планетного штрих‑кода на C#. Узнайте,
  как генерировать изображения планетного штрих‑кода с помощью Aspose.BarCode, используя
  заполненные и пустые полосы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: ru
lastmod: 2026-09-07
og_description: Создавайте PNG‑изображения штрих‑кода Planet на C# быстро. Следуйте
  этому руководству, чтобы узнать, как генерировать изображения штрих‑кода Planet
  с заполненными и пустыми полосами с помощью Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Создание PNG‑штрихкода планеты на C# — полный учебный курс
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать PNG‑изображение планетарного штрихкода на C# – пошаговое руководство
url: /ru/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать PNG штрих‑кода Planet с C# – пошаговое руководство

Если вам нужно **создать PNG штрих‑кода Planet** в C#, это руководство покажет вам точные шаги. Независимо от того, создаёте ли вы интеграцию с почтовой службой или панель логистики, вы узнаете **как генерировать изображения штрих‑кода Planet** с заполненными и пустыми полосами, используя библиотеку Aspose.BarCode.

В этом руководстве вы:

* Настроите папку вывода для ваших изображений.  
* Сконфигурируете `BarcodeGenerator` для символьного набора Planet.  
* Сгенерируете PNG с стилем заполненных полос по умолчанию.  
* Сгенерируете PNG с пустыми полосами для визуального контраста.  

Внешние сервисы не требуются — всё работает локально на .NET 6 или новее.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

| Требование | Почему это важно |
|-------------|-------------------|
| .NET 6 SDK (или новее) | Предоставляет среду выполнения для консольного приложения C#. |
| Visual Studio 2022 или VS Code | Любая IDE, способная компилировать проекты C#. |
| Aspose.BarCode for .NET (NuGet‑пакет `Aspose.BarCode`) | Содержит класс `BarcodeGenerator`, используемый для рендеринга штрих‑кодов Planet. |
| Права записи в папку на диске | PNG‑файлы будут сохраняться в этом месте. |

Установите NuGet‑пакет с помощью следующей команды:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Создать новый консольный проект

Откройте терминал и выполните:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Это создаст минимальное консольное приложение C# с именем **PlanetBarcodeDemo**.

## Шаг 2: Определить каталог вывода

Первый фрагмент кода определяет, где будут храниться сгенерированные PNG‑файлы. Подойдёт как абсолютный, так и относительный путь; просто убедитесь, что папка существует, либо позвольте программе создать её.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Почему этот шаг?* Разделение вывода и исходного кода делает проект аккуратным и предотвращает случайные перезаписи.

## Шаг 3: Сгенерировать штрих‑код Planet с заполненными полосами

Штрих‑код Planet состоит из концентрических кругов (по умолчанию заполненных). Мы настраиваем X‑размер (ширина каждой полосы в пикселях) и затем сохраняем изображение в формате PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Объяснение**

* `EncodeTypes.Planet` указывает Aspose использовать символьный набор Planet, который часто применяется в почтовых службах.  
* `XDimension.Pixels = 4` даёт чёткий, печатаемый размер без необходимости ручного масштабирования.  
* Метод `Save` записывает PNG‑файл; можно также выбрать JPEG или BMP, изменив `BarCodeImageFormat`.

## Шаг 4: Сгенерировать штрих‑код Planet с пустыми полосами

Иногда требуется визуализация с пустыми (прозрачными) полосами — например, когда штрих‑код накладывается на цветной фон. Установка `FilledBars` в `false` создаёт такой стиль.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Объяснение**

* `FilledBars = false` отключает сплошные круги, оставляя только контуры.  
* Все остальные параметры (X‑размер, строка данных) остаются одинаковыми, гарантируя, что оба изображения представляют одни и те же данные.

## Шаг 5: Запустить программу и проверить вывод

Скомпилируйте и выполните:

```bash
dotnet run
```

Вы должны увидеть сообщения в консоли, подтверждающие сохранение файлов, а папка `Barcodes` будет содержать:

* `PostalPlanetFilledBars.png` — классический штрих‑код Planet с заполненными полосами.  
* `PostalPlanetEmptyBars.png` — те же данные, отображённые пустыми полосами.

Откройте PNG‑файлы в любом просмотрщике изображений. Оба изображения кодируют числовую строку **123456** и могут быть считаны стандартными почтовыми сканерами штрих‑кодов.

## Часто задаваемые вопросы и обработка граничных случаев

### Что делать, если нужен другой формат данных?

Штрих‑коды Planet принимают числовые строки длиной до 12 цифр. При передаче нечислового значения Aspose бросит `ArgumentException`. Проверьте ввод перед созданием генератора:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Как изменить размер изображения без изменения толщины полос?

Используйте свойство `Resolution` или масштабируйте полученный bitmap после сохранения:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Можно ли генерировать другие форматы изображений?

Да. Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg`, `Bmp` или `Gif`. API поддерживает все распространённые растровые форматы.

### Как настроить цвета?

Установите `BarColor` и `BackColor` в параметрах `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Эти параметры работают как для версии с заполненными, так и для версии с пустыми полосами.

## Профессиональные советы для продакшн‑использования

* **Кешируйте генератор**, когда нужно отрисовать множество штрих‑кодов с одинаковыми настройками — повторная инициализация объекта создаёт лишние накладные расходы.  
* **Освобождайте** объекты `BarcodeGenerator`, если создаёте их в большом количестве в цикле (они реализуют `IDisposable`).  
* **Проверяйте каталог вывода** заранее, чтобы избежать исключений во время выполнения при попытке записи в защищённые директории.  

## Заключение

Теперь вы знаете, как **создать PNG штрих‑кода Planet** в C#, и понимаете, **как генерировать изображения штрих‑кода Planet** как с заполненными, так и с пустыми полосами. Полный, готовый к запуску пример демонстрирует настройку каталога вывода, конфигурацию `BarcodeGenerator` и сохранение результатов в виде PNG‑файлов.

Далее вы можете изучить:

* Добавление **читаемого человеком текста** под штрих‑кодом (`planetFilled.Parameters.Caption.Visible = true`).  
* Интеграцию сгенерированных PNG в **PDF‑счёт** с помощью Aspose.PDF.  
* Переход к другим почтовым символьным наборам, таким как **IMB** или **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Не стесняйтесь экспериментировать с толщиной полос, цветами и разрешением изображений, чтобы они соответствовали требованиям вашего приложения. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создать изображение штрих‑кода Planet в C# – Как генерировать почтовый штрих‑код](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Создать штрих‑код Planet в C# – Полное пошаговое руководство](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Генерировать PNG штрих‑код с Aspose.BarCode для .NET: Одномерные заполненные полосы](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}