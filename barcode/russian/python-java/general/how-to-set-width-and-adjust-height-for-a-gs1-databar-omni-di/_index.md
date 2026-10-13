---
category: general
date: 2026-09-29
description: Как установить ширину штрихкода GS1 DataBar Omni‑Directional и изменить
  его высоту с помощью C#. Следуйте пошаговому руководству с полным кодом.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: ru
lastmod: 2026-09-29
og_description: Как задать ширину штрихкода GS1 DataBar Omni‑Directional и изменить
  высоту в C#. Узнайте точные вызовы API и посмотрите полный рабочий пример.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Как задать ширину штрихкода GS1 DataBar – руководство по C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Как задать ширину и отрегулировать высоту штрих‑кода GS1 DataBar Omni‑Directional
  в C#
url: /ru/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как установить ширину и настроить высоту штрих‑кода GS1 DataBar Omni‑Directional в C#

Установка ширины штрих‑кода GS1 DataBar Omni‑Directional — частая задача, когда требуется точный размер для сканирующего оборудования. В этом руководстве вы также узнаете **как изменить высоту**, чтобы штрих‑код идеально вписался в ваш макет. Руководство проведёт вас через весь процесс, от настройки проекта до полностью готового примера кода.

Мы рассмотрим:

* Необходимый пакет NuGet и версия .NET.
* Почему X‑dimension (ширина модуля) важна для читаемости штрих‑кода.
* Точные вызовы API для **установки ширины** и **изменения высоты**.
* Обработку граничных случаев, таких как минимальная ширина модуля и рендеринг в высоком разрешении.
* Полный пример, который можно скопировать и вставить, создающий два PNG‑файла с разной высотой штрихов.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

| Требование | Причина |
|------------|--------|
| .NET 6.0 SDK or later | В примере используются современные возможности C# и он работает на Windows, Linux или macOS. |
| Visual Studio 2022 (or any C# IDE) | Обеспечивает IntelliSense для API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Содержит `BarcodeGenerator`, `EncodeTypes` и поддержку форматов изображений. Установите с помощью `dotnet add package Aspose.Barcode`. |
| Write permission to a folder where PNG files will be saved | Разрешение на запись в папку, где будут сохраняться PNG‑файлы. |

## Как установить ширину штрих‑кода

Шаг **установки ширины** выполняется путем настройки свойства `XDimension` параметров штрих‑кода. `XDimension` представляет ширину модуля (самый маленький штрих или пробел) в пикселях, пунктах или миллиметрах. Правильная настройка гарантирует соответствие штрих‑кода требованиям сканера.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Почему важна X‑dimension

* **Допуск сканера** – большинство сканеров ожидают минимальную ширину модуля; слишком маленькое значение может вызвать ошибки чтения.  
* **Разрешение печати** – при печати с 300 dpi модуль 2 px соответствует ~0.17 mm, что находится в рекомендованном диапазоне для GS1 DataBar.  
* **Размер изображения** – большие значения X‑dimension увеличивают общую ширину штрих‑кода, что может влиять на ограничения макета.

### Советы для надёжной настройки ширины

* **Никогда не задавайте XDimension менее 1 px** – библиотека ограничит значение, но полученный штрих‑код может быть нечитаемым.  
* **Соответствуйте целевому DPI** – если вы рендерите в формат высокого разрешения (например, TIFF с 600 dpi), увеличьте XDimension пропорционально.  
* **Тестируйте реальным сканером** – после изменения ширины проверьте штрих‑код на устройстве, которое будет его считывать.

## Как изменить высоту штрих‑кода

После определения ширины вы можете управлять вертикальным размером с помощью свойства `BarHeight`. Следующий код демонстрирует **как изменить высоту** с 30 px до 60 px и сохранить два отдельных изображения.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Понимание высоты штрихов

* **Визуальный баланс** – более высокие штрихи улучшают читаемость на фонах с низким контрастом, но увеличивают вертикальный размер изображения.  
* **Регулятивные ограничения** – некоторые стандарты (например, маркировка розничных товаров) задают максимальную высоту штрихов; корректируйте соответственно.  
* **Соотношение сторон** – изменение высоты не влияет на ширину модуля; оба параметра можно настраивать независимо.

### Обработка граничных случаев при изменении высоты

| Ситуация | Рекомендуемый подход |
|-----------|----------------------|
| Высота < 10 px | Увеличьте до минимум 10 px; очень короткие штрихи могут игнорироваться сканерами. |
| Очень высокие штрихи (≥ 100 px) | Убедитесь, что носитель (бумага, этикетка) может вместить дополнительное пространство. |
| Необходим пропорциональный масштаб | Вычислите `BarHeight = XDimension * desiredRatio`, чтобы сохранить визуальную согласованность. |

## Полный, исполняемый пример

Ниже приведена полная программа, объединяющая шаги **установки ширины** и **изменения высоты**. Скопируйте код в новый консольный проект, восстановите пакет NuGet Aspose.Barcode и запустите его. Два PNG‑файла появятся в папке `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Ожидаемый результат**

Запуск программы создаёт два PNG‑файла:

* `DatabarBarHeight30Pixels.png` – штрих‑код высотой 30 px, модули шириной 2 px.  
* `DatabarBarHeight60Pixels.png` – тот же штрих‑код с двойной высотой.

Откройте любое из изображений в любом просмотрщике; вы увидите чистый символ GS1 DataBar Omni‑Directional, готовый к сканированию.

## Часто задаваемые вопросы

| Вопрос | Ответ |
|----------|--------|
| *Можно ли использовать миллиметры вместо пикселей?* | Да. Установите `generator.Parameters.Barcode.XDimension.Millimeters` и `BarHeight.Millimeters`. Библиотека преобразует их в пиксели устройства на основе DPI изображения. |
| *Что делать, если нужен другой тип штрих‑кода?* | Замените `EncodeTypes.DatabarOmniDirectional` на любое другое значение `EncodeTypes` (например, `EncodeTypes.QR`). Свойства ширины и высоты работают так же. |
| *Можно ли генерировать SVG вместо PNG?* | Используйте `BarCodeImageFormat.Svg` в вызове `Save`. Настройки ширины/высоты остаются применимыми. |
| *Нужно ли вызывать `generator.Dispose()`?* | `BarcodeGenerator` реализует `IDisposable`. В консольном приложении вы можете обернуть его в блок `using`, но для короткоживущих примеров это необязательно. |

## Заключение

Теперь вы знаете **как установить ширину** штрих‑кода GS1 DataBar Omni‑Directional и **как изменить высоту** с помощью API Aspose.Barcode в C#. Полный пример демонстрирует создание генератора, настройку `XDimension` и `BarHeight`, а также сохранение PNG‑файлов с разными вертикальными размерами.

Отсюда вы можете:

* Экспериментировать с другими `EncodeTypes` (например, QR, Code128).  
* Рендерить в форматы высокого разрешения, такие как TIFF, для печати.  
* Интегрировать генератор в веб‑API, который возвращает штрих‑коды «на лету».

Удачной разработки, и пусть ваши штрих‑коды всегда считываются без ошибок!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как изменить высоту штрих‑кода в C# – Полное руководство](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Пример генератора штрих‑кода в C# – установка ширины и высоты](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Как использовать генератор штрих‑кода C# для создания штрих‑кодов DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}