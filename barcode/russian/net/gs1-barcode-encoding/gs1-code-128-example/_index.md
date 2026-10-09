---
date: 2026-09-08
description: Узнайте, как создать code 128 barcode и генерировать GS1 barcode в C#
  с Aspose.BarCode для .NET. Пошаговое руководство, требования и настройка без кода.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Пример GS1 Code 128
og_description: Узнайте, как создать code 128 barcode и генерировать GS1 barcode в
  C# с Aspose.BarCode для .NET. Следуйте пошаговому руководству, чтобы быстро генерировать
  и сохранять изображения barcode.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Как создать code 128 barcode с GS1 с помощью Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Как создать code 128 barcode с GS1 с помощью Aspose.BarCode
url: /ru/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код code 128 с GS1, используя Aspose.BarCode

В этом учебнике вы узнаете, как **создать штрих‑код code 128**, соответствующий стандарту GS1, используя библиотеку Aspose.BarCode для .NET. Независимо от того, нужен ли вам штрих‑код для инвентаризации, доставки или точки продаж, это руководство проведёт вас через каждый шаг — от настройки среды разработки до сохранения окончательного изображения — чтобы вы могли начать генерировать надёжные штрих‑коды за считанные минуты.

## Быстрые ответы
- **Какой основной класс используется для генерации штрих‑кода?** `BarcodeGenerator` создает и настраивает изображение штрих‑кода.  
- **Какую символьную схему использует GS1 Code 128?** Она использует тип `EncodeTypes.Code128` с форматированием данных, специфичным для GS1.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; для продакшн‑использования требуется коммерческая лицензия.  
- **Можно ли изменить формат изображения?** Да — сохраняйте как PNG, JPEG, BMP или TIFF, изменив расширение файла.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, и .NET 6+.

## Что такое создание штрих‑кода code 128?
`create code 128 barcode` относится к генерации линейного штрих‑кода, который кодирует буквенно‑цифровые данные с использованием символьной схемы Code 128, широко применяемой в логистике, поскольку поддерживает полный набор ASCII и может включать идентификаторы приложений GS1. Штрих‑код может хранить идентификаторы продуктов, серийные номера и другие пользовательские данные, что делает его подходящим для широкого спектра бизнес‑сценариев.

## Почему стоит использовать Aspose.BarCode для GS1 Code 128?
Aspose.BarCode поддерживает **30+ barcode symbologies** и может отрисовывать изображения до **10,000 × 10,000 px** без потери качества, что делает её подходящей для печати этикеток высокого разрешения. Библиотека также автоматически проверяет структуры данных GS1, снижая риск некорректных штрих‑кодов в производственных линиях. Кроме того, она предлагает обширные параметры настройки размеров, цвета и макета, что помогает соответствовать строгим отраслевым стандартам.

## Предварительные требования
1. **Среда разработки .NET** – Visual Studio 2022, Rider или любая IDE, поддерживающая .NET 6+.  
2. **Aspose.BarCode for .NET** – скачайте его со **страницы загрузки Aspose.BarCode for .NET** по адресу [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) и добавьте NuGet‑пакет `Aspose.BarCode` в ваш проект.  
3. **Базовые знания C#** – вы должны быть уверены в создании консольных или Windows‑приложений.  
4. **Понимание GS1 Code 128** – необязательно, но полезно; GS1 использует идентификаторы приложений (AI), такие как `(01)` для GTIN и `(21)` для серийных номеров.

## Как создать штрих‑код code 128 пошагово

Загрузите библиотеку, настройте тип штрих‑кода, задайте данные GS1, настройте размеры и, наконец, сохраните изображение. Прямой ответ на вопрос «как создать штрих‑код code 128?» таков: **instantiate `BarcodeGenerator` with `EncodeTypes.Code128` and GS1‑formatted data, adjust `XDimension` if needed, then call `Save` with the desired file name and format**. Ниже приведены детали каждого шага.

### Шаг 1: укажите путь к каталогу
Определите папку, в которой будет сохранено сгенерированное изображение. Делая путь настраиваемым, вы делаете код переиспользуемым в разных средах.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Замените `"Your Directory Path"` на абсолютный или относительный путь, в который ваше приложение может записывать данные, например `@"C:\Barcodes"` или `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Шаг 2: создать штрих‑код GS1 Code 128
Создайте генератор штрих‑кода, укажите символьную схему и передайте данные, отформатированные по GS1. Строка данных должна включать идентификаторы приложений, заключённые в скобки.

```csharp
string path = "Your Directory Path";
```

В примере используется GTIN `(01)12345678901231`, серийный номер `(21)ASPOSE` и дополнительный пользовательский AI `(30)9876`. Aspose.BarCode автоматически вставляет требуемый символ FNC1 для соответствия GS1.

### Шаг 3: настроить параметры штрих‑кода
Настройте визуальные параметры, такие как `XDimension` (ширина узкой полосы), чтобы контролировать плотность штрих‑кода. Вы также можете изменить высоту, цвета и отступы.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Установка `XDimension = 2` даёт штрих‑код, который легко сканируется большинством портативных считывателей, при этом размер изображения остаётся умеренным.

### Шаг 4: сохранить изображение штрих‑кода
Сохраните сгенерированный штрих‑код на диск. Вы можете выбрать PNG для безпотерьного качества, JPEG для меньшего размера файлов или TIFF для печатных процессов. Метод `Save` записывает файл изображения в формате, указанном в расширении файла.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Замените `GS1Code128Example.png` на любое допустимое имя файла и расширение, соответствующее желаемому формату вывода.

### Шаг 5: проверить штрих‑код (необязательно)
После сохранения вы можете загрузить изображение обратно в приложение или использовать сканер штрих‑кодов, чтобы убедиться, что закодированные данные совпадают с исходной строкой. Этот шаг полезен во время разработки и автоматизированного тестирования.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Распространённые проблемы и советы по их устранению
- **FNC1 not detected** – Убедитесь, что строка данных начинается с открывающей скобки и содержит действительные GS1 AI; библиотека автоматически вставляет FNC1 только для распознанных шаблонов.  
- **Image not saved** – Проверьте, существует ли целевой каталог и имеет ли приложение права на запись. Используйте `Directory.CreateDirectory(path)`, чтобы создать его «на лету».  
- **Barcode too dense** – Уменьшите `XDimension` или увеличьте высоту изображения, чтобы сканерам было проще считывать узкие полосы.  
- **Unsupported characters** – Code 128 может кодировать только полный набор ASCII; избегайте Unicode‑символов за пределами этого диапазона.

## Часто задаваемые вопросы

**Q: Можно ли генерировать штрих‑коды в веб‑API без установки полной .NET Framework?**  
A: Да, Aspose.BarCode работает с .NET Core и .NET 5/6, поэтому вы можете создать лёгкий REST‑endpoint, который по запросу возвращает изображения штрих‑кодов.

**Q: Поддерживает ли библиотека пакетную генерацию нескольких штрих‑кодов?**  
A: Абсолютно. Пройдитесь по коллекции строк данных, создайте `BarcodeGenerator` для каждой и вызовите `Save` внутри цикла. Библиотека потокобезопасна для параллельной обработки.

**Q: Есть ли способ встроить штрих‑код напрямую в PDF?**  
A: Используйте Aspose.PDF для создания PDF‑документа, затем вызовите `PdfPage.AddImage` с потоком изображения штрих‑кода. Это избавляет от необходимости записывать промежуточные файлы на диск.

**Q: Как убедиться, что штрих‑код соответствует стандартам качества ISO/GS1?**  
A: Установите `BarcodeGenerator.Options.Barcode.XDimension` минимум 0.33 mm и задайте `BarHeight` в соответствии с размером этикетки. Aspose.BarCode проверяет формат AI и бросает исключение при неверных данных.

**Q: Какие варианты лицензирования доступны для продакшн‑использования?**  
A: Aspose предлагает бессрочные, подписные и облачные модели лицензирования. Пробная лицензия подходит для оценки, но платная лицензия убирает водяной знак оценки и открывает все функции.

## Дополнительные ресурсы

- **Документация** – Доступ к полной справке API по адресу [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Download** – Получите последнюю версию библиотеки по ссылке [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Free trial** – Начните 30‑дневный пробный период на сайте [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Purchase** – Приобретите коммерческую лицензию по адресу [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Support** – Присоединяйтесь к форуму сообщества по адресу [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) для получения помощи в решении проблем.

---

**Последнее обновление:** 2026-09-08  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как создать штрих‑код ITF-14 .NET – Полные руководства Aspose.BarCode Tutorials](/barcode/net/)
- [Генерация одноразмерных Databar 2D штрих‑кодов с использованием Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}