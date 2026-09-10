---
date: 2026-06-09
description: Узнайте, как генерировать штрих‑код DataMatrix с помощью Aspose.BarCode
  для .NET, настраивать соотношения сторон, режимы ECC и кодирование DataMatrix C40
  для эффективного создания штрих‑кодов.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Настройка штрих‑кода DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создание штрих‑кода DataMatrix – профессиональное руководство с Aspose.BarCode
url: /ru/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода DataMatrix – Профессиональное руководство с Aspose.BarCode

Добро пожаловать в наш всесторонний учебный цикл по **generate datamatrix barcode** с использованием Aspose.BarCode для .NET. Независимо от того, являетесь ли вы опытным разработчиком, оттачивающим вывод штрих‑кода, или новичком, желающим понять основы, это руководство проведёт вас через каждый шаг — от базовой конфигурации до продвинутых техник кодирования — чтобы вы могли создавать надёжные, готовые к сканированию штрих‑коды в любом приложении .NET.

## Быстрые ответы
- **Какова основная цель?** Создавать и настраивать штрих‑коды DataMatrix программно.  
- **Какая библиотека используется?** Aspose.BarCode for .NET.  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшна требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Можно ли настроить соотношение сторон?** Да — см. раздел «Как настроить соотношение сторон DataMatrix».

## Что такое generate datamatrix barcode?
Штрих‑код DataMatrix — это двумерная матрица из чёрных и белых ячеек, способная хранить до 2 300 буквенно‑цифровых символов. С помощью Aspose.BarCode вы можете **generate datamatrix barcode** изображения, PDF или SVG напрямую из вашего кода .NET, управляя размером, уровнем коррекции ошибок и режимом кодирования, чтобы соответствовать любому отраслевому стандарту.

## Почему стоит использовать Aspose.BarCode для DataMatrix?
Aspose.BarCode отображает символы DataMatrix с разрешением до **600 dpi** без пикселизации, гарантируя чёткое сканирование на принтерах высокого разрешения. Он поддерживает **все более 50 режимов ECC и macro** — включая ECC 000‑140, ECC 200 и Macro 05/06 — так что вы можете выбрать оптимальный уровень коррекции ошибок для размера ваших данных. API предлагает варианты кодирования **ASCII, C40, Text, X12 и Bytes**, позволяя эффективно упаковывать данные. Интеграция требует только один пакет NuGet и не требует внешних нативных библиотек.

## Как настроить соотношение сторон DataMatrix
Свойство `AspectRatio` класса `BarCodeGenerator` управляет пропорцией ширины к высоте генерируемого символа DataMatrix. `BarCodeGenerator` — основной класс в Aspose.BarCode, используемый для создания изображений штрих‑кодов.

**Direct answer:** Установите `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (или любое значение от 0.5 до 2.0) перед вызовом `GenerateBarCodeImage()`. Библиотека автоматически пересчитывает размер модуля, чтобы сохранить надёжность сканирования, соблюдая запрошенное соотношение.

### Пошагово
1. **Создать экземпляр** `BarCodeGenerator` с `EncodeTypes.DataMatrix`.  
2. **Настроить** `AspectRatio` до нужного значения.  
3. **Сгенерировать** изображение и проверить его сканером или встроенным считывателем Aspose.

## Как генерировать штрих‑коды DataMatrix ECC 000‑140
ECC 000‑140 идеален для коротких строк данных, где требуется компактный символ, предоставляя до 140 кодовых слов коррекции ошибок. `DataMatrixEccMode.Ecc000140` выбирает схему коррекции ошибок ECC 000‑140 для DataMatrix.

**Direct answer:** Примените `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` перед рендерингом. Это переключает кодировщик на алгоритм ECC 000‑140, создавая наименьшую возможную матрицу для заданных данных при сохранении надёжной коррекции ошибок.

### Практический совет
При кодировании числовых данных менее 20 символов ECC 000‑140 часто даёт матрицу 10 × 10, что экономит ценное пространство этикетки.

## Как генерировать штрих‑коды DataMatrix ECC 200
ECC 200 — самый широко используемый режим DataMatrix, поддерживающий до 2 335 буквенно‑цифровых символов и обеспечивающий превосходную коррекцию ошибок. `DataMatrixEccMode.Ecc200` выбирает схему коррекции ошибок ECC 200 для DataMatrix.

**Direct answer:** Установите `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` и задайте полезную нагрузку через `CodeText`. Библиотека затем автоматически выбирает оптимальный размер матрицы.

### Когда предпочитать ECC 200
Используйте ECC 200 для более длинных строк, смешанных данных или когда требуется наибольшая устойчивость к повреждениям — до **30 %** символа может быть восстановлено.

## Как освоить кодирование DataMatrix в режиме ASCII
Режим ASCII кодирует символы, используя один байт на символ, что делает его самым экономичным по объёму для простого текста. `DataMatrixEncodeMode.Ascii` указывает генератору использовать кодирование ASCII для символа DataMatrix.

**Direct answer:** Присвойте `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` и задайте `CodeText` вашей ASCII‑строкой. Движок упаковывает данные без лишних накладных расходов, создавая наименьшую возможную матрицу для чистого ASCII‑контента.

### Пример сценария
SKU склада, состоящий из заглавных букв и цифр (например, “AB1234”), идеально подходит для режима ASCII, часто получая матрицу 12 × 12.

## Как генерировать DataMatrix в режиме (Auto)
Режим Auto позволяет Aspose.BarCode анализировать ввод и автоматически выбирать наиболее эффективное кодирование (ASCII, C40, Text, X12 или Bytes). `DataMatrixEncodeMode.Auto` включает эту функцию автоматического выбора.

**Direct answer:** Установите `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Библиотека оценивает полезную нагрузку, выбирает оптимальный режим и генерирует штрих‑код за один шаг.

### Преимущества
Режим Auto снижает затраты на разработку и гарантирует наименьший возможный символ для смешанных данных, повышая скорость сканирования.

## Как использовать режим кодирования DataMatrix (Bytes)
Режим Bytes предназначен для бинарных данных, таких как зашифрованные полезные нагрузки или сжатые файлы. `DataMatrixEncodeMode.Bytes` указывает генератору рассматривать каждый байт как необработанные данные.

**Direct answer:** Используйте `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` и задайте строку, закодированную в Base64, как `CodeText`. Кодировщик рассматривает каждый байт как необработанные данные, сохраняя точное бинарное представление.

### Сценарий использования
Встраивание 128‑битного GUID или небольшого зашифрованного токена непосредственно в символ DataMatrix.

## Как освоить режим кодирования DataMatrix (C40)
Режим C40 сжимает заглавные буквенно‑цифровые данные, достигая сокращения размера до **40 %** по сравнению с ASCII. `DataMatrixEncodeMode.C40` активирует этот алгоритм сжатия.

**Direct answer:** Установите `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` и передайте строку в верхнем регистре (например, “HELLO WORLD”). Движок упаковывает три символа в два кодовых слова, уменьшая конечную матрицу.

### Профессиональный совет
C40 работает лучше всего, когда полезная нагрузка состоит преимущественно из заглавных букв, цифр и пробелов. Для смешанного регистра рекомендуется режим Auto.

## Как настроить текст кода DataMatrix
Свойство `CodeText` определяет точные данные, хранящиеся в штрих‑коде. Оно может включать простой текст, числовые строки или даже XML‑полезные нагрузки. `CodeText` — основной строковый параметр `BarCodeGenerator`, содержащий полезную нагрузку штрих‑кода.

**Direct answer:** Присвойте `generator.Parameters.Barcode.CodeText = "YourDataHere"` перед рендерингом. Свойство принимает любую строку UTF‑8 до максимальной длины, поддерживаемой выбранным режимом ECC.

### Продвинутый совет
Сочетайте `CodeText` с `ExtendedDataMatrix`, чтобы внедрять дополнительную метадату без увеличения видимого размера матрицы.

## Как освоить конфигурацию макросов DataMatrix
Режимы Macro (Macro 05 и Macro 06) позволяют встраивать вторичный символ DataMatrix в основной, что полезно для ссылки на внешние источники данных. `DataMatrixMacroMode.Macro05` и `DataMatrixMacroMode.Macro06` включают эти макро‑функции.

**Direct answer:** Включите макро‑режим с помощью `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (или `Macro06`) и задайте свойства `MacroPdf417` для вторичной полезной нагрузки. Генератор создаёт составной символ, который сканеры могут интерпретировать как два связанных кода.

### Пример из реального мира
Встраивание URL в макро‑часть при сохранении идентификаторов продукта в основном символе, обеспечивая бесшовную интеграцию web‑to‑barcode.

---

*Список учебных материалов Aspose.BarCode для .NET*

## Учебные материалы по конфигурации штрих‑кода DataMatrix
### [Настройка соотношения сторон DataMatrix](./datamatrix-aspect-ratio-customization/)
Узнайте, как настраивать соотношение сторон штрих‑кода DataMatrix с помощью Aspose.BarCode для .NET. Пошаговое руководство по генерации штрих‑кодов.
### [Генерация штрих‑кодов DataMatrix ECC 000-140](./datamatrix-ecc-000-140-configuration/)
Создавайте штрих‑коды DataMatrix ECC 000-140 с лёгкостью, используя Aspose.BarCode для .NET. Повышайте эффективность управления запасами и не только.
### [Генерация штрих‑кодов DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Узнайте, как генерировать штрих‑коды DataMatrix ECC 200 в .NET с помощью Aspose.BarCode. Оптимизируйте операции с помощью эффективного создания штрих‑кодов.
### [Освоение кодирования DataMatrix в ASCII](./datamatrix-encoding-mode-ascii/)
Научитесь создавать штрих‑коды DataMatrix в режиме ASCII с помощью Aspose.BarCode для .NET. Пошаговое руководство для разработчиков.
### [Генерация режима DataMatrix (Auto)](./datamatrix-encoding-mode-auto/)
Узнайте, как генерировать режим DataMatrix (Auto) с помощью Aspose.BarCode для .NET. Это пошаговое руководство охватывает всё от предварительных требований до чтения штрих‑кодов.
### [Режим кодирования DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Узнайте, как кодировать данные в формате DataMatrix, используя режим Bytes с Aspose.BarCode для .NET. Следуйте нашему пошаговому руководству по генерации и распознаванию штрих‑кодов.
### [Освоение режима кодирования DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Освойте режим кодирования DataMatrix (C40) с Aspose.BarCode для .NET. Эффективно создавайте пользовательские штрих‑коды. Изучите пошаговое руководство.
### [Настройка текста кода DataMatrix](./datamatrix-extended-code-text-configuration/)
Узнайте, как настраивать расширенный текст кода DataMatrix с помощью Aspose.BarCode для .NET. Генерируйте, распознавайте и интегрируйте штрих‑коды в ваши .NET‑приложения.
### [Освоение конфигурации макросов DataMatrix](./datamatrix-macro-configuration/)
Узнайте, как настраивать макро‑штрих‑коды DataMatrix с помощью Aspose.BarCode для .NET. Генерируйте, настраивайте и распознавайте штрих‑коды DataMatrix в ваших .NET‑приложениях.

## Часто задаваемые вопросы

**Q: Как мне решить, какой режим ECC использовать?**  
A: Выбирайте ECC 000‑140 для небольших наборов данных с ограниченной коррекцией ошибок, либо ECC 200 для больших данных и более высокой надёжности. Режим Macro добавляет дополнительный слой данных для связывания.

**Q: Могу ли я встроить пользовательский текст в штрих‑код DataMatrix?**  
A: Да, задайте свойство `CodeText` своей пользовательской строкой, затем выберите соответствующий режим кодирования (ASCII, C40 и т.д.), чтобы контролировать размер.

**Q: Есть ли способ автоматически выбрать лучший режим кодирования?**  
A: Установите `EncodeMode` в `Auto`; Aspose.BarCode оценивает полезную нагрузку и автоматически выбирает наиболее экономичный по объёму режим.

**Q: Какие соображения по производительности при работе с большими партиями штрих‑кодов?**  
A: Повторно используйте один экземпляр `BarCodeGenerator`, включайте многопоточность и генерируйте PNG‑изображения для без потерь качества или JPEG для меньшего размера файла. Обработка 10 000 символов обычно завершается менее чем за 30 секунд на стандартном 8‑ядерном сервере.

**Q: Поддерживает ли Aspose.BarCode .NET Core и .NET 5/6?**  
A: Абсолютно — библиотека полностью совместима с .NET Framework, .NET Core и последними версиями .NET, предоставляя одинаковый набор функций на всех платформах.

**Последнее обновление:** 2026-06-09  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose

## Связанные учебные материалы
- [Как генерировать штрих‑коды DataMatrix (ECC 200) с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Освоение кодирования DataMatrix в ASCII с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Создание PNG штрих‑кода — соотношение сторон DataMatrix — Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}