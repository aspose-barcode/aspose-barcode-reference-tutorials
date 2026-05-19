---
date: 2026-05-19
description: Узнайте, как создать Aztec barcode с помощью Aspose.BarCode for .NET,
  настроить aspect ratios, закодировать bytes или text, а также использовать master
  symbol modes.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Кодирование Aztec Barcode
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Как создать Aztec barcode с Aspose.BarCode for .NET
url: /ru/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Кодирование штрихкода Aztec

## Быстрые ответы
- **Какая библиотека поддерживает штрихкоды Aztec?** Aspose.BarCode for .NET  
- **Можно ли изменить соотношение сторон?** Да, через свойство `AspectRatio`  
- **Возможна ли кодировка на уровне байтов?** Абсолютно — используйте метод `EncodeBytes`  
- **Какие уровни коррекции ошибок доступны?** Уровни 0 до 4 (чем выше, тем больше избыточности)  
- **Нужна ли лицензия для продакшна?** Да, коммерческая лицензия снимает ограничения оценки  

## Что такое штрихкод Aztec?
Штрихкод Aztec — это двумерный матричный код, который может кодировать до 3 000 цифровых или 2 300 буквенно-цифровых символов. Он содержит центральный паттерн поиска, обеспечивая быструю сканировку даже при печати символа в низком разрешении. Поскольку паттерн расположен в центре, код можно считывать с любой стороны, что делает его высоконадежным для мобильных и промышленных приложений.

## Как настроить соотношение сторон штрихкода Aztec?
`BarcodeGenerator` — основной класс, используемый для создания штрихкодов в Aspose.BarCode. Установите свойство `AspectRatio` у объекта `BarcodeGenerator` в нужное соотношение ширины к высоте, затем сгенерируйте изображение. Настройка соотношения сторон помогает разместить штрихкод в ограниченных пространствах UI или макетах этикеток без потери надёжности сканирования, а также позволяет соответствовать требованиям бренда или конкретным требованиям принтера.

### Шаги по настройке соотношения сторон
1. **Создайте экземпляр `BarcodeGenerator`** с `EncodeTypes.Aztec`.  
2. **Назначьте ваши данные** (текст, байты или числовую строку).  
3. **Установите `AspectRatio`** — например, `1.5` для более широкой полосы.  
4. **Сгенерируйте изображение** с помощью `Save` или `GetBarCodeImage`.  

## Как закодировать необработанные байты в штрихкод Aztec?
`EncodeBytes` — метод, принимающий массив байтов и преобразующий его в матрицу Aztec. Передайте массив байтов в метод `EncodeBytes` объекта `BarcodeGenerator`. API автоматически преобразует бинарные данные в компактную матрицу Aztec, сохраняя каждый бит. Это идеально для встраивания зашифрованных полезных нагрузок, бинарных идентификаторов или сжатых файлов непосредственно в штрихкод.

### Шаги по кодированию байтов
1. **Подготовьте массив байтов** (например, `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Создайте экземпляр `BarcodeGenerator`** с `EncodeTypes.Aztec`.  
3. **Вызовите `EncodeBytes(data)`** для загрузки бинарного содержимого.  
4. **Отобразите штрихкод** с помощью `Save` или `GetBarCodeImage`.  

## Как закодировать текст в штрихкод Aztec?
`CodeText` — свойство, содержащее обычный текст для кодирования. Используйте свойство `CodeText` объекта `BarcodeGenerator` для передачи обычного текста. Библиотека автоматически выбирает оптимальный режим кодирования (numeric, alphanumeric, или byte) и применяет соответствующий уровень коррекции ошибок. Это упрощает встраивание URL‑адресов, идентификаторов продуктов или любой читаемой строки.

### Шаги по кодированию текста
1. **Создайте генератор** с `EncodeTypes.Aztec`.  
2. **Установите `CodeText`** в строку, которую хотите закодировать.  
3. **При необходимости скорректируйте `ErrorLevel`** для большей устойчивости.  
4. **Сгенерируйте изображение** с помощью `Save` или `GetBarCodeImage`.  

## Как генерировать штрихкоды Aztec с разными уровнями коррекции ошибок?
`ErrorLevel` — свойство, контролирующее количество избыточных данных, добавляемых в штрихкод. Настройте свойство `ErrorLevel` (0‑4) перед рендерингом. Более высокие уровни увеличивают количество избыточных данных, позволяя считывать штрихкод даже при повреждении до 30 % символа. Это критически важно для суровых условий, таких как промышленная маркировка или наружные вывески.

### Шаги по установке уровня коррекции ошибок
1. **Создайте экземпляр `BarcodeGenerator`** для Aztec.  
2. **Назначьте ваши данные** (текст или байты).  
3. **Установите `ErrorLevel`** — например, `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Отобразите штрихкод** в предпочтительном формате вывода.  

## Какие существуют режимы символов Aztec и как их использовать?
`SymbolMode` — настройка, определяющая размер матрицы и ёмкость данных генерируемого кода Aztec. Библиотека предлагает четыре режима: **Auto**, **FullRange**, **Compact** и **Rune**.  

- **Auto** — генератор выбирает минимально возможный размер.  
- **FullRange** — позволяет использовать максимальный размер матрицы для очень больших наборов данных.  
- **Compact** — создаёт более маленький, плотный символ, идеальный для ограниченного пространства.  
- **Rune** — специализированный режим для кодирования Unicode‑рун.  

Выберите режим через `Generator.Parameters.Barcode.Aztec.SymbolMode`. Каждый режим балансирует размер, читаемость и ёмкость данных, позволяя адаптировать штрихкод под ограничения вашего приложения.

## Руководства по кодированию штрихкода Aztec
Ниже представлены пошаговые руководства, которые подробно рассматривают каждую из вышеописанных тем. Нажмите любую ссылку, чтобы изучить полные примеры кода, требования и рекомендации по лучшим практикам.

### [Настройка соотношения сторон штрихкода Aztec](./aztec-aspect-ratio-customization/)
Learn how to customize Aztec barcode aspect ratios using Aspose.BarCode for .NET. Create unique, flexible barcodes for your .NET applications.

### [Кодирование байтов Aztec](./aztec-bytes-encoding/)
Learn how to perform Aztec Bytes Encoding with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code examples included.

### [Кодирование текста штрихкода Aztec](./aztec-code-text-encoding/)
Discover the power of Aztec Code Text Encoding with Aspose.BarCode for .NET. Learn how to create and recognize Aztec codes in your .NET applications.

### [Генерация штрихкодов Aztec с уровнем коррекции ошибок](./aztec-error-level-example/)
Learn how to generate Aztec error barcodes with different error levels using Aspose.BarCode for .NET. Comprehensive guide for barcode creation.

### [Освоение режима символов Aztec](./aztec-symbol-mode-example/)
Explore Aztec Symbol Mode in Aspose.BarCode for .NET and learn how to generate versatile barcodes with ease. Get hands‑on with Auto, FullRange, Compact, and Rune modes in this comprehensive tutorial.

## Часто задаваемые вопросы

**Q: Какие версии .NET поддерживает Aspose.BarCode для кодирования Aztec?**  
**A:** Библиотека работает с .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 и более новыми версиями.

**Q: Могу ли я создать высокоразрешающий штрихкод Aztec для печати?**  
**A:** Да — установите свойство `Resolution` (например, 300 dpi) перед сохранением изображения, чтобы получить качество, готовое к печати.

**Q: Какой объём данных может содержать штрихкод Aztec?**  
**A:** До 3 000 цифровых или 2 300 буквенно-цифровых символов, или примерно 1 800 байт необработанных данных в режиме Compact.

**Q: Можно ли считать штрихкод Aztec, который был повернут?**  
**A:** Абсолютно — декодер Aspose.BarCode автоматически определяет ориентацию и корректирует её во время чтения.

**Q: Нужна ли лицензия для разработки и тестирования?**  
**A:** Бесплатная оценочная лицензия доступна для тестирования; коммерческая лицензия требуется для продакшн‑развертываний.

**Last Updated:** 2026-05-19  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как сгенерировать штрихкод Aztec с пользовательским соотношением сторон, используя Aspose.BarCode для .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Кодирование байтов Aztec с помощью генератора штрихкодов .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Как создать штрихкод Aztec с коррекцией ошибок в .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}