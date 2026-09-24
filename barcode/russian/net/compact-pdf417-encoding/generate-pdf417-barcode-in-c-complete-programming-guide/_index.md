---
category: general
date: 2026-07-18
description: Быстро генерируйте штрих‑код PDF417. Узнайте, как установить связанный
  режим и как генерировать штрих‑код PDF417 с помощью Aspose.BarCode в понятном пошаговом
  руководстве.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: ru
lastmod: 2026-07-18
og_description: Генерируйте PDF417 штрих‑код мгновенно. Этот учебник показывает, как
  установить связанный режим и как генерировать PDF417 штрих‑код с помощью Aspose.BarCode,
  полностью с исполняемым кодом.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Создание штрих‑кода PDF417 на C# – Полное пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Создание штрихкода PDF417 на C# – Полное руководство по программированию
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# – Полное руководство по программированию

Когда‑то вам нужно **создать штрих‑код PDF417** в приложении .NET, но вы не знали, с чего начать? Вы не одиноки. Будь то принтер посадочных талонов, сканер склада или просто эксперименты с 2‑D штрих‑кодами — запустить PDF417 проще, чем кажется.

В этом руководстве мы пройдём все шаги по **созданию штрих‑кода PDF417** с помощью Aspose.BarCode, покажем **как включить режим linked**, а также расскажем **как генерировать штрих‑код PDF417** с пользовательскими параметрами — всё в одном готовом к копированию примере.

## Что вы узнаете

- Какой минимальный пакет NuGet нужен.
- Как инициализировать генератор PDF417 со своим текстом.
- **Как включить режим linked**, чтобы штрих‑код мог переноситься на несколько строк.
- Дополнительные настройки, такие как размер модуля и количество колонок.
- Как сохранить результат в PNG, JPEG или любой поддерживаемый формат.
- Распространённые подводные камни и быстрые советы по устранению проблем.

### Предварительные требования

- .NET 6.0 или новее (код также работает на .NET Framework 4.7+).
- Базовые знания C#.
- Visual Studio 2022 (или любая другая IDE).
- Бесплатная пробная версия Aspose.BarCode или лицензированная копия.

> **Полезный совет:** Если вы только что настроили машину, выполните `dotnet add package Aspose.BarCode` в терминале внутри папки проекта. Это загрузит всё необходимое.

---

## Шаг 1: Установите Aspose.BarCode и добавьте пространства имён

Сначала подключим библиотеку к проекту.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Затем в начале вашего C#‑файла подключите необходимые пространства имён:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Почему это важно:** Без пространства имён `Aspose.BarCode.Generation` вы не получите доступ к `BarcodeGenerator`, а пространство `System.Drawing.Imaging` предоставляет перечисление `ImageFormat` для сохранения файлов.

---

## Шаг 2: Инициализируйте генератор штрих‑кода PDF417

Теперь создаём экземпляр генератора и передаём ему текст, который нужно закодировать. Это ядро **как генерировать штрих‑код PDF417**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Пояснение:** `EncodeTypes.Pdf417` сообщает Aspose, что мы работаем с символьной системой PDF417. Второй аргумент, `"Aspose"`, — данные, которые будут отображаться при сканировании штрих‑кода.

---

## Шаг 3: Задайте размер модуля (X‑Dimension)

Размер модуля определяет, насколько большим будет каждый крошечный квадрат (или «пиксель») штрих‑кода. Меньшие значения дают более плотный код; большие — делают его более читаемым на принтерах с низким разрешением.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Обычный диапазон:** 1–4 пикселя подходит для большинства экранов. Если печатаете на принтере с высоким DPI, увеличьте значение до 3 или 4.

---

## Шаг 4: Настройте количество колонок и включите режим linked

Здесь мы отвечаем на вопрос **как включить режим linked**. Linked‑mode позволяет штрих‑коду PDF417 разбиваться на несколько строк, что удобно при ограниченном горизонтальном пространстве.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Зачем нужен режим linked?** Представьте, что штрих‑код должен поместиться в узком элементе интерфейса. При `IsLinked = true` библиотека автоматически разбивает символ на строки, сохраняя возможность сканирования.

> **Особый случай:** Если задать слишком маленькое значение `Columns` и одновременно включить linked‑mode, Aspose может резко увеличить количество строк, что может выйти за пределы небольшого холста изображения. Следите за конечными размерами изображения.

---

## Шаг 5: Сохраните изображение штрих‑кода

Наконец, запишем штрих‑код в файл. Вы можете выбрать PNG, JPEG, BMP или даже PDF. PNG без потерь, поэтому идеально подходит для дальнейшей обработки.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Результат:** Вы получите чёткий штрих‑код PDF417 с тремя колонками, размером модуля 2 пикселя и, при необходимости, переносом строк благодаря linked‑mode.

---

## Полный рабочий пример

Ниже полностью готовая к запуску программа. Скопируйте её в новый консольный проект (`dotnet new console`) и нажмите **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Ожидаемый результат

При запуске программа выведет строку‑подтверждение, а в папке появится файл `Pdf417Linked.png`. Открытие PNG покажет штрих‑код PDF417 с тремя колонками, который может занимать две строки (благодаря linked‑mode). Сканирование смартфоном отобразит текст **«Aspose»**.

---

## Часто задаваемые вопросы и устранение неполадок

### 1. *Что делать, если штрих‑код выглядит размытым?*  
Чаще всего это проблема DPI. Увеличьте `XDimension.Pixels` или сохраните изображение с более высоким разрешением, используя `generator.Save(..., BarCodeImageFormat.Png, 300)`, где `300` — DPI.

### 2. *Можно ли кодировать более длинные строки?*  
Да — PDF417 способен хранить до ~1 850 символов. Если вы превысите ёмкость при выбранном количестве колонок, библиотека автоматически добавит строки. Отрегулируйте `Columns` или включите `IsLinked`, чтобы штрих‑код оставался компактным.

### 3. *Нужна ли лицензия для продакшн‑использования?*  
Aspose.BarCode работает в режиме оценки, но сгенерированный штрих‑код будет содержать небольшую водяную метку. Приобретите лицензию, чтобы её убрать и открыть расширенные возможности, такие как настройка уровня коррекции ошибок.

### 4. *Как генерировать штрих‑код PDF417 в других форматах?*  
Просто измените второй аргумент метода `Save`. Для JPEG используйте `BarCodeImageFormat.Jpeg`; для PDF — `BarCodeImageFormat.Pdf`.

---

## Расширение примера

Теперь, когда вы знаете **как генерировать штрих‑код PDF417** и **как включить режим linked**, можно изучить:

- **Уровень коррекции ошибок** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **Добавление рамки** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **Пользовательские цвета** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **Встраивание штрих‑кода в PDF‑отчёт** – комбинируйте Aspose.PDF с Aspose.BarCode.

Все эти настройки следуют одной схеме: найдите нужное свойство в `generator.Parameters.Barcode.Pdf417` (или в общем объекте `Barcode`) и задайте значение.

---

## Заключение

Мы рассмотрели всё, что нужно для **создания штрих‑кода PDF417** в C#, от установки Aspose.BarCode до настройки linked‑mode и сохранения изображения. Следуя этим шагам, вы получите готовый к использованию генератор штрих‑кодов, который можно внедрить в любое .NET‑решение.

Главные выводы:

1. Инициализируйте с `EncodeTypes.Pdf417`.
2. Настройте `XDimension` для визуальной чёткости.
3. Установите `Columns` и включите `IsLinked`, чтобы управлять раскладкой (**как включить режим linked**).
4. Сохраните в нужном формате.

Экспериментируйте с дополнительными параметрами и не стесняйтесь делиться результатами или задавать вопросы в комментариях. Приятного кодинга, и пусть ваши штрих‑коды всегда сканируются с первого раза!

## Что изучать дальше?

Следующие руководства охватывают смежные темы, расширяющие техники, продемонстрированные в этом пособии. Каждый ресурс содержит полностью рабочие примеры кода с пошаговыми объяснениями, чтобы вы могли освоить дополнительные возможности API и исследовать альтернативные подходы в своих проектах.

- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑коды PDF417 – компактное кодирование PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Как генерировать изображение штрих‑кода в Java с Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}