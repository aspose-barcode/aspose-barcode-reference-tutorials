---
date: 2026-04-05
description: Узнайте, как создать изображение штрих‑кода Codabar в Java с контрольной
  суммой, и посмотрите пример считывателя штрих‑кодов на Java с использованием Aspose.BarCode.
  Следуйте этому пошаговому руководству, чтобы генерировать и распознавать штрих‑коды.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: Применение контрольной суммы для CodaBar
second_title: Aspose.BarCode Java API
title: Как создать изображение штрихкода Codabar в Java с контрольной суммой
url: /ru/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода Codabar в Java с контрольной суммой

## Введение

В этом руководстве вы **создадите изображения штрих‑кода codabar в Java** с контрольной суммой Mod 10, используя Aspose.BarCode for Java. Мы пройдем процесс генерации штрих‑кода CodaBar, включения контрольной суммы и последующей проверки с помощью **java barcode reader example**. К концу у вас будет готовый фрагмент кода, который можно вставить в любой проект на Java, будь то система управления библиотекой, принтер этикеток для медицинской лаборатории или решение для розничной кассы.

## Быстрые ответы
- **Что делает контрольная сумма?** Она проверяет целостность данных штрих‑кода при сканировании.  
- **Какая библиотека требуется?** Aspose.BarCode for Java.  
- **Нужна ли лицензия для разработки?** Временная лицензия подходит для тестирования; полная лицензия требуется для продакшна.  
- **Можно ли настроить внешний вид штрих‑кода?** Да — цвет, размер и шрифт можно изменить через параметры генератора.  
- **Совместима ли она со всеми версиями Java?** Библиотека поддерживает Java 8 и новее.

## Как создать штрих‑код codabar в Java

Ниже вы найдете краткое пошаговое руководство, которое объясняет **почему каждая строка важна**, чтобы вы могли с уверенностью адаптировать код к своим проектам.

### Что такое штрих‑код CodaBar?

CodaBar — это линейная (1‑мерная) символьная система, широко используемая в библиотеках, банках крови и розничной торговле. Она кодирует числовые данные и несколько специальных символов, что делает её идеальной для простых машинно‑читаемых меток. Добавление контрольной суммы (Mod 10) повышает точность считывания, особенно при печати низкого качества.

### Почему использовать Aspose.BarCode for Java?

Aspose.BarCode предлагает **java barcode reader example**, который абстрагирует детали низкого уровня генерации и распознавания штрих‑кодов. Он предоставляет:

* Полный контроль над режимами контрольных сумм.  
* Бесшовную интеграцию с IDE Java.  
* Обширную документацию и оперативную поддержку.  

### Предварительные требования

Прежде чем приступить, убедитесь, что у вас есть:

- Установленный Java Development Kit (JDK) 8 или новее.  
- Библиотека Aspose.BarCode for Java. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).  
- Базовое знакомство с концепциями программирования на Java.  

### Импорт пакетов

In your Java project, import the necessary classes to work with Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

### Пошаговое руководство

#### Шаг 1: Настройка окружения

Создайте новый проект Java и добавьте JAR‑файл Aspose.BarCode в путь сборки. Определите папку, куда будут сохраняться сгенерированные изображения.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### Шаг 2: Генерация изображения штрих‑кода CodaBar с контрольной суммой

Создайте экземпляр `BarcodeGenerator`, включите контрольную сумму, выберите режим Mod 10 и сохраните изображение.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### Шаг 3: Пример java barcode reader – Распознавание штрих‑кода

Теперь считайте штрих‑код, включив проверку контрольной суммы, чтобы убедиться в правильности данных.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Выполнение кода выведет декодированный текст, тип символьной системы и рассчитанную контрольную сумму, подтверждая, что штрих‑код был сгенерирован и проверен корректно.

### Распространённые сценарии использования

- **Управление библиотекой:** Кодировать идентификаторы книг для быстрого сканирования при выдаче.  
- **Этикетки банка крови:** Обеспечить точную идентификацию пациентов с защитой контрольной суммы.  
- **Этикетки полок в рознице:** Печатать недорогие, высокоскоростные штрих‑коды для учёта запасов.  

### Распространённые проблемы и решения

| Проблема | Решение |
|-------|----------|
| **Checksum validation fails** | Verify that `EnableChecksum` is set to `YES` and that `CodabarChecksumMode` matches the mode used during generation (Mod 10). |
| **File not found error** | Ensure `dataDir` points to an existing folder and that the generated image (`Codabar_Mod10.png`) is saved there before reading. |
| **Unsupported Java version** | Use Java 8 or later; older versions may lack required APIs. |

## Часто задаваемые вопросы

**В: Совместима ли Aspose.BarCode со всеми версиями Java?**  
О: Aspose.BarCode разработана для работы с Java 8 и новее. См. официальную документацию для подробной совместимости.

**В: Можно ли настроить внешний вид сгенерированного штрих‑кода?**  
О: Да, вы можете изменить цвета, шрифты и формат изображения через API параметров генератора.

**В: Доступны ли временные лицензии для тестирования?**  
О: Да, временную лицензию для Aspose.BarCode можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где можно найти дополнительную поддержку и ресурсы?**  
О: Посетите [форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13) для поддержки сообщества и обсуждений.

**В: Доступна ли бесплатная пробная версия?**  
О: Да, вы можете ознакомиться с функциями Aspose.BarCode, скачав бесплатную пробную версию [здесь](https://releases.aspose.com/).

---

**Последнее обновление:** 2026-04-05  
**Тестировано с:** Aspose.BarCode for Java 24.12  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}