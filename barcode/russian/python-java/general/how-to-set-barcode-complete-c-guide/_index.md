---
category: general
date: 2026-08-15
description: Как установить параметры штрихкода в C# и генерировать изображения штрихкода.
  Узнайте пошагово, как создать штрихкод Databar и сохранить файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: ru
lastmod: 2026-08-15
og_description: Как установить штрих‑код в C# с помощью Aspose.Barcode, а затем сгенерировать
  изображение штрих‑кода в C#. Следуйте этому руководству, чтобы создать штрих‑код
  Databar и сохранить файлы PNG.
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: Как установить штрих‑код в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Как установить штрих‑код — полное руководство по C#
url: /ru/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как задать штрих‑код – полное руководство на C#

Если вы ищете **как задать параметры штрих‑кода** в проекте .NET, это руководство покажет точные шаги, которые вам нужны. Вы узнаете, **как генерировать изображения штрих‑кода**, создать штрих‑код Databar и управлять высотой полосы пиксель‑за‑пикселем — все с чистым, готовым к продакшну кодом на C#.

В этом руководстве вы:

* Установите необходимый пакет NuGet.  
* Создадите штрих‑код Databar Omnidirectional (часть «создать штрих‑код Databar»).  
* Отрегулируете X‑размер и высоту полосы, чтобы продемонстрировать **как задать штрих‑код** размеры.  
* Сохраните результат в виде PNG‑файлов, охватывая сценарий **генерации изображения штрих‑кода C#**.

Код работает с последней версией Aspose.Barcode для .NET (v 24.12 на момент написания) и запускается на .NET 6 или новее.

---

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6 SDK (или более поздняя версия).  
* IDE, например Visual Studio 2022 или VS Code.  
* Доступ в Интернет для загрузки пакета NuGet Aspose.Barcode.

Дополнительные сторонние библиотеки не требуются.

---

## Шаг 1: Установите Aspose.Barcode для .NET

Самый надёжный способ **генерировать изображения штрих‑кода** в C# — использовать Aspose.Barcode. Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию в ваш файл проекта, обеспечивая наличие класса `BarcodeGenerator` и перечисления `EncodeTypes`.

*Совет:* Держите пакет в актуальном состоянии (`dotnet list package --outdated`), чтобы получать исправления ошибок и новые символьные наборы штрих‑кодов.

---

## Шаг 2: Создайте штрих‑код Databar (create Databar barcode)

Databar Omnidirectional идеален для розничной торговли и логистики, так как может кодировать значение GTIN‑14 плюс дополнительные данные. Следующий код создаёт объект штрих‑кода:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Почему это важно:* Перечисление `EncodeTypes.DatabarOmniDirectional` указывает библиотеке использовать символьный набор Databar, а строка `"(01)12345678901231"` следует формату GS1 Application Identifier для 14‑значного GTIN.

---

## Шаг 3: Определите общие параметры — X‑размер и базовую высоту

Большинство сканеров штрих‑кодов ожидают минимальный X‑размер (ширина самой узкой полосы). Установка значения 2 пикселя даёт компактное, но читаемое изображение.

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Позже вы сможете изменить высоту полосы без пересоздания генератора — это и есть суть **как задать штрих‑код** атрибуты после инициализации.

---

## Шаг 4: Задайте высоту первой полосы и сохраните изображение (generate barcode image C#)

Теперь мы демонстрируем первую часть **как задать штрих‑код** высоту. Высота полосы определяет визуальную длину каждой полосы; значение 30 пикселей даёт короткий штрих‑код, а 60 пикселей — более высокий вариант.

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

После выполнения `DatabarBarHeight30Pixels.png` будет содержать штрих‑код Databar с высотой полосы 30 пикселей. Откройте файл в любом просмотрщике изображений, чтобы проверить результат.

---

## Шаг 5: Измените высоту полосы и сохраните второе изображение

Чтобы показать, что **как задать штрих‑код** значения можно менять «на лету», мы меняем высоту полосы на 60 пикселей и сохраняем второй файл.

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла, показывающие одинаковые данные Databar, но с разной визуальной высотой. Это полезно, когда нужен более крупный штрих‑код для печатных этикеток или более маленький — для отображения на экране.

---

## Шаг 6: Полный, готовый к запуску пример

Объединив всё вместе, получаем автономную консольную программу, выполняющую все описанные выше шаги. Скопируйте код в новый файл `Program.cs`, замените `YOUR_DIRECTORY` на реальный путь к папке и запустите его.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**Ожидаемый вывод**

При запуске программы в консоли будет выведено:

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

И папка `C:\Barcodes` (или указанный вами путь) будет содержать два PNG‑файла. Оба изображения отображают действительный штрих‑код Databar Omnidirectional, который может сканировать любой стандартный GS1‑ридер.

---

## Часто задаваемые вопросы

**Работает ли это с другими форматами изображений?**  
Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp`, `Gif` или `Tiff`, чтобы получить соответствующий тип файла.

**Можно ли изменить цвет переднего плана?**  
Установите `generator.Parameters.Barcode.ForeColor` в любое значение `System.Drawing.Color`, например `Color.Blue`.

**А если нужен другой символьный набор?**  
Передайте другое значение `EncodeTypes` в конструктор, например `EncodeTypes.Code128` для линейного штрих‑кода или `EncodeTypes.QR` для матричного кода.

**Можно ли встроить штрих‑код в PDF?**  
Aspose.Barcode предоставляет класс `PdfGenerator`. После генерации изображения его можно добавить на страницу PDF с помощью Aspose.PDF.

---

## Лучшие практики генерации штрих‑кодов в C#

* **Повторно используйте экземпляр `BarcodeGenerator`**, когда нужно лишь подправить размеры — это избавляет от лишних выделений памяти.  
* **Освобождайте генератор** (`generator.Dispose()`) после завершения работы, чтобы быстро освободить нативные ресурсы.  
* **Проверяйте входные данные** (например, длину GTIN) перед созданием штрих‑кода, чтобы избежать исключений во время выполнения.  
* **Тестируйте с физическим сканером** после изменения X‑размера или высоты полосы; экстремальные значения могут ухудшить читаемость.  
* **Убедитесь, что папка вывода доступна для записи** учетной записи, под которой запускается приложение; иначе `Save` бросит `UnauthorizedAccessException`.

---

## Заключение

Теперь вы знаете **как задать свойства штрих‑кода**, такие как X‑размер и высота полосы, **как генерировать изображения штрих‑кода** на C#, а также точные шаги **создания файлов штрих‑кода Databar** с помощью Aspose.Barcode. Следуя полному примеру, вы сможете генерировать несколько PNG‑файлов с разными визуальными характеристиками, удовлетворяя требование **генерации изображения штрих‑кода C#** для любого .NET‑приложения.

Далее изучайте связанные темы, такие как **как генерировать штрих‑коды** массово, встраивание штрих‑кодов в PDF или переход к другим символьным наборам, например QR или Code 128. Экспериментируйте с параметрами, показанными здесь, чтобы точно настроить внешний вид штрих‑кода под вашу среду сканирования. Приятного кодинга!

## Что изучать дальше?

Следующие учебные материалы охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}