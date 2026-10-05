---
date: 2026-08-17
description: Узнайте, как создать штрих‑код DataMatrix с macro characters с помощью
  Aspose.BarCode для .NET и откройте, как использовать DataMatrix в ваших приложениях.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Конфигурация DataMatrix Macro
og_description: Узнайте, как создать штрих‑код DataMatrix с macro characters с помощью
  Aspose.BarCode для .NET. Это руководство предоставляет пошаговый код, варианты настройки
  и советы по проверке для надёжного создания штрих‑кодов.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Создайте штрих‑код DataMatrix с macro characters с помощью Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Как создать штрих‑код DataMatrix с macro characters в .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код DataMatrix с макросимволами в .NET

## Введение

Создание **штрих‑кода DataMatrix**, содержащего макросимволы, позволяет упаковать дополнительную справочную информацию в крошечный квадратный символ. В этом руководстве вы узнаете, как **создать штрих‑код DataMatrix** с макросимволами, используя Aspose.BarCode для .NET, настроить размер и уровень коррекции ошибок и мгновенно проверить результат. К концу вы будете готовы внедрять штрих‑коды с поддержкой макросов в этикетки продуктов, документы или медицинские устройства.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.BarCode for .NET  
- **Могу ли я создать штрих‑код DataMatrix с макросимволами?** Да – установите свойство `MacroCharacters`.  
- **Нужна ли лицензия для продакшна?** Для использования в продакшн‑режиме требуется действующая лицензия Aspose.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Доступна ли бесплатная пробная версия?** Абсолютно – скачайте её с официального сайта Aspose.

## Требования

Прежде чем погрузиться в настройку макросимволов, убедитесь, что у вас есть следующее:

1. **Visual Studio** – любой современный выпуск подойдет.  
2. **Aspose.BarCode for .NET** – скачайте её по [the download link](https://releases.aspose.com/barcode/net/).  
3. **Базовые знания .NET** – знакомство с C# и экосистемой .NET.

## Импорт пространств имён

Мы начинаем с подключения пространств имён, необходимых для генерации и распознавания штрих‑кодов.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Что такое «генерация штрих‑кода DataMatrix» с макросимволами?

`MacroCharacters` позволяет штрих‑кодам DataMatrix включать макросимволы, ссылающиеся на дополнительные данные. Используя макросимволы, такие как Macro05 или Macro06, один штрих‑код может указывать на более большой набор данных или последовательность связанных штрих‑кодов, что ценно в логистике, производстве и отслеживании документов, где требуется компактное кодирование связанной информации.

## Почему использовать Aspose.BarCode для генерации штрих‑кода DataMatrix?

Aspose.BarCode предоставляет точный контроль над размером DataMatrix, уровнем коррекции ошибок и настройками макросимволов, поддерживая более 30 символогий штрих‑кодов и обрабатывая файлы до 10 МБ без загрузки полного изображения в память. Его кросс‑платформенная реализация на .NET работает на .NET Framework, .NET Core и .NET 5/6 и включает встроенное распознавание, позволяющее мгновенно проверять штрих‑код.

## Пошаговое руководство

### Шаг 1: настройка проекта

Создайте новое консольное приложение (или любой проект .NET) в Visual Studio. Добавьте ссылку на DLL‑файлы Aspose.BarCode, полученные из загрузки.

### Шаг 2: настройка макросимволов DataMatrix

Суть руководства – здесь мы действительно **создаём штрих‑код DataMatrix** с макросимволом.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Совет:** Замените `"ASPOSE"` любой строкой, которую нужно закодировать. Макросимвол (`Macro05`) сообщает сканерам, что этот штрих‑код является частью макросеквенции.

### Шаг 3: настройка параметров штрих‑кода для коррекции ошибок

Перед сохранением вы можете настроить дополнительные параметры:

- **XDimension** – управляет размером каждого модуля (пикселя).  
- **Margin**, **ErrorCorrection** и **EncodingMode** – все доступны через `gen.Parameters.Barcode.DataMatrix`.

### Шаг 4: сохранение штрих‑кода

Приведённый выше фрагмент сохраняет изображение как `DataMatrixMacro.png` в указанной вами папке. PNG – без потерь, что делает его идеальным для дальнейшей обработки.

### Шаг 5: распознавание штрих‑кода

`BarCodeReader` – класс Aspose.BarCode для декодирования штрих‑кодов из изображений. С помощью `BarCodeReader` мы сразу же считываем сгенерированное изображение, чтобы подтвердить правильность макросимвола и данных. Такая проверка в обе стороны особенно полезна при автоматическом тестировании.

## Как использовать DataMatrix в реальных сценариях?

Вы можете применять штрих‑коды DataMatrix с макросимволами для маркировки продукции, связывания серийных номеров с центральной базой данных, отслеживания документов путем встраивания ссылки на цифровую запись, а также для меток медицинского оборудования, которые хранят данные о пациенте или устройстве в крошечном сканируемом символе. Такие сценарии снижают ручной ввод данных и повышают прослеживаемость.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| Штрих‑код не распознаётся | Неправильный `XDimension` или низкое разрешение изображения | Увеличьте `XDimension.Pixels` до 4‑6 и сохраняйте как PNG или TIFF |
| Макросимвол игнорируется | Сканер не поддерживает режим макросимволов | Используйте сканер/ридер, который явно поддерживает макросимволы DataMatrix (например, более новые версии ZXing) |
| Путь не найден | Неверная переменная `path` | Убедитесь, что каталог существует, или используйте `Path.Combine` с `Environment.CurrentDirectory` |

## Часто задаваемые вопросы

**В: Что такое Aspose.BarCode для .NET?**  
Aspose.BarCode для .NET – мощная библиотека, позволяющая разработчикам .NET генерировать и распознавать штрих‑коды в различных форматах, включая DataMatrix, QR и другие.

**В: Почему стоит использовать штрих‑коды DataMatrix?**  
Штрих‑коды DataMatrix компактны, высоконадежны и могут хранить большие объёмы данных, что делает их идеальными для производства, логистики и здравоохранения.

**В: Где найти документацию по Aspose.BarCode для .NET?**  
Документацию можно найти по ссылке [документацию Aspose.BarCode для .NET](https://reference.aspose.com/barcode/net/).

**В: Доступна ли бесплатная пробная версия Aspose.BarCode для .NET?**  
Да, вы можете скачать бесплатную пробную версию по ссылке [ссылка на бесплатную пробную версию](https://releases.aspose.com/).

**В: Где я могу получить поддержку по Aspose.BarCode для .NET?**  
Если у вас есть вопросы или нужна поддержка, посетите форум Aspose.BarCode для .NET по ссылке [форум поддержки](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-08-17  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Создать штрих‑код aspose .net – Настройка текста кода DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Как генерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Конфигурация Structured Append для DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}