---
date: 2026-09-28
description: Узнайте, как считывать DataMatrix и как легко генерировать штрихкоды
  DataMatrix с помощью Aspose.BarCode for .NET. Изучите программирование считывателя,
  структурное добавление и руководства по генерации.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Чтение штрихкода DataMatrix
og_description: Как считывать штрихкоды DataMatrix с помощью Aspose.BarCode for .NET
  – быстрый кроссплатформенный гид, охватывающий чтение, структурное добавление и
  генерацию. (150‑160 characters)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Как считывать штрихкоды DataMatrix с помощью Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Как считывать штрихкоды DataMatrix с помощью Aspose.BarCode for .NET
url: /ru/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как читать штрихкоды DataMatrix

Если вам нужно **как читать DataMatrix** эффективно в среде .NET, это руководство предоставляет пошаговое описание чтения, настройки structured append и генерации штрихкодов DataMatrix с помощью Aspose.BarCode для .NET. Вы узнаете, почему эта библиотека является лучшим выбором, что необходимо подготовить заранее и где найти самые полезные фрагменты кода.

## Быстрые ответы
- **What is DataMatrix?** Двумерный матричный штрихкод, который хранит большие объёмы данных в крошечном пространстве.  
- **Which library helps you read DataMatrix in .NET?** Aspose.BarCode for .NET.  
- **Do I need a license?** Доступна бесплатная пробная версия; для продакшн‑использования требуется коммерческая лицензия.  
- **Can I generate DataMatrix barcodes as well?** Да — используйте тот же API для **как генерировать DataMatrix** штрихкодов с пользовательскими настройками.  
- **Supported platforms?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 на Windows, Linux и macOS.

## Что такое чтение штрихкода DataMatrix?

Чтение штрихкода DataMatrix извлекает закодированный текст или бинарные данные из изображения, страницы PDF или кадра живого видео. Декодер Aspose.BarCode работает напрямую с объектами `System.Drawing.Image`, `Stream` или `PdfPage`, поэтому вы можете передавать ему файлы, потоки памяти или захваченные с камеры изображения без дополнительных шагов преобразования.

## Почему использовать Aspose.BarCode для DataMatrix?

Aspose.BarCode обрабатывает до **5 000 штрихкодов в секунду** на стандартном процессоре 2,5 ГГц, поддерживает **более 50 форматов ввода** и не требует **никаких внешних нативных зависимостей**. Библиотека работает на Windows, Linux и macOS, поддерживает уровни коррекции ошибок от ECC 000 до ECC 200 и предоставляет встроенную обработку structured‑append — всё это при использовании памяти менее 20 МБ для пакета из 1 000 страниц.

## Предварительные требования
- .NET Framework 4.5+ или .NET Core 3.1+ (любая современная версия .NET).  
- Установлен пакет NuGet Aspose.BarCode for .NET.  
- Базовые знания C# и IDE, такой как Visual Studio или Rider.

## Программирование чтения DataMatrix: бесшовная интеграция

### Как прочитать штрихкод DataMatrix в .NET?
`BarcodeReader` — класс Aspose.BarCode, который декодирует штрихкоды из изображений, потоков или страниц PDF.  
Загрузите изображение или страницу PDF, создайте `BarcodeReader`, включите флаг `ReadMultipleBarcodes`, если ожидаете более одного кода, и вызовите `Read`. Метод возвращает коллекцию `BarCodeResult`, содержащую декодированное значение, тип символьной системы и степень уверенности.  
`BarCodeResult` представляет один декодированный штрихкод, включая его значение, тип символьной системы и степень уверенности.

### Как включить обработку structured append?
Установите свойство `ReadStructuredAppend` в `true` перед вызовом `Read`. Читатель автоматически соединит фрагменты, принадлежащие одному логическому сообщению, и вернёт единый объединённый результат.

## Конфигурация structured append для DataMatrix: точная организация данных

Structured Append позволяет одному логическому сообщению быть разбитым на несколько символов DataMatrix. При включении этой функции Aspose.BarCode собирает фрагменты на основе номеров последовательности, встроенных в каждый символ. Это идеально подходит для кодирования длинных URL, больших бинарных блоков или многостраничных документов.

## Генерация штрихкодов DataMatrix: раскрытие креативности с Aspose.BarCode для .NET

`BarcodeGenerator` — класс Aspose.BarCode, используемый для генерации изображений штрихкодов с настраиваемыми параметрами. Тот же класс `BarcodeGenerator`, который вы используете для чтения, также создаёт символы DataMatrix. Вы можете управлять размером модуля, отступом, уровнем ECC и даже внедрять изображение логотипа. Генератор выводит файлы PNG, JPEG, SVG или PDF, предоставляя полную гибкость для веб‑, печатных или мобильных сценариев.

## Учебные материалы по чтению штрихкодов DataMatrix
### [Программирование чтения DataMatrix](./datamatrix-reader-programming/)
Изучите программирование чтения DataMatrix с Aspose.BarCode для .NET. Узнайте, как генерировать и считывать штрихкоды DataMatrix в ваших .NET‑приложениях с помощью этого подробного руководства.
### [Конфигурация Structured Append для DataMatrix](./datamatrix-structured-append-configuration/)
Узнайте, как создавать и читать конфигурацию structured append для DataMatrix в .NET с помощью Aspose.BarCode для высокоэффективной организации данных.
### [Генерация штрихкодов DataMatrix](./datamatrix-versions/)
Узнайте, как генерировать штрихкоды DataMatrix в .NET с помощью Aspose.BarCode для .NET. Пользовательские размеры, поддержка ECC и многое другое.

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.BarCode в коммерческих проектах?**  
A: Да. Для использования в продакшн‑среде требуется действующая коммерческая лицензия, но доступна бесплатная пробная версия для оценки.

**Q: Поддерживает ли библиотека чтение DataMatrix из PDF‑файлов?**  
A: Абсолютно. Вы можете загрузить страницу PDF как поток изображения и передать её напрямую считывателю штрихкодов.

**Q: Как обрабатывать Structured Append, когда штрихкод разбит на несколько изображений?**  
A: API автоматически собирает фрагменты, если вы включите свойство `ReadStructuredAppend` перед декодированием.

**Q: Какие уровни коррекции ошибок доступны при генерации штрихкода DataMatrix?**  
A: Вы можете выбрать ECC 000, 050, 080, 100, 140 и 200 в зависимости от требуемой плотности данных и надёжности.

**Q: Есть ли способ повысить производительность чтения при больших пакетах изображений?**  
A: Да — используйте `BarcodeReader` с установленным `ReadMultipleBarcodes` в `true` и обрабатывайте изображения в параллельных потоках.

---

**Последнее обновление:** 2026-09-28  
**Тестировано с:** Aspose.BarCode for .NET 24.12  
**Автор:** Aspose

## Связанные учебные материалы

- [Как генерировать штрихкоды DataMatrix с помощью Aspose.BarCode для .NET – пошаговое руководство](/barcode/net/datamatrix-barcode-configuration/)
- [Как читать DataMatrix Append с Aspose.BarCode для .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Генерация штрихкода DataMatrix в режиме ASCII с Aspose.BarCode для .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}