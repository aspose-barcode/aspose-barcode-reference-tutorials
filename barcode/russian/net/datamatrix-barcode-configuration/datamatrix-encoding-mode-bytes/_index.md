---
date: 2026-05-30
description: Узнайте, как генерировать штрих‑код DataMatrix в режиме Bytes и считывать
  штрих‑код DataMatrix с помощью Aspose.BarCode для .NET – пошаговое руководство по
  штрих‑коду.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Режим кодирования DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создание штрих‑кода DataMatrix в режиме Bytes с помощью Aspose.BarCode для
  .NET
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода DataMatrix в режиме Bytes с Aspose.BarCode для .NET

В этом руководстве вы узнаете, как **создать штрих‑код DataMatrix** с использованием режима кодирования Bytes, а затем **прочитать штрих‑код DataMatrix** с помощью Aspose.BarCode для .NET. Независимо от того, разрабатываете ли вы систему управления складом или мобильное приложение для билетов, пошаговое руководство ниже покажет, как настроить параметры генератора штрих‑кода, создать изображение высокого качества и снова его декодировать — всё это в нескольких строках C#.

## Быстрые ответы
- **Могу ли я создать штрих‑код DataMatrix в .NET?** Yes, use `BarcodeGenerator` with `EncodeTypes.DataMatrix` and set `DataMatrixEncodeMode.Bytes`.
- **Какой метод читает штрих‑код?** `BarCodeReader` reads the image and returns the encoded text.
- **Нужна ли лицензия для продакшн?** A commercial license is required; a free trial is available.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Сколько байтов я могу закодировать?** Up to 1,555 bytes in a single DataMatrix symbol.

## Что такое генерация штрих‑кода DataMatrix?
**Создание штрих‑кода DataMatrix** означает создание двумерного, квадратного штрих‑кода, способного хранить бинарные данные. Aspose.BarCode отображает символ в виде изображения PNG, JPG или SVG, которое может быть считано любым сканером. Он широко используется для отслеживания запасов, управления документами и аутентификации, поскольку обеспечивает высокую плотность данных и возможности коррекции ошибок, делая его надёжным даже при печати низкого качества.

## Почему использовать режим кодирования Bytes?
Режим Bytes позволяет внедрять необработанные бинарные данные (до 1 555 байтов) без преобразования их в текст, что идеально подходит для серийных номеров, GUID‑ов или зашифрованных полезных нагрузок. Aspose.BarCode поддерживает **30+ символогий штрих‑кодов** и может обрабатывать **многостраничные документы** без загрузки всего файла в память, обеспечивая высокую производительность даже в сценариях с большим объёмом данных.

## Предварительные требования

Прежде чем приступить к процессу кодирования, вам потребуются следующие предварительные условия:

1. Aspose.BarCode for .NET: Чтобы начать, вам необходимо установить библиотеку Aspose.BarCode for .NET. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/net/). Другие продукты Aspose также доступны [здесь](https://releases.aspose.com/).
2. Ваша среда разработки: Убедитесь, что у вас настроена среда разработки, включая Visual Studio или любую другую IDE по вашему выбору.
3. Базовые знания C#: В этом руководстве предполагается, что вы имеете базовое понимание программирования на C#.

Для получения помощи посетите [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

С этими предварительными условиями вы готовы начать кодировать данные в формате DataMatrix, используя режим Bytes.

## Импорт пространств имён

Чтобы использовать Aspose.BarCode для .NET, импортируйте необходимые пространства имён в начале вашего файла C#:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Теперь, когда среда готова, пройдём точные шаги по **созданию штрих‑кода DataMatrix** и последующему его чтению.

## Как создать штрих‑код DataMatrix в режиме Bytes?

Загрузите `BarcodeGenerator`, установите режим кодирования в Bytes, при необходимости настройте отображаемый текст, сохраните изображение и, наконец, используйте `BarCodeReader` для проверки результата — всё это в шести лаконичных шагах. Такой подход гарантирует надёжный штрих‑код, соответствующий стандарту ISO/IEC 16022.

### Шаг 1: Инициализация BarcodeGenerator

`BarcodeGenerator` — основной класс, используемый для генерации изображений штрих‑кодов для заданной символогии и данных.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Шаг 2: Установить режим кодирования DataMatrix в Bytes

`DataMatrixEncodeMode.Bytes` указывает генератору рассматривать ввод как необработанные бинарные байты, а не как текст.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Шаг 3: Установить отображаемый текст

Свойство `CodeText` задаёт человекочитаемый текст, отображаемый под символом штрих‑кода.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Шаг 4: Сохранить изображение штрих‑кода

Метод `Save` записывает сгенерированный штрих‑код в файл изображения в указанном формате.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Шаг 5: Попробовать распознать

`BarCodeReader` читает изображения штрих‑кодов и извлекает закодированные данные.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Шаг 6: Итерация и отображение результатов

Итерируйтесь по `reader.ReadBarCodes()`, чтобы получить каждый обнаруженный штрих‑код и его `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

С помощью этих шагов вы успешно **создали штрих‑код DataMatrix** в режиме Bytes и проверили его с помощью Aspose.BarCode для .NET. Библиотека абстрагирует детали низкоуровневого кодирования, позволяя сосредоточиться на бизнес‑логике, а не на математике штрих‑кодов.

## Распространённые проблемы и решения

- **Закодированные данные усечены** — Убедитесь, что массив байтов не превышает 1 555 байтов; иначе библиотека автоматически переключится на больший размер символа или выбросит исключение.
- **Изображение выглядит размытым** — Сохраните изображение с более высоким разрешением (например, 300 dpi), установив `generator.Parameters.ImageResolution` перед вызовом `Save`.
- **Reader возвращает null** — Проверьте, что путь к изображению правильный и файл не повреждён; также убедитесь, что `BarCodeReader` создан с параметром `DecodeType.DataMatrix`.

## Часто задаваемые вопросы

**В: Что такое режим кодирования DataMatrix?**  
О: Режим кодирования DataMatrix определяет, как входные данные преобразуются в двумерный шаблон; режим Bytes сохраняет необработанные бинарные байты напрямую.

**В: Как получить бесплатную пробную версию Aspose.BarCode для .NET?**  
О: Вы можете получить бесплатную пробную версию Aspose.BarCode для .NET [здесь](https://releases.aspose.com/).

**В: Где найти документацию по Aspose.BarCode для .NET?**  
О: Документация по Aspose.BarCode для .NET доступна [здесь](https://reference.aspose.com/barcode/net/).

**В: Подходит ли Aspose.BarCode для .NET для коммерческого использования?**  
О: Да, Aspose.BarCode для .NET подходит для коммерческого использования. Вы можете приобрести лицензию [здесь](https://purchase.aspose.com/buy).

**В: Могу ли я использовать временную лицензию для Aspose.BarCode для .NET?**  
О: Да, вы можете получить временную лицензию для Aspose.BarCode для .NET [здесь](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-05-30  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Мастер кодирования DataMatrix в ASCII с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Чтение штрих‑кода DataMatrix C# – Генерация режима DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Как создать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}