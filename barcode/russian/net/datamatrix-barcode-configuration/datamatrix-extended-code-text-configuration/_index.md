---
date: 2026-09-23
description: Узнайте, как использовать Aspose.BarCode для генерации штрих‑кода DataMatrix
  с расширенным текстом кода в .NET, идеально подходящего для приложений инвентаризации
  и логистики.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Настройка расширенного текста кода DataMatrix
og_description: Как использовать Aspose.BarCode для генерации штрих‑кода DataMatrix
  с расширенным текстом кода в .NET. Следуйте быстрому пошаговому руководству для
  решений в области инвентаризации и логистики.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Как использовать Aspose.BarCode для создания текста кода DataMatrix в .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Как использовать Aspose.BarCode для создания текста кода DataMatrix в .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать Aspose.BarCode для создания текста DataMatrix в .NET

Интеграция штрихкодов в современные .NET‑приложения больше не является нишевой задачей — это ключевое требование для инвентаризации, логистики и мобильных решений сканирования. В этом руководстве вы **узнаете, как использовать Aspose.BarCode** для настройки штрихкода DataMatrix с расширенным текстом кода, создания изображения и программной проверки. Вы увидите, почему этот подход идеален для создания штрихкода для инвентаризации и как он вписывается в проекты .NET Core или .NET 6.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.BarCode for .NET  
- **Какой тип штрихкода?** DataMatrix с расширенным текстом кода  
- **Можно ли использовать .NET Core / .NET 6?** Да, API кросс‑платформенный  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; для продакшна требуется лицензия  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера  

## Что такое Aspose.BarCode для .NET?
Aspose.BarCode для .NET — это коммерческая библиотека, позволяющая разработчикам генерировать и распознавать более 30 символогий штрихкодов, включая DataMatrix, QR и Code 128, а также создавать изображения размером до 10 000 × 10 000 пикселей без внешних зависимостей. Она поддерживает .NET Framework 4.5+, .NET Core 3.1+ и .NET 5/6/7.

## Почему использовать расширенный текст кода DataMatrix?
Расширенный текст кода DataMatrix позволяет внедрять несколько схем кодирования — UTF‑8, C40, Text, X12 — в один символ, предоставляя до **3116 кодовых слов** (примерно 155 KB данных) в одном компактном квадрате. Эта возможность идеальна для многоязычной маркировки продукции, отслеживания медицинских устройств и умной упаковки, где необходимо сочетать буквенно-цифровые идентификаторы с бинарными полезными нагрузками.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующее:

1. **Aspose.BarCode for .NET** – загрузите её с официального сайта **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Среда разработки .NET** – Visual Studio, Rider или VS Code с .NET SDK.  
3. **Базовые знания C#** – вы должны быть уверены в работе с классами, пространствами имён и директивой `using`.

## Импорт пространств имён

Добавьте необходимые пространства имён в начало вашего C#‑файла, чтобы компилятор знал, где находятся классы штрихкода.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Эти пространства имён предоставляют доступ как к функциям генерации штрихкодов, так и к функциям распознавания.

## Как настроить расширенный текст кода DataMatrix?

Загрузите builder, добавьте нужные сегменты и позвольте Aspose.BarCode автоматически обрабатывать маркеры ECI. Этот прямой‑ответный абзац описывает точные шаги: создать `DataMatrixExtCodetextBuilder`, добавить сегменты Unicode, C40, обычного текста и режима Text, затем получить объединённую строку для генератора.

### Шаг 1: Определите папку вывода

Укажите, где будет сохранено сгенерированное изображение штрихкода. Замените заполнитель на действительный путь на вашем компьютере.

```csharp
string path = "Your Directory Path";
```

### Шаг 2: Сформируйте расширенный текст кода

`DataMatrixExtCodetextBuilder` — вспомогательный класс, который собирает расширенный текст кода в соответствии со спецификацией DataMatrix. Он автоматически вставляет необходимые маркеры ECI (Extended Channel Interpretation).

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Эта комбинация демонстрирует, как можно объединить символы Unicode, кодирование C40, обычный текст и режим Text в одном символе DataMatrix.

### Шаг 3: Сгенерировать окончательную строку текста кода

После настройки всех частей получите объединённую строку, которую Aspose.BarCode внедрит в штрихкод.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Шаг 4: Создать штрихкод DataMatrix

`BarcodeGenerator` — основной класс, который создаёт изображения штрихкодов. Создайте его с `EncodeTypes.DataMatrix` и расширенным текстом кода, затем задайте визуальные параметры, такие как X‑dimension, формат изображения и необязательный человекочитаемый текст.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Приведённый выше код **создаёт штрихкод aspose .net** с нужным расширенным текстом кода и сохраняет его в файл PNG.

### Шаг 5: Проверить штрихкод, считав его обратно

`BarCodeReader` проверяет, что сгенерированный символ может быть корректно декодирован, что важно для автоматических тестовых конвейеров и обеспечения качества.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Если всё настроено правильно, консоль выведет точный расширенный текст кода, который вы создали ранее.

## Распространённые проблемы и их устранение

| Проблема | Причина | Решение |
|----------|---------|---------|
| Штрихкод не читается | X‑dimension слишком низкая | Увеличьте `XDimension.Pixels` (например, 4 → 6) |
| Искаженые символы | Неправильное кодирование ECI | Убедитесь, что `ECIEncodings.UTF8` соответствует набору символов |
| Файл не сохранён | Недействительный путь | Используйте абсолютный путь или убедитесь, что папка существует |
| Исключение лицензии | Срок пробной версии истёк | Примените временную или полную лицензию (см. FAQ) |

## Часто задаваемые вопросы

### Вопрос 1: Что такое Aspose.BarCode для .NET?
A1: Aspose.BarCode для .NET — мощная библиотека, позволяющая разработчикам генерировать и распознавать широкий спектр символогий штрихкодов, включая DataMatrix, QR, Code128 и другие.

### Вопрос 2: Где найти документацию по Aspose.BarCode для .NET?
A2: Полную справочную информацию API можно найти по ссылке **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Вопрос 3: Доступна ли бесплатная пробная версия Aspose.BarCode для .NET?
A3: Да, бесплатную пробную версию можно скачать по ссылке **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Вопрос 4: Как получить временную лицензию для тестирования?
A4: Временные лицензии предоставляются для оценки и могут быть запрошены по ссылке **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Вопрос 5: Где можно получить поддержку или задать вопросы по Aspose.BarCode для .NET?
A5: Официальный форум Aspose.BarCode — лучшее место для получения помощи: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Последнее обновление:** 2026-09-23  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как генерировать штрихкоды DataMatrix с помощью Aspose.BarCode для .NET – пошаговое руководство](/barcode/net/datamatrix-barcode-configuration/)
- [Создать штрихкод DataMatrix в режиме ASCII с Aspose.BarCode для .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Создать штрихкод Aztec с текстовым кодированием с помощью Aspose.BarCode для .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}