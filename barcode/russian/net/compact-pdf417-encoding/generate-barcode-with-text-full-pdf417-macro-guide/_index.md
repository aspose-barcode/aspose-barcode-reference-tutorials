---
category: general
date: 2026-07-18
description: Создавайте штрих‑коды с текстом с помощью Aspose.BarCode для .NET. Узнайте,
  как генерировать штрих‑коды PDF417, задавать параметры макросов и экспортировать
  изображения PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: ru
lastmod: 2026-07-18
og_description: Быстро генерируйте штрих‑код с текстом в C#. Этот пошаговый учебник
  показывает, как создавать штрих‑коды PDF417, настраивать макросы и сохранять их
  в PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Создать штрих‑код с текстом – мастер создания макроса PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Создание штрихкода с текстом – Полное руководство по PDF417 Macro
url: /ru/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрихкода с текстом – Полное руководство по Macro PDF417

Когда‑нибудь задумывались **как генерировать PDF417** штрихкоды, которые также включают пользовательский текст? В этом руководстве вы увидите точно, как **создавать штрихкод с текстом** с помощью Aspose.BarCode for .NET, и мы пройдем все настройки, необходимые для символа Macro PDF417. Без лишних слов, только полностью готовый пример, который вы можете сразу добавить в свой проект.

Мы рассмотрим:

* Требуемый пакет NuGet и директивы `using`.  
* Как создать генератор штрихкода, поддерживающий Unicode‑символы.  
* Настройку размера модуля, количества колонок и макроспецифических идентификаторов.  
* Сохранение результата в PNG‑файл и проверку вывода.  

К концу вы получите готовое PNG‑изображение штрихкода Macro PDF417, которое можно внедрить в счета, билеты или любой документ, требующий машинно‑читаемого сегмента.

---

## Требования

Перед тем как приступить, убедитесь, что у вас есть:

| Требование | Причина |
|-------------|--------|
| **.NET 6.0** или новее | Aspose.BarCode поддерживает .NET Standard 2.0+, поэтому .NET 6 предоставляет вам новейшую среду выполнения. |
| **Visual Studio 2022** (или любую IDE C#) | Для удобного редактирования и отладки. |
| **Aspose.BarCode for .NET** пакет NuGet | Библиотека, которая действительно создает штрихкод. Установите её с помощью `dotnet add package Aspose.BarCode`. |
| **Разрешение на запись** в папку вывода | Методу `Save` необходимо записать PNG‑файл. |

Если что‑то из этого вам незнакомо, сделайте паузу и разберитесь — иначе код выбросит очевидные исключения.

---

## Шаг 1 – Установить и импортировать библиотеку

Сначала добавьте пакет NuGet в ваш проект:

```bash
dotnet add package Aspose.BarCode
```

Затем подключите необходимые пространства имён:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Pro tip:** Если вы используете Visual Studio, щёлкните правой кнопкой мыши по проекту → *Manage NuGet Packages* → найдите *Aspose.BarCode* и установите последнюю стабильную версию.

---

## Шаг 2 – Создать генератор штрихкода с вашим пользовательским текстом

*Основная* задача — **создавать штрихкод с текстом**, содержащий специальные символы, такие как “Å” и “©”. Конструктор принимает тип кодирования и строку исходных данных:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Почему это важно: `EncodeTypes.MacroPdf417` сообщает Aspose, что нам нужна макро‑версия, позволяющая разбить большое сообщение на несколько символов. Строка текста может быть любой последовательностью UTF‑8; Aspose обрабатывает конвертацию внутренне.

---

## Шаг 3 – Настроить базовый внешний вид (размер модуля)

«Модуль» штрихкода — это самая маленькая чёрно‑белая ячейка. Установка её пиксельного размера контролирует общие размеры изображения без изменения плотности данных:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Если нужен более крупный образ для печати, увеличьте значение до 4 или 6. Помните, что большие модули увеличивают конечный размер PNG‑файла.

---

## Шаг 4 – Настроить параметры Macro PDF417

Macro PDF417 добавляет два идентификатора, позволяющих сканеру собрать несколько символов в одно целое. Обычно задаются следующие свойства:

| Свойство | Что делает |
|----------|------------|
| `Columns` | Количество столбцов данных на символ (влияет на ширину). |
| `MacroPdf417FileID` | Уникальный идентификатор для всего макро‑файла (должен быть ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Индекс текущего сегмента (0‑254). |

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Edge‑case note:** `MacroPdf417FileID` должен быть одинаковым для каждого сегмента в одном логическом файле. Если вы генерируете несколько сегментов, используйте один и тот же ID, иначе получите несвязанные символы, которые нельзя будет объединить.

---

## Шаг 5 – Сохранить штрихкод в PNG‑изображение

Теперь, когда всё настроено, запишите изображение на диск:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Метод `Save` автоматически создаёт PNG, управляя DPI и глубиной цвета. После выполнения откройте файл — вы увидите что‑то вроде этого:

![Пример штрихкода с текстом](/images/barcode-example.png){.center alt="Пример штрихкода с текстом"}

Если штрихкода нет, проверьте, существует ли папка и имеет ли приложение права на запись.

---

## Полный, готовый к запуску пример

Скопируйте весь фрагмент ниже в новое консольное приложение (`dotnet new console`) и запустите его. Он создаст PNG в папке `C:\Barcodes` (сначала создайте папку).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Expected output** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

А PNG‑файл отобразит компактный символ Macro PDF417, содержащий текст “Åspóse.Barcóde©”.

---

## Часто задаваемые вопросы и подводные камни

| Вопрос | Ответ |
|--------|-------|
| *Можно ли использовать другой формат изображения?* | Конечно — замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif`. PNG без потерь, поэтому мы используем его по умолчанию. |
| *Что делать, если нужно более одного сегмента?* | Создайте новый `BarcodeGenerator` для каждого сегмента, оставьте `MacroPdf417FileID` одинаковым и увеличьте `MacroPdf417SegmentID` (0‑254). |
| *Мой текст содержит эмодзи — они будут работать?* | Aspose.BarCode поддерживает UTF‑8, так что большинство эмодзи работают. Убедитесь, что целевой сканер может их декодировать; многие промышленные сканеры обрабатывают только буквенно‑цифровые данные. |
| *Штрихкод слишком широкий для моей этикетки.* | Уменьшите `Columns` или увеличьте размер модуля. Меньшее количество колонок делает символ уже, но может потребовать принтер с более высоким DPI. |
| *Нужна ли лицензия?* | Бесплатная оценочная лицензия подходит для тестирования, но добавляет небольшую водяную метку. Для продакшна приобретите лицензию, чтобы убрать водяную метку и открыть полный набор функций. |

---

## Следующие шаги

Теперь, когда вы знаете **как генерировать PDF417** штрихкоды с пользовательским текстом, вы можете:

* **Decode** штрихкод в мобильном приложении, используя `BarCodeReader` из Aspose.BarCode.  
* **Combine** несколько макросегментов в один PDF‑документ для пакетной печати.  
* **Explore other symbologies** (QR, DataMatrix) с аналогичными параметрами.  
* **Adjust error correction level** через `Pdf417.ErrorCorrectionLevel` для более тяжёлых условий.

Каждая из этих тем опирается на те же базовые концепции, которые вы только что изучили, так что переход будет плавным.

---

## Заключение

Мы прошли полный сквозной процесс, позволяющий **создавать штрихкод с текстом** и, в частности, **как генерировать Macro PDF417** символы с помощью Aspose.BarCode for .NET. Установив X‑dimension, количество колонок и макро‑идентификаторы, вы получаете полный контроль над размером, компоновкой и обработкой многосегментных данных. Полученный PNG можно печатать, внедрять в PDF‑файлы или отправлять сканеру без дополнительного преобразования.

Попробуйте, поиграйте с параметрами, и пусть штрихкод работает на ваш бизнес‑кейс. Если возникнут сложности, документация Aspose и форумы сообщества — отличные ресурсы для дальнейшего изучения. Happy coding!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to generate DataMatrix barcode with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}