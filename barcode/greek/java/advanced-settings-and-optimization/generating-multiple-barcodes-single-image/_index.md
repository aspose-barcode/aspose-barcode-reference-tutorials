---
date: 2026-04-03
description: Μάθετε πώς να δημιουργείτε QR code σε Java και να παράγετε πολλαπλούς
  γραμμικούς κώδικες σε μία εικόνα χρησιμοποιώντας το Aspose.BarCode for Java. Περιλαμβάνει
  εγκατάσταση, κώδικα και αντιμετώπιση προβλημάτων.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Δημιουργία πολλαπλών γραμμωτών κωδίκων σε μία εικόνα
second_title: Aspose.BarCode Java API
title: Δημιουργία QR Code με Java – Δημιουργία πολλαπλών γραμμωτών κωδίκων σε μία
  εικόνα
url: /el/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία QR Code Java – Δημιουργία Πολλαπλών Barcode σε Μία Εικόνα

## Εισαγωγή

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Aspose.BarCode for Java provides the most complete set of symbologies.  
- **Μπορώ να δημιουργήσω διαφορετικούς τύπους barcode μαζί;** Yes, you can mix CODE_39, QR, AZTEC, and more on a single canvas.  
- **Χρειάζομαι άδεια για ανάπτυξη;** A free trial works for testing; a commercial license is required for production.  
- **Ποια έκδοση της Java υποστηρίζεται;** Java 8 and newer are fully compatible.  
- **Μπορεί να ρυθμιστεί η μορφή εξόδου;** You can export the combined image as PNG, JPEG, BMP, etc.  

## Τι είναι η δημιουργία QR code java;

## Γιατί να χρησιμοποιήσετε το Aspose.BarCode Java για τη δημιουργία barcode σε Java;

## Προαπαιτούμενα

- Βασική κατανόηση του προγραμματισμού Java.  
- Java Development Kit (JDK) εγκατεστημένο στο σύστημα σας.  
- Aspose.BarCode for Java library downloaded and set up. You can download it [here](https://releases.aspose.com/barcode/java/).  
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA.

## Εισαγωγή Ονοματοχώρων

In your Java project, import the necessary namespaces to access the Aspose.BarCode functionality. Add the following import statements at the beginning of your Java class:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Βήμα 1: Ορισμός του Καταλόγου Πόρων

Define the path to the resource directory where the generated barcodes will be saved. This directory is crucial for organizing and managing your barcode images.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Βήμα 2: Δημιουργία Συλλογής Barcode

Initialize a `HashMap` to store the barcode data. Each entry in the collection represents a barcode with its respective encoding type.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Βήμα 3: Δημιουργία Εικόνων Barcode

Iterate through the collection and generate barcode images using the Aspose.BarCode library. Store the images in an `ArrayList` for further processing.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Βήμα 4: Δημιουργία Ενιαίας Εικόνας

Determine the maximum width and total height of the barcode images. Create a `BufferedImage` to combine individual barcode images into a single output image.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Βήμα 5: Αποθήκευση του Αποτελέσματος

Save the final combined image to a specified file location.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Κοινές Περιπτώσεις Χρήσης για Δημιουργία Πολλαπλών Barcode

- **Ετικέτες συσκευασίας** – combine product, batch, and shipping codes on a single label.  
- **Εισιτήρια εκδηλώσεων** – embed QR, Data Matrix, and Code 128 identifiers for different scanning stations.  
- **Διαχείριση αποθεμάτων** – display SKU, RFID tag data, and serial numbers together for quick audit.

## Αντιμετώπιση Προβλημάτων & Συμβουλές

- **Προβλήματα μεγέθους εικόνας** – adjust the `offset` variable to increase or decrease spacing between barcodes.  
- **Μη υποστηριζόμενη συμβολική** – verify that your Aspose.BarCode version supports the desired barcode type.  
- **Απόδοση** – reuse a single `Graphics` object if you generate many images in a loop.

## Συχνές Ερωτήσεις

**Q1: Μπορώ να προσαρμόσω την εμφάνιση των μεμονωμένων barcode στην παραγόμενη εικόνα;**  
A1: Yes, Aspose.BarCode provides extensive customization options for barcode appearance, allowing you to tailor each barcode's style to your preferences.

**Q2: Είναι το Aspose.BarCode συμβατό με διαφορετικές συμβολές barcode;**  
A2: Absolutely! Aspose.BarCode supports a wide range of symbologies, including CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.

**Q3: Πώς μπορώ να ενσωματώσω το Aspose.BarCode στο Java project μου;**  
A3: Simply download the Aspose.BarCode for Java library from [here](https://releases.aspose.com/barcode/java/) and follow the installation instructions provided in the documentation.

**Q4: Μπορώ να χρησιμοποιήσω το Aspose.BarCode για εμπορικές εφαρμογές;**  
A4: Yes, you can obtain a license from [here](https://purchase.aspose.com/buy) to use Aspose.BarCode for commercial purposes.

**Q5: Υπάρχουν διαθέσιμες δοκιμαστικές επιλογές για το Aspose.BarCode;**  
A5: Certainly! You can explore the features of Aspose.BarCode by obtaining a free trial license [here](https://releases.aspose.com/).

**Q6: Πώς δημιουργώ έναν υψηλής ανάλυσης QR code για εκτύπωση;**  
A6: Set the desired DPI on the `BarcodeGenerator` before calling `generateBarCodeImage()`, then save the image in a loss‑less format such as PNG.

**Q7: Τι πρέπει να κάνω αν η ενιαία εικόνα εμφανίζεται κομμένη;**  
A7: Verify that the `offset` and canvas size calculations correctly account for all barcode heights; increasing the canvas height or reducing individual barcode sizes resolves most truncation issues.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}