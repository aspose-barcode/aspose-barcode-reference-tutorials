---
date: 2026-05-24
description: Узнайте, как создать штрих‑код codabar с символами начала и конца, используя
  Aspose.BarCode для .NET. Пошаговое руководство по генерации штрих‑кодов для разработчиков.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: 'Codabar: символы начала/конца'
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создание штрих‑кода Codabar с символами начала/конца в Aspose.BarCode для .NET
url: /ru/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода Codabar с символами начала/конца в Aspose.BarCode для .NET

## Введение

В этом руководстве вы **создадите изображения штрих‑кода Codabar**, включающие явные символы начала/конца, используя Aspose.BarCode для .NET. Независимо от того, разрабатываете ли вы систему учёта розничных товаров, трекер лабораторных образцов или решение для медицинских записей, числовая символьная система Codabar опирается на эти граничные символы для обеспечения надёжного сканирования. В течение нескольких минут мы рассмотрим всё — от настройки окружения до сохранения PNG‑файлов, чтобы вы могли сразу начать генерировать штрих‑коды Codabar.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.BarCode for .NET  
- **В каком формате можно сохранить штрих‑код?** PNG (`BarCodeImageFormat.Png`)  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Можно ли изменить символы начала/конца?** Да — используйте `CodabarSymbol.A`, `B`, `C` или `D`.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое Codabar и почему символы начала/конца важны?

Codabar — это числовая система штрих‑кодов, широко используемая в библиотеках, здравоохранении и управлении запасами. Символы начала и конца (A‑D или дефис) определяют границы штрих‑кода, позволяя сканерам точно определить, где начинаются и заканчиваются данные, с точностью чтения 99,9 %.

## Почему использовать Aspose.BarCode для .NET?

Aspose.BarCode поддерживает **более 30 символогий штрих‑кодов** и может генерировать изображения размером до **10 000 × 10 000 px**, не загружая весь документ в память. Он работает на Windows, Linux и macOS и совместим с .NET Framework, .NET Core и .NET 5+, предоставляя гибкость на всех современных платформах.

## Требования

1. **Настройка окружения** – Убедитесь, что у вас есть рабочее .NET‑разработческое окружение. При необходимости обратитесь к [документации](https://reference.aspose.com/barcode/net/).  
2. **Библиотека Aspose.BarCode для .NET** – Скачайте и установите библиотеку с официального [источника](https://releases.aspose.com/barcode/net/).  
3. **Базовые знания .NET** – Знание C# и IDE, такой как Visual Studio, Rider или VS Code.  
4. **IDE** – Visual Studio, Rider или Visual Studio Code подходят.

Теперь, когда мы рассмотрели требования, давайте перейдём к реальному коду.

## Как сгенерировать штрих‑код Codabar с символами начала/конца?

Загрузите `BarcodeGenerator`, задайте тип кодирования **Codabar** и передайте строку данных, уже содержащую необходимые символы начала/конца (например, “-12345-”). Затем настройте X‑Dimension, при необходимости выберите другой символ начала/конца и в конце сохраните изображение в формате PNG. Этот сквозной процесс создаёт готовый к использованию штрих‑код всего в несколько строк кода C#.

### Импорт пространств имён

Класс `BarcodeGenerator` и связанные типы находятся в пространстве имён `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Шаг 1: Инициализация генератора штрих‑кода

`BarcodeGenerator` — основной класс, создающий изображения штрих‑кодов. Он принимает тип символогии и строку данных в качестве аргументов конструктора.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Полезный совет:** Дефис (`-`) является одним из допустимых символов начала/конца для Codabar. Вы также можете использовать `A`, `B`, `C` или `D` в зависимости от требований вашего приложения.

### Шаг 2: Установка X‑Dimension (ширина элемента штрих‑кода)

`XDimension` управляет шириной самого узкого штриха. Большие значения повышают читаемость на принтерах с низким разрешением, а меньшие значения экономят место на этикетках высокой плотности.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Почему это важно:** Регулировка `XDimension` помогает соответствовать требованиям сканеров, которые часто требуют минимальную ширину штриха 0,25 мм.

### Шаг 3: Определение символов начала и конца

Codabar поддерживает четыре символа начала/конца (A, B, C, D). Ниже приведены примеры для каждого варианта. Выберите тот, который соответствует спецификации системы, с которой вы интегрируетесь.

#### Установка Start A и Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Установка Start B и Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Установка Start C и Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Установка Start D и Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Вы можете повторить конфигурацию для каждого необходимого символа; пример ниже сохраняет четыре отдельные изображения — по одному для каждой пары начала/конца.

### Шаг 4: Сохранение сгенерированных изображений штрих‑кода (PNG)

`Save` записывает штрих‑код в файл. Использование `BarCodeImageFormat.Png` создаёт без потерь PNG‑изображения, идеально подходящие для веб‑ и печатных задач.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Каждый файл теперь содержит **пример штрих‑кода Codabar** с соответствующими символами начала/конца.

## Распространённые проблемы и устранение неполадок

| Симптом | Возможная причина | Решение |
|---------|-------------------|---------|
| Штрих‑код выглядит искажённым | X‑Dimension слишком низкое для выбранного разрешения принтера | Увеличьте `XDimension.Pixels` (например, до 3 или 4) |
| Сканер не может прочитать начало/конец | Неправильный символ начала/конца для целевой системы | Проверьте требуемый символ (A‑D) и установите его соответствующим образом |
| PNG‑файл пустой или повреждён | Неверный путь вывода или недостаточные права записи | Убедитесь, что `path` указывает на существующую папку и приложение имеет права записи |

## Часто задаваемые вопросы

**Q1: Что такое Codabar и почему символы начала и конца важны?**  
A: Codabar — это числовая система штрих‑кодов, используемая в учёте запасов, библиотеках и здравоохранении. Символы начала/конца определяют границы штрих‑кода, гарантируя, что сканеры знают, где начинаются и заканчиваются данные.

**Q2: Можно ли настроить внешний вид штрих‑кодов Codabar с помощью Aspose.BarCode для .NET?**  
A: Да. Помимо X‑Dimension, вы можете менять цвета, добавлять отступы и экспортировать в PDF или SVG, используя тот же API.

**Q3: Есть ли ограничения у штрих‑кодов Codabar в отношении кодирования данных?**  
A: Codabar в основном поддерживает только числовые данные (0‑9) и ограниченный набор специальных символов. Он не подходит для полностью алфавитно‑цифровых строк.

**Q4: Подходит ли Aspose.BarCode для .NET для коммерческого использования и как получить лицензию?**  
A: Да, он готов к продакшну. Приобретите лицензию на [странице покупки Aspose](https://purchase.aspose.com/buy).

**Q5: Где можно получить помощь или обсудить проблемы, связанные с Aspose.BarCode для .NET?**  
A: Присоединяйтесь к сообществу на [форуме поддержки Aspose.BarCode для .NET](https://forum.aspose.com/c/barcode/13), где помогут как инженеры Aspose, так и другие разработчики.

**Last Updated:** 2026-05-24  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Связанные руководства

- [Codabar: символы начала/конца и контрольная сумма](/barcode/net/codabar-encoding-and-checksum/)
- [Как добавить контрольную сумму к штрих‑кодам Codabar с помощью Aspose.BarCode для .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Полные руководства и примеры Aspose.BarCode для .NET](/barcode/net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}