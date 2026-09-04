---
date: 2026-07-23
description: Узнайте, как оценить качество чтения штрих‑кода в Java с помощью Aspose.Barcode.
  Пошаговое руководство по получению процента качества распознавания с использованием
  aspose barcode java.
keywords:
- aspose barcode java
- barcode reading quality
- barcode confidence score
lastmod: 2026-07-23
linktitle: Получение качества распознавания штрих‑кода в процентах
og_description: aspose barcode java позволяет получать качество чтения штрих‑кода
  в виде процента уверенности. Узнайте точные шаги, предварительные требования и лучшие
  практики в этом кратком руководстве.
og_image_alt: Guide to retrieve barcode reading quality percentage using Aspose.Barcode
  Java
og_title: Aspose.Barcode Java – Получить качество распознавания штрих‑кода в процентах
schemas:
- author: Aspose
  dateModified: '2026-07-23'
  description: Learn how to assess barcode reading quality in Java with Aspose.Barcode.
    Step‑by‑step guide to retrieve recognition quality percentage using aspose barcode
    java.
  headline: Aspose.Barcode Java – Getting Barcode Recognition Quality in Percent
  type: TechArticle
- questions:
  - answer: It’s the confidence score (0‑100 %) that the library assigns to each decoded
      barcode.
    question: What does “reading quality” mean?
  - answer: Any recent Aspose.Barcode Java release (the sample uses the latest 24.x
      series).
    question: Which library version is required?
  - answer: A temporary license works for testing; a full license is required for
      production.
    question: Do I need a license?
  - answer: Yes – the `DecodeType.ALL_SUPPORTED_TYPES` flag enables every format supported
      by Aspose.Barcode.
    question: Can I read all barcode types?
  - answer: Absolutely – the same confidence algorithm is applied across 1‑D and 2‑D
      symbologies.
    question: Is the quality value reliable for QR codes?
  type: FAQPage
second_title: Aspose.Barcode Java API
tags:
- barcode recognition
- aspose barcode
- java barcode processing
title: Aspose.Barcode Java – Получение качества распознавания штрих‑кода в процентах
url: /ru/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Получение качества распознавания штрихкода в процентах

## Введение

Если вам нужно **оценить качество чтения штрихкода** в Java‑приложении, **Aspose.Barcode Java** предоставляет простой API, который возвращает качество распознавания в процентах. В этом руководстве мы пройдем пошагово все необходимые действия для получения этого процента, объясним, почему эта метрика важна, и покажем, как интегрировать вызов в ваш существующий код. Используя **aspose barcode java**, вы можете принимать решения в реальном времени о том, достаточно ли надежно сканирование для последующей обработки.

## Быстрые ответы
- **Что означает “reading quality”?** Это показатель уверенности (0‑100 %), который библиотека присваивает каждому декодированному штрихкоду.  
- **Какая версия библиотеки требуется?** Любой недавний релиз Aspose.Barcode Java (в примере используется последняя серия 24.x).  
- **Нужна ли лицензия?** Временная лицензия подходит для тестирования; полная лицензия требуется для продакшн.  
- **Могу ли я считывать все типы штрихкодов?** Да — флаг `DecodeType.ALL_SUPPORTED_TYPES` включает все форматы, поддерживаемые Aspose.Barcode.  
- **Надежно ли значение качества для QR‑кодов?** Абсолютно — тот же алгоритм уверенности применяется к 1‑D и 2‑D символогиям.

## Что такое Aspose.Barcode Java и как оценить качество чтения штрихкода?

Aspose.Barcode Java — это чисто Java‑библиотека, которая генерирует, считывает и анализирует штрихкоды более чем **30 символогиями**. Одной из самых полезных диагностик является метрика **reading quality**, которая показывает, насколько уверенно движок декодировал символ. Эта метрика важна, когда нужно решить, принимать ли скан, запросить повторное захватывание или запустить логику обработки ошибок.

## Почему использовать Aspose.Barcode Java для качества чтения штрихкода?

Использование Aspose.Barcode Java предоставляет разработчикам надёжный показатель уверенности для всех поддерживаемых символогий, позволяя точно валидировать сканы. Чисто Java‑реализация библиотеки устраняет зависимости от нативных библиотек, а оптимизированный движок обеспечивает быструю обработку и детальные оценки качества, помогая приложениям принимать обоснованные решения о приёме или отклонении данных штрихкода.

- **Последовательные оценки уверенности** для всех поддерживаемых символогий.  
- **Отсутствие нативных DLL** — чистый Java, поэтому работает на любой платформе, совместимой с JVM.  
- **Тонкий контроль**: вы можете получать качество для каждого штрихкода, а не только глобальный проход/непроход.  
- **Оптимизированный по производительности** движок чтения, который обрабатывает изображения до 10 МБ менее чем за 200 мс на типичном сервере.  
- **Поддерживает более 30 типов штрихкодов**, от классического Code‑39 до современных QR и DataMatrix.

## Требования

Перед тем как начать, убедитесь, что у вас есть:

- **Среда разработки Java** — JDK 8 или новее, с вашей любимой IDE (IntelliJ, Eclipse, VS Code и т.д.).  
- **Библиотека Aspose.Barcode Java** — скачайте последнюю JAR‑файл с официального сайта: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Пример изображения штрихкода** — в руководстве используется `code39Extended.jpg`, расположенный в папке `BarcodeReader/advanced_features/`.

Теперь, когда всё готово, перейдём к коду.

## Импорт пространств имён

`BarCodeReader`, `BarCodeResult` и вспомогательные классы находятся в пакете `com.aspose.barcode`. BarCodeReader — основной класс, который считывает изображение и обнаруживает штрихкоды. BarCodeResult представляет один декодированный штрихкод и его свойства. Импортируйте их, чтобы получить доступ к объектам считывателя и результата, необходимым для извлечения качества.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

## Шаг 1: Установите путь к каталогу ресурсов

Определите папку, содержащую пример изображения. `Utils.getDataDir` — вспомогательная функция, которая определяет абсолютный путь для текущего проекта.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

## Шаг 2: Инициализируйте объект BarCodeReader

BarCodeReader создаёт сеанс сканирования для заданного изображения и настроек декодирования. `BarCodeReader` — основной класс, который сканирует изображение и возвращает коллекцию обнаруженных штрихкодов. Передавая `DecodeType.ALL_SUPPORTED_TYPES`, вы инструктируете движок искать каждый известный ему формат.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

## Шаг 3: Считайте штрихкоды и получите процент качества

`BarCodeResult` содержит декодированный текст и метрики качества для одного штрихкода. Метод `getReadingQuality()` возвращает показатель уверенности в процентах. Загрузите изображение с помощью `new BarCodeReader(imagePath, DecodeType.ALL_SUPPORTED_TYPES)`, вызовите `readBarCodes()`, затем пройдитесь по каждому `BarCodeResult` и вызовите `getReadingQuality()`. Метод возвращает значение типа double от 0 до 100, представляющее уверенность. Оценивая это значение, вы можете задавать пороги приёма, вести журнал метрик или предлагать пользователю повторное сканирование при низком качестве, обеспечивая надёжную обработку данных.

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**Что происходит здесь?**  
- `readBarCodes()` возвращает коллекцию объектов `BarCodeResult`, по одному для каждого найденного штрихкода.  
- `getReadingQuality()` возвращает `double` от `0` до `100`, представляющий уровень уверенности.  
- Вы можете использовать это значение, чтобы решить, приемлемо ли сканирование, или нужно предложить пользователю повторить попытку.

## Что такое метрика качества чтения?

Метрика качества чтения — это процент уверенности (0‑100 %), вычисляемый движком Aspose.Barcode на основе чёткости изображения, контраста штрихкода и успешности декодирования. Более высокое значение означает, что движок более уверен, что декодированные данные соответствуют реальному символу.

## Как получить процент качества чтения штрихкода?

Загрузите изображение с помощью `new BarCodeReader(imagePath, DecodeType.ALL_SUPPORTED_TYPES)`, вызовите `readBarCodes()`, затем пройдитесь по каждому `BarCodeResult` и вызовите `getReadingQuality()`. Метод возвращает значение типа double от 0 до 100, представляющее уверенность. Оценивая это значение, вы можете задавать пороги приёма, вести журнал метрик или предлагать пользователю повторное сканирование при низком качестве, обеспечивая надёжную обработку данных.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Качество всегда 0** | Изображение имеет низкое разрешение или сильно размыто. | Используйте источник с более высоким разрешением или примените предварительную обработку изображения (например, резкость). |
| **Штрихкоды не обнаружены** | Неправильный флаг `DecodeType`. | Убедитесь, что используете `DecodeType.ALL_SUPPORTED_TYPES` или укажите точный тип, который ожидаете. |
| **Исключение при `Utils.getDataDir`** | Структура проекта отличается от примера. | Замените вызов вспомогательной функции на жёстко заданный абсолютный путь или относительный путь, соответствующий вашей структуре. |

## Часто задаваемые вопросы

### Q1: Совместим ли Aspose.Barcode со всеми типами штрихкодов?

A1: Aspose.Barcode поддерживает широкий спектр символогий штрихкодов, включая 1‑D (Code‑39, Code‑128, UPC) и 2‑D (QR, DataMatrix, PDF417) стандарты.

### Q2: Могу ли я использовать Aspose.Barcode в коммерческих целях?

A2: Да, вы можете использовать Aspose.Barcode как в личных, так и в коммерческих проектах. Информация о лицензировании доступна [здесь](https://purchase.aspose.com/buy).

### Q3: Как получить временную лицензию для тестирования?

A3: Получите временную лицензию через портал Aspose [здесь](https://purchase.aspose.com/temporary-license/).

### Q4: Где можно найти дополнительную поддержку и обсуждения сообщества?

A4: Посетите [форум Aspose.Barcode](https://forum.aspose.com/c/barcode/13) для поддержки от сообщества и официальной помощи.

### Q5: Есть ли примеры кода в документации?

A5: Да, в официальной документации предоставлены полные примеры кода [здесь](https://reference.aspose.com/barcode/java/).

## Заключение

Используя **Aspose.Barcode Java**, вы можете без труда получить процент **качества чтения штрихкода** для любого сканированного символа. Эта метрика позволяет создавать более интеллектуальную логику валидации, улучшать пользовательский опыт и поддерживать высокую целостность данных в ваших Java‑приложениях.

---

**Последнее обновление:** 2026-07-23  
**Тестировано с:** Aspose.Barcode Java 24.11  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Чтение штрихкода из изображения — освоение извлечения области штрихкода в Java с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/extracting-barcode-region-information/)
- [Определение ориентации штрихкода в Java с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [Как считывать 1D штрихкоды в Java с использованием Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}