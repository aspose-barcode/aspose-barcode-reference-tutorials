---
category: general
date: 2026-10-08
description: Создайте пустой штрих‑код Planet с помощью C# и узнайте, как генерировать
  почтовый штрих‑код с использованием Aspose.BarCode. Включён пошаговый код и советы.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: ru
lastmod: 2026-10-08
og_description: Создайте пустой штрих‑код Planet с помощью Aspose.BarCode на C# и
  посмотрите, как генерировать изображения почтовых штрих‑кодов для почтовых приложений.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Создайте пустой планетный штрих‑код – руководство по почтовому штрих‑коду
  на C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Создать пустой планетарный штрих‑код, сгенерировать почтовый штрих‑код на C#
url: /ru/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать пустой Planet штрих‑код, сгенерировать почтовый штрих‑код в C#

Если вам нужно **создать пустой Planet штрих‑код** для почтовой системы, это руководство покажет, как сделать это с помощью Aspose.BarCode для .NET. Вы также узнаете **как генерировать почтовый штрих‑код** в виде изображений, таких как Planet и RM4SCC, настроить ширину полос и управлять параметром заполненных‑полос.

Генерация почтовых штрих‑кодов не требует отдельной графической библиотеки. SDK Aspose.BarCode предоставляет единый API, который обрабатывает кодирование, рендеринг изображения и выбор формата изображения. К концу этого урока у вас будет три готовых PNG‑файла:

* `PostalPlanetEmptyBars.png` – Planet штрих‑код с пустыми полосами  
* `PostalPlanetFilledBars.png` – Planet штрих‑код со стандартными заполненными полосами  
* `PostalRM4SCCFilledBars.png` – RM4SCC штрих‑код с заполненными полосами  

Эти файлы можно вставить в любой шаблон почтовой этикетки, распечатать их на конвертах или передать стороннему сервису.

## Предварительные требования

* .NET 6.0 или новее (код также работает с .NET Framework 4.7+).  
* Visual Studio 2022 или любой IDE для C#.  
* Aspose.BarCode for .NET – установить через NuGet:

```bash
dotnet add package Aspose.BarCode
```

Дополнительные зависимости не требуются.

## Создание пустого Planet штрих‑кода с Aspose.BarCode

Символика Planet является частью семейства штрих‑кодов United States Postal Service (USPS). По умолчанию SDK рисует **заполненные** полосы. Чтобы **создать пустой Planet штрих‑код**, отключите флаг `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Почему это работает:**  
`EncodeTypes.Planet` указывает генератору использовать символику Planet. `XDimension.Pixels` контролирует физическую ширину каждой полосы, что критично для почтовых сканеров, ожидающих определённый размер модуля. Установка `FilledBars` в `false` заставляет рендерер рисовать только контур каждой полосы, создавая *пустой* вид, требуемый некоторыми почтовыми стандартами.

### Ожидаемый результат

Вы найдёте `PostalPlanetEmptyBars.png` в целевой папке. На изображении показан Planet штрих‑код, где каждая полоса представлена контуром, а не сплошным прямоугольником.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="Создать пустой Planet штрих‑код – пример Planet штрих‑кода с пустыми полосами"}

## Как сгенерировать изображения почтовых штрих‑кодов (заполненная версия)

Большинство почтовых процессов используют версию со стандартными заполненными полосами. Тот же API может сгенерировать заполненный Planet штрих‑код и RM4SCC штрих‑код всего в несколько строк кода.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Почему может понадобиться RM4SCC:**  
RM4SCC — более новый штрих‑код USPS, который кодирует те же данные, что и Planet, но с более высокой плотностью. Некоторые перевозчики требуют RM4SCC для получения скидок при массовой рассылке. Приведённый выше код демонстрирует, как **создать почтовый штрих‑код** для обоих стандартов без изменения общего рабочего процесса.

### Ожидаемый результат

* `PostalPlanetFilledBars.png` – классический Planet штрих‑код со заполненными полосами.  
* `PostalRM4SCCFilledBars.png` – RM4SCC штрих‑код со заполненными полосами, визуально похожий, но с более плотным расположением.

Оба файла можно открыть в любом просмотрщике изображений для проверки шаблона полос.

## Настройка ширины полос для разных разрешений печати

Почтовые сканеры часто указывают минимальную ширину модуля (например, 0.013 дюйма). Если ваш принтер работает с 300 dpi, модуль в 4 пикселя соответствует 0.013 дюйма. Отрегулируйте значение `XDimension.Pixels`, чтобы оно соответствовало вашему оборудованию:

| Желаемый модуль (дюймы) | DPI | Необходимо пикселей (`XDimension`) |
|--------------------------|-----|--------------------------------------|
| 0.013                    | 300 | 4                                    |
| 0.013                    | 600 | 8                                    |
| 0.015                    | 300 | 5                                    |

**Совет:** Всегда тестируйте

## Что вам следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые развивают техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как создать Planet штрих‑код PNG с C# – пошаговое руководство](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Создание почтового штрих‑кода в C# – полное руководство с Planet штрих‑кодом](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Как сгенерировать почтовый штрих‑код в C# с Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}