---
date: 2025-11-30
description: Изучите, как оценивать качество считывания штрих‑кода в Java с помощью
  Aspose.Barcode. Пошаговое руководство по получению процента качества распознавания.
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – Получение качества распознавания штрихкода в процентах
url: /ru/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – Получение качества распознавания штрихкода в процентах

## Introduction

Если вам необходимо **оценить качество чтения штрихкода** в Java‑приложении, **Aspose.Barcode Java** предоставляет простой API, который возвращает качество распознавания в процентах. В этом руководстве мы пройдем все необходимые шаги для получения этого процента, объясним, почему эта метрика важна, и покажем, как интегрировать вызов в ваш существующий код.

## Quick Answers
- **Что означает «качество чтения»?** Это показатель уверенности (0‑100 %), который библиотека присваивает каждому декодированному штрихкоду.  
- **Какая версия библиотеки требуется?** Любая современная версия Aspose.Barcode Java (в примере используется последняя серия 24.x).  
- **Нужна ли лицензия?** Временная лицензия подходит для тестирования; полная лицензия требуется для продакшн.  
- **Можно ли читать все типы штрихкодов?** Да — флаг `DecodeType.ALL_SUPPORTED_TYPES` включает все форматы, поддерживаемые Aspose.Barcode.  
- **Надежно ли значение качества для QR‑кодов?** Абсолютно — тот же алгоритм уверенности применяется к 1‑D и 2‑D символогиям.

## What is Aspose.Barcode Java and How to Assess Barcode Reading Quality?

**Aspose.Barcode Java** — полностью управляемая библиотека, позволяющая разработчикам генерировать, считывать и анализировать штрихкоды без внешних зависимостей. Одной из самых полезных диагностик является метрика **качество чтения**, которая показывает, насколько уверенно движок декодировал символ. Эта метрика важна, когда нужно решить, принимать ли скан, запросить повторный захват или запустить обработку ошибок.

## Why Use Aspose.Barcode Java for Barcode Reading Quality?

- **Последовательные показатели уверенности** для всех поддерживаемых символогий.  
- **Без нативных DLL** — чистый Java, поэтому работает на любой платформе, совместимой с JVM.  
- **Тонкий контроль**: вы можете получать качество для каждого штрихкода, а не только глобальный результат «пройден/не пройден».  
- **Оптимизированный по производительности** движок чтения, масштабируемый от настольных приложений до облачных сервисов.

## Prerequisites

Перед началом убедитесь, что у вас есть:

- **Среда разработки Java** — JDK 8 или новее, с вашей любимой IDE (IntelliJ, Eclipse, VS Code и т.д.).  
- **Библиотека Aspose.Barcode Java** — скачайте последнюю JAR с официального сайта: [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/).  
- **Пример изображения штрихкода** — в руководстве используется `code39Extended.jpg`, расположенный в папке `BarcodeReader/advanced_features/`.

Теперь, когда всё готово, перейдём к коду.

## Import Namespaces

Следующие импорты дают доступ к классам считывателя и результата, необходимым для извлечения качества.

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### Step 1: Set the Resource Directory Path

Шаг 1: Установите путь к каталогу ресурсов

Определите папку, содержащую пример изображения. `Utils.getDataDir` — вспомогательная функция, которая определяет абсолютный путь для текущего проекта.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### Step 2: Initialize the BarCodeReader Object

Шаг 2: Инициализируйте объект BarCodeReader

Создайте экземпляр `BarCodeReader`, указывая ему файл изображения и задав попытку **всех поддерживаемых типов штрихкодов**.

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### Step 3: Read the Barcodes and Retrieve the Quality Percentage

Шаг 3: Считайте штрихкоды и получите процент качества

Итерируйте каждый обнаруженный штрихкод, выводите его текст, тип и процент **качества чтения**, возвращаемый методом `getReadingQuality()`.

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
- Вы можете использовать это значение, чтобы решить, приемлем ли скан или нужно попросить пользователя выполнить повторную попытку.

## Common Issues and Solutions

| Проблема | Причина | Решение |
|-------|-------|-----|
| **Качество всегда 0** | Изображение низкого разрешения или сильно размыто. | Используйте источник с более высоким разрешением или примените предобработку изображения (например, резкость). |
| **Штрихкоды не обнаружены** | Неправильный флаг `DecodeType`. | Убедитесь, что используете `DecodeType.ALL_SUPPORTED_TYPES` или укажите точный тип, который ожидаете. |
| **Исключение при `Utils.getDataDir`** | Структура проекта отличается от образца. | Замените вызов вспомогательной функции на жёстко заданный абсолютный путь или относительный путь, соответствующий вашей структуре. |

## Frequently Asked Questions

### Q1: Совместима ли Aspose.Barcode со всеми типами штрихкодов?

A1: Aspose.Barcode поддерживает широкий спектр символогий штрихкодов, включая 1‑D (Code‑39, Code‑128, UPC) и 2‑D (QR, DataMatrix, PDF417) стандарты.

### Q2: Можно ли использовать Aspose.Barcode в коммерческих целях?

A2: Да, вы можете использовать Aspose.Barcode как в личных, так и в коммерческих проектах. Подробности лицензирования доступны [здесь](https://purchase.aspose.com/buy).

### Q3: Как получить временную лицензию для тестирования?

A3: Получите временную лицензию через портал Aspose [здесь](https://purchase.aspose.com/temporary-license/).

### Q4: Где можно найти дополнительную поддержку и обсуждения в сообществе?

A4: Посетите [форум Aspose.Barcode](https://forum.aspose.com/c/barcode/13) для поддержки от сообщества и официальной помощи.

### Q5: Есть ли примеры кода в документации?

A5: Да, в официальной документации предоставлены полные примеры кода [здесь](https://reference.aspose.com/barcode/java/).

## Conclusion

Используя **Aspose.Barcode Java**, вы можете без труда получить процент **качества чтения штрихкода** для любого отсканированного символа. Эта метрика позволяет создавать более интеллектуальную логику валидации, улучшать пользовательский опыт и поддерживать высокую целостность данных в ваших Java‑приложениях.

---

**Последнее обновление:** 2025-11-30  
**Тестировано с:** Aspose.Barcode Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}