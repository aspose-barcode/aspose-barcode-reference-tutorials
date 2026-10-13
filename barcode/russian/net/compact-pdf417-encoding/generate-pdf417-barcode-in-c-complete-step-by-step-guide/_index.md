---
category: general
date: 2026-09-23
description: Узнайте, как быстро сгенерировать штрих‑код PDF417 в C#, изменить его
  размер и задать пользовательские размеры с помощью Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate pdf417 barcode c#
- adjust barcode size c#
- custom barcode dimensions
lastmod: 2026-09-23
og_description: Как сгенерировать штрих‑код PDF417 в C# за считанные минуты. В этом
  руководстве показано, как кодировать текст, управлять X‑dimension и настраивать
  расположение столбцов и строк с помощью Aspose.BarCode.
og_image_alt: 'Developer guide: generate PDF417 barcode with custom dimensions using
  C#'
og_title: Как сгенерировать штрих‑код PDF417 в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate PDF417 barcode quickly with C#. Includes text
    encoding, size adjustment, and custom dimensions.
  headline: How to generate PDF417 barcode in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
- Aspose.BarCode
title: Как сгенерировать штрих‑код PDF417 в C# – полное пошаговое руководство
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код PDF417 на C# – полное пошаговое руководство

Когда‑нибудь вам нужно было **создать штрих‑код PDF417**, но вы не знали, какие настройки изменить? Вы не одиноки — многие разработчики сталкиваются с тем же, когда впервые работают с 2‑D штрих‑кодами. Хорошая новость? С несколькими строками C# вы можете превратить любую строку в сканируемое изображение PDF417, контролировать её точный размер и даже задать пользовательскую раскладку столбцов‑строк.

В этом руководстве мы пройдемся по тому, как **создать штрих‑код из текста**, настроить размер штрих‑кода и задать пользовательские размеры штрих‑кода — все с использованием популярной библиотеки Aspose.BarCode. К концу у вас будет готовый пример, который можно добавить в любой проект .NET.

![Пример генерации штрих‑кода PDF417](https://example.com/og-image.png "Пример генерации штрих‑кода PDF417")
[Пример генерации штрих‑кода PDF417](https://example.com/og-image.png "Пример генерации штрих‑кода PDF417")

## Быстрые ответы
- **Какая библиотека создает штрих‑коды PDF417 в .NET?** Aspose.BarCode for .NET.
- **Сколько строк кода требуется для базового штрих‑кода?** Только три строки: создать генератор, задать X‑dimension, сохранить изображение.
- **Могу ли я настроить столбцы и строки?** Да, вы можете задать `Columns` и `Rows` в параметрах PDF417.
- **Какие форматы изображений поддерживаются?** PNG, JPEG, BMP, GIF, SVG и PDF.
- **Работают ли символы Unicode?** Абсолютно; API полностью поддерживает кодировку UTF‑8.

## Что означает «как сгенерировать PDF417»?
Фраза «how to generate PDF417» относится к процессу создания 2‑D штрих‑кода PDF417 из текстовых данных с помощью программной библиотеки. С Aspose.BarCode вы можете выполнить это менее чем за минуту. Это включает в себя взятие обычной строки, передачу её генератору штрих‑кода, реализующему спецификацию PDF417, и получение матрицы черных и белых модулей, которую можно отобразить как изображение или встроить в документ.

## Почему использовать Aspose.BarCode для генерации PDF417?
Aspose.BarCode поддерживает **более 50 форматов ввода и вывода** и может обрабатывать **многостраничные документы без загрузки всего файла в память**. Библиотека работает на **.NET 6+, .NET Framework 4.8 и .NET Core**, предоставляя гибкость для настольных, серверных и облачных сред.

## Предварительные требования
- .NET 6.0 или новее (код также работает на .NET Framework 4.8).
- Visual Studio 2022 или любой IDE, поддерживающий C#.
- Aspose.BarCode for .NET (бесплатная пробная версия или лицензия). Установите через NuGet:

```bash
dotnet add package Aspose.BarCode
```

Вот и всё — после подключения пакета вы готовы к работе.

## Как сгенерировать штрих‑код PDF417 на C#?

Загрузите ваш текст, настройте генератор и сохраните изображение в три простых шага. Этот прямой ответ дает вам полный рабочий процесс без дополнительных пояснений. Сначала создайте экземпляр `BarcodeGenerator` с символьностью PDF417 и вашими данными. Затем настройте визуальные параметры, такие как X‑dimension, столбцы и строки. Наконец, вызовите `Save`, чтобы записать изображение на диск в нужном формате.

### Шаг 1 – создать штрих‑код PDF417 с текстовыми данными

Класс `BarcodeGenerator` создает изображения штрих‑кодов на основе указанной символьности и данных.  
Первое, что нам нужно, — это экземпляр `BarcodeGenerator`, который знает, что мы работаем с символьностью PDF417 и с точным текстом, который хотим закодировать.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Почему это важно:**  
> `EncodeTypes.Pdf417` указывает библиотеке использовать 2‑D формат PDF417, а второй аргумент — это полезная нагрузка **generate barcode from text**. Всё, что вы передадите сюда, становится данными, хранящимися в матрице штрих‑кода.

### Шаг 2 – настроить размер штрих‑кода (X‑dimension)

Свойство `XDimension` определяет ширину в пикселях одного модуля (самого маленького черного или белого квадрата) в изображении штрих‑кода.  

`XDimension` контролирует ширину одного модуля (самого маленького черного или белого квадрата) в пикселях.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Pro tip:**  
> Значение 2 px хорошо подходит для большинства сценариев отображения на экране. Для печати с высоким разрешением вы можете увеличить его до 3 или 4 px. Помните, что большие X‑dimension увеличивают общий размер изображения.

### Шаг 3 – задать пользовательские размеры штрих‑кода (столбцы и строки)

PDF417 позволяет задать, сколько столбцов и строк будет занимать штрих‑код. Здесь вступают в силу **custom barcode dimensions**.  

Параметры `Pdf417` позволяют указать точную сетку столбцов‑строк для штрих‑кода.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Что происходит «под капотом»?**  
> Библиотека перераспределяет закодированные данные по указанной сетке. Меньшее количество столбцов делает штрих‑код выше; больше строк — короче. Поэкспериментируйте с числами, пока визуальный баланс не будет соответствовать вашим требованиям.

### Шаг 4 – сохранить изображение штрих‑кода

Теперь, когда всё настроено, мы просто просим генератор записать PNG‑файл. PNG — без потерь, поэтому чёткость модулей сохраняется.  
`Save` записывает сгенерированный штрих‑код в файл в выбранном формате изображения.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

При запуске программы вы увидите файл по пути `C:\Barcodes\CustomLayout.png`, который будет выглядеть аналогично скриншоту выше. Сканирование его любым совместимым считывателем PDF417 вернёт исходную строку `Åspóse.Barcóde©`.

## Полный рабочий пример

Ниже приведена полная программа, которую можно скопировать и вставить в консольное приложение. В ней включены все директивы `using` и обработка ошибок, ожидаемая в продакшн‑коде.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Ожидаемый вывод

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…и создаёт PNG, который можно открыть в любом просмотрщике изображений. Если вы отсканируете его мобильным приложением (например, «Barcode Scanner» на iOS/Android), декодированный текст будет точно **Åspóse.Barcóde©**.

## Часто задаваемые вопросы и крайние случаи

| Question | Answer |
|----------|--------|
| **Можно ли использовать другой формат изображения?** | Да — `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` или `Svg` поддерживаются. Просто измените второй аргумент метода `Save`. |
| **Что если мой текст содержит символы Unicode?** | Aspose.BarCode полностью поддерживает UTF‑8, поэтому пример с `Å` и `©` работает сразу из коробки. |
| **Как изменить уровень коррекции ошибок?** | Используйте `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (уровни 0‑8). Более высокие уровни повышают избыточность, но также увеличивают размер. |
| **Мне нужен прозрачный фон — можно ли это сделать?** | Установите `generator.Parameters.Barcode.Image.TransparentBackground = true;` перед сохранением. |
| **Можно ли встроить штрих‑код напрямую в PDF?** | Конечно. Замените вызов `Save` на `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` и вы получите одностраничный PDF с штрих‑кодом. |

## Часто задаваемые вопросы

**Q: Работает ли библиотека на .NET Core и .NET 5/6?**  
A: Да, Aspose.BarCode for .NET поддерживает .NET Core 3.1, .NET 5, .NET 6 и более новые версии.

**Q: Могу ли я генерировать несколько штрих‑кодов в цикле?**  
A: Абсолютно. Создайте новый `BarcodeGenerator` для каждой строки или переиспользуйте тот же экземпляр, изменив свойство `CodeText`.

**Q: Какой максимальный размер может иметь сгенерированное изображение?**  
A: API может создавать изображения до **10 000 × 10 000 пикселей**; потребление памяти растёт вместе с X‑dimension и настройками столбцов/строк.

**Q: Требуется ли лицензия для использования в продакшене?**  
A: Да, коммерческая лицензия убирает водяные знаки оценки и открывает полный набор функций. Бесплатная пробная версия доступна для тестирования.

**Q: Нужно ли вручную освобождать генератор?**  
A: `BarcodeGenerator` реализует `IDisposable`. Оберните его в блок `using` или вызовите `Dispose()`, чтобы своевременно освободить неуправляемые ресурсы.

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Как сгенерировать Aztec‑штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как генерировать штрих‑коды — типы одноразмерных штрих‑кодов](/barcode/english/net/one-dimensional-barcode-types/)
- [Генерация DataMatrix штрих‑кода — профессиональное руководство с Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

---

**Last Updated:** 2026-09-23  
**Tested with:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Похожие руководства

- [Настройка размера штрих‑кода C Руководство по генерации Pdf417 штрих‑кодов](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Пример Aspose Barcode: генерация Macro Pdf417 на C](/barcode/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Генерация Micro Pdf417 штрих‑кода на C — полное руководство](/barcode/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}