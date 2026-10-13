---
date: 2026-09-28
description: Узнайте, как создать 2d матричный штрих‑код с Aspose.BarCode for .NET
  – пошаговое руководство по генерации штрих‑кодов DotCode с extended code text.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Настройка DotCode Extended Code Text
og_description: Узнайте, как создать 2d матричный штрих‑код с использованием Aspose.BarCode
  for .NET. Это руководство пошагово показывает, как генерировать штрих‑коды DotCode
  с extended code text.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Создание 2d матричного штрих‑кода с Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Как создать 2d матричный штрих‑код с помощью Aspose.BarCode for .NET
url: /ru/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать 2d matrix barcode via Aspose.BarCode for .NET

## Введение

В области генерации и управления штрих‑кодами Aspose.BarCode for .NET выделяется как универсальное решение, поддерживающее **более 50 форматов ввода и вывода** и способное обрабатывать документы из сотен страниц без загрузки всего файла в память. Независимо от того, нужны ли вам штрих‑коды для отслеживания продукции, контроля запасов или данных‑насыщенных приложений, создание **2d matrix barcode** такого как DotCode с расширенным кодтекстом позволяет внедрять как текстовые, так и бинарные полезные нагрузки в компактный квадратный символ. Это руководство пошагово покажет, как построить такой расширенный кодтекст и отобразить окончательное изображение.

## Краткие ответы
- **Что означает “create dotcode extended codetext”?** Это построение штрих‑кода DotCode, который включает FNC1, ECICodetext, обычный текст и разделители символов в едином расширенном полезном нагрузке.  
- **Какая библиотека требуется?** Aspose.BarCode for .NET.  
- **Нужна ли лицензия?** Временная лицензия подходит для оценки; для продакшна требуется полная лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера.

## Как создать расширенный кодтекст dotcode

Загрузите проект, укажите каталог, соберите расширенный кодтекст и сгенерируйте изображение — все это менее чем в дюжине строк кода. Ниже представлена прямая инструкция, суммирующая весь процесс:

Загрузите `BarcodeGenerator` с `EncodeTypes.DotCode`, соберите расширенный кодтекст с помощью `DotCodeExtendedCodetextBuilder` (добавив FNC1, ECICodetext, обычный текст и разделители FNC3), затем вызовите `Save` для записи PNG‑файла. Эта последовательность создаёт полностью совместимый 2d matrix barcode одним вызовом.

## Что такое расширенный кодтекст dotcode?

**dotcode extended codetext** — это составная строка, объединяющая несколько сегментов данных — например, идентификаторы FNC1, ECICodetext, обычный текст и разделители FNC3 — в одну полезную нагрузку, которую может декодировать DotCode. Он позволяет кодировать многоязычный текст, бинарные блобы и структурированные данные в одном 2d matrix barcode, что делает его идеальным для цепочек поставок, здравоохранения и IoT‑сценариев.

## Зачем использовать Aspose.BarCode для этой задачи?

Aspose.BarCode обрабатывает **до 500 страниц в секунду** на типичном серверном оборудовании и поддерживает **более 30 символогий штрих‑кодов**, включая DotCode. Его API `GetExtendedCodetext` гарантирует правильное размещение управляющих символов, устраняя ошибки ручного конкатенирования строк и обеспечивая соответствие ISO/IEC 24724. Кроме того, он предоставляет встроенную коррекцию ошибок и автоматическое управление quiet‑zone, уменьшая необходимость ручной настройки.

## Требования

- **Aspose.BarCode for .NET** — скачать из [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- Среда разработки .NET (рекомендовано Visual Studio 2022 или новее).  
- По желанию: временный файл лицензии для оценки.

## Импорт пространств имён

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Эти пространства имён предоставляют класс `BarcodeGenerator` и вспомогательный `DotCodeExtendedCodetextBuilder`, необходимые для примера.

```csharp
using Aspose.BarCode.Generation;
```

Теперь, когда требования выполнены, разберём процесс генерации DotCode Extended Code Text пошагово.

## Шаг 1: определить путь к каталогу

Укажите, где будет сохранён сгенерированный PNG. Используйте абсолютный или относительный путь, в который приложение имеет право записи.

```csharp
string path = "Your Directory Path";
```

Замените `"Your Directory Path"` на реальный путь в вашей системе.

## Шаг 2: создать расширенный кодтекст dotcode

Класс `DotCodeExtendedCodetextBuilder` собирает различные сегменты в одну строку расширенного кодтекста.

Для создания DotCode Extended Code Text выполните следующие подпункты:

### 2.1 добавить идентификатор формата fnc1

Идентификатор формата FNC1 отмечает начало нового поля данных. Он необходим для символов DotCode, соответствующих стандарту GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 добавить ecicodetext

ECICodetext кодирует специальные символы и международный текст. В этом примере мы кодируем `"犬Right狗"` в UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 добавить обычный кодтекст

Можно также добавить обычный текст в DotCode Extended Code Text. Здесь добавляем `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 добавить разделитель символов fnc3

Разделитель FNC3 отделяет разные секции кода, улучшая читаемость для сканеров.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 добавить инициализацию чтения fnc3

Этот шаг добавляет информацию о инициализации чтения FNC3, которая указывает сканеру, как интерпретировать последующие данные.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 сгенерировать кодтекст

Теперь сгенерируйте DotCode Extended Codetext, вызвав метод `GetExtendedCodetext` у объекта `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Шаг 3: сгенерировать изображение dotcode

Отрисуйте изображение штрих‑кода из расширенного кодтекста.

#### 3.1 инициализировать генератор штрих‑кода

Класс `BarcodeGenerator` — ядро Aspose.BarCode для создания любого штрих‑кода. Вы создаёте его, указывая нужную символогию (`EncodeTypes.DotCode`) и только что построенный расширенный кодтекст.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Наконец, вызовите `Save` для записи PNG‑файла на диск. Изображение готово к внедрению в отчёты, мобильные приложения или печатные этикетки.

## Распространённые проблемы и решения

- **Неправильная кодировка** — Убедитесь, что при добавлении многоязычного текста используется `ECIEncodings.UTF8`; иначе символы могут отображаться некорректно.  
- **Ошибки доступа к файлу** — Проверьте, что приложение имеет права записи в целевой каталог.  
- **Отсутствует quiet zone** — Установите `gen.Parameters.Barcode.Margin`, если сканеру требуется дополнительное свободное пространство вокруг символа.

## Часто задаваемые вопросы

**В: Можно ли использовать сгенерированный штрих‑код в мобильном приложении?**  
О: Да. PNG‑изображение, созданное генератором, можно внедрять в iOS, Android или любые кроссплатформенные мобильные приложения.

**В: Что делать, если нужно закодировать бинарные данные вместо текста?**  
О: Используйте метод `AddECICodetext` с соответствующим `ECIEncodings` (например, `ECIEncodings.Base64`) для внедрения бинарных полезных нагрузок.

**В: Как изменить размер штрих‑кода без потери читаемости?**  
О: Отрегулируйте свойство `XDimension.Pixels`; большие значения увеличивают размер модуля, меньшие — делают штрих‑код более компактным.

**В: Можно ли добавить quiet zone вокруг штрих‑кода?**  
О: Да. Установите `gen.Parameters.Barcode.Margin` для задания желаемой quiet zone в пикселях.

**В: Поддерживает ли библиотека .NET 8?**  
О: Последние версии Aspose.BarCode совместимы с .NET 8; достаточно подключить соответствующую версию пакета NuGet.

Если требуется дополнительная помощь или есть вопросы, посетите [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) или обратитесь к сообществу на [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-09-28  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Create DotCode Barcode .NET (Auto Mode) with Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/net/datamatrix-barcode-configuration/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}