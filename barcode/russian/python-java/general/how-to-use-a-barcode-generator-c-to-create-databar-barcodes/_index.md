---
category: general
date: 2026-09-07
description: Учебник по генератору штрихкодов на C#, показывающий, как создавать PNG‑файлы
  штрихкодов и генерировать штрихкоды DataBar с настраиваемыми строками и столбцами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: ru
lastmod: 2026-09-07
og_description: 'генератор штрихкодов C#: научитесь создавать PNG‑файлы штрихкодов
  и генерировать штрихкоды DataBar с пользовательскими строками и столбцами всего
  за несколько минут'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: Генератор штрихкодов C# – создание штрихкодов DataBar и PNG‑изображений
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Как использовать генератор штрихкодов C# для создания штрихкодов DataBar
url: /ru/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать генератор штрих‑кодов C# для создания штрих‑кодов DataBar

Если вам нужен **barcode generator C#** для создания штрих‑кодов высокого качества, это руководство покажет, как **generate barcode PNG** файлы и **create DataBar barcodes** с пользовательскими строками и столбцами. Независимо от того, разрабатываете ли вы систему учёта розничных товаров или платформу для билетов, приведённые ниже шаги позволяют создать штрих‑код DataBar Expanded Stacked в одном самостоятельном примере.

В этом руководстве вы узнаете:

* Как создать экземпляр `BarcodeGenerator` для символьной системы DataBar Expanded Stacked.  
* Как настроить параметры столбцов и строк в соответствии со спецификациями ISO / GS1.  
* Как сохранить результат в виде PNG‑изображения, которое можно внедрить в веб‑страницы или распечатать на этикетках.  

Внешние сервисы не требуются — только библиотека Aspose.BarCode for .NET (или любая совместимая библиотека, использующая тот же API). Код работает на .NET 6+ и совместим с Visual Studio, Rider или любой другой IDE, поддерживающей C#.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6 SDK или более поздняя версия, установленная.  
* Ссылка на пакет NuGet `Aspose.BarCode` (или эквивалентную библиотеку, предоставляющую `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`).  
* Базовое знакомство с синтаксисом C# и структурой проекта.  

Вы можете добавить пакет через командную строку:

```bash
dotnet add package Aspose.BarCode
```

## Шаг 1: Инициализация генератора штрих‑кодов C# для DataBar Expanded Stacked

Первый шаг — создать экземпляр `BarcodeGenerator`, нацеленный на символьную систему **DataBar Expanded Stacked**. Этот объект содержит все параметры рендеринга, включая текст для кодирования.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Почему это важно:** Значение перечисления `EncodeTypes.DatabarExpandedStacked` сообщает библиотеке, какой стандарт штрих‑кода применять. Использование правильного перечисления гарантирует, что сгенерированное изображение соответствует спецификациям GS1 DataBar.

## Шаг 2: Настройка количества столбцов (используются строки по умолчанию)

DataBar Expanded Stacked может быть разделён на несколько столбцов. Регулировка количества столбцов меняет визуальную плотность и может помочь разместить более длинные строки данных в ограниченном пространстве.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Совет:** Количество столбцов по умолчанию равно 1. Установка значения 4 создаёт четыре сложенных столбца, что идеально для более длинных числовых строк, при этом высота штрих‑кода остаётся управляемой.

## Шаг 3: Генерация PNG‑штрих‑кода с применённой настройкой столбцов

Теперь сохраните штрих‑код как PNG‑изображение. PNG сохраняет чёткие границы, необходимые сканерам, и хорошо подходит как для веб‑, так и для печатных носителей.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Файл `DatabarCols4.png` содержит **barcode PNG**, который можно напрямую внедрить в HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Шаг 4: Создание отдельного экземпляра генератора для настройки строк

Если необходимо управлять количеством строк вместо столбцов, создайте новый экземпляр `BarcodeGenerator`. Повторное использование того же объекта после изменения измерения может привести к неожиданным артефактам макета, поэтому создание нового объекта — самый надёжный подход.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Шаг 5: Установка количества строк (используются столбцы по умолчанию)

Строки влияют на вертикальное расположение модулей штрих‑кода. Увеличение количества строк делает штрих‑код выше, что может потребоваться для определённых размеров этикеток.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Почему строки vs. столбцы:** Столбцы делят штрих‑код по горизонтали, а строки — по вертикали. Выберите ориентацию, которая лучше всего подходит для макета вашей этикетки.

## Шаг 6: Генерация PNG‑штрих‑кода с применённой настройкой строк

Наконец, сохраните штрих‑код с настроенными строками в виде PNG‑файла.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два отдельных PNG‑файла:

* `DatabarCols4.png` — 4 столбца, 1 строка.  
* `DatabarRows3.png` — 1 столбец, 3 строки.

Оба изображения готовы к немедленному использованию в приложениях, отчетах или печатных этикетках.

## Как генерировать PNG‑файлы штрих‑кодов в C# с пользовательскими размерами

Показанный выше шаблон можно переиспользовать для любого варианта DataBar или других символьных систем, поддерживаемых библиотекой. Ниже представлена компактная заготовка, которую можно скопировать и вставить в вспомогательный класс:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Вызовите метод так:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Особые случаи, которые следует учитывать**

* **Длина данных** – DataBar Expanded Stacked может кодировать до 74 числовых символов. Превышение этого лимита вызывает исключение. Проверьте длину входных данных перед вызовом генератора.  
* **Недопустимые размеры** – Библиотека ограничивает количество столбцов 1‑4 и строк 1‑3 для этой символьной системы. Значения вне этих диапазонов будут игнорированы или вызовут ошибку.  
* **Разрешение изображения** – Если требуется более высокое разрешение для печати, установите `generator.Parameters.ImageResolution` перед сохранением.

## Ожидаемый результат

При открытии `DatabarCols4.png` или `DatabarRows3.png` вы должны увидеть чёткий, высококонтрастный штрих‑код DataBar. Сканирование изображения сканером, совместимым с GS1, возвращает исходный текст `"Databar Expanded Stacked long"`.

![Пример штрих‑кода DataBar Expanded Stacked, сохранённого как PNG с помощью генератора штрих‑кодов C#](image.png)

*Alt text: Пример штрих‑кода DataBar Expanded Stacked, сохранённого как PNG с помощью генератора штрих‑кодов C#*

## Заключение

В этом руководстве показано, как **barcode generator C#** можно использовать для **create DataBar barcodes** и **generate barcode PNG** файлов с пользовательскими настройками строк и столбцов. Следуя шести шагам — инициализации генератора, настройке столбцов или строк и сохранению в PNG — вы получаете готовые к использованию изображения, подходящие для систем учёта, билетов или любых сценариев, требующих надёжного отображения штрих‑кодов.

Далее вы можете изучить:

* Добавление цвета или фоновых изображений в PNG (по‑прежнему совместимо с большинством сканеров).  
* Использование других символьных систем, таких как QR, Code 128 или PDF417, через тот же API `BarcodeGenerator`.  
* Встраивание сгенерированного PNG непосредственно в представления ASP.NET Core MVC или компоненты Blazor.

Не стесняйтесь экспериментировать с различными строками данных, размерами и форматами изображений (например, JPEG, BMP). Тот же шаблон применим, делая **barcode generator C#** универсальным инструментом в наборе любого .NET‑разработчика. Приятного кодирования!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, основанные на техниках, продемонстрированных в этом руководстве. Каждый ресурс содержит полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Создать штрих‑код C# – Создать DataBar штрих‑код](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Пример Barcode Generator – Создать изображение DataBar в C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Пример Barcode Generator в C# – Установить столбцы, строки и экспортировать изображение](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}