---
date: 2025-12-18
description: Узнайте, как создать изображение штрих‑кода Codabar, и посмотрите пример
  Java‑чтения штрих‑кода с использованием Aspose.BarCode. Генерируйте и распознавайте
  штрих‑коды без усилий с помощью этого пошагового руководства.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Как создать изображение штрих‑кода Codabar с контрольной суммой в Java
url: /ru/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрих‑кода Codabar с контрольной суммой в Java

## Introduction

В этом руководстве вы узнаете, как **создать изображение штрих‑кода codabar** с контрольной суммой в Java, используя Aspose.BarCode. Мы пройдем процесс генерации штрих‑кода CodaBar, включения контрольной суммы и последующего чтения его с помощью **примера java barcode reader**. В конце у вас будет готовый фрагмент кода, который можно вставить в любой проект Java.

## Quick Answers
- **Что делает контрольная сумма?** Она проверяет целостность данных штрих‑кода при сканировании.  
- **Какая библиотека требуется?** Aspose.BarCode for Java.  
- **Нужна ли лицензия для разработки?** Временная лицензия подходит для тестирования; полная лицензия необходима для продакшн.  
- **Можно ли настроить внешний вид штрих‑кода?** Да — цвет, размер и шрифт можно изменить через параметры генератора.  
- **Совместима ли она со всеми версиями Java?** Библиотека поддерживает Java 8 и новее.

## What is a CodaBar barcode?

CodaBar — линейная (одномерная) символьная система, широко используемая в библиотеках, банках крови и розничной торговле. Она кодирует числовые данные и несколько специальных символов, что делает её идеальной для простых, машинно‑читаемых меток. Добавление контрольной суммы (Mod 10) повышает точность считывания, особенно при низкокачественной печати.

## Why use Aspose.BarCode for Java?

Aspose.BarCode предоставляет **java barcode reader example**, который абстрагирует низкоуровневые детали генерации и распознавания штрих‑кодов. Он обеспечивает:

* Полный контроль над режимами контрольных сумм.  
* Бесшовную интеграцию с IDE Java.  
* Обширную документацию и поддержку.  

## Prerequisites

Перед тем как приступить, убедитесь, что у вас есть:

- Установленный Java Development Kit (JDK) на вашем компьютере.  
- Библиотека Aspose.BarCode for Java. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).  
- Базовое понимание программирования на Java.  

## Import Packages

В вашем Java‑проекте импортируйте необходимые классы для работы с Aspose.BarCode:

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

## Step‑by‑step Guide

### Step 1: Set Up the Environment

Создайте новый Java‑проект и добавьте JAR‑файл Aspose.BarCode в путь сборки. Определите папку, куда будут сохраняться сгенерированные изображения.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Step 2: Generate a CodaBar barcode image with checksum

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

### Step 3: Java barcode reader example – Recognize the barcode

Теперь считайте штрих‑код обратно, включив проверку контрольной суммы, чтобы убедиться в правильности данных.

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

## Common Issues and Solutions

| Проблема | Решение |
|----------|---------|
| **Проверка контрольной суммы не прошла** | Убедитесь, что `EnableChecksum` установлен в `YES` и что `CodabarChecksumMode` соответствует режиму, использованному при генерации (Mod 10). |
| **Ошибка: файл не найден** | Убедитесь, что `dataDir` указывает на существующую папку и что сгенерированное изображение (`Codabar_Mod10.png`) сохранено там перед чтением. |
| **Неподдерживаемая версия Java** | Используйте Java 8 или новее; более старые версии могут не иметь необходимых API. |

## Frequently Asked Questions

**В: Совместима ли Aspose.BarCode со всеми версиями Java?**  
О: Aspose.BarCode разработана для работы с Java 8 и новее. См. официальную документацию для подробной совместимости.

**В: Можно ли настроить внешний вид сгенерированного штрих‑кода?**  
О: Да, можно изменять цвета, шрифты и формат изображения через API параметров генератора.

**В: Доступны ли временные лицензии для тестирования?**  
О: Да, временную лицензию для Aspose.BarCode можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где можно найти дополнительную поддержку и ресурсы?**  
О: Посетите [форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13) для поддержки сообщества и обсуждений.

**В: Есть ли бесплатная пробная версия?**  
О: Да, вы можете ознакомиться с возможностями Aspose.BarCode, скачав бесплатную пробную версию [здесь](https://releases.aspose.com/).

---

**Последнее обновление:** 2025-12-18  
**Тестировано с:** Aspose.BarCode for Java 24.12  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}