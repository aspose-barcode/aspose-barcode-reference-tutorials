---
date: 2026-06-09
description: Узнайте, как генерировать штрихкоды DataMatrix и сохранять их в формате
  PNG, используя кодирование C40 с Aspose.BarCode – полное руководство по генерации
  штрихкодов в .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Режим кодирования DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Как сгенерировать PNG DataMatrix с кодированием C40 с помощью Aspose.BarCode
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Основной режим кодирования DataMatrix (C40) с Aspose.BarCode для .NET

## Введение

В этом руководстве вы узнаете **как сгенерировать datamatrix** штрих‑коды и сохранить их в виде PNG‑файлов, используя режим кодирования C40 с Aspose.BarCode для .NET. Независимо от того, создаёте ли вы систему учёта, генератор транспортных этикеток или любое решение, требующее компактных, высокоплотных символов, освоение C40 позволяет получать более мелкие символы без потери читаемости. Мы пройдём каждый шаг — от настройки окружения до получения готового PNG‑файла — чтобы вы могли сразу интегрировать код в свой проект.

## Быстрые ответы
- **Что означает “how to generate datamatrix”?** Создание изображения штрих‑кода DataMatrix программным способом.  
- **Какой режим кодирования рассматривается?** DataMatrix C40, эффективная буквенно‑цифровая схема.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Можно ли запускать это на .NET Core?** Да, Aspose.BarCode полностью поддерживает .NET Core, .NET 5, .NET 6 и более новые версии.  
- **В каком формате создаётся файл?** PNG — без потерь, удобный для веб‑использования формат изображения.

## Как сгенерировать DataMatrix с кодированием C40

Загрузите данные, настройте генератор и вызовите `Save` — это полный рабочий процесс в трёх лаконичных шагах. Класс `BarcodeGenerator` отвечает за создание символа, а перечисление `BarCodeImageFormat.Png` указывает Aspose.BarCode записать результат в файл PNG. `Save` сохраняет сгенерированное изображение штрих‑кода по указанному пути в выбранном формате. Этот абзац‑ответ даёт вам готовое решение от начала до конца, прежде чем мы разберём каждую строку кода.

## Что такое режим кодирования DataMatrix (C40)?

`DataMatrixEncodeMode` — это перечисление, которое указывает, какую схему кодирования Aspose.BarCode следует использовать для символов DataMatrix. Параметр `DataMatrixEncodeMode.C40` выбирает буквенно‑цифровое кодирование C40, которое упаковывает буквы, цифры и ограниченный набор знаков пунктуации в меньшее количество модулей, уменьшая общий размер символа при сохранении читаемости типичного текста инвентаризации. Эта эффективная схема идеальна, когда требуется компактное кодирование буквенно‑цифровых данных.

## Почему использовать Aspose.BarCode для .NET?

Aspose.BarCode предоставляет **30+ настраиваемых параметров** для размеров, уровней коррекции ошибок и режимов кодирования, а также поддерживает **50+ форматов изображений и штрих‑кодов**. Библиотека работает на **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, обеспечивая генерацию без внешних зависимостей, которая работает на серверах, настольных ПК и мобильных устройствах.

## Требования

Перед тем как перейти к коду, убедитесь, что у вас есть следующее:

1. **Среда разработки .NET** — Visual Studio, Rider или любой IDE, поддерживающий C#.  
2. **Aspose.BarCode для .NET** — установленный через NuGet или официальный установщик. Подробнее см. в [документации](https://reference.aspose.com/barcode/net/).  
3. **Базовые знания C#** — вы должны уверенно работать с пространствами имён, классами и директивами using.  
4. **Папка с правом записи** — каталог на вашем компьютере, куда будет сохраняться PNG.

## Импорт необходимых пространств имён

Класс `BarcodeGenerator` является точкой входа для создания любого штрих‑кода. Добавьте требуемое пространство имён в начало вашего C#‑файла, чтобы получить доступ к API генерации:

```csharp
using Aspose.BarCode.Generation;
```

## Пошаговое создание штрих‑кода

Ниже представлена **пошаговая инструкция** по созданию штрих‑кода. Каждый шаг объяснён простыми словами, а оригинальные заполнители оставлены без изменений для удобства копирования.

### Шаг 1: Укажите путь к каталогу
Задайте папку, в которой будет храниться PNG‑изображение. Замените заполнитель реальным путём на вашем компьютере.

```csharp
string path = "Your Directory Path";
```

### Шаг 2: Настройка генерации штрих‑кода
Создайте экземпляр `BarcodeGenerator`, укажите `EncodeTypes.DataMatrix` и передайте данные, которые нужно закодировать.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Шаг 3: Настройка штрих‑кода
Настройте X‑размер (ширина модуля в пикселях) и переключите режим кодирования на C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Шаг 4: Сохранить изображение штрих‑кода
Наконец, сохраните сгенерированный штрих‑код в файл PNG. Это конкретный ответ на **как сохранить png** с помощью Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

При запуске программы вы найдёте `DataMatrixEncodeModeC40.png` в указанной папке, готовый к использованию в отчётах, этикетках или веб‑страницах.

## Распространённые проблемы и советы

- **Invalid Path** — Убедитесь, что каталог существует и у вас есть права записи; иначе `gen.Save` выбросит исключение.  
- **Incorrect Encoding Mode** — Если необходимо кодировать символы, не входящие в набор C40, переключитесь на `DataMatrixEncodeMode.Auto` или другой подходящий режим.  
- **Image Size** — Отрегулируйте `XDimension.Pixels`, чтобы увеличить или уменьшить общий размер штрих‑кода без потери читаемости.

## Часто задаваемые вопросы

**Q: Что такое режим кодирования DataMatrix (C40)?**  
A: C40 — компактная буквенно‑цифровая схема кодирования для символов DataMatrix, идеальная для текста, содержащего буквы, цифры и ограниченный набор специальных символов.

**Q: Где можно найти документацию Aspose.BarCode для .NET?**  
A: Документацию можно найти [здесь](https://reference.aspose.com/barcode/net/). Она содержит подробные рекомендации по всем типам штрих‑кодов и параметрам кодирования.

**Q: Совместима ли библиотека Aspose.BarCode для .NET со всеми версиями .NET?**  
A: Да, библиотека поддерживает широкий спектр версий .NET, от .NET Framework 4.5+ до .NET 6 и более новых.

**Q: Можно ли попробовать Aspose.BarCode для .NET перед покупкой?**  
A: Да, вы можете воспользоваться бесплатной пробной версией Aspose.BarCode для .NET, перейдя по [этой ссылке](https://releases.aspose.com/). Это позволит протестировать функции и возможности библиотеки.

**Q: Где можно получить поддержку по Aspose.BarCode для .NET?**  
A: Поддержку и сообщество можно найти на [форуме Aspose](https://forum.aspose.com/c/barcode/13).

## Заключение

Следуя этому **пошаговому руководству**, вы теперь точно знаете **как сгенерировать datamatrix** штрих‑коды и сохранить их в виде PNG‑файлов, используя режим кодирования C40 с Aspose.BarCode для .NET. Такой подход даёт полный контроль над внешним видом, размером и представлением данных штрих‑кода, упрощая внедрение высококачественных штрих‑кодов в любое .NET‑приложение.

---

**Последнее обновление:** 2026-06-09  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Кодирование DataMatrix в байтах с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Главное кодирование DataMatrix в ASCII с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Как сгенерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}