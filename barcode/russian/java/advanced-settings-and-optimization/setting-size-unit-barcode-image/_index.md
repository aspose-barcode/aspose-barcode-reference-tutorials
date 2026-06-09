---
date: 2026-02-07
description: Узнайте, как использовать Aspose.BarCode для Java, чтобы создать штрих‑код
  CODE_128, сгенерировать изображение штрих‑кода в Java и задать точные единицы размеров
  — идеально подходит для штрих‑кодов в системе учёта запасов или генерации транспортных
  этикеток.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 'aspose barcode java: Создать штрих‑код CODE_128 с единицей измерения размера'
url: /ru/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java: Создание штрих‑кода CODE_128 с единицей измерения размера

## Introduction

В этом пошаговом руководстве вы **используете aspose barcode java** для создания штрих‑кода CODE_128, генерации изображения штрих‑кода java и точного управления единицей измерения размера результата. Независимо от того, создаёте ли вы штрих‑код для системы учёта, генератора транспортных этикеток или любого Java‑приложения, требующего надёжных штрих‑кодов, Aspose.BarCode for Java предоставляет полную гибкость всего в несколько строк кода.

## Quick Answers
- **What library do I need?** Aspose.BarCode for Java (aspose barcode java).  
- **Which barcode type is covered?** CODE_128 (create code128 barcode java).  
- **How do I set the size unit?** Use the `BarHeight` property with `.setPoint()`.  
- **Can I generate barcode image java in other formats?** Yes – PNG, JPEG, BMP, etc.  
- **What are the prerequisites?** JDK installed, Aspose.BarCode library, and a Java IDE.

## What is **create code128 barcode java**?

Создание штрих‑кода CODE_128 в Java означает создание экземпляра класса `BarcodeGenerator` с перечислением `EncodeTypes.CODE_128` и передачу строки данных, которую необходимо закодировать. Эта символьная система широко используется в логистике, так как поддерживает полный набор символов ASCII и обеспечивает высокую плотность данных — что делает её идеальной для сценариев штрих‑кода в системе учёта.

## Why use Aspose.BarCode to **generate barcode image java**?

- **Full control over dimensions** – you can set bar height, module size, and image resolution.  
- **No external dependencies** – pure Java, works on any platform that supports the JDK.  
- **Rich customization** – colors, fonts, margins, and even QR codes are supported.  
- **High performance** – generates images in milliseconds, suitable for batch processing and generate shipping label barcode workflows.  

## Prerequisites

Before we start, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or later installed on your machine.  
2. **Aspose.BarCode for Java library** – download the latest JAR from the Aspose website (trial or licensed).  
3. **A Java IDE** – such as IntelliJ IDEA, Eclipse, or VS Code with Java extensions.  

## Import Namespaces

Add the required imports at the top of your Java class so you can access Aspose.BarCode’s API:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to **generate barcode image java** with Aspose.BarCode?

Below is the complete workflow. Each step is explained in plain language, and the original code blocks are kept exactly as they were.

### Step 1: Define the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the absolute path where you want the barcode image saved. This folder will hold the generated PNG/JPEG files that you can later embed in invoices, packing slips, or inventory reports.

### Step 2: Instantiate the Barcode Object

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Here we **create code128 barcode java** by passing `EncodeTypes.CODE_128` and the data string `"1234567"`.

### Step 3: Set Bar Height (Size Unit)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

The `setPoint()` method defines the height in points (1 point = 1/72 inch). Adjust this value to meet your layout requirements—larger values produce taller bars, which is often needed for high‑resolution shipping labels.

### Step 4: Save the Image

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

The `save()` call writes the generated barcode to the folder you specified. The image format is inferred from the file extension (JPEG in this case). You can switch to PNG, BMP, or TIFF simply by changing the extension.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **Image not created** | `dataDir` path is incorrect or missing write permissions. | Verify the folder exists and your application has write access. |
| **Barcode appears too small** | Bar height set in points is too low for the chosen DPI. | Increase the value passed to `setPoint()` or adjust image DPI via `bb.getParameters().getImage().setResolution()`. |
| **Unsupported characters** | CODE_128 supports only ASCII; you passed Unicode. | Use a different symbology (e.g., QR_CODE) for non‑ASCII data. |

## Frequently Asked Questions

**Q: Is Aspose.BarCode for Java suitable for both barcode generation and recognition?**  
A: Yes, the library supports both generation and recognition of a wide range of symbologies.

**Q: Can I customize the appearance of the generated barcode images?**  
A: Absolutely. You can change colors, add captions, modify margins, and even embed logos using the extensive `Parameters` API.

**Q: How can I obtain a temporary license for Aspose.BarCode for Java?**  
A: Visit [here](https://purchase.aspose.com/temporary-license/) to request a temporary license for evaluation.

**Q: Where can I find support for Aspose.BarCode for Java?**  
A: The Aspose.BarCode community forum is the best place for help. Check the [forum](https://forum.aspose.com/c/barcode/13) for answers and to ask new questions.

**Q: What are the supported barcode symbologies in Aspose.BarCode for Java?**  
A: The library supports dozens of symbologies, including CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, and many more.

### Additional Tips (Pro tip)

- **Batch processing:** Wrap the steps above in a loop to generate hundreds of barcodes for bulk inventory uploads.  
- **Resolution control:** Use `bb.getParameters().getImage().setResolution(300)` to produce 300 dpi images, which are ideal for high‑quality print labels.  

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}