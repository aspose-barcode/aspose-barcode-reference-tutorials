---
category: general
date: 2026-10-02
description: Узнайте, как создавать штрих‑код rm4scc на C# и генерировать почтовый
  штрих‑код с произвольной высотой. Включает пошаговый код для штрих‑кодов Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: ru
lastmod: 2026-10-02
og_description: Создайте штрих‑код rm4scc на C# и узнайте, как генерировать почтовый
  штрих‑код с точными размерами. Полный пример кода и рекомендации по лучшим практикам.
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: Создание штрих‑кода rm4scc с пользовательской высотой – руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: Как создать штрих‑код rm4scc и управлять его высотой в C#
url: /ru/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код rm4scc и задать его высоту в C#

Если вам нужно **создать штрих‑код rm4scc** для почтовой системы, это руководство покажет, как именно генерировать почтовые штрих‑коды и задавать точную высоту полос. Вы увидите как подход с автоматическим размером, так и технику явного указания высоты, чтобы выбрать метод, соответствующий вашим требованиям к дизайну.

Генерация почтового штрих‑кода — распространённая задача при создании транспортных этикеток, программ пакетной рассылки или любого решения, интегрирующегося с национальными почтовыми службами. В этом уроке рассматривается:

* **как генерировать почтовый штрих‑код** для символогий RM4SCC и Planet  
* **генерировать штрих‑код planet** с теми же настройками для сравнения  
* **как задать высоту штрих‑кода** фиксированным значением в пикселях  
* полностью готовый, исполняемый код C# с использованием библиотеки Aspose.BarCode  

К концу статьи у вас будет готовая к запуску консольная программа, которая создаст четыре PNG‑файла — два с автоматической высотой и два с фиксированной высотой 100 px.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).  
* Visual Studio 2022 или любая IDE, способная собирать проекты C#.  
* Пакет **Aspose.BarCode for .NET** из NuGet (`Install-Package Aspose.BarCode`).  

Дополнительная настройка не требуется; библиотека самостоятельно обрабатывает всё рендеринг изображений.

## Шаг 1: Создание проекта и импорт пространств имён

Создайте новый консольный проект и добавьте необходимые директивы `using`. Этот шаг подготавливает окружение для генерации штрих‑кодов.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*Почему это важно*: Объявление `outputFolder` один раз избавляет от повторений и упрощает изменение пути назначения позже. Вызов `CreateDirectory` гарантирует, что операция сохранения не провалится из‑за отсутствия папки.

## Шаг 2: Как генерировать почтовый штрих‑код с высотой по умолчанию

### 2.1 Создание штрих‑кода RM4SCC (авто‑высота)

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 Создание штрих‑кода Planet (авто‑высота)

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

Оба вызова опускают свойство `BarHeight`, поэтому библиотека рассчитывает оптимальную высоту в соответствии со спецификациями символогии. Это самый простой способ **как генерировать почтовый штрих‑код**, когда у вас нет строгих ограничений по макету.

## Шаг 3: Как задать высоту штрих‑кода для точного размещения

Когда шаблон этикетки требует фиксированного визуального размера, необходимо явно задать высоту полос. Ниже показано, **как задать высоту штрих‑кода** в 100 пикселей для обеих символогий.

### 3.1 Штрих‑код RM4SCC фиксированной высоты

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 Штрих‑код Planet фиксированной высоты

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*Почему это работает*: Свойство `BarHeight.Pixels` переопределяет автоматический расчёт, заставляя рендерер использовать точно указанное количество пикселей. Это необходимо, когда штрих‑код должен выравниваться с другими элементами интерфейса или печатными шаблонами.

## Шаг 4: Проверка сгенерированных изображений

После завершения программы откройте четыре PNG‑файла в папке `outputFolder`. Вы должны увидеть:

| Имя файла | Высота | Символика |
|-----------|--------|-----------|
| `PostalRM4SCC_AutoHeight.png` | Авто‑рассчитанная (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | Авто‑рассчитанная (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px** (точно) | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px** (точно) | Planet |

Изображения «FixedHeight» имеют полосы ровно 100 px в высоту, что соответствует требованию **как задать высоту штрих‑кода** для стандартизированного формата этикетки.

## Шаг 5: Распространённые подводные камни и рекомендации

* **Недопустимые значения высоты** — Установка `BarHeight.Pixels` в отрицательное число вызывает `ArgumentException`. Всегда проверяйте пользовательский ввод перед присвоением.  
* **Учёт разрешения** — Визуальный размер на экране также зависит от DPI. При экспорте в PDF рассмотрите возможность установки `ImageResolution`, чтобы сохранить физические размеры.  
* **X‑dimension vs. высота полос** — `XDimension.Pixels` управляет **шириной** полос, а не их высотой. Пропуск этой настройки может сделать штрих‑код слишком тонким, особенно при низком DPI.  
* **Потокобезопасность** — Экземпляры `BarcodeGenerator` **не** являются потокобезопасными. Создавайте новый объект для каждого потока или синхронизируйте доступ, если генерируете много штрих‑кодов параллельно.

## Полный исходный код (исполняемый)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

Скопируйте код в `Program.cs`, восстановите пакеты NuGet и выполните `dotnet run`. Консоль подтвердит успешную генерацию, а PNG‑файлы появятся в `C:/Barcodes/`.

## Заключение

Теперь вы знаете, как **создать штрих‑код rm4scc** и **сгенерировать штрих‑код planet** в C#, как с автоматическим масштабированием, так и с вручную заданной высотой полос. Управляя `BarHeight.Pixels`, вы отвечаете на вопрос **как задать высоту штрих‑кода**, гарантируя, что ваши почтовые штрих‑коды идеально впишутся в любой макет этикетки.

Далее вы можете изучить:

* **как генерировать почтовый штрих‑код** в других форматах, таких как PDF или SVG (`BarCodeImageFormat.Pdf`, `BarCodeImageFormat.Svg`).  
* Добавление читаемого человеком текста под штрих‑кодом (`Parameters.Caption`).  
* Интеграцию генератора в API ASP.NET Core для выдачи штрих‑кодов по запросу.

Не стесняйтесь экспериментировать с различными значениями `XDimension`, цветами или фоновыми изображениями, чтобы соответствовать вашему бренду, при этом соблюдая стандарты штрих‑кодов. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}