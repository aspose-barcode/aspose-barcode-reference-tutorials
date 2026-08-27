---
date: 2026-05-24
description: Узнайте, как создавать aztec barcode .NET с использованием Aspose.BarCode
  для .NET, охватывая режимы символов Auto, FullRange, Compact и Rune, с пошаговым
  руководством.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Пример режима символов Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создание Aztec Barcode .NET с Aspose.BarCode
url: /ru/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение режима символов Aztec с Aspose.BarCode для .NET

Если вы хотите **быстро и надёжно создавать Aztec‑штрихкоды в .NET**, Aspose.BarCode для .NET предоставляет полнофункциональный API, работающий на .NET Framework, .NET Core и .NET 5/6+. В этом руководстве мы рассмотрим четыре режима символов Aztec — Auto, FullRange, Compact и Rune — покажем, как переключаться между ними и сохранять результат в виде изображения. К концу вы сможете внедрять Aztec‑штрихкоды в любое .NET‑приложение, используя всего несколько строк кода.

## Быстрые ответы
- **Какая библиотека генерирует Aztec‑штрихкоды в .NET?** Aspose.BarCode для .NET.  
- **Сколько режимов символов поддерживает Aztec?** Четыре: Auto, FullRange, Compact и Rune.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для оценки; для продакшна требуется коммерческая лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ и .NET 6+.  
- **Можно ли выводить PNG, JPEG или SVG?** Да — поддерживаются все стандартные форматы изображений.

## Что такое create aztec barcode .net?
`create aztec barcode .net` обозначает процесс генерации двумерного штрихкода Aztec с помощью API Aspose.BarCode в среде .NET. API автоматически обрабатывает кодирование, выбор режима символов и рендеринг изображения, позволяя разработчикам получать штрихкоды высокого качества без работы с низкоуровневыми деталями, такими как расчёт коррекции ошибок или манипуляция пикселями.

## Почему стоит использовать Aspose.BarCode для Aztec‑штрихкодов?
Aspose.BarCode поддерживает **более 30 символогий** и может рендерить изображения размером до **10 000 × 10 000 px** без загрузки всего файла в память. Он обрабатывает документ из 500 страниц менее чем за **2 секунды** на типичном сервере, что делает его идеальным для высокопроизводительных корпоративных сценариев.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть следующее:

- Практические навыки разработки на .NET.  
- Установленная Visual Studio.  
- Копия Aspose.BarCode для .NET. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/net/). Также можете ознакомиться с другими продуктами Aspose [здесь](https://releases.aspose.com/).

Теперь, когда всё готово, приступим к примерам режимов символов Aztec.

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён для работы с Aspose.BarCode для .NET. Откройте проект в Visual Studio и добавьте следующие директивы using в начало вашего файла кода:

```csharp
using Aspose.BarCode.Generation;
```

После подключения пространств имён вы можете приступить к использованию Aspose.BarCode для .NET.

## Как настроить BarcodeGenerator для Aztec‑штрихкодов?

Класс `BarcodeGenerator` — основной компонент, создающий изображения штрихкодов на основе выбранной символогии и параметров конфигурации. Он предоставляет простой API для указания типа штрихкода, данных для кодирования и различных параметров рендеринга перед сохранением результата в файл изображения.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

На этом этапе мы настроили генератор и задали текст кода для кодирования.

## Как установить режим символов Aztec в Auto?

Перечисление `AztecSymbolMode` определяет четыре возможных режима символов для Aztec‑штрихкодов, а опция **Auto** позволяет библиотеке автоматически выбирать наиболее компактный размер, сохраняя все требования к данным и коррекции ошибок. Этот режим идеален для большинства сценариев, когда нужен наименьший возможный штрихкод без ручной настройки.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Этот шаг гарантирует автоматический выбор режима символов Aztec, а полученный штрихкод сохраняется в виде изображения.

## Как принудительно установить режим FullRange?

Когда требуется максимальная ёмкость данных, можно выбрать значение **FullRange** перечисления `AztecSymbolMode`. Этот режим отключает автоматическое уменьшение размера, позволяя штрихкоду хранить полный диапазон символов и достигать наивысшей плотности информации, что полезно для больших наборов данных.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Это создаст штрихкод с режимом FullRange Aztec Symbol Mode.

## Как сгенерировать компактный Aztec‑штрихкод?

Значение **Compact** перечисления `AztecSymbolMode` создаёт более маленький штрихкод за счёт уменьшения количества слоёв в матрице. Это приводит к более экономичному использованию пространства, что подходит для приложений с ограниченной площадью отображения, таких как мобильные экраны или небольшие этикетки.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Этот шаг настраивает генерацию штрихкода в компактном режиме Aztec Symbol Mode.

## Как создать Rune‑Aztec‑штрихкод?

Режим **Rune** — специализированный вариант символогии Aztec, который кодирует числовые данные с помощью пользовательского набора символов, предлагая отличительный визуальный стиль при сохранении той же силы коррекции ошибок, что и другие режимы. Он полезен, когда необходимо подчеркнуть числовую информацию.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Этот шаг меняет текст кода на «123» и генерирует штрихкод в режиме Rune Aztec Symbol Mode.

## Распространённые проблемы и решения

- **Изображение не сохраняется** — Убедитесь, что папка вывода существует и приложение имеет права записи.  
- **Неожиданный размер символа** — Проверьте, что вы не переопределили `EncodeMode` где‑то ещё в коде.  
- **Исключение лицензии** — Пробная версия добавляет водяной знак; примените действующую лицензию, чтобы убрать его.

## Часто задаваемые вопросы

**В: Какова цель режима Symbol Mode в генерации Aztec‑штрихкодов?**  
О: Режим Symbol Mode определяет, как библиотека упаковывает данные в слои, влияя на размер, ёмкость и читаемость.

**В: Можно ли изменить текст кода для Aztec‑штрихкодов в Aspose.BarCode для .NET?**  
О: Да, просто присвойте новое значение свойству `CodeText` перед вызовом `Save`.

**В: Доступна ли бесплатная пробная версия Aspose.BarCode для .NET?**  
О: Да, бесплатную пробную версию Aspose.BarCode для .NET можно скачать [здесь](https://releases.aspose.com/).

**В: Где найти полную документацию по Aspose.BarCode для .NET?**  
О: Полную документацию по Aspose.BarCode для .NET можно посмотреть [здесь](https://reference.aspose.com/barcode/net/).

**В: Как получить временную лицензию для Aspose.BarCode для .NET?**  
О: Временную лицензию для Aspose.BarCode для .NET можно получить, перейдя по [этой ссылке](https://purchase.aspose.com/temporary-license/).

## Заключение

В этом руководстве мы рассмотрели, как **create aztec barcode .net** с помощью Aspose.BarCode, охватив режимы Auto, FullRange, Compact и Rune. Теперь у вас есть надёжная база для внедрения универсальных Aztec‑штрихкодов в любые .NET‑приложения, будь то настольные программы, веб‑серверы или облачные сервисы.

Если у вас есть вопросы или нужна дополнительная помощь, не стесняйтесь обращаться к сообществу Aspose.BarCode на их [форуме поддержки](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-05-24  
**Тестировано с:** Aspose.BarCode 24.11 для .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Aztec Bytes Encoding using barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [How to create Aztec barcode with error correction in .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}