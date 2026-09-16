---
category: general
date: 2026-07-18
description: Создайте штрих‑код RM4SCC на C# быстро; узнайте, как задать высоту штрих‑кода
  и сгенерировать штрих‑код Planet с пользовательскими размерами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- generate planet barcode
- how to set barcode height
language: ru
lastmod: 2026-07-18
og_description: Создайте штрих‑код RM4SCC на C# и узнайте, как задать высоту штрих‑кода.
  Также посмотрите, как сгенерировать штрих‑код Planet с помощью той же библиотеки.
og_image_alt: Screenshot of a generated RM4SCC barcode with custom height in C#
og_title: Создание штрих‑кода RM4SCC на C# – Быстрая установка пользовательской высоты
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create RM4SCC barcode in C# quickly; learn how to set barcode height
    and also generate Planet barcode with custom dimensions.
  headline: Create RM4SCC Barcode in C# – Full Guide to Set Height
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Создание штрих‑кода RM4SCC в C# – Полное руководство по установке высоты
url: /ru/python-java/general/create-rm4scc-barcode-in-c-full-guide-to-set-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода RM4SCC в C# – Полное руководство по установке высоты

Когда‑нибудь вам нужно было **создать штрих‑код RM4SCC** в приложении .NET, но вы не знали, как управлять его размером? Вы не одиноки. Независимо от того, создаёте ли вы систему рассылки или панель логистики, правильная высота штрих‑кода может стать разницей между успешным сканированием и неудачей.

В этом руководстве мы пройдём весь процесс: от установки библиотеки до **генерации штрих‑кода Planet** в качестве примера рядом, и, наконец, до **того, как установить высоту штрих‑кода** для обоих типов штрих‑кодов. К концу вы получите готовое к запуску консольное приложение, которое выводит PNG‑файлы с точными нужными вам размерами.

---

## Что понадобится

- **.NET 6 SDK** (или любая современная версия .NET) – код работает и на .NET Framework, но .NET 6 — оптимальный вариант.
- **Aspose.BarCode for .NET** пакет NuGet – это библиотека, предоставляющая класс `BarcodeGenerator`.
- Небольшие знания C# – мы постараемся сделать синтаксис дружелюбным для начинающих.
- IDE или текстовый редактор (Visual Studio, VS Code, Rider — выбирайте, что вам нравится).

> **Совет:** Если вы используете CI/CD конвейер, добавьте ссылку на NuGet в ваш `.csproj`, чтобы сборка никогда не забывала о зависимости.

---

## Шаг 1: Настройка проекта

Откройте терминал и создайте новый консольный проект:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Вот и всё — ваш проект теперь ссылается на библиотеку, которая обеспечивает всё, что будет дальше.

### Добавьте директивы using

Откройте `Program.cs` и вставьте следующее в начало:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, for clarity
```

Эти пространства имён дают нам доступ к `BarcodeGenerator` и перечислению форматов изображений, которое мы будем использовать позже.

---

## Шаг 2: Определите вспомогательный метод для сохранения изображений

Чтобы избежать повторения одинаковой логики сохранения, мы обернём её в небольшой метод. Это также демонстрирует **как установить высоту штрих‑кода** позже.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string fileName)
{
    // Ensure the output directory exists
    var dir = System.IO.Path.GetDirectoryName(fileName);
    if (!System.IO.Directory.Exists(dir))
        System.IO.Directory.CreateDirectory(dir);

    // Save as PNG – you can switch to JPEG, BMP, etc.
    generator.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved: {fileName}");
}
```

> **Почему это важно:** Централизация логики сохранения означает, что вам нужно будет менять формат или папку только в одном месте, если требования изменятся.

---

## Шаг 3: Генерация штрих‑кода Planet (часть «генерация штрих‑кода planet»)

Прежде чем перейти к деталям RM4SCC, давайте создадим **штрих‑код Planet**. Это даст вам быструю визуальную проверку того, что библиотека работает.

```csharp
// Create a Planet barcode with default height
var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // X‑dimension controls the narrow bar width; 4 px is a good default
    XDimension = { Pixels = 4 }
};
SaveBarcode(planetDefault, "output/PlanetDefault.png");

// Create a Planet barcode with an explicit 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    XDimension = { Pixels = 4 },
    BarHeight = { Pixels = 100 } // <-- how to set barcode height
};
SaveBarcode(planetFixed, "output/PlanetHeight100.png");
```

**Ожидаемый результат:** В папке `output` появятся два PNG‑файла — один с автоматически рассчитанной высотой библиотекой, другой ровно 100 px в высоту.

---

## Шаг 4: Создание штрих‑кода RM4SCC — основная цель

А теперь звезда шоу: **создать штрих‑код RM4SCC**. RM4SCC — это Royal Mail 4‑State Code, широко используемый в почтовой системе Великобритании.

```csharp
// RM4SCC with default (auto) height
var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    XDimension = { Pixels = 4 }
};
SaveBarcode(rm4sccDefault, "output/RM4SCCDefault.png");

// RM4SCC with an explicit 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    XDimension = { Pixels = 4 },
    BarHeight = { Pixels = 100 } // <-- how to set barcode height
};
SaveBarcode(rm4sccFixed, "output/RM4SCCHeight100.png");
```

**Что вы увидите:**  
- `RM4SCCDefault.png` — библиотека выбирает удобную высоту на основе X‑dimension.  
- `RM4SCCHeight100.png` — чёткий штрих‑код высотой 100 пикселей, готовый к печати на конвертах.

> **Зачем устанавливать высоту?** Некоторые принтеры этикеток требуют минимальную высоту полосы для надёжного сканирования. Фиксируя высоту, вы гарантируете соответствие требованиям на разных устройствах.

---

## Шаг 5: Понимание настроек высоты (Ответ на вопрос «как установить высоту штрих‑кода»)

И примеры Planet, и RM4SCC используют одно и то же свойство:

```csharp
generator.BarHeight.Pixels = <desiredHeight>;
```

- **`BarHeight`** — это объект `BarHeight`, который объединяет несколько единиц измерения (пиксели, миллиметры, дюймы).  
- **`.Pixels`** — самая простая единица для вывода на экран, но вы также можете использовать `.Millimeters` или `.Inches`, если ориентируетесь на печатные носители.

### Пограничные случаи и советы

| Ситуация | Рекомендуемый подход |
|-----------|----------------------|
| **Очень маленькое X‑dimension (например, 1 px)** | Увеличьте `BarHeight`, чтобы штрих‑код оставался читаемым. |
| **Печать на высоко‑разрешающих принтерах этикеток** | Используйте `.Millimeters` для независимого от устройства размера. |
| **Смешанные типы штрих‑кодов в одном изображении** | Устанавливайте `BarHeight` *после* `XDimension` для каждого генератора, чтобы избежать случайного наследования. |
| **Динамические данные (например, коды, вводимые пользователем)** | Оборачивайте создание генератора в метод, принимающий параметры `code` и `height`. |

---

## Шаг 6: Полный рабочий пример

Ниже представлен единый, автономный пример программы, который вы можете скопировать и вставить в `Program.cs`. Он включает всё — от настройки проекта до сохранения изображений.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

class Program
{
    static void Main()
    {
        string outputDir = "output/";

        // Helper ensures folder exists and logs the save
        void Save(BarcodeGenerator gen, string file) => SaveBarcode(gen, file);

        // ---------- Planet barcode ----------
        var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            XDimension = { Pixels = 4 }
        };
        Save(planetDefault, $"{outputDir}PlanetDefault.png");

        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 } // how to set barcode height
        };
        Save(planetFixed, $"{outputDir}PlanetHeight100.png");

        // ---------- RM4SCC barcode ----------
        var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            XDimension = { Pixels = 4 }
        };
        Save(rm4sccDefault, $"{outputDir}RM4SCCDefault.png");

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 } // how to set barcode height
        };
        Save(rm4sccFixed, $"{outputDir}RM4SCCHeight100.png");

        Console.WriteLine("All barcodes generated!");
    }

    static void SaveBarcode(BarcodeGenerator generator, string fileName)
    {
        var dir = System.IO.Path.GetDirectoryName(fileName);
        if (!System.IO.Directory.Exists(dir))
            System.IO.Directory.CreateDirectory(dir);

        generator.Save(fileName, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved: {fileName}");
    }
}
```

Запустите его с помощью:

```bash
dotnet run
```

Вы должны увидеть вывод в консоли, подтверждающий сохранение каждого файла, а папка `output` будет содержать четыре PNG‑файла с именами, указанными выше.

---

## Заключение

Теперь вы знаете **как создать штрих‑код RM4SCC** в C# и управлять его размерами с помощью всего лишь нескольких назначений свойств. Мы также рассмотрели **генерацию штрих‑кода planet** как быструю проверку, и изучили нюансы **установки высоты штрих‑кода** для различных сценариев печати.

Следующие шаги? Попробуйте заменить перечисление `EncodeTypes` на другие символьные наборы (Code128, QR, DataMatrix) и поэкспериментировать с `BarHeight` в миллиметрах для высоко‑разрешающих принтеров. Если нужно встроить штрих‑код в PDF, комбинируйте Aspose.BarCode с Aspose.PDF — ещё один мощный набор.

Есть вопросы или хотите поделиться своими настройками? Оставьте комментарий ниже, и счастливого кодинга!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полные рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать Aztec штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Как создать тихую зону штрих‑кода для ITF-14 с помощью Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Как создать тихую зону штрих‑кода для Code 16K с использованием Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}