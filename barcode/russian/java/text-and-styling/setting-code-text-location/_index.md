---
date: 2026-05-04
description: Узнайте, как создать штрих‑код Data Matrix с помощью Java‑библиотеки
  для штрих‑кодов и установить расположение текста штрих‑кода над символом с помощью
  Aspose.BarCode. Следуйте нашему пошаговому примеру генерации штрих‑кода.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Настройка расположения текста кода
second_title: Aspose.BarCode Java API
title: Создание штрихкода Data Matrix с помощью Java Barcode Library и установка положения
  текста кода
url: /ru/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода Data Matrix с помощью Java Barcode Library и установка расположения текста кода

## Введение

Если вы создаёте систему учёта, доставки или отслеживания на Java, вы быстро обнаружите, что надёжная **java barcode library** необходима. С помощью **Aspose.BarCode for Java** вы можете сгенерировать **Data Matrix barcode** всего в несколько строк кода и полностью контролировать визуальное оформление, включая место появления человекочитаемого текста. В этом руководстве мы пройдём полный **barcode generation example**, покажем, как **customize barcode text** размещать, и объясним, почему размещение текста над символом может улучшить удобство использования.

## Быстрые ответы
- **Какая библиотека используется?** Aspose.BarCode for Java  
- **Какой тип штрих‑кода демонстрируется?** Data Matrix  
- **Как задать расположение текста кода?** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **Нужна ли лицензия для продакшн?** Yes, a commercial license is required  
- **Можно ли запускать код на Java 8+?** Absolutely, it supports Java 8 and later  

## Что такое Java barcode library?
A **java barcode library** provides developers with ready‑made APIs to create, read, and style 1‑D and 2‑D barcodes directly from Java applications. It abstracts the complex encoding rules and lets you focus on business logic instead of low‑level image processing.

## Почему использовать Java barcode library для примера генерации штрих‑кода?
- **Speed:** Generate high‑quality barcodes in milliseconds.  
- **Reliability:** Built‑in compliance with ISO/IEC standards.  
- **Flexibility:** Full control over size, color, margins, and **barcode text** placement.  
- **Cross‑platform:** Works on any JVM‑based environment, from desktop apps to cloud services.

## Что такое Data Matrix barcode?
A Data Matrix barcode is a two‑dimensional (2‑D) symbol that stores large amounts of data in a compact square or rectangular pattern. It’s widely used for marking small items, electronics, and medical devices because it can encode up to 2,335 alphanumeric characters.

## Зачем задавать расположение текста штрих‑кода?
Placing the human‑readable text **above**, **below**, or **beside** the barcode helps users quickly verify the encoded data without scanning. Adjusting the text location improves UI consistency, meets branding guidelines, and can reduce errors in manual data entry.

## Требования

- Basic knowledge of Java programming.  
- Java Development Kit (JDK) installed.  
- An IDE such as Eclipse or IntelliJ IDEA.  
- Aspose.BarCode for Java library (download it from [here](https://releases.aspose.com/barcode/java/)).  

## Импорт пакетов

First, import the essential Aspose.BarCode classes into your project:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Пошаговое руководство

### Шаг 1: Определить пути к каталогам
Specify where you want to read/write files. Replace the placeholders with actual paths on your machine.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Шаг 2: Создать экземпляр BarcodeGenerator
Instantiate `BarcodeGenerator` with the **Data Matrix** type and provide the code text you wish to encode.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Шаг 3: Установить расположение текста штрих‑кода (настроить текст штрих‑кода)
Use the `CodeLocation` enumeration to move the human‑readable text. In this example we place it **above** the barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro tip:** To place the text **below** the symbol, simply change `CodeLocation.ABOVE` to `CodeLocation.BELOW`.

### Шаг 4: Сохранить сгенерированное изображение штрих‑кода
Finally, write the barcode image to disk. The file will contain the Data Matrix symbol with the text positioned above it.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Распространённые проблемы и решения
- **Text not appearing:** Ensure you are using a version of Aspose.BarCode that supports `CodeLocation`.  
- **File path errors:** Verify that `dataDir` ends with a file separator (`/` or `\\`) appropriate for your OS.  
- **Unsupported characters:** Data Matrix can encode only a limited set of characters; avoid special symbols not in the ISO/IEC 16022 standard.  

## Часто задаваемые вопросы (FAQ)

### В: Могу ли я настроить внешний вид сгенерированного штрих‑кода?
A: Yes, Aspose.BarCode provides extensive customization options, allowing you to control colors, margins, and font styles.

### В: Совместима ли Aspose.BarCode с Java 8 и более поздними версиями?
A: Absolutely, the library works with Java 8 and all subsequent releases.

### В: Как интегрировать Aspose.BarCode в мой существующий Java‑проект?
A: Add the Aspose.BarCode JAR files to your project’s classpath, import the required packages, and you’re ready to generate barcodes.

### В: Доступна ли пробная версия Aspose.BarCode?
A: Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [here](https://releases.aspose.com/).

### В: Где я могу получить помощь или поддержку по Aspose.BarCode?
A: Visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) for community assistance and official support.

## Дополнительные часто задаваемые вопросы

**Q: Can I generate a barcode with text positioned below the symbol?**  
A: Yes, set `CodeLocation.BELOW` in the same `setLocation` method.

**Q: Does the library support other 2‑D barcodes like QR Code?**  
A: Absolutely, simply change `EncodeTypes.DATA_MATRIX` to `EncodeTypes.QR`.

**Q: How do I change the font size of the barcode text?**  
A: Use `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Заключение

You’ve now learned how to **create a Data Matrix barcode** in Java using a **java barcode library** and precisely control **how to set barcode text** location with Aspose.BarCode. Experiment with other `CodeLocation` values, font settings, and color options to match your application’s design requirements.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}