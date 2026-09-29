---
category: general
date: 2026-08-09
description: Быстро генерируйте штрих‑код PDF417 на C#. Узнайте, как создавать PDF417
  в компактном режиме, управлять колонками и получать PNG‑вывод с помощью API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: ru
lastmod: 2026-08-09
og_description: Создайте штрих‑код PDF417 на C# с лаконичным примером. Это руководство
  показывает, как настроить компактный режим, установить количество столбцов и сохранить
  результат в виде PNG‑изображения.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Создание штрих‑кода PDF417 в C# – полный учебник
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Создание штрих‑кода PDF417 в C# — пошаговое руководство
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода PDF417 в C# – пошаговое руководство

Если вам нужно **создавать штрих‑код PDF417** в приложении .NET, этот учебник покажет вам точный способ сделать это. Вы увидите полностью готовую, исполняемую программу, которая создает компактный штрих‑код PDF417, настраивает его размер и сохраняет изображение в файл PNG.

Создание штрих‑кода PDF417 является распространённой задачей для мобильных билетов, отслеживания инвентаря и защиты документов. В этом руководстве рассматриваются основные параметры конфигурации, объясняется, почему каждый из них важен, и даются практические советы для реального использования.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия установлен  
* IDE для C#, например Visual Studio 2022 или Visual Studio Code  
* Пакет NuGet **Aspose.BarCode for .NET** (версия 23.10 или новее)  

Вы можете установить пакет с помощью следующей команды CLI:

```bash
dotnet add package Aspose.BarCode
```

Код ниже предполагает, что пакет подключён и у вас есть права записи в каталог вывода.

## Шаг 1: Настройка проекта и импорт пространств имён

Создайте новый консольный проект и добавьте необходимые директивы `using`. Эти пространства имён предоставляют класс `BarcodeGenerator` и перечисление форматов изображений.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Почему это важно:** Импорт правильных пространств имён гарантирует, что компилятор сможет найти тип `BarcodeGenerator` и перечисление `BarCodeImageFormat`. Отсутствие нужного пространства имён приводит к ошибке компиляции, что останавливает процесс генерации штрих‑кода.

## Шаг 2: Инициализация `BarcodeGenerator` с кодировкой PDF417

Конструктор `BarcodeGenerator` принимает два аргумента: символьный набор штрих‑кода (`EncodeTypes.Pdf417`) и текст, который нужно закодировать. PDF417 поддерживает широкий диапазон символов, включая Unicode‑символы.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Объяснение:**  
* `EncodeTypes.Pdf417` указывает библиотеке использовать стандарт PDF417.  
* Пример текста содержит символы с диакритическими знаками и знак копирайта, чтобы продемонстрировать работу с Unicode.  

Если нужно кодировать только числовые данные, можно передать простую строку, например `"1234567890"`.

## Шаг 3: Регулировка X‑размера для более высокой разрешающей способности

X‑размер контролирует ширину отдельного модуля штрих‑кода (самого маленького чёрного или белого элемента). Установка меньшего значения в пикселях даёт изображение более высокого разрешения.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Зачем это менять?** Стандартный X‑размер 3–4 пикселя может давать штрих‑код, выглядящий грубо на экранах с высоким DPI. Уменьшение до **2 пикселей** обеспечивает баланс между читаемостью и размером файла, особенно если позже включить компактный режим.

## Шаг 4: Настройка количества столбцов

PDF417 позволяет указать, сколько столбцов должно содержать изображение штрих‑кода. Меньшее количество столбцов делает штрих‑код уже, но выше, тогда как больше столбцов создаёт более широкий и короткий штрих‑код.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Практический совет:** Для мобильных билетов, которые должны помещаться в узкой этикетке, количество столбцов **3–5** обычно работает хорошо. Увеличьте количество, если у вас много данных и нужен более короткий штрих‑код.

## Шаг 5: Включение компактного режима для обрезки пустых строк

Компактный режим удаляет ненужные строки из матрицы штрих‑кода, уменьшая общий размер изображения без потери закодированных данных.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Когда использовать:** Если вы генерируете штрих‑коды для хранения или передачи по сети, компактный режим может уменьшить PNG‑файл до 30 %. Однако некоторые старые сканеры могут не поддерживать обрезанный PDF417; проверьте совместимость с вашим оборудованием.

## Шаг 6: Сохранение штрих‑кода как PNG‑изображения

Выберите путь вывода и вызовите `Save`. Перечисление `BarCodeImageFormat.Png` создаёт безпотерьное изображение, подходящее для большинства приложений.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Проверка результата:** Откройте PNG‑файл в любом просмотрщике изображений. Вы должны увидеть плотный, контрастный штрих‑код, соответствующий примеру текста. Сканирование изображения с помощью считывателя PDF417 (например, ZXing или мобильного приложения) вернёт исходную строку `"Åspóse.Barcóde©"`.

![Созданный штрих‑код PDF417, сохранённый как PNG](compact-pdf417.png "Созданный штрих‑код PDF417 в C#")

*Изображение выше демонстрирует окончательный результат кода из учебника.*

## Полный, исполняемый пример

Объединив все части, получаем полностью готовую консольную программу, которую можно скопировать, вставить и запустить.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Ожидаемый вывод

Запуск программы выводит:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Файл `CompactPdf417.png` содержит компактный штрих‑код PDF417, который кодирует предоставленную Unicode‑строку. Сканирование изображения стандартным считывателем PDF417 возвращает точный текст.

## Общие варианты и граничные случаи

| Ситуация | Настройка | Причина |
|-----------|------------|--------|
| **Более длинный набор данных** (например, > 150 символов) | Увеличьте `generator.Parameters.Barcode.Pdf417.Columns` до 6‑8 | Большее количество столбцов предотвращает чрезмерную высоту штрих‑кода. |
| **Необходимость прозрачного фона** | Используйте `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Прозрачный PNG лучше интегрируется в наложения пользовательского интерфейса. |
| **Создание JPEG для веба** | Измените формат на `BarCodeImageFormat.Jpeg` и при необходимости задайте `ImageQuality` | JPEG уменьшает размер файла за счёт потери безупречного качества. |
| **Обработка null или пустого ввода** | Защитите ввод перед созданием генератора: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Предотвращает исключения во время выполнения и обеспечивает осмысленные штрих‑коды. |

## Советы для продакшн‑использования

* **Обработка исключений:** Оберните логику генерации в блок `try/catch`, чтобы регистрировать ошибки, такие как недостаток места на диске или неверные параметры.  
* **Производительность:** Переиспользуйте один экземпляр `BarcodeGenerator` при генерации множества штрих‑кодов с одинаковыми настройками; обновляйте только свойство `CodeText` между сохранениями.  
* **Безопасность:** Если кодируемый текст содержит конфиденциальную информацию, рассмотрите возможность её шифрования перед передачей в генератор и расшифровки после сканирования.  

## Заключение

Теперь вы знаете, как **создавать штрих‑код PDF417** в C# с помощью библиотеки Aspose.BarCode, настраивать компактный режим, управлять количеством столбцов и экспортировать результат в PNG‑изображение. Этот учебник охватывает каждый шаг от настройки проекта до обработки граничных случаев, предоставляя готовое решение для приложений, работающих со штрих‑кодами.

Далее изучайте связанные темы, такие как **создание QR‑кодов в C#**, **пакетная генерация штрих‑кодов** и **интеграция сканирования штрих‑кодов в мобильные приложения**. Все они опираются на те же фундаментальные возможности `BarcodeGenerator`, которые вы только что освоили.

Удачной разработки!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в собственных проектах.

- [Как генерировать штрих‑коды PDF417 – компактное кодирование PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Как создать штрих‑код – компактный PDF417 с Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Как генерировать штрих‑код Aztec с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}