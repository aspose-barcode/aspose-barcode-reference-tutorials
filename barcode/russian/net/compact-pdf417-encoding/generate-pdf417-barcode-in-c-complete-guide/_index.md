---
category: general
date: 2026-07-15
description: Быстро генерируйте штрих‑код PDF417 и узнайте, как задать количество
  столбцов для компактного изображения штрих‑кода PDF417 в C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set columns
- pdf417 barcode image
- Aspose.BarCode PDF417
- C# barcode generation
- compact PDF417
language: ru
lastmod: 2026-07-15
og_description: Создавайте штрих‑код PDF417 с помощью Aspose.BarCode и узнайте, как
  установить количество столбцов для создания компактного изображения штрих‑кода PDF417.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Создание штрих‑кода PDF417 на C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly and learn how to set columns for a
    compact PDF417 barcode image in C#.
  headline: Generate PDF417 Barcode in C# – Complete Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Генерация штрихкода PDF417 в C# – Полное руководство
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих‑кода PDF417 в C# – Полное руководство

Когда‑то вам нужно **сгенерировать штрих‑код PDF417** в проекте .NET, но вы не знаете, с чего начать? Вы не одиноки. Во многих корпоративных приложениях — будь то принтеры посадочных талонов, бирки инвентаря или мобильные билеты — PDF417 является рабочей лошадкой, упаковывающей большое количество данных в небольшой визуальный след.

Дело в том, что библиотека Aspose.BarCode делает весь процесс почти безболезненным, и вы даже можете управлять **тем, как задать столбцы**, чтобы штрих‑код был максимально компактным. К концу этого руководства у вас будет готовое PNG‑изображение **штрих‑кода PDF417**, которое можно вставить в любой UI, письмо или задачу печати.

## Что вы получите в результате

- Полностью рабочее консольное приложение C#, создающее штрих‑код PDF417.  
- Чёткое понимание *X‑Dimension* (размера модуля) и почему это важно.  
- Пошаговые инструкции о **том, как задать столбцы** для более плотного штрих‑кода.  
- Сохранённый файл `PNG`, который можно сразу открыть для проверки результата.  
- Советы по устранению распространённых проблем (например, нечитаемые штрих‑коды, неверный формат изображения).

> **Prerequisites** – .NET 6+ SDK, Visual Studio 2022 (или любой другой редактор), и ссылка NuGet на `Aspose.BarCode`. Больше ничего не требуется.

---

## Шаг 1: Установите пакет Aspose.BarCode через NuGet

Прежде чем мы сможем *сгенерировать штрих‑код PDF417*, библиотека должна быть добавлена в проект.

```bash
dotnet add package Aspose.BarCode
```

Эта единственная строка подтягивает все типы, которые вам понадобятся, включая `BarcodeGenerator`, `EncodeTypes` и перечисление `BarCodeImageFormat`.

> **Pro tip:** Если вы таргетируете .NET Framework вместо .NET 6, используйте классическую команду PowerShell `Install-Package Aspose.BarCode` в консоли Package Manager.

---

## Шаг 2: Создайте минимальное консольное приложение

Сделаем небольшую программу, которая ничего не делает, кроме как генерирует штрих‑код. Откройте новую папку, выполните `dotnet new console`, затем замените автоматически сгенерированный `Program.cs` кодом ниже.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Почему это важно:**  
- `EncodeTypes.Pdf417` сообщает библиотеке, что нам нужен штрих‑код PDF417, а не QR или Code128.  
- `XDimension.Pixels` управляет разрешением каждого крошечного чёрного или белого модуля.  
- Блок **how to set columns** напрямую влияет на форму **изображения штрих‑кода PDF417**.  
- `Truncate = true` убирает все лишние пустые строки, давая «компактный» вид, который любят многие сканеры.

---

## Шаг 3: Углубляемся – Понимание столбцов и усечения

### Как задать столбцы

PDF417 располагает данные в матрице *строк* × *столбцов*. По умолчанию библиотека использует 5 столбцов, что подходит для большинства случаев. Однако вам может потребоваться более узкий штрих‑код для этикетки или более широкий для повышения надёжности сканирования. Свойство:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

принимает значения от **1** до **30** (точный лимит зависит от длины данных). Ниже быстрый шпаргалка:

| Столбцы | Прибл. ширина (мм) | Когда использовать |
|---------|-------------------|----------------------|
| 1‑3     | Очень узко        | Маленькая этикетка, ограниченное пространство |
| 4‑6     | Стандартно        | Большинство чеков, билетов |
| 7‑10    | Шире              | Высокоплотные данные, лучшая читаемость |

### Truncate (режим компактности)

Установка `Truncate = true` заставляет кодировщик отрезать все ненужные пустые строки внизу. Результат — **компактное изображение штрих‑кода PDF417**, занимающее минимальную площадь при сохранении всех данных. Если вы получаете ошибку «штрих‑код слишком велик для этикетки», переключите этот флаг.

---

## Шаг 4: Запустите приложение и проверьте результат

Скомпилируйте и выполните:

```bash
dotnet run
```

Вы должны увидеть сообщение в консоли, подтверждающее место сохранения. Перейдите в папку и откройте `CompactPdf417.png`. Изображение будет выглядеть примерно так:

![Generated PDF417 barcode image](./CompactPdf417.png "Generated PDF417 barcode image – compact PNG created by Aspose.BarCode")

*Текст альтернативного описания:* **Сгенерированное изображение штрих‑кода PDF417** — компактный PNG‑файл, полученный с помощью кода из руководства.

Если ваш сканер смог его прочитать, поздравляем — вы успешно **сгенерировали штрих‑код PDF417** и освоили **то, как задать столбцы** для аккуратного **изображения штрих‑кода PDF417**.

---

## Шаг 5: Распространённые проблемы и их решения

| Симптом | Вероятная причина | Быстрое решение |
|---------|-------------------|-----------------|
| Штрих‑код выглядит размытым | `XDimension.Pixels` слишком низкое (например, 1) | Увеличьте до 2‑3 пикселей для более чёткого изображения. |
| Сканер не читает | Слишком много столбцов для заданных данных | Уменьшите `Columns` или включите `Truncate`. |
| Неправильный формат файла | По ошибке сохранено с `BarCodeImageFormat.Jpeg` | Используйте `BarCodeImageFormat.Png` для без потерь. |
| Исключение `ArgumentOutOfRangeException` | Количество столбцов превышает допустимый диапазон | Держите столбцы в пределах 1‑30 и убедитесь, что данные помещаются. |

---

## Шаг 6: Дальше — настройка цветов и добавление текста

Если хотите, чтобы штрих‑код соответствовал фирменной палитре, можно изменить цвета переднего плана и фона:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Или добавить человекочитаемый текст под штрих‑кодом:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Эти дополнения необязательны, но показывают, насколько гибким может быть процесс **генерации штрих‑кода PDF417**.

---

## Заключение

Мы прошли полный пример от начала до конца, который **генерирует штрих‑код PDF417** с помощью Aspose.BarCode, объяснил **как задать столбцы** для управления размерами штрих‑кода и сохранил результат в виде чёткого **изображения штрих‑кода PDF417** в формате PNG. Код автономный, работает с .NET 6+ и может быть добавлен в любой существующий проект без лишних хлопот.

Что дальше? Попробуйте кодировать более крупные полезные нагрузки (например, JSON), поэкспериментируйте с различными форматами изображений или интегрируйте генератор в веб‑API, который будет отдавать штрих‑коды по запросу. Возможности безграничны, а у вас теперь есть надёжная база для дальнейшего развития.

Счастливого кодинга, и пусть ваши штрих‑коды всегда сканируются с первой попытки!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}