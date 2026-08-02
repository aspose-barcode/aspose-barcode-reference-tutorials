---
date: 2026-08-02
description: Пошаговое руководство по чтению DataMatrix barcode C# и генерации изображения
  barcode C# с использованием Aspose.BarCode for .NET с авто‑кодированием.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Режим кодирования DataMatrix (Auto)
og_description: Узнайте, как читать DataMatrix barcode C# и генерировать его в режиме
  Auto с помощью Aspose.BarCode for .NET. Этот учебник охватывает настройку, код и
  устранение неполадок.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Как читать DataMatrix barcode C# – Auto mode
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Как читать DataMatrix barcode C# – Auto mode
url: /ru/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать DataMatrix штрих‑код C# – Авто режим

В современном быстро меняющемся цифровом мире **how to read datamatrix** быстро и надёжно является ключевым для учёта запасов, безопасного обращения с документами и множества других корпоративных сценариев. В этом руководстве мы покажем, как сгенерировать DataMatrix штрих‑код в режиме *Auto* с помощью Aspose.BarCode для .NET, а затем как считать этот штрих‑код в C#. Независимо от того, следуете ли вы руководству по штрих‑коду или вам нужен готовый пример кода, вы получите готовое к продакшн‑использованию решение, которое можно добавить в любой проект .NET.

## Быстрые ответы
- **Что делает режим “Auto”?** Он позволяет Aspose.BarCode автоматически выбирать лучшую схему кодирования для ваших данных.  
- **Какая библиотека требуется?** Aspose.BarCode for .NET (доступна бесплатная пробная версия).  
- **Могу ли я считывать штрих‑код в том же приложении?** Да — используйте `BarCodeReader` с `DecodeType.DataMatrix`.  
- **Нужна ли лицензия для продакшн‑среды?** Для использования в продакшн‑среде требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` — класс Aspose.BarCode для сканирования изображений и получения информации о штрих‑коде.

## Что такое чтение DataMatrix штрих‑кода C#?
Чтение DataMatrix штрих‑кода в C# означает декодирование двумерной матрицы чёрных и белых модулей обратно в исходный текст или данные. Aspose.BarCode абстрагирует низкоуровневую обработку изображений, позволяя сосредоточиться на бизнес‑логике, пока библиотека автоматически обрабатывает коррекцию ошибок, выбор размера символа и поддержку Unicode.

## Почему использовать Aspose.BarCode для генерации изображения штрих‑кода C#?
Aspose.BarCode автоматически выбирает оптимальное кодирование, поддерживает **30+ barcode symbologies**, и может генерировать DataMatrix символы размером до **1558 × 1558 модулей** — значительно больше, чем у большинства конкурентов. Он работает на Windows, Linux и macOS без нативных зависимостей, предоставляя единый кроссплатформенный API как для генерации, так и для чтения.

## Предварительные требования

1. **Среда .NET** – Установите последнюю среду выполнения .NET с сайта [веб‑сайт .NET](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Скачайте библиотеку с [веб‑сайта](https://releases.aspose.com/barcode/net/).  

## Импорт пространств имён
Пространство имён `Aspose.BarCode` содержит все необходимые классы для создания и чтения штрих‑кодов. Импортируйте его в начале файла перед любым другим кодом.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Теперь, когда пространства имён импортированы, давайте пройдёмся по коду шаг за шагом.

## Шаг 1: Установите путь к каталогу
Выберите папку, в которой будет сохранён сгенерированный PNG (или любой поддерживаемый формат). Этот путь может быть абсолютным или относительным к вашему проекту.

```csharp
string path = "Your Directory Path";
```

Замените `"Your Directory Path"` на предпочитаемую папку. Возможность конфигурировать выходную папку делает руководство переиспользуемым в разных средах.

## Шаг 2: Создайте DataMatrix штрих‑код в режиме Auto
`DataMatrixEncodeMode.Auto` сообщает генератору автоматически выбирать оптимальную схему кодирования для переданных данных.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Не стесняйтесь заменить пример текста любой строкой, для которой вам нужно **how to generate datamatrix**. Режим Auto автоматически переключится между Base‑256, ASCII или другими схемами, чтобы получить наименьший возможный символ.

## Шаг 3: Считайте штрих‑код (чтение DataMatrix штрих‑кода C#)
`BarCodeReader` — класс Aspose.BarCode для сканирования изображений и получения информации о штрих‑коде. Он поддерживает чтение из потоков, файлов и объектов bitmap, что делает его идеальным для сценариев **read barcode from file**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Этот фрагмент кода декодирует только что сгенерированное изображение и выводит исходный текст в консоль, демонстрируя полный цикл от генерации до чтения.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Штрих‑код не обнаружен** | Разрешение изображения слишком низкое | Увеличьте `XDimension.Pixels` (например, до 6) |
| **Неправильные символы** | Неправильное кодирование ECI | Установите `ECIEncoding` в соответствии с вашими данными (UTF‑8, ASCII и т.д.) |
| **Исключение при `ReadBarCodes`** | Bitmap освобождён до чтения | Сохраните экземпляр `Bitmap` живым до завершения чтения |

## Часто задаваемые вопросы

**Q: Что такое режим кодирования DataMatrix “Auto”?**  
A: Он позволяет Aspose.BarCode автоматически выбирать оптимальный метод кодирования для предоставленных данных, упрощая процесс **how to generate datamatrix**.

**Q: Могу ли я настроить размеры генерируемого штрих‑кода?**  
A: Да — измените `generator.Parameters.Barcode.XDimension.Pixels`, чтобы задать размер модуля.

**Q: Подходит ли Aspose.BarCode for .NET для коммерческого использования?**  
A: Абсолютно. Приобретите лицензию на [веб‑сайте](https://purchase.aspose.com/buy).

**Q: Доступна ли бесплатная пробная версия?**  
A: Да, вы можете опробовать Aspose.BarCode с бесплатной пробной версией по [этой ссылке](https://releases.aspose.com/).

**Q: Какие варианты кодирования доступны для DataMatrix штрих‑кодов?**  
A: Aspose.BarCode поддерживает UTF‑8, ASCII и другие кодировки ECI; задайте нужное значение через `ECIEncoding`.

## Заключение

Теперь у вас есть полностью готовый к продакшн‑использованию пример, который **reads DataMatrix barcode C#**, генерирует штрих‑код в режиме Auto и проверяет результат — всё с помощью Aspose.BarCode для .NET. Экспериментируйте с разными текстами, размерами и настройками ECI, чтобы подобрать оптимальное решение для вашего сценария, и обратитесь к официальной [документации](https://reference.aspose.com/barcode/net/) для более глубокой настройки.

---

**Последнее обновление:** 2026-08-02  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как считывать DataMatrix штрих‑коды с помощью Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/)
- [Конфигурация Structured Append для DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Программирование чтения DataMatrix с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}