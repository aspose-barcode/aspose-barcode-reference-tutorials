---
date: 2026-06-29
description: Узнайте, как генерировать штрих‑код Codabar с контрольной суммой, используя
  Aspose.BarCode для .NET. Пошаговое руководство, охватывающее режимы контрольных
  сумм Mod10 и Mod16.
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Вычисление контрольной суммы Codabar
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Генерация штрих‑кода Codabar с контрольной суммой (Aspose.BarCode .NET)
url: /ru/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать штрих‑код Codabar с контрольной суммой (Aspose.BarCode .NET)

Codabar — это широко используемая линейная система штрих‑кодов, применяемая в логистике, библиотеках и здравоохранении. **Создание штрих‑кода Codabar с контрольной суммой** значительно повышает целостность данных, обнаруживая ошибки ввода до того, как они приведут к проблемам. В этом руководстве вы узнаете, как добавить контрольную сумму при *создании штрих‑кода Codabar* с помощью Aspose.BarCode для .NET, а также увидите работу режимов контрольных сумм Mod10 и Mod16.

## Быстрые ответы
- **Что означает «добавить контрольную сумму» для Codabar?** Это добавляет цифру обнаружения ошибок, которая проверяет закодированные данные.  
- **Какие режимы контрольных сумм поддерживаются?** Mod10 (стандартный) и Mod16 (повышенной точности).  
- **Нужна ли лицензия для использования функции?** Да — для продакшн‑использования требуется действующая лицензия Aspose.BarCode для .NET.  
- **Какие версии .NET совместимы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Где сохраняются сгенерированные изображения?** В папку, указанную в переменной `path`.

## Как создать штрих‑код Codabar с контрольной суммой?

Загрузите ваши данные, включите контрольную сумму, выберите `CodabarChecksumMode.Mod10` или `CodabarChecksumMode.Mod16` и вызовите `Save`. Aspose.BarCode выполняет вычисление и автоматически добавляет цифру контрольной суммы, поэтому вы получаете готовое к сканированию изображение одним вызовом метода. При сохранении также можно указать папку вывода, имя файла и формат изображения (например, PNG).

## Зачем добавлять контрольную сумму к штрих‑коду Codabar?

Добавление контрольной суммы уменьшает количество односимвольных ошибок **до 99,9 %** и обнаруживает большинство ошибок перестановки, что критически важно для отраслей, таких как банки крови, где ошибка в одной цифре может иметь серьёзные последствия. Это также обеспечивает соответствие нормативным требованиям многих логистических стандартов.

## Предварительные требования

1. **Aspose.BarCode for .NET** — загрузите последнюю версию по ссылке [here](https://releases.aspose.com/barcode/net/).  
2. **C# development environment** — Visual Studio, VS Code или любой IDE, поддерживающий .NET.

Теперь, когда всё готово, давайте пройдёмся по реализации.

## Импорт пространств имён

Класс `BarcodeGenerator` находится в пространстве имён `Aspose.BarCode.Generation`. Импортируйте его в начале вашего файла:

`using Aspose.BarCode.Generation;`

## Что такое класс BarcodeGenerator?

Класс `BarcodeGenerator` — это основной объект Aspose.BarCode, который создаёт, настраивает и рендерит изображение штрих‑кода. Он инкапсулирует все настройки, специфичные для штрих‑кода, такие как символьный набор, текст, размер и параметры контрольной суммы, позволяя генерировать изображения одним вызовом `Save`. Изменяя свойство `Parameters`, вы можете настраивать внешний вид, режим кодирования и функции обнаружения ошибок для любого поддерживаемого типа штрих‑кода.

## Шаг 1: Инициализация генератора штрих‑кода

Создайте экземпляр `BarcodeGenerator`, укажите символьный набор Codabar и предоставьте данные, которые нужно закодировать. Замените `"Your Directory Path"` реальной папкой, в которой вы хотите сохранять изображения.

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## Шаг 2: Создание штрих‑кода Codabar **без** контрольной суммы

Если устаревшая система ожидает простой штрих‑код, установите параметр контрольной суммы в `Default`. Это отключит добавление дополнительной цифры.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## Шаг 3: Создание штрих‑кода Codabar с контрольной суммой **Mod10**

Включите контрольную сумму и выберите алгоритм Mod10, который является самым распространённым режимом для Codabar.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## Шаг 4: Создание штрих‑кода Codabar с контрольной суммой **Mod16**

Для сценариев с более высоким уровнем обнаружения ошибок переключитесь на Mod16. Изменение ограничивается единственной установкой свойства.

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

С помощью этих четырёх простых шагов вы узнали **как создавать штрих‑код Codabar** с контрольной суммой и как переключаться между режимами Mod10 и Mod16 с помощью Aspose.BarCode для .NET.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| Сгенерированное изображение пустое | `path` указывает на несуществующую папку | Убедитесь, что каталог существует, или вызовите `Directory.CreateDirectory(path)` перед сохранением |
| Контрольная сумма не применена | `IsChecksumEnabled` оставлен в значении `Default` | Установите `IsChecksumEnabled = EnableChecksum.Yes` перед сохранением |
| Неправильный режим контрольной суммы | Используется неверное значение перечисления | Используйте `CodabarChecksumMode.Mod10` или `CodabarChecksumMode.Mod16` по необходимости |

## Часто задаваемые вопросы

**Q: Можно ли использовать контрольную сумму Mod16 для штрих‑кодов книг в библиотеке?**  
A: Конечно. Mod16 обеспечивает более надёжное обнаружение ошибок, что полезно в средах с высоким пропускным способностью, таких как библиотеки.

**Q: Влияет ли включение контрольной суммы на скорость сканирования?**  
A: Дополнительная цифра добавляет незначительное время обработки; большинство сканеров обрабатывают её без заметных задержек.

**Q: Как программно проверить контрольную сумму?**  
A: После генерации штрих‑кода пересчитайте контрольную сумму, используя тот же `CodabarChecksumMode`, и сравните её с последним символом закодированной строки.

**Q: Можно ли настроить внешний вид цифры контрольной суммы?**  
A: Да. Используйте настройки внешнего вида `BarcodeGenerator` (например, `BarHeight`, `ForeColor`), чтобы оформить весь штрих‑код, включая цифру контрольной суммы.

**Q: Что делать, если нужно генерировать несколько штрих‑кодов в цикле?**  
A: Создайте один экземпляр `BarcodeGenerator`, обновляйте свойство `CodeText` для каждой итерации и вызывайте `Save` с уникальным именем файла каждый раз.

Если у вас возникнут сложности, сообщество Aspose.BarCode готово помочь на форуме [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

**Последнее обновление:** 2026-06-29  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## Связанные руководства

- [Создать штрих‑код Codabar с символами начала/конца в Aspose.BarCode для .NET](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Полные руководства и примеры Aspose.BarCode для .NET](/barcode/net/)
- [Создать штрих‑код DataMatrix — профессиональное руководство с Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}