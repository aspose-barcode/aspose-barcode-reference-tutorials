---
category: general
date: 2026-11-14
description: Создайте микробар‑код micro PDF417 в C# с помощью Aspose.BarCode — пошаговое
  руководство, охватывающее настройку генератора, X‑размер, количество столбцов и
  экспорт в PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: ru
lastmod: 2026-11-14
og_description: Создайте микробарcode PDF417 в C# с помощью Aspose.BarCode. Узнайте,
  как настроить генератор, установить XDimension, выбрать количество столбцов и экспортировать
  в PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Создание микро‑штрих‑кода PDF417 в C# – полное руководство по программированию
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Как создать микро PDF417 штрих‑код в C#
url: /ru/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать микро PDF417 штрих‑код в C#  

Если вам нужно **быстро создать микро PDF417 штрих‑код**, это руководство покажет вам готовое, готовое к запуску решение. Вы увидите, как создать генератор штрих‑кода, настроить X‑dimension, выбрать количество столбцов и, наконец, сохранить результат в виде PNG‑изображения — используя библиотеку Aspose.BarCode для .NET.

Создание микро PDF417 штрих‑кода не требует сложного конвейера сборки. К концу этого руководства у вас будет один файл C#, который генерирует изображение штрих‑кода высокого качества, которое можно внедрять в отчёты, этикетки или мобильные приложения.

## Требования  

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7+).  
* Среда разработки, например Visual Studio 2022, VS Code или Rider.  
* Лицензия Aspose.BarCode для .NET (или бесплатный оценочный ключ). Вы можете получить её на [веб‑сайте Aspose](https://purchase.aspose.com/barcode/net).  

> **Совет:** Если вы используете оценочную версию, сгенерированный PNG будет содержать небольшую водяную метку «Evaluation». Лицензированная версия удаляет её автоматически.

## Шаг 1: Настройка проекта  

Создайте новый консольный проект и добавьте пакет Aspose.BarCode через NuGet.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Команда `dotnet add package` загружает зависимости **Aspose.BarCode C# example**, поэтому вам не нужно вручную управлять DLL‑файлами.

## Шаг 2: Написание полного кода  

Замените автоматически сгенерированный `Program.cs` следующим кодом. Он демонстрирует, как **создать микро pdf417 штрих‑код** от начала до конца.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Почему каждая строка важна  

* **Конструктор BarcodeGenerator** — создаёт **генератор микро pdf417 штрих‑кода** с текстом, который вы хотите закодировать.  
* **XDimension.Pixels** — управляет шириной модуля; установка значения `2` пикселя даёт плотный, высоко‑разрешающий штрих‑код, подходящий для большинства сканеров.  
* **Pdf417.Columns** — MicroPDF417 поддерживает только 1‑4 столбца. Выбор `4` уменьшает высоту штрих‑кода, что полезно при ограниченном вертикальном пространстве.  
* **Метод Save** — сохраняет штрих‑код в файл PNG. PNG — без потерь, что гарантирует сканеру точное чтение сгенерированного шаблона.

## Шаг 3: Сборка и запуск  

Скомпилируйте и выполните программу:

```bash
dotnet run
```

Вы должны увидеть вывод в консоли:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

В папке проекта появится файл с именем **MicroPdf417.png**. Откройте его в любом просмотрщике изображений; вы увидите чёткий микро PDF417 штрих‑код, кодирующий строку `"Åspóse.Barcóde©"`.

![Сгенерированный пример микро PDF417 штрих‑кода](MicroPdf417.png "Сгенерированный пример микро PDF417 штрих‑кода"){.center-image width=400 alt="Сгенерированный пример изображения микро PDF417 штрих‑кода"}

*Изображение выше — результат кода, показанного в Шаге 2.*

## Шаг 4: Распространённые варианты и граничные случаи  

| Ситуация | Как адаптировать код |
|-----------|----------------------|
| **Разная длина данных** | MicroPDF417 может кодировать до 1 200 символов. Просто измените второй аргумент `BarcodeGenerator`. |
| **Более высокое разрешение** | Увеличьте `XDimension.Pixels` до `3` или `4`. Большие модули улучшают читаемость на сканерах с низким разрешением, но увеличивают размер изображения. |
| **Пользовательские цвета** | После создания генератора установите `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` и `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Сохранение в других форматах** | Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Gif` в зависимости от ваших последующих требований. |
| **Встраивание в PDF** | Используйте `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` и затем объедините PDF с другими документами с помощью Aspose.PDF. |

> **Обратите внимание:** Установка `XDimension.Pixels` ниже `1` вызывает `ArgumentOutOfRangeException`. Всегда держите значение `1` или выше.

## Шаг 5: Проверка штрих‑кода  

Чтобы убедиться, что штрих‑код сканируется корректно:

1. Откройте PNG в просмотрщике изображений.  
2. Используйте любое приложение для сканирования штрих‑кодов на смартфоне, поддерживающее PDF417 (большинство приложений «сканер QR‑кода» включают его).  
3. Сканируйте изображение; приложение должно отобразить исходный текст `"Åspóse.Barcóde©"`.

Если сканирование не удалось, дважды проверьте настройки **X‑dimension** и **column** — слишком маленькая ширина модуля или неподдерживаемое количество столбцов могут сделать шаблон нечитаемым.

## Заключение  

Теперь вы знаете, как **создать микро pdf417 штрих‑код** в C# с помощью Aspose.BarCode. В руководстве рассмотрено:

* Создание **генератора микро pdf417 штрих‑кода**.  
* **Установите XDimension пиксели** для контроля ширины модуля.  
* **Определите столбцы штрих‑кода** для настройки формы.  
* **Сохраните штрих‑код как PNG** для безпотерьного вывода изображения.  

Отсюда вы можете изучать дополнительные возможности, такие как настройка цветов, встраивание штрих‑кода в PDF или генерация штрих‑кодов «на лету» в веб‑API ASP.NET Core. Приятного кодирования!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать PNG штрих‑кода в C# – полное руководство по GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Как создать macro PDF417 штрих‑код в C# с использованием Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Создать PDF417 штрих‑код в C# с помощью Aspose.BarCode – пошаговое руководство](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}