---
title: Применение контрольной суммы для CodaBar в Java
linktitle: Применение контрольной суммы для CodaBar
second_title: API Aspose.BarCode Java
description: Узнайте, как применить контрольную сумму для CodaBar в Java с помощью Aspose.BarCode. Создавайте и распознавайте штрих-коды без особых усилий с помощью этого пошагового руководства.
type: docs
weight: 11
url: /ru/java/checksum-and-validation/applying-checksum-codabar/
---

## Введение

Добро пожаловать в это пошаговое руководство по применению контрольной суммы для CodaBar в Java с использованием Aspose.BarCode. Aspose.BarCode for Java — это мощная библиотека, которая позволяет разработчикам легко создавать и распознавать штрих-коды в приложениях Java. В этом уроке мы сосредоточимся на конкретной задаче применения контрольной суммы для штрих-кодов CodaBar.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

- На вашем компьютере установлен Java Development Kit (JDK).
-  Aspose.BarCode для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/barcode/java/).
- Базовое понимание программирования на Java.

## Импортировать пакеты

В вашем Java-проекте обязательно импортируйте необходимые пакеты для работы с Aspose.BarCode:

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

## Шаг 1: Настройте среду

Начните с создания нового проекта Java и включения библиотеки Aspose.BarCode в зависимости вашего проекта. Настройте среду разработки с необходимыми ресурсами.

```java
// Путь к каталогу ресурсов.
String dataDir = "Your Document Directory";
```

## Шаг 2: Создание штрих-кода CodaBar

Теперь давайте сгенерируем штрих-код CodaBar с включенной контрольной суммой.

```java
// Создать экземпляр объекта BarcodeGenerator
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Установите для свойства EnableChecksum значение да.
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Установите CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Сохраните изображение в системе
generator.save(dataDir + "Codabar_Mod10.png");
```

## Шаг 3. Распознавание штрих-кода CodaBar

Теперь давайте реализуем часть распознавания штрих-кода CodaBar с помощью контрольной суммы.

```java
// Инициализировать объект читателя
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Установите для свойства ChecksumValidation устройства чтения значение On.
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Получить значение контрольной суммы
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Выполните следующие шаги, чтобы легко применить контрольную сумму для CodaBar в Java с помощью Aspose.BarCode.

## Заключение

В этом уроке мы рассмотрели, как применять контрольную сумму для штрих-кодов CodaBar в Java с помощью Aspose.BarCode. Эта библиотека предоставляет простой способ создания и распознавания штрих-кодов с различными вариантами настройки.

---

## Часто задаваемые вопросы

### Совместим ли Aspose.BarCode со всеми версиями Java?
Aspose.BarCode предназначен для работы с различными версиями Java. Обязательно проверьте документацию на предмет сведений о совместимости.

### Могу ли я настроить внешний вид сгенерированного штрих-кода?
Да, Aspose.BarCode предлагает широкие возможности настройки, позволяющие вам контролировать внешний вид сгенерированных штрих-кодов.

### Доступны ли временные лицензии для целей тестирования?
 Да, вы можете получить временную лицензию для Aspose.BarCode на сайте[здесь](https://purchase.aspose.com/temporary-license/).

### Где я могу найти дополнительную поддержку и ресурсы?
 Посетить[Форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13) за поддержку сообщества и обсуждения.

### Доступна ли бесплатная пробная версия?
 Да, вы можете изучить возможности Aspose.BarCode, загрузив бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).