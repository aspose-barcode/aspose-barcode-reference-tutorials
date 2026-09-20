---
category: general
date: 2026-09-19
description: пример генератора штрихкодов на C#, показывающий, как генерировать штрихкоды
  в C# с использованием Aspose.BarCode для колонных и строковых макетов
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: ru
lastmod: 2026-09-19
og_description: Пример генератора штрихкодов демонстрирует, как генерировать штрихкоды
  в C# с использованием макетов столбцов и строк с помощью Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: пример генератора штрихкодов – создание штрихкодов DataBar Expanded Stacked
  в C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать пример генератора штрихкода на C# с DataBar Expanded Stacked
url: /ru/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# пример генератора штрихкодов – создание DataBar Expanded Stacked штрихкодов в C#

Если вам нужен **пример генератора штрихкодов**, который работает в проекте .NET, это руководство покажет, как именно генерировать штрихкоды C# с помощью библиотеки Aspose.BarCode. Вы увидите, как настроить DataBar Expanded Stacked штрихкод как для колонного, так и для строкового расположения, и получите готовый к запуску код, создающий PNG‑изображения.

В руководстве рассматривается всё: от установки пакета NuGet до сохранения готовых изображений, так что вы сможете скопировать код в своё решение без дополнительного поиска.

## Что вы узнаете

* Как установить и подключить Aspose.BarCode в проект C#.  
* Как создать **пример генератора штрихкодов**, кодирующий длинную строку данных.  
* Как задать 4‑колоночный и 3‑строчный макет для одного и того же типа штрихкода.  
* Как сохранить сгенерированные изображения в виде PNG‑файлов.  

К концу статьи у вас будет два готовых PNG‑файла: `ExpandedStackedCols4.png` (четыре колонки) и `ExpandedStackedRows3.png` (три строки).

## Предпосылки

* .NET 6.0 SDK или новее (код также работает с .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code или любой другой предпочитаемый IDE для C#.  
* Доступ в Интернет для загрузки пакета NuGet **Aspose.BarCode**.  

Дополнительные внешние сервисы не требуются.

## Шаг 1: Установите пакет NuGet Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию Aspose.BarCode в ваш файл проекта. После восстановления пакета вы сможете использовать его пространства имён в файлах C#.

## Шаг 2: Добавьте необходимые директивы using

Создайте новое консольное приложение C# (или добавьте код в существующий проект) и включите следующие инструкции `using` в начале файла:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Эти директивы дают доступ к классу `BarcodeGenerator` и перечислению `EncodeTypes`, используемым в **примере генератора штрихкодов**.

## Шаг 3: Создайте пример генератора штрихкодов с 4‑колоночным макетом

Первая часть примера формирует DataBar Expanded Stacked штрихкод, использующий четырёхколоночную компоновку. Код ниже следует точным шагам оригинального фрагмента, но содержит комментарии, объясняющие необходимость каждой строки.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Почему это работает**

* `EncodeTypes.DatabarExpandedStacked` указывает Aspose.BarCode генерировать символ DataBar Expanded Stacked, подходящий для розничных приложений.  
* Установка `DataBar.Columns` в `4` заставляет генератор разбить символ на четыре вертикальные секции, улучшая читаемость на узких этикетках.  
* `Save` записывает штрихкод на диск; аргумент `BarCodeImageFormat.Png` гарантирует безпотерянное качество изображения.

Выполнение этого блока создаст `ExpandedStackedCols4.png` в рабочем каталоге приложения. Файл содержит высоко‑разрешённый штрихкод, который может сканировать любой стандартный считыватель DataBar.

## Шаг 4: Переинициализируйте генератор для другого макета

Чтобы продемонстрировать строковый макет, нужен новый экземпляр `BarcodeGenerator`. Переинициализация гарантирует, что предыдущая настройка колонок не повлияет на новую конфигурацию.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Шаг 5: Настройте штрихкод для 3‑строчного макета

API DataBar также поддерживает строковую компоновку. Установка свойства `Rows` определяет, сколько горизонтальных секций будет содержать символ.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Почему стоит выбирать строки вместо колонок**

Строки полезны, когда высота этикетки ограничена, а ширина достаточна. Трёхстрочный макет сжимает штрихкод по вертикали, сохраняя необходимый объём данных.

## Полный исходный файл

Ниже представлен полностью автономный `Program.cs`, который можно сразу компилировать и запускать. Он включает примеры как для колонок, так и для строк, поэтому одной запуском вы получите два PNG‑файла.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Ожидаемый вывод

После запуска программы вы увидите два сообщения в консоли, подтверждающие создание файлов:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Оба PNG‑файла отобразят DataBar Expanded Stacked штрихкод, кодирующий строку `"Long data string"`. Сканирование любого из изображений стандартным сканером штрихкодов вернёт исходные данные.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| **Можно ли изменить формат изображения?** | Да. Замените `BarCodeImageFormat.Png` на `Jpeg`, `Bmp` или `Tiff` в зависимости от ваших требований. |
| **Что если строка данных короче?** | Формат DataBar автоматически подстраивает размер символа; менять настройки макета не требуется. |
| **Как задать размер штрихкода (ширина/высота)?** | Используйте `generator.Parameters.Image.Width` и `generator.Parameters.Image.Height` перед вызовом `Save`. |
| **Можно ли добавить читаемую подпись?** | Установите `generator.Parameters.Barcode.CodeText` и включите `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Какие версии .NET поддерживаются?** | Aspose.BarCode поддерживает .NET Standard 2.0, .NET 5/6 и .NET Framework 4.6.1+. |

Учитывая эти варианты, **пример генератора штрихкодов** становится достаточно надёжным для использования в продакшене.

## Профессиональные советы

* **Повторно используйте объект генератора только при неизменном макете.** Создание нового экземпляра для каждого макета, как показано в шагах 4‑5, предотвращает случайное перенесение свойств.  
* **Проверьте сгенерированный штрихкод** с помощью `generator.Validate()`, если необходимо гарантировать соответствие стандартам ISO/GS1.  
* **Пакетная обработка:** Оберните логику колонок и строк в цикл, проходящий по списку конфигураций макетов. Это уменьшит дублирование кода при необходимости множества вариантов.

## Заключение

Этот **пример генератора штрихкодов** демонстрирует, как **генерировать штрихкоды C#**, получая как 4‑колоночный, так и 3‑строчный DataBar Expanded Stacked штрихкод. Теперь у вас есть полностью готовая к запуску программа, понимание ключевых свойств (`Columns`, `Rows`) и практические рекомендации по расширению решения.

Далее изучайте связанные темы, такие как **настройка цветов штрихкода**, **встраивание штрихкодов в PDF‑документы** или **генерация QR‑кодов с Aspose.BarCode**. Каждый из этих вопросов опирается на те же принципы API, рассмотренные здесь.

Не стесняйтесь экспериментировать с разными строками данных, форматами изображений и комбинациями макетов. Приятного кодинга!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Пример генератора штрихкодов в C# – установка колонок, строк и экспорт изображения](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Генерация Databar штрихкода Aspose.BarCode с помощью .NET API – настройка строк и колонок](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Пример генератора штрихкодов в C# – установка ширины и высоты](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}