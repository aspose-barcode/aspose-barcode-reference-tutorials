---
category: general
date: 2026-09-19
description: Руководство по генератору штрихкодов на C# показывает, как сгенерировать
  штрихкод Planet и экспортировать его изображение в PNG всего за несколько строк.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: ru
lastmod: 2026-09-19
og_description: Генератор штрихкодов C# позволяет быстро создавать штрихкоды Planet
  и экспортировать изображение в формате PNG для любого приложения .NET.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: Генератор штрихкодов C# – создать штрихкод Planet и экспортировать изображение
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Как использовать генератор штрихкодов C# для штрихкода Planet
url: /ru/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрихкодов C# для штрихкода Planet

Если вам нужен **barcode generator C#**, способный создавать штрихкод Planet, это руководство предоставляет полное решение. Вы узнаете, **как генерировать данные штрихкода**, настроить внешний вид и **экспортировать изображение штрихкода** в файл PNG всего несколькими строками кода.

Создание штрихкодов — распространённая потребность для систем учёта, платформ билетирования и IoT‑устройств. К концу этого руководства у вас будет автономное консольное приложение, которое генерирует чистый штрихкод Planet, отключает заполнение полос и сохраняет результат на диск. Внешние инструменты не требуются, кроме библиотеки штрихкодов.

## Предварительные требования

* .NET 6.0 SDK или более поздняя версия, установленная  
* Библиотека штрихкодов, совместимая с C# (в примере используется **Aspose.BarCode for .NET**, поддерживающая символогию Planet)  
* IDE или редактор, например Visual Studio 2022, VS Code или Rider  

Библиотеку можно добавить через NuGet:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Используйте последнюю стабильную версию пакета, чтобы получить исправления ошибок и улучшения производительности.

## Использование barcode generator C# для создания штрихкода Planet

Первый шаг — создать экземпляр генератора с символогией Planet и данными, которые вы хотите закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` — точка входа для всех операций со штрихкодами. Конструктор принимает символогию (`EncodeTypes.Planet`) и исходные данные (`"123456"`). Этот код **создаёт штрихкод Planet**, который позже можно отобразить как изображение.

## Настройка параметров штрихкода

Для управления визуальным качеством вы можете изменить X‑dimension (ширину модуля) и решить, заполнять ли полосы.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Установка `XDimension.Pixels` в **4** даёт штрихкод более высокого разрешения без значительного увеличения размера файла.  
* `FilledBars = false` создаёт стиль только с контурами, что полезно, когда нужно, чтобы штрихкод гармонировал с фоном или при печати на устройствах с низким расходом чернил.

## Экспорт изображения штрихкода

После настройки генератора сохраните результат в файл PNG. Метод `Save` принимает полный путь и желаемый формат изображения.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Код записывает **export barcode image** `PlanetEmptyBars.png` на рабочий стол пользователя. PNG — формат без потерь, сохраняющий чёткие края штрихкода, что делает его идеальным как для отображения на экране, так и для печати высокого разрешения.

> **Edge case:** Если вам нужен другой формат (JPEG, BMP, GIF), замените `BarCodeImageFormat.Png` на соответствующее значение перечисления. JPEG вводит артефакты сжатия, которые могут влиять на читаемость сканером, поэтому используйте его только когда размер файла имеет критическое значение.

## Полный, исполняемый пример

Ниже приведена полная программа, которую вы можете скопировать, вставить и сразу запустить.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

При запуске программы вы должны увидеть сообщение, похожее на:

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

Открытие PNG‑файла отображает чистый штрихкод Planet с пустыми полосами, точно как настроено.

![пример генератора штрихкодов C#](/images/barcode-generator-csharp.png){alt="пример генератора штрихкодов C#"}

## Часто задаваемые вопросы и устранение неполадок

| Вопрос | Ответ |
|----------|--------|
| **Могу ли я генерировать другие символогии с тем же кодом?** | Да. Замените `EncodeTypes.Planet` на любой поддерживаемый тип, например `EncodeTypes.Code128` или `EncodeTypes.QR`. |
| **Что делать, если штрихкод не сканируется?** | Убедитесь, что длина данных соответствует спецификации Planet (ровно 6 числовых символов). Также обеспечьте достаточный контраст между штрихкодом и фоном. |
| **Как изменить размер изображения?** | Отрегулируйте `generator.Parameters.ImageWidth` и `generator.Parameters.ImageHeight` или измените `XDimension` для пропорционального масштабирования штрихкода. |
| **Можно ли добавить подпись под штрихкодом?** | Используйте `generator.Parameters.Barcode.CodeTextVisible = true;` и настройте `CodeTextParameters` для шрифта, выравнивания и отступов. |

## Следующие шаги

Теперь, когда вы освоили **как генерировать штрихкоды** с помощью **barcode generator C#**, вы можете исследовать:

* Генерацию пакетных файлов штрихкодов с использованием списка значений в CSV.  
* Встраивание PNG в PDF‑счета с помощью Aspose.PDF.  
* Переход к форматам `export barcode image`, таким как SVG, для масштабируемой веб‑графики.

Эти расширения углубляют ваше понимание автоматизации штрихкодов в .NET и готовят к реальным сценариям интеграции.

---

**Итоги:** В этом руководстве продемонстрирован полный рабочий процесс **barcode generator C#** — создание штрихкода Planet, настройка его внешнего вида и **экспорт изображения штрихкода** в PNG. Вы можете адаптировать тот же шаблон для других символогий, форматов изображений и мест назначения вывода. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полные рабочие примеры кода с пошаговыми объяснениями, помогающие вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Генератор штрихкодов C# – создание изображения штрихкода](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Создание изображения штрихкода Planet в C# – Как генерировать почтовый штрихкод](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Пример генератора штрихкодов в C# – Установка столбцов, строк и экспорт изображения](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}