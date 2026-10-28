---
category: general
date: 2026-10-28
description: Создайте штрих‑код PDF417 на C# и экспортируйте его в виде PNG‑изображения.
  Узнайте, как настроить макет, задать столбцы и строки и сохранить файл.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: ru
lastmod: 2026-10-28
og_description: Создайте штрих‑код PDF417 на C# и сохраните его в виде PNG‑изображения.
  Следуйте этому полному руководству, чтобы настроить макет, задать количество столбцов
  и строк и получить файл штрих‑кода высокого качества.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Создание штрих‑кода PDF417 в формате PNG – учебник C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Создание штрих‑кода PDF417 в формате PNG на C# – пошаговое руководство
url: /ru/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих‑кода PDF417 в формате PNG на C# – пошаговое руководство

Если вам нужно **создать штрих‑код PDF417** в приложении .NET, это руководство покажет, как именно создать штрих‑код и сохранить его как PNG‑изображение. Вы узнаете, как настроить макет штрих‑кода, задать количество столбцов и строк, а также получить файл, который можно использовать в учёте, билетных системах или мобильных сканерах.

В этом учебнике рассматривается всё: от установки необходимой библиотеки до обработки исключительных ситуаций, таких как неверные значения макета. Никакой внешней документации не требуется — просто скопируйте код, запустите его, и у вас будет готовое изображение штрих‑кода.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия  
* Среда разработки C# (Visual Studio, VS Code или Rider)  
* Доступ в Интернет для загрузки пакета NuGet **Aspose.BarCode for .NET** (библиотека, используемая в примерах)  

Эти требования гарантируют, что код будет компилироваться и работать без дополнительной настройки.

## Шаг 1: Установите библиотеку для штрих‑кодов

Самый простой способ получить возможность **генерировать штрих‑коды PNG** — использовать официальный пакет Aspose.BarCode. Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит библиотеку и её зависимости в ваш файл проекта. После успешной установки вы сможете ссылаться на классы в своих C#‑файлах.

## Шаг 2: Создайте генератор штрих‑кода PDF417

Создание объекта штрих‑кода — фундамент процесса. Ниже приведён фрагмент, который создаёт генератор, кодирующий текст `"Sample"` с помощью символьного набора PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Почему это важно* — Класс `BarcodeGenerator` инкапсулирует все настройки, необходимые для рендеринга. Указывая `EncodeTypes.Pdf417`, вы сообщаете библиотеке, что нужно создать **штрих‑код PDF417**, который представляет собой многослойный линейный код, идеальный для хранения больших объёмов данных.

## Шаг 3: Как задать столбцы и строки PDF417

Штрих‑код PDF417 можно настроить, изменяя его матрицу. Два самых часто используемых параметра — **columns** (горизонтальные модули) и **rows** (вертикальные модули). Управление этими значениями влияет на размер и читаемость штрих‑кода.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Как настроить штрих‑код PDF417 под конкретные размеры

* Используйте значения в пределах документированных диапазонов; числа вне диапазона вызывают исключение.  
* Большее количество столбцов сжимает штрих‑код по горизонтали, а увеличение количества строк увеличивает высоту.  
* Подгоняйте макет под целевую поверхность печати или расстояние сканирования.

Если нужен иной профиль, измените числа соответственно. Библиотека автоматически пересчитает размер модуля, чтобы штрих‑код оставался сканируемым.

## Шаг 4: Как сгенерировать PNG‑штрих‑код

Сохранение штрих‑кода в файл PNG — однострочная операция, как только генератор полностью настроен. PNG обеспечивает безпотерьное сжатие, что делает его идеальным для чётких изображений штрих‑кодов.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Почему PNG* — Перечисление `BarCodeImageFormat.Png` указывает библиотеке рендерить штрих‑код в формате PNG. Этот формат сохраняет резкие границы, что критично для сканеров, полагающихся на высококонтрастные края.

### Ожидаемый результат

Запуск программы создаёт файл **CustomLayout.png** в рабочем каталоге приложения. При открытии файла вы увидите прямоугольный штрих‑код PDF417 с четырьмя столбцами и девятью строками, кодирующий строку `"Sample"`.

![Создать штрих‑код PDF417 в формате PNG](https://example.com/images/pdf417-custom.png "Создать штрих‑код PDF417 в формате PNG")

*Текст альтернативного изображения*: **Создать штрих‑код PDF417 в формате PNG** — изображение штрих‑кода, полученное с помощью кода из учебника.

## Шаг 5: Проверка штрих‑кода и устранение распространённых проблем

После генерации изображения следует убедиться, что сканер или средство проверки могут его прочитать. Ниже несколько быстрых проверок:

| Проблема | Причина | Решение |
|----------|----------|----------|
| Штрих‑код размытый | Изображение было изменено в размере после генерации | Сохраняйте оригинальный размер PNG; избегайте масштабирования в UI‑элементах |
| Сканер сообщает «недопустимые данные» | Столбцы/строки вне диапазона или слишком длинный текст для выбранного макета | Уменьшите объём кодируемого текста или увеличьте количество строк/столбцов |
| PNG‑файл пустой | Путь в `generator.Save` указывает на несуществующий каталог | Убедитесь, что каталог существует, либо используйте абсолютный путь |

**Совет профессионала:** Когда нужен прозрачный фон (например, наложение штрих‑кода на элемент интерфейса), установите `generator.Parameters.Image.TransparentBackground = true;` перед вызовом `Save`.

## Полный рабочий пример

Ниже представлена полная программа, которую можно скопировать, вставить и запустить без изменений (за исключением пути вывода, если требуется).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Запуск программы выводит сообщение‑подтверждение и создаёт `CustomLayout.png` в той же папке, где находится исполняемый файл.

## Заключение

Теперь вы знаете, как **генерировать штрих‑код PDF417** на C#, настраивать его макет с конкретными столбцами и строками и экспортировать результат в виде **изображения PNG**. Мы рассмотрели установку библиотеки Aspose.BarCode, инициализацию генератора, применение пользовательских размеров, сохранение файла и проверку результата.

Дальше вы можете изучать дополнительные параметры, такие как уровень коррекции ошибок, отступы штрих‑кода или встраивание изображения непосредственно в PDF‑отчёт. Все эти темы опираются на базовый шаблон, продемонстрированный в этом руководстве, так что вы готовы адаптировать решение под любые сценарии генерации штрих‑кодов в .NET.

---


## Что изучать дальше?


Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}