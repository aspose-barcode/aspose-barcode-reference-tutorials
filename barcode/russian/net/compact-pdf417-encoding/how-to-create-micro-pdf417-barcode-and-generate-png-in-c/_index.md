---
category: general
date: 2026-10-28
description: Создайте микробаркод PDF417 и узнайте, как генерировать PNG‑изображение
  штрихкода с простым примером на C#, работающим с .NET 6.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- C# barcode generation
- MicroPdf417 encoding
- barcode image export
language: ru
lastmod: 2026-10-28
og_description: Создайте микроштрих‑код PDF417 и посмотрите, как сгенерировать PNG‑изображение
  штрих‑кода с помощью лаконичного примера на C#. Следуйте полному рабочему процессу
  от настройки до проверки изображения.
og_image_alt: Generated micro pdf417 barcode saved as a PNG file
og_title: Создание микробарcode PDF417 и генерация PNG в C# — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create micro pdf417 barcode and learn how to generate barcode PNG with
    a simple C# example that works with .NET 6.
  headline: How to create micro pdf417 barcode and generate PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
title: Как создать микро‑PDF417 штрих‑код и сгенерировать PNG в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать микро pdf417 штрих‑код и сгенерировать PNG на C#

Если вам нужно **создать микро pdf417 штрих‑код** для системы билетов, этикетки инвентаризации или мобильного приложения, это руководство покажет вам точно **как сгенерировать PNG штрих‑кода** с помощью C#. Вы получите полностью готовую исполняемую программу, объяснение каждой опции конфигурации и советы по работе с типичными краевыми случаями.

Создание изображения штрих‑кода не требует тяжёлой графической библиотеки — достаточно современного .NET‑runtime и SDK для штрих‑кодов, поддерживающего MicroPdf417. К концу этого урока у вас будет PNG‑файл, который можно отобразить на веб‑странице, встроить в PDF или отправить на принтер.

## Что вы узнаете

* Установить и подключить библиотеку штрих‑кодов, поддерживающую MicroPdf417.  
* Написать чистый C#‑код, который **создаёт микро pdf417 штрих‑код**.  
* Настроить X‑dimension и количество колонок для оптимальной читаемости.  
* Использовать API библиотеки для **генерации PNG штрих‑кода**.  
* Проверить результат и устранить типичные проблемы.

## Предварительные требования

| Требование | Почему это важно |
|-------------|----------------|
| .NET 6 SDK (или новее) | Пример использует top‑level statements, доступные в .NET 6+. |
| Visual Studio 2022 или VS Code | Любая IDE, поддерживающая C#, подходит, но эти варианты упрощают отладку. |
| Aspose.BarCode for .NET (или любая библиотека, реализующая `EncodeTypes.MicroPdf417`) | Класс `BarcodeGenerator`, используемый ниже, берётся из этого пакета. |
| Базовые знания C# | Вы должны быть уверены в работе с директивами `using` и методом `Main`. |

Вы можете установить SDK через NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Настройте проект для **создания микро pdf417 штрих‑кода**

Создайте новый консольный проект и добавьте ссылку на библиотеку:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

Проект теперь содержит файл `Program.cs`, куда мы поместим полный пример.

## Шаг 2: Напишите полностью готовую программу на C#

Ниже представлена автономная программа, которая **создаёт микро pdf417 штрих‑код** и сохраняет его как PNG‑изображение. Все необходимые пространства имён и обработка ошибок включены, так что вы можете скопировать‑вставить её в `Program.cs` и запустить.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – Unicode characters are supported.
        const string barcodeText = "Åspóse.Barcóde©";

        // 1️⃣ Create a MicroPdf417 barcode generator.
        // This step is the core of how to generate barcode png.
        var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, barcodeText);

        // 2️⃣ Set the X‑dimension (module width) in pixels.
        // A value of 2 pixels yields a compact but readable symbol.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define the number of columns (1‑4 allowed for MicroPdf417).
        // More columns produce a shorter symbol; 4 columns is a good default.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Choose the output folder (ensure it exists on your machine).
        const string outputPath = "output.png";

        try
        {
            // 5️⃣ Save the generated barcode as a PNG image.
            // This is the final step of how to generate barcode png.
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved successfully to '{outputPath}'.");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

### Почему важна каждая строка

* **`EncodeTypes.MicroPdf417`** указывает SDK использовать символьность MicroPdf417 — компактную версию PDF417, подходящую для небольших этикеток.  
* **`XDimension.Pixels = 2`** задаёт ширину каждого модуля. Меньшие значения уменьшают изображение; большие значения повышают надёжность сканирования на низкоразрешающих устройствах.  
* **`Pdf417.Columns = 4`** определяет количество колонок данных. MicroPdf417 позволяет 1‑4 колонки; больше колонок уменьшают высоту штрих‑кода.  
* **`Save(..., BarCodeImageFormat.Png)`** — решающий вызов для **как сгенерировать barcode png**. PNG сохраняет без потерь, что идеально для дальнейшей обработки.

## Шаг 3: Запустите программу и проверьте результат

Выполните приложение:

```bash
dotnet run
```

Если всё настроено правильно, вы увидите:

```
✅ Barcode saved successfully to 'output.png'.
```

Откройте `output.png` в любом просмотрщике изображений. Файл должен показывать чёткий символ MicroPdf417, кодирующий текст `"Åspóse.Barcóde©"`.

### Ожидаемый визуальный результат

![Generated micro pdf417 barcode saved as PNG](output.png "Generated micro pdf417 barcode saved as PNG")
*Image alt text: Generated micro pdf417 barcode saved as a PNG file.*

## Краевые случаи и устранение неполадок

| Ситуация | Что проверить | Рекомендованное решение |
|-----------|---------------|-----------------|
| **Штрих‑код нечитаем на экранах с низким разрешением** | X‑dimension слишком мала (например, 1 пиксель) | Увеличьте `XDimension.Pixels` до 3‑4. |
| **Текст обрезан** | Входная строка превышает ёмкость MicroPdf417 для выбранного количества колонок | Уменьшите длину текста или увеличьте `Columns` до 4 (максимум). |
| **Unicode‑символы отображаются как квадраты** | Шрифт fallback не поддерживается библиотекой | Убедитесь, что версия библиотеки поддерживает Unicode; альтернативно используйте только ASCII‑данные. |
| **Файл не создаётся** | Каталог вывода не существует или нет прав доступа | Сначала создайте каталог или запустите приложение с повышенными привилегиями. |

## Профессиональные советы для продакшн‑использования

* **Кешировать генератор**, если создаёте много штрих‑кодов с одинаковыми настройками — это уменьшит накладные расходы на создание объектов.  
* **Пакетный экспорт**: перебирайте коллекцию строк, меняйте `generator.CodeText` на каждой итерации и вызывайте `Save` с уникальным именем файла.  
* **Валидация перед сохранением**: вызовите `generator.ValidateParameters()` (если доступно), чтобы заранее отловить ошибки конфигурации.  
* **Сжатие PNG**: используйте `System.Drawing` или `ImageSharp` для пост‑обработки PNG и уменьшения размера файла при передаче по сети.

## Связанные темы, которые стоит изучить дальше

* **Как создать QR‑коды с Aspose.BarCode** — аналогичный рабочий процесс, другая символьность.  
* **Встраивание PNG штрих‑кода в HTML‑email** — закодируйте изображение в base64 и вставьте его в `<img src="data:image/png;base64,…">`.  
* **Генерация PDF‑документов со штрих‑кодами** — комбинируйте PNG с библиотекой PDF, такой как

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}