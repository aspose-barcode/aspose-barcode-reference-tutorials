---
date: 2026-06-14
description: Узнайте, как считывать DataMatrix и генерировать штрихкоды с структурированным
  добавлением в .NET, используя Aspose.BarCode — быструю и надёжную библиотеку штрихкодов.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Конфигурация DataMatrix Structured Append
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Как считывать DataMatrix Append с Aspose.BarCode для .NET
url: /ru/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Конфигурация структурного добавления DataMatrix с Aspose.BarCode для .NET

Если вы разработчик, ищущий **how to read datamatrix** с использованием структурного добавления в ваших .NET приложениях, Aspose.BarCode для .NET — ваше решение. В этом пошаговом руководстве мы пройдем процесс создания и декодирования штрихкодов DataMatrix, разделенных на несколько символов. К концу этого урока вы будете уверенно создавать, настраивать и считывать штрихкоды DataMatrix с структурным добавлением с помощью Aspose.BarCode для .NET.

## Быстрые ответы
- **Какая библиотека обрабатывает структурное добавление DataMatrix?** Aspose.BarCode for .NET.
- **Сколько символов может содержать одна последовательность структурного добавления?** До 16 символов DataMatrix.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для разработки и тестирования.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Можно ли считывать штрихкод без файла изображения?** Да, можно декодировать из массива байтов или потока.

## Что такое how to read datamatrix?
**how to read datamatrix** относится к процессу декодирования символов DataMatrix и, при необходимости, объединения частей последовательности структурного добавления для получения исходных данных. Aspose.BarCode предоставляет встроенную поддержку этого процесса, автоматически управляя порядком символов и конкатенацией данных.

## Почему использовать Aspose.BarCode для структурного добавления DataMatrix?
Aspose.BarCode поддерживает **30+ символогий штрихкодов** и может декодировать изображения размером до **10 000 × 10 000 px** менее чем за **200 ms** на типичном серверном оборудовании. Библиотека также предлагает **развёртывание без зависимостей**, что означает отсутствие необходимости в дополнительных нативных DLL, и работает на платформах Windows, Linux и macOS .NET.

## Предварительные требования

Перед тем как приступить к уроку, вам понадобится:

1. Aspose.BarCode for .NET Library – загрузите её с [здесь](https://releases.aspose.com/barcode/net/).
2. Вы также можете просмотреть другие продукты Aspose [здесь](https://releases.aspose.com/).
3. Среда разработки .NET, например Visual Studio 2022 или Visual Studio Code с расширением C#.

Теперь давайте начнём создавать и считывать штрихкоды DataMatrix с структурным добавлением.

## Импорт пространств имён

Первый шаг — импортировать пространства имён, которые предоставляют API штрихкодов.

Класс `BarCodeWriter` является точкой входа Aspose.BarCode для создания штрихкодов, а `BarCodeReader` отвечает за декодирование.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Теперь, когда вы импортировали необходимые пространства имён, давайте сгенерируем штрихкод с структурным добавлением.

## Как считывать штрихкоды DataMatrix с структурным добавлением?
Загрузите сгенерированное изображение (или поток) в `BarCodeReader`, включите опцию `ReadStructuredAppend` и вызовите `ReadBarcode`. Читатель автоматически вернёт объединённые данные и предоставит детали последовательности, такие как `StructuredAppendFileId`, `StructuredAppendTotalCount` и `StructuredAppendSegmentId`. Объединённый результат возвращается в виде одной строки, а также вы можете получить отдельные идентификаторы сегментов через свойство `StructuredAppendSegmentId` читателя для пользовательской обработки.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

На этом этапе мы используем читатель для извлечения идентификатора штрихкода, общего количества и идентификатора файла, подтверждая, что конфигурация структурного добавления была правильно интерпретирована.

## Шаг 1: Настройка конфигурации структурного добавления DataMatrix
Для создания штрихкода DataMatrix с структурным добавлением необходимо настроить его конфигурацию. Это включает определение пути к каталогу, идентификатора штрихкода, количества штрихкодов и идентификатора файла.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

На этом этапе мы настроили штрихкод DataMatrix с желаемыми параметрами.

## Распространённые проблемы и решения
- **Неправильный порядок сегментов:** Убедитесь, что значения `StructuredAppendSegmentId` идут последовательно, начиная с 0; иначе читатель не сможет правильно собрать данные.
- **Несоответствие общего количества:** `StructuredAppendTotalCount` должен быть одинаковым для всех символов; несоответствие приведёт к тому, что читатель будет считать последовательность неполной.
- **Качество изображения:** Изображения низкого разрешения могут вызывать ошибки декодирования. Стремитесь к минимуму **300 dpi** при рендеринге штрихкода в bitmap.

## Часто задаваемые вопросы

### Q1: Что такое DataMatrix structured append и зачем он используется?
A1: Структурное добавление DataMatrix — это функция, позволяющая разбить большой объём данных на несколько более мелких штрихкодов. Это особенно полезно, когда пространство для одного штрихкода ограничено или требуется эффективная организация данных. Широко используется в логистике, здравоохранении и производстве.

### Q2: Могу ли я использовать Aspose.BarCode для .NET в своём open‑source проекте?
A2: Да, Aspose.BarCode для .NET предлагает бесплатную пробную версию, которую можно использовать в open‑source проектах. Вы можете найти пробную версию [здесь](https://releases.aspose.com/).

### Q3: Есть ли поддержка сообщества для Aspose.BarCode для .NET?
A3: Да, вы можете получить поддержку сообщества и взаимодействовать с другими пользователями на форуме Aspose.BarCode [здесь](https://forum.aspose.com/c/barcode/13).

### Q4: Как получить временную лицензию для Aspose.BarCode для .NET?
A4: Если вам нужна временная лицензия для оценки или тестирования, вы можете получить её [здесь](https://purchase.aspose.com/temporary-license/).

### Q5: Поддерживает ли Aspose.BarCode для .NET другие типы штрихкодов?
A5: Да, Aspose.BarCode для .NET поддерживает широкий спектр типов штрихкодов, включая QR‑коды, Code 128, EAN‑13 и многие другие. Вы можете ознакомиться с полной документацией [здесь](https://reference.aspose.com/barcode/net/) чтобы увидеть полный список поддерживаемых типов штрихкодов.

---

**Последнее обновление:** 2026-06-14  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства
- [Программирование чтения DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Генерация штрихкодов DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Мастер конфигурации макросов DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}