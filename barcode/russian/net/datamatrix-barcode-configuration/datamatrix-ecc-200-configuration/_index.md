---
date: 2026-08-02
description: Узнайте, как создать штрих‑код DataMatrix, сгенерировать DataMatrix и
  изучить генерацию штрих‑кодов высокой плотности с Aspose.BarCode для проектов на
  .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Конфигурация DataMatrix ECC 200
og_description: Создайте штрих‑код DataMatrix с Aspose.BarCode для .NET. В этом руководстве
  показана генерация штрих‑кодов высокой плотности, настройка временной лицензии Aspose
  и пошаговый код на C#.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Создание штрих‑кода DataMatrix – руководство Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Как создать штрих‑код DataMatrix (ECC 200) с помощью Aspose.BarCode для .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код DataMatrix (ECC 200) с помощью Aspose.BarCode для .NET

## Введение

В этом руководстве вы **создадите штрих‑код DataMatrix** (ECC 200) с помощью Aspose.BarCode для .NET. Независимо от того, создаёте ли вы систему учёта запасов, POS‑систему или автоматизируете документооборот, штрих‑код высокой плотности может хранить большое количество данных в крошечном пространстве. Мы пройдём каждый шаг настройки, объясним, почему каждый параметр важен, и предоставим готовые C#‑фрагменты.

## Быстрые ответы

- **Какая библиотека лучше всего подходит для DataMatrix в .NET?** Aspose.BarCode for .NET  
- **Какой уровень ECC предоставляет ECC 200?** Высокоплотная коррекция ошибок для надёжного сканирования.  
- **Нужна ли лицензия для запуска примера?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Могу ли я выводить PNG, JPEG или TIFF?** Да — метод `Save` поддерживает несколько форматов изображений.

## Что такое DataMatrix ECC 200?

DataMatrix ECC 200 — это высокоплотный двумерный штрих‑код, который может хранить до 2 335 буквенно‑цифровых символов или 1 556 байт бинарных данных в компактном квадратном или прямоугольном шаблоне. Он использует коррекцию ошибок Рида‑Соломона для восстановления потерянных или повреждённых модулей, что делает его идеальным для таких приложений, как маркировка деталей аэрокосмической отрасли, фармацевтическая маркировка и логистика, где надёжность критична.

## Почему использовать генерацию штрих‑кодов Aspose?

Aspose.BarCode поддерживает **30+ символогий**, может рендерить изображения размером до 10 000 × 10 000 px без загрузки всего файла в память и обеспечивает детерминированный вывод на Windows, Linux и macOS. Его API позволяет управлять каждым параметром рендеринга, делая его самым гибким выбором для сценариев **barcode generation ASP.NET**.

## Предварительные требования

1. **Среда разработки** — Visual Studio с установленным соответствующим .NET framework.  
2. **Aspose.BarCode for .NET** — загрузите и установите с сайта, [здесь](https://releases.aspose.com/barcode/net/).  
3. **Лицензия** — получите временную лицензию для тестирования [здесь](https://purchase.aspose.com/temporary-license/).  
4. **Основы C#** — знакомство с синтаксисом C# и структурой проекта.

Теперь, когда основные моменты покрыты, перейдём к настройке DataMatrix ECC 200.

## Импорт пространств имён

Пространство имён `Aspose.BarCode.Generation` содержит все классы, необходимые для создания штрих‑кода. Импортируйте его в начале вашего файла:

```csharp
using Aspose.BarCode.Generation;
```

## Как создать штрих‑код DataMatrix (ECC 200) пошагово

Чтобы создать штрих‑код DataMatrix ECC 200, вам просто нужно загрузить данные, которые вы хотите закодировать, настроить несколько ключевых параметров у `BarcodeGenerator`, а затем вызвать `Save` для записи файла изображения. Этот трёхшаговый процесс обрабатывает кодирование, коррекцию ошибок и выбор формата вывода, позволяя интегрировать создание штрих‑кода в любое .NET‑приложение с минимальным объёмом кода.

### Шаг 1: Инициализация Barcode Generator

`BarcodeGenerator` — основной класс Aspose.BarCode, который создаёт и рендерит штрих‑коды. Он принимает тип символогии и текст для кодирования.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Замените `"Your Directory Path"` на путь к папке, в которой вы хотите сохранить изображение.

### Шаг 2: Установите XDimension и тип ECC

`XDimension` определяет размер в пикселях каждого модуля DataMatrix, а `DataMatrixEcc` выбирает уровень коррекции ошибок. ECC 200 обеспечивает наивысшую степень коррекции для этой символогии.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Отрегулируйте значение пикселей, если нужны более крупные или мелкие модули; типичные значения — 4‑6 px для отображения на экране и 8‑10 px для печатных этикеток.

### Шаг 3: Сгенерировать и сохранить изображение штрих‑кода

Метод `Save` записывает штрих‑код в файл. Вы можете выбрать PNG, JPEG или TIFF, передав соответствующее значение перечисления `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Tiff`, если ваш процесс требует другого формата.

## Распространённые проблемы и их устранение

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Штрих‑код выглядит размытым | XDimension слишком низкое | Увеличьте `XDimension.Pixels` до 6‑8 |
| Сканирование не удаётся на мобильном | Неправильный уровень ECC | Убедитесь, что `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Файл не создан | Недопустимая строка пути | Используйте абсолютный путь или убедитесь, что папка существует |

## Часто задаваемые вопросы

**Q: Можно ли использовать этот код в консольном приложении .NET Core?**  
A: Да, тот же API работает в проектах .NET Core, .NET 5 и .NET 6.

**Q: Как изменить формат вывода на JPEG?**  
A: Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` в вызове `Save`.

**Q: Можно ли встроить штрих‑код непосредственно в PDF?**  
A: Да — сначала сгенерируйте изображение, затем добавьте его в PDF с помощью Aspose.PDF или любой другой PDF‑библиотеки.

**Q: Что делать, если нужно закодировать символы Unicode?**  
A: DataMatrix поддерживает UTF‑8; просто передайте строку Unicode генератору, как показано.

**Q: Поддерживает ли библиотека пакетную генерацию нескольких штрих‑кодов?**  
A: Абсолютно — разместите код генерации внутри цикла и меняйте данные/значение для каждой итерации.

## Заключение

Мы рассмотрели всё, что необходимо для **создания штрих‑кода DataMatrix** (ECC 200) с помощью Aspose.BarCode для .NET: от предварительных требований и импорта пространств имён до настройки X‑dimension, выбора уровня ECC и сохранения изображения в желаемом формате. Экспериментируйте с множеством дополнительных свойств — таких как отступ, цвет фона и вращение — чтобы точно настроить вывод под ваш конкретный сценарий.

Если вы столкнётесь с какими‑либо проблемами, сообщество готово помочь на форуме [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13). Приятного кодирования!

---

**Последнее обновление:** 2026-08-02  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как сгенерировать штрих‑коды DataMatrix ECC 000-140 с помощью Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Как считывать штрих‑коды DataMatrix с помощью Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/)
- [Создать PNG‑штрих‑код — соотношение сторон DataMatrix — Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}