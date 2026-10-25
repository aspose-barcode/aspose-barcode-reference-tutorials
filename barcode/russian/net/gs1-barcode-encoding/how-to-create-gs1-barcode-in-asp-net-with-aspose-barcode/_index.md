---
category: general
date: 2026-10-24
description: Узнайте, как создать штрих‑код GS1 в ASP.NET с помощью Aspose.BarCode.
  Пошаговое руководство по генерации штрих‑кода из строки и выводу в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: ru
lastmod: 2026-10-24
og_description: Как создать штрих‑код GS1 в ASP.NET с использованием Aspose.BarCode.
  Следуйте этому руководству, чтобы сгенерировать штрих‑код из строки, настроить визуальные
  параметры и сохранить файлы PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Как создать штрих‑код GS1 в ASP.NET — полное руководство Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Как создать GS1‑штрихкод в ASP.NET с помощью Aspose.BarCode
url: /ru/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать GS1 barcode в ASP.NET с Aspose.BarCode

Если вам нужно **how to create GS1 barcode** в приложении ASP.NET, это руководство покажет точные шаги. Вы увидите, как сгенерировать штрих‑код из строки, настроить визуальный вид и сохранить результат в виде PNG‑изображения.

Создание GS1 barcode не требует пользовательской логики кодирования. При использовании Aspose.BarCode вы получаете надёжное, соответствующее стандартам решение, которое работает на .NET 6+ и более ранних фреймворках. Это руководство охватывает всё — от настройки проекта до проверки результата, так что вы можете скопировать код непосредственно в свой веб‑проект.

## Требования

* Visual Studio 2022 (или любая IDE, поддерживающая .NET)
* .NET 6 SDK (или .NET Framework 4.7.2 и выше)
* Базовые знания ASP.NET Core или ASP.NET Framework
* Лицензия Aspose.BarCode (бесплатная оценочная версия подходит для тестирования)

Дополнительные сторонние библиотеки не требуются, так как Aspose.BarCode обрабатывает всё кодирование и рендеринг внутри.

## Шаг 1: Создать новый проект ASP.NET

Откройте Visual Studio и создайте **ASP.NET Core Web App** (выберите шаблон *Empty*). Для классического проекта Web Forms тот же код работает в файле code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Запуск проекта должен отобразить *GS1 barcode generator is ready.* в браузере. Это подтверждает, что веб‑хост работает.

## Шаг 2: Установить Aspose.BarCode через NuGet

Откройте **Package Manager Console** и выполните:

```powershell
Install-Package Aspose.BarCode
```

Пакет добавляет пространство имён `Aspose.BarCode.Generation`, которое содержит класс `BarcodeGenerator`, который вы будете использовать для **generate barcode from string**. Команда NuGet также обновляет файл проекта необходимой ссылкой.

## Шаг 3: Сгенерировать простой barcode из строки

Чтобы продемонстрировать базовое использование, создайте вспомогательный метод, возвращающий массив байтов PNG. Этот метод можно вызвать из контроллера, Razor‑страницы или любого конечного пункта.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Теперь вы можете вызвать `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` из любого конечного пункта и записать полученные байты в HTTP‑ответ. Это демонстрирует шаблон **barcode generator asp.net** для произвольных строк.

## Шаг 4: How to create GS1 barcode – пример Micro PDF417

GS1 barcode включают идентификаторы приложений (AI), передающие информацию о продукте. Aspose.BarCode поддерживает совместимый с GS1 вариант Micro PDF417, который идеален для компактного представления данных.

### 4.1 Подготовьте строку данных GS1

Данные GS1 должны быть заключены в скобки с кодом AI. Для идентификатора продукта (01) и номера партии (10) строка выглядит так:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Скобки являются частью стандарта; Aspose.BarCode парсит их автоматически.

### 4.2 Создайте генератор GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Откройте генератор через ASP.NET endpoint

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Переход по адресу `https://localhost:5001/gs1barcode` теперь передаёт сгенерированный PNG. Изображение соответствует спецификации GS1, а файл также сохраняется на диск для последующего использования.

## Шаг 5: Отображение дополнительных типов barcode

Тот же подход **create barcode with aspose** работает и для других символогий. Ниже быстрый пример, создающий QR‑code из URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Вы можете заменить `EncodeTypes.QR` на `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` или любой другой поддерживаемый тип. Визуальные параметры (`XDimension`, `Resolution`, `Color`) настраиваются через объект `Parameters`.

## Шаг 6: Распространённые подводные камни и рекомендации по лучшим практикам

| Проблема | Почему происходит | Как избежать |
|----------|-------------------|--------------|
| **Incorrect AI formatting** | Отсутствие скобок или неверная длина AI вызывают ошибки кодирования. | Всегда формируйте строку GS1 точно в соответствии со стандартом. Используйте вспомогательный метод для конкатенации AI. |
| **Too many columns** | Micro PDF417 поддерживает только 1‑4 столбца; установка 5 вызывает исключение. | Проверьте значение столбцов перед назначением: `if (columns < 1 || columns > 4) throw …` |
| **Low image resolution** | Маленькие значения `XDimension` могут сделать штрих‑код нечитаемым на принтерах. | Для печатных штрих‑кодов увеличьте `Resolution` (например, `generator.Parameters.Image.Resolution = 300`). |
| **File path issues on Linux** | Жёстко заданные обратные слеши ломаются на не‑Windows хостах. | Используйте `Path.Combine` для построения путей; он учитывает разделители ОС. |
| **License not applied** | Бесплатная оценочная версия добавляет водяной знак после 30 дней. | Примените лицензию заранее: `new License().SetLicense("Aspose.BarCode.lic");` |

## Шаг 7: Проверка сгенерированного barcode

После запуска endpoint откройте PNG в любом просмотрщике изображений. Чтобы убедиться, что данные GS1 закодированы правильно, можно воспользоваться бесплатным мобильным сканером, поддерживающим GS1 Micro PDF417 (многие приложения‑сканеры перечисляют эту символогию). Сканируйте изображение; приложение должно вернуть:

```
(01)12345678901234
(10)ABCD
```

Если сканер сообщает об ошибке, ещё раз проверьте форматирование AI и количество столбцов.

## Заключение

Теперь вы знаете **how to create GS1 barcode** в среде ASP.NET с использованием Aspose.BarCode. В руководстве рассмотрено:

* Настройка проекта ASP.NET и установка пакета NuGet Aspose.BarCode.  
* Использование **generate barcode from string** для общих barcode.  
* Реализация **create barcode with aspose** для создания изображения GS1‑compatible Micro PDF417.  
* Сохранение изображения на диск и передача его через HTTP endpoint.  

Отсюда вы можете изучать другие символогии GS1 (например, GS1 DataMatrix) или интегрировать генератор в более крупный процесс обработки заказов. Экспериментируйте с различными значениями `XDimension`, цветами и уровнями коррекции ошибок, чтобы соответствовать вашему бренду и условиям сканирования.

Удачной разработки, и пусть ваши приложения говорят на универсальном языке barcode!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в своих проектах.

- [Как создать штрих‑код Code 128 с GS1 с помощью Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Как создать Quiet Zone для штрих‑кода ITF-14 с использованием Aspose.BarCode для .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Как создать штрих‑код ITF-14 .NET – комплексные руководства Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}