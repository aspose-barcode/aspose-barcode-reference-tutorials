---
category: general
date: 2026-08-22
description: Создайте штрих‑код FCC 11 на C# с помощью Aspose.BarCode. Изучите пошаговый
  код, настройте размеры и сгенерируйте PNG‑изображения для Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: ru
lastmod: 2026-08-22
og_description: Создайте штрих‑код FCC 11 на C# с помощью Aspose.BarCode. Следуйте
  этому краткому руководству, чтобы генерировать PNG‑штрихкоды для Australia Post,
  включая варианты FCC 59 и FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Создание штрих‑кода FCC 11 в C# – полное руководство Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Как создать штрих‑код FCC 11 в C# с помощью Aspose.BarCode
url: /ru/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрихкод FCC 11 в C# с Aspose.BarCode

Если вам нужно **создать штрихкод FCC 11** в .NET‑приложении, это руководство покажет точный код, который требуется. Вы увидите, как настроить размеры штрихкода, выбрать правильную таблицу кодирования и сохранить результат в виде PNG‑файла.

Генерация штрихкодов Australia Post — частая потребность в логистике, почтовых системах и учёте запасов. Этот учебник охватывает формат FCC 11 и также демонстрирует, как создавать штрихкоды FCC 59 и FCC 62 с различными таблицами кодирования, чтобы вы могли переиспользовать тот же шаблон для других почтовых служб.

## Что вам понадобится

Прежде чем начать, убедитесь, что у вас есть:

* .NET 6.0 SDK или более поздняя версия, установленная  
* Visual Studio 2022 (или любой IDE, поддерживающий C#)  
* Действующая лицензия **Aspose.BarCode for .NET** – для оценки подходит community edition  
* Права записи в папку, куда будут сохраняться PNG‑файлы  

Эти предварительные условия гарантируют, что код скомпилируется и выполнится без дополнительной настройки.

## Шаг 1: Установите NuGet‑пакет Aspose.BarCode

Откройте терминал в папке проекта и выполните:

```bash
dotnet add package Aspose.BarCode
```

Эта команда добавит последнюю стабильную версию библиотеки в ваш файл проекта. Пакет содержит класс `BarcodeGenerator`, используемый в этом руководстве.

## Шаг 2: Определите папку вывода

Создайте папку, в которой будут храниться сгенерированные изображения. Путь может быть абсолютным или относительным к исполняемому файлу.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` гарантирует, что папка существует, предотвращая ошибки выполнения при записи файла методом `Save`.

## Шаг 3: Сгенерируйте штрихкод FCC 11

Формат FCC 11 является кодировкой по умолчанию для почтовых штрихкодов Australia Post. Следующий код создаёт штрихкод, кодирующий числовую строку `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Почему это работает:**  
* `EncodeTypes.AustraliaPost` указывает библиотеке применять правила кодирования Australia Post.  
* Строка данных `1101234567` соответствует спецификации FCC 11: первые две цифры (`11`) определяют формат, далее следует 7‑значный клиентский референс.  
* `XDimension` и `BarHeight` контролируют размер печатаемого штрихкода, что важно для читаемости сканером.  

После запуска программы вы найдёте файл `PostalAustraliaPostFCC11.png` в папке `Barcodes`. Изображение выглядит так:

![создать пример штрихкода fcc 11](https://example.com/fcc11.png "Штрихкод FCC 11, сгенерированный Aspose.BarCode")

## Шаг 4: Создайте дополнительные штрихкоды Australia Post (по желанию)

Хотя основной целью является **создание штрихкода FCC 11**, часто требуется генерировать штрихкоды FCC 59 или FCC 62 для разных классов почты. Ниже приведён код, который переиспользует тот же экземпляр `BarcodeGenerator`, меняя только строку данных и необязательную таблицу кодирования.

### 4.1 FCC 59 с кодированием N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 с кодированием N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 с кодированием C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 с другим кодированием

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Все четыре изображения сохраняются рядом в одной папке, что упрощает визуальное сравнение.

## Шаг 5: Понимание таблиц кодирования

Australia Post определяет три таблицы кодирования:

* **N‑Table** – интерпретирует только числовую клиентскую информацию. Используйте её, когда полезная нагрузка содержит только цифры.  
* **C‑Table** – поддерживает буквенно‑цифровые символы, полезна для референс‑номеров, включающих буквы.  
* **Other** – резервный вариант для пользовательских или расширенных форматов данных.

Выбор правильной таблицы гарантирует, что сканер штрихкода декодирует информацию точно так, как задумано. Если не указать свойство `AustralianPostEncodingTable`, библиотека по умолчанию использует N‑Table, что может обрезать небуквенно‑цифровые символы.

## Советы, граничные случаи и распространённые подводные камни

| Ситуация | Рекомендуемый подход |
|-----------|----------------------|
| Длина строки данных короче требуемой | Дополните числовую часть ведущими нулями, чтобы соответствовать спецификации FCC. |
| Штрихкод выглядит размытым при печати | Увеличьте `XDimension` до 5 или 6 пикселей и проверьте настройки DPI принтера. |
| Сканер возвращает «недопустимый формат» | Убедитесь, что выбранная таблица кодирования (N‑Table, C‑Table, Other) соответствует полезной нагрузке. |
| Запуск на Linux без GUI | Убедитесь, что подключён пакет `System.Drawing.Common`, либо используйте метод `Save` с `BarCodeImageFormat.Png`, который не требует контекста отображения. |
| Требуется другой формат изображения | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Tiff` по необходимости. |

Эти практические рекомендации основаны на реальных внедрениях решений для почтовых штрихкодов.

## Полный исполняемый пример

Ниже представлена автономная программа, которую можно скопировать в новый консольный проект (`dotnet new console`) и выполнить без изменений.



## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как генерировать штрихкод java – штрихкод Australia Post с Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Создание одноразмерного Databar GS1 Encoding с Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Как создать тихую зону штрихкода .NET для Code 16K с помощью Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}