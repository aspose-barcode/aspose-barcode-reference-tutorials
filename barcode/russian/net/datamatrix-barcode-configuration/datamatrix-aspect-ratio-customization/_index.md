---
date: 2026-05-30
description: Узнайте, как создать PNG штрих-кода с пользовательским соотношением сторон
  DataMatrix, используя Aspose.BarCode для .NET. Пошаговое руководство по генерации
  штрих-кодов и настройке их размеров.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Настройка соотношения сторон DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создать PNG штрих-кода – Соотношение сторон DataMatrix – Aspose.BarCode
url: /ru/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать PNG штрих‑кода – Соотношение сторон DataMatrix – Aspose.BarCode

Создание **barcode PNG** с пользовательским соотношением сторон DataMatrix является распространённым требованием, когда необходимо **create barcode PNG** файлы, соответствующие определённым ограничениям макета. В этом руководстве мы пройдём точные шаги по **create barcode PNG** файлам с использованием Aspose.BarCode для .NET, объясним, почему может потребоваться изменить соотношение сторон, и покажем, как точно настроить вывод для вашего приложения.

## Быстрые ответы
- **Что контролирует “aspect ratio”?** It defines the width‑to‑height proportion of the DataMatrix modules.  
- **Могу ли я выводить PNG, JPEG или SVG?** Yes – the `Save` method supports PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF.  
- **Нужна ли лицензия для этой функции?** A free trial works for development; a full license is required for production.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Сколько значений aspect‑ratio является допустимыми?** Any positive float; typical values are 0.5 – 2.0.

## Что такое штрих‑код DataMatrix и почему следует регулировать его соотношение сторон?
Штрих‑код DataMatrix — это двумерный матричный код, который хранит большие объёмы данных в компактном квадрате. Регулировка **aspect ratio** позволяет растягивать или сжимать модули по горизонтали, что полезно, когда необходимо разместить штрих‑код в узких колонках или широких этикетках без потери надёжности сканирования.

## Почему использовать Aspose.BarCode для создания barcode PNG?
Aspose.BarCode поддерживает **7 форматов изображений** — PNG, JPEG, BMP, GIF, TIFF, SVG и PDF — и может обрабатывать **более 50 форматов ввода и вывода** в памяти, работая с документами в сотни страниц без загрузки всего файла. Библиотека предоставляет удобный API, позволяющий генерировать штрих‑код DataMatrix в одну строку кода, гарантируя пиксель‑точный рендеринг и полную совместимость с .NET.

## Предварительные требования

Прежде чем начать настройку соотношения сторон DataMatrix, убедитесь, что у вас есть следующие предварительные требования:

1. **Visual Studio** – любая современная версия подойдет.  
2. **Aspose.BarCode for .NET** – скачайте его [здесь](https://releases.aspose.com/barcode/net/).  
3. Вы также можете изучить другие релизы продуктов Aspose [здесь](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – ваш проект должен использовать поддерживаемую версию.

## Импорт пространств имён

Сначала необходимо импортировать нужное пространство имён в ваш проект C#:

`using Aspose.BarCode.Generation;` импортирует пространство имён, содержащее классы генерации штрих‑кодов.  

```csharp
using Aspose.BarCode.Generation;
```

> **Совет:** Оставляйте эту инструкцию `using` в начале файла, чтобы класс `BarcodeGenerator` всегда был доступен.

## Как создать barcode PNG с пользовательским соотношением сторон?

Загрузите `BarcodeGenerator`, задайте тип DataMatrix, настройте свойство `AspectRatio` и вызовите `Save`. Этот однострочный шаблон создаёт barcode PNG, сохраняющий указанное соотношение, а библиотека автоматически обрабатывает масштабирование модулей и зоны тишины.

`BarcodeGenerator` создаёт изображение штрих‑кода из указанной символьной системы и данных.  

### Шаг 1: Настройте проект
Создайте новый консольный или Windows Forms проект в Visual Studio и добавьте ссылку на DLL Aspose.BarCode.

### Шаг 2: Инициализируйте генератор штрих‑кода
Создайте его экземпляр с символьной системой DataMatrix и данными, которые нужно закодировать:

`BarcodeGenerator` создаёт изображение штрих‑кода из указанной символьной системы и данных.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Эта строка создаёт генератор, готовый генерировать штрих‑код DataMatrix, содержащий пример текста.

### Шаг 3: Настройте соотношение сторон и сохраните PNG файлы
Теперь вы можете изменить **aspect ratio** и сохранить каждую версию как PNG‑изображение:

`AspectRatio` задаёт пропорцию ширины к высоте модулей DataMatrix.  
`Save` записывает сгенерированное изображение штрих‑кода в файл выбранного формата.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Первый вызов создаёт штрих‑код с квадратным соотношением (`AspectRatio = 1`).  
- Второй вызов сжимает штрих‑код по горизонтали (`AspectRatio = 0.5`), получая более широкое изображение.

Теперь у вас есть два файла **barcode PNG** с разными соотношениями сторон, готовые к использованию в отчётах, этикетках или элементах интерфейса.

## Распространённые проблемы и решения

| Проблема | Решение |
|----------|----------|
| **Сгенерированное изображение размыто** | Увеличьте параметр `Resolution` перед сохранением (`gen.Parameters.ImageResolution = 300`). |
| **Штрих‑код не сканируется** | Убедитесь, что соотношение сторон находится в диапазоне 0.5 – 2.0 и оставьте достаточную зону тишины (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Ошибки пути к файлу** | Используйте `Path.Combine` для построения пути вывода и проверьте, что папка существует. |

## Часто задаваемые вопросы

**В: Могу ли я настроить соотношение сторон других типов штрих‑кодов с помощью Aspose.BarCode для .NET?**  
A: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments through their specific parameter objects.

**В: Доступна ли бесплатная пробная версия Aspose.BarCode для .NET?**  
A: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).

**В: Где можно приобрести лицензию на Aspose.BarCode для .NET?**  
A: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).

**В: Совместим ли Aspose.BarCode для .NET с различными версиями .NET Framework?**  
A: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest .NET releases.

**В: Могу ли я генерировать штрих‑коды в разных форматах с Aspose.BarCode для .NET?**  
A: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported out of the box.

## Заключение

Настройка **aspect ratio** штрих‑кода DataMatrix и **создание barcode PNG** файлов проста с Aspose.BarCode для .NET. Следуя приведённым выше шагам, вы сможете генерировать идеально масштабированные штрих‑коды, соответствующие точным требованиям макета вашего проекта. Исследуйте дополнительные параметры, такие как `Resolution`, `Margin` и `Color`, чтобы ещё более адаптировать вывод, и учитывайте возможности `generate datamatrix barcode` при создании приложений, удобных для сканирования, в Visual Studio.

Для более глубокого изучения ознакомьтесь с официальной [документацией](https://reference.aspose.com/barcode/net/) или присоединитесь к сообществу на [форуме Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-05-30  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать штрих‑код DataMatrix – Профессиональное руководство с Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Как генерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Освоить кодирование DataMatrix в ASCII с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}