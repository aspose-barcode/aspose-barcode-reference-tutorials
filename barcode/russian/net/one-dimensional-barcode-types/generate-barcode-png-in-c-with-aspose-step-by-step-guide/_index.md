---
category: general
date: 2026-11-27
description: Генерируйте PNG‑изображение штрихкода в C# быстро с помощью Aspose.BarCode.
  Узнайте, как создать штрихкод в C#, задать размеры, выбрать столбцы и сохранить
  в формате PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode png
- create barcode image c#
- generate barcode with aspose
language: ru
lastmod: 2026-11-27
og_description: Создайте PNG‑изображение штрих‑кода в C# с помощью Aspose.BarCode.
  Следуйте этому руководству, чтобы создать изображение штрих‑кода в C#, настроить
  размер и сохранить его как файл PNG.
og_image_alt: Screenshot of a generated MicroPdf417 barcode PNG
og_title: Генерация PNG‑штрихкода в C# с Aspose – полный учебник
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  headline: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  name: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '* **Step 1** – Instantiating `BarcodeGenerator` ties the text you want
      to encode to a specific barcode type. If you need a different symbology (e.g.,
      QR, Code128), you only change `EncodeTypes`. * **Step 2** – The X‑dimension
      controls the smallest bar width. Adjusting this value influences both read'
  - name: Expected output
    text: 'Below is a textual representation of the generated PNG (the actual image
      will be visual, not text):'
  - name: Generating other barcode formats
    text: To **generate barcode with Aspose** for a different symbology, replace `EncodeTypes.MicroPdf417`
      with another enum value, such as `EncodeTypes.QR` or `EncodeTypes.Code128`.
      The rest of the code remains identical.
  - name: Changing image format
    text: 'Aspose supports several raster formats (`Png`, `Jpeg`, `Bmp`, `Gif`). To
      save as JPEG, modify the `Save` call:'
  - name: Handling large text payloads
    text: MicroPdf417 has a limited data capacity. If your text exceeds this limit,
      Aspose throws an `ArgumentException`. In such cases, switch to the full `Pdf417`
      symbology, which supports longer strings.
  - name: Running in a web application
    text: 'When generating a barcode image on the fly in ASP.NET Core, you can write
      the PNG directly to the response stream:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Создание PNG‑штрихкода в C# с помощью Aspose – пошаговое руководство
url: /ru/net/one-dimensional-barcode-types/generate-barcode-png-in-c-with-aspose-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация PNG штрих‑кода в C# с Aspose – пошаговое руководство

Если вам нужно **создать PNG штрих‑кода** в .NET‑приложении, это руководство покажет, как сделать это с помощью Aspose.BarCode. Вы узнаете, как **создать код C# для изображения штрих‑кода**, настроить размеры, указать количество столбцов и сохранить результат в файл PNG.

Генерация штрих‑кодов — распространённая потребность для систем учёта, платформ продажи билетов и мобильных приложений. Использование Aspose устраняет необходимость во внешних сервисах или сложных библиотеках обработки изображений. К концу этого руководства у вас будет автономная, исполняемая программа, создающая PNG штрих‑кода MicroPdf417 на диске.

## Предварительные требования

* **.NET 6.0** или более поздней версии (код также работает с .NET Framework 4.7+).  
* Действительная лицензия **Aspose.BarCode for .NET** или временный оценочный ключ.  
* IDE, например **Visual Studio 2022** или **VS Code** с расширением C#.

Дополнительные пакеты NuGet не требуются, кроме `Aspose.BarCode`.

## Шаг 1: Установите пакет NuGet Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю библиотеку Aspose.BarCode в ваш проект, предоставив доступ к классу `BarcodeGenerator`, используемому в течение всего руководства.

## Шаг 2: Настройте простое консольное приложение

Создайте новый консольный проект, если у вас его ещё нет:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Замените содержимое `Program.cs` ниже приведённым скелетом. Скелет включает необходимые директивы `using` и метод `Main`, в котором мы разместим логику генерации штрих‑кода.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation code will be inserted here.
        }
    }
}
```

## Шаг 3: Сгенерировать PNG штрих‑кода с помощью Aspose.BarCode

Ниже представлен полный код, **генерирующий PNG штрих‑кода** с использованием символьного набора MicroPdf417. Каждая строка прокомментирована, чтобы объяснить её назначение, что поможет адаптировать пример к другим типам штрих‑кодов.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for MicroPdf417 with the desired text.
            //    EncodeTypes.MicroPdf417 tells Aspose which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, "Sample text");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            //    A smaller value yields a more compact barcode; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns for the MicroPdf417 barcode.
            //    Valid values are 1‑4. More columns reduce the height but increase width.
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Choose the output path. Ensure the directory exists or Aspose will throw an exception.
            string outputPath = "MicroPdf417.png";

            // 5️⃣ Save the generated barcode as a PNG image.
            //    BarCodeImageFormat.Png is the most widely supported raster format.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG generated at: {outputPath}");
        }
    }
}
```

### Почему каждый шаг важен

* **Шаг 1** – Создание экземпляра `BarcodeGenerator` связывает текст, который вы хотите закодировать, с конкретным типом штрих‑кода. Если нужен другой символьный набор (например, QR, Code128), достаточно изменить `EncodeTypes`.
* **Шаг 2** – Параметр X‑dimension управляет минимальной шириной полосы. Регулировка этого значения влияет как на читаемость, так и на физический размер печатного штрих‑кода.
* **Шаг 3** – MicroPdf417 позволяет сбалансировать высоту и ширину, задавая количество столбцов. Для мобильных экранов часто лучше более широкий, но более короткий штрих‑код.
* **Шаг 5** – Сохранение в PNG сохраняет без потерь качество изображения, что критично для точности сканирования.

## Шаг 4: Запустите программу и проверьте результат

Соберите и запустите проект:

```bash
dotnet run
```

Вы должны увидеть сообщение в консоли:

```
Barcode PNG generated at: MicroPdf417.png
```

Перейдите в папку проекта и откройте `MicroPdf417.png`. На изображении виден чёткий штрих‑код MicroPdf417, кодирующий текст *Sample text*. Большинство сканеров штрих‑кодов и мобильных приложений могут прочитать этот файл без дополнительной настройки.

### Ожидаемый вывод

Ниже представлено текстовое представление сгенерированного PNG (само изображение будет визуальным, а не текстовым):

```
┌─────────────────────────────────────┐
│ █ █ █ █   █ █ █ █   █ █ █ █ █ █ █   │
│ █   █ █ █ █   █ █ █ █ █   █ █ █ █   │
│ ... (barcode pattern)               │
└─────────────────────────────────────┘
```

Если открыть PNG в просмотрщике изображений, вы увидите чёткий штрих‑код с четырьмя столбцами и шириной модуля в два пикселя.

## Шаг 5: Распространённые варианты и граничные случаи

### Генерация других форматов штрих‑кодов

Чтобы **создать штрих‑код с Aspose** для другого символьного набора, замените `EncodeTypes.MicroPdf417` на другое значение перечисления, например `EncodeTypes.QR` или `EncodeTypes.Code128`. Остальная часть кода остаётся неизменной.

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

### Изменение формата изображения

Aspose поддерживает несколько растровых форматов (`Png`, `Jpeg`, `Bmp`, `Gif`). Чтобы сохранить как JPEG, измените вызов `Save`:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

### Обработка больших текстовых нагрузок

MicroPdf417 имеет ограниченную ёмкость данных. Если ваш текст превышает этот лимит, Aspose генерирует `ArgumentException`. В таких случаях переключитесь на полный символьный набор `Pdf417`, который поддерживает более длинные строки.

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, longText);
```

### Запуск в веб‑приложении

При генерации изображения штрих‑кода «на лету» в ASP.NET Core вы можете записать PNG напрямую в поток ответа:

```csharp
byte[] pngBytes = generator.GenerateBarCodeImage(BarCodeImageFormat.Png);
return File(pngBytes, "image/png");
```

## Профессиональные советы для продакшн‑использования

* **Лицензировать заранее** – Использование оценочной версии добавляет водяной знак к изображению. Примените лицензию до первого вызова `Save`, чтобы избежать его.
* **Проверять ввод** – Убедитесь, что передаваемый текст соответствует набору символов выбранного символьного набора; иначе Aspose выбросит исключение.
* **Кешировать сгенерированные изображения** – Если один и тот же штрих‑код запрашивается многократно, сохраняйте PNG на диск или в память, чтобы снизить нагрузку на CPU.
* **Потокобезопасность** – Экземпляры `BarcodeGenerator` не являются потокобезопасными. Создавайте новый генератор для каждого запроса или синхронизируйте доступ.

## Заключение

Теперь вы знаете, как **создавать PNG штрих‑кода** в C# с помощью Aspose.BarCode, начиная с установки пакета и заканчивая настройкой размеров и сохранением изображения. Полный пример демонстрирует стандартный рабочий процесс для **создания изображений штрих‑кодов C#** и может быть расширен на другие типы штрих‑кодов, форматы изображений и сценарии развертывания.  

Далее изучайте связанные темы, такие как **генерация штрих‑кода с Aspose** для PDF‑документов, добавление уровней коррекции ошибок для QR‑кодов или интеграция сканирования штрих‑кодов с помощью Aspose.OCR. Экспериментируйте с различными `EncodeTypes` и параметрами, чтобы найти оптимальную конфигурацию для вашего приложения.

Удачной разработки!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающие освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать набор штрих‑кодов пользовательского размера и сохранить изображение в C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Изображение штрих‑кода PNG в C# — генерация штрих‑кодов, изменение высоты](/barcode/english/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/)
- [Как создать PNG штрих‑кода в C# с использованием Aspose.Barcode](/barcode/english/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}