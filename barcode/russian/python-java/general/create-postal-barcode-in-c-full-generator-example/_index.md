---
category: general
date: 2026-07-15
description: Быстро создайте почтовый штрих‑код на C#. Этот пример генератора штрих‑кодов
  показывает, как экспортировать штрих‑код в формате PNG для штрих‑кодов Planet и
  RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: ru
lastmod: 2026-07-15
og_description: Создайте почтовый штрих‑код на C# с помощью пошагового руководства.
  Узнайте пример генератора штрих‑кода, позволяющий экспортировать изображение штрих‑кода
  в формате PNG.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Создание почтового штрихкода в C# – Полное руководство по генератору
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Создание почтового штрихкода в C# – Полный пример генератора
url: /ru/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание почтового штрихкода в C# – Полный пример генератора

Когда‑то задавались вопросом, как **создать почтовый штрихкод** в проекте .NET без бесконечного поиска в документации? Вы не одиноки. Будь то система печати почтовых ярлыков или автоматизация массовой отправки, генерация чистого PNG‑изображения штрихкода — необходимый навык. В этом руководстве мы пройдем полный **пример генератора штрихкода**, показывающий, как **экспортировать изображение штрихкода** в **формате PNG**.

Мы охватим всё: от настройки папки вывода до изменения ширины модуля и высоты полос для стандартов Planet и RM4SCC. К концу вы получите готовое консольное приложение, которое создаст четыре PNG‑файла — два с автоматической высотой и два с фиксированной высотой 100 px. Никакого лишнего, только практическое решение, которое можно скопировать и вставить.

## Предварительные требования

Прежде чем приступать, убедитесь, что у вас есть:

- .NET 6 SDK или новее (код работает с .NET Core и .NET Framework)
- IDE или редактор, с которым вам удобно (Visual Studio, VS Code, Rider…)
- NuGet‑пакет Aspose.BarCode for .NET (устанавливается командой `dotnet add package Aspose.BarCode`)

И всё — никаких дополнительных сервисов, никаких веб‑API. Только локальный проект C#.

## Создание почтового штрихкода – пошагово

Ниже процесс разбит на пять чётких шагов. Каждый шаг имеет описательный заголовок **H2**, содержащий основной или вторичный ключевой запрос, чтобы вы быстро нашли нужное.

### Шаг 1: Подготовьте каталог вывода

Прежде всего нам нужна папка, где будут храниться сгенерированные PNG‑файлы. Жёстко заданный путь подходит для демонстрации, но в продакшене его обычно берут из конфигурации.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Совет:** Использование `Path.Combine` делает код независимым от ОС, а `Directory.CreateDirectory` безопасно вызывается даже если папка уже существует.

### Шаг 2: Сгенерировать штрихкод Planet с автоматической высотой

Теперь переходим к сути **как сгенерировать штрихкод planet**. Мы создаём экземпляр `BarcodeGenerator`, задаём ширину модуля (X‑dimension) и позволяем библиотеке определить высоту полос.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Перечисление `EncodeTypes.Planet` сообщает Aspose, что нам нужен символьный набор Planet, который широко используется почтовыми службами многих стран. Поскольку мы не задавали `BarHeight`, генератор выбирает разумное значение по умолчанию, сохраняющее читаемость штрихкода.

### Шаг 3: Сгенерировать штрихкод RM4SCC с автоматической высотой

RM4SCC — канадский формат почтового штрихкода. Код почти идентичен примеру с Planet, демонстрируя шаблон **пример генератора штрихкода**, который можно переиспользовать для любой поддерживаемой символьной системы.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Снова полагаемся на автоматическую высоту, что идеально для быстрых прототипов или когда масштабирование выполняет принтер.

### Шаг 4: Сгенерировать штрихкод Planet с фиксированной высотой (100 px)

Иногда система рассылки требует строго заданную высоту полос — возможно, принтер ожидает ровно 100 px. Вот как **экспортировать изображение штрихкода** с принудительно установленной высотой.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Установка `BarHeight.Pixels` переопределяет автоматический расчёт. Остальные параметры остаются прежними, обеспечивая визуальную согласованность между изображениями с автоматической и фиксированной высотой.

### Шаг 5: Сгенерировать штрихкод RM4SCC с фиксированной высотой (100 px)

Повторяем подход фиксированной высоты для RM4SCC. Это демонстрирует гибкость **пример генератора штрихкода**: можно комбинировать автоматические и ручные настройки для каждой символьной системы.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Полный листинг исходного кода

Объединив всё вместе, получаем полностью рабочую программу. Скопируйте блок ниже в новый консольный проект и нажмите **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

Запуск этой программы создаёт следующие файлы (все в **формате PNG штрихкода**):

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Каждое изображение — чёткое чёрно‑белое представление, готовое к печати или дальнейшей обработке.

## Почему такой подход работает

- **Последовательность:** Фиксируя `XDimension.Pixels` в 4 для всех штрихкодов, вы гарантируете одинаковую ширину модуля, что критично для сканеров, ожидающих определённый размер точки.
- **Гибкость:** Одна и та же кодовая база позволяет переключаться между автоматической и фиксированной высотой без переписывания логики генератора — идеально для решений, работающих с несколькими перевозчиками.
- **Производительность:** Генерация PNG — лёгкая операция; библиотека Aspose сразу записывает изображение на диск, избегая лишних расходов памяти.
- **Переносимость:** Вызовы `Path.Combine` и `Directory.CreateDirectory` делают код кроссплатформенным, так что один и тот же источник работает в Windows, Linux и macOS.

## Распространённые ошибки и как их избежать

| Проблема | Почему возникает | Решение |
|----------|------------------|---------|
| Штрихкод выглядит размытым | Слишком маленькая X‑dimension (например, 1 px) | Увеличьте `XDimension.Pixels` минимум до 3‑4 для почтовых штрихкодов |
| Сканер отклоняет изображение | Высота полос слишком мала или велика для принтера | Используйте `BarHeight.Pixels`, подбирая значение под спецификации принтера |
| PNG‑файл повреждён | Не закрыт поток (редко с Aspose) | Позвольте методу `Save` управлять освобождением; избегайте ручного управления потоком, если это не необходимо |
| Папка вывода не найдена | Жёстко заданный путь указывает на несуществующий каталог | Всегда вызывайте `Directory.CreateDirectory` перед сохранением |

## Расширение примера

Теперь, когда вы освоили основы **создания почтового штрихкода**, можно попробовать:

- **Добавить читаемый человеком текст** под штрихкодом (свойство `DisplayText`)
- **Изменить цвета** (`ForeColor`, `BackColor`) для брендинга
- **Пакетная обработка** списка почтовых кодов из CSV (цикл над генератором)
- **Экспорт в другие форматы**, такие как SVG или PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Каждое из этих расширений следует тому же шаблону, продемонстрированному в этом **пример генератора штрихкода**, так что вы можете экспериментировать без начала с нуля.

## Заключение

Вы


## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, развивая техники, продемонстрированные в этом пособии. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Создание изображения штрихкода C# – пример GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Как создать расширенный codetext для dotcode с Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Как создать Aztec‑штрихкод с коррекцией ошибок в .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}