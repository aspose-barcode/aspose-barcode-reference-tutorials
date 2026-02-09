---
date: 2026-02-09
description: Μάθετε πώς να δημιουργείτε γραμμωτούς κώδικες σε μία μόνο εικόνα σε Java
  χρησιμοποιώντας το Aspose.BarCode, μια ισχυρή βιβλιοθήκη δημιουργίας γραμμωτών κωδίκων
  για Java. Αυτός ο οδηγός καλύπτει την ενσωμάτωση και τη δημιουργία πολλαπλών γραμμωτών
  κωδίκων.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Πώς να δημιουργήσετε γραμμωτούς κώδικες σε μία εικόνα στην Java
url: /el/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Πολλαπλών Γραμμωτών σε Μία Εικόνα σε Java με το Aspose.BarCode

## Introduction

Αν ψάχνετε για έναν αξιόπιστο τρόπο **πώς να δημιουργήσετε γραμμωτούς κώδικες** σε μια εφαρμογή Java, βρίσκεστε στο σωστό μέρος. Με το Aspose.BarCode for Java μπορείτε να τοποθετήσετε διάφορους τύπους γραμμωτών κωδίκων σε μία εικόνα με μόνο λίγες γραμμές κώδικα. Αυτό το tutorial σας καθοδηγεί βήμα‑βήμα σε όλη τη διαδικασία — από τη ρύθμιση του έργου μέχρι την αποθήκευση της συνδυασμένης εικόνας — ώστε να αρχίσετε αμέσως να χρησιμοποιείτε τη δημιουργία γραμμωτών κωδίκων στις λύσεις σας.

## Quick Answers
- **What library should I use?** Το Aspose.BarCode for Java παρέχει το πιο πλήρες σύνολο συμβολισμών.  
- **Can I generate different barcode types together?** Ναι, μπορείτε να συνδυάσετε CODE_39, QR, AZTEC και άλλους σε έναν καμβά.  
- **Do I need a license for development?** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Which Java version is supported?** Η Java 8 και νεότερες εκδόσεις είναι πλήρως συμβατές.  
- **Is the output format configurable?** Μπορείτε να εξάγετε την συνδυασμένη εικόνα ως PNG, JPEG, BMP κ.λπ.

## What is “how to generate barcodes” in Java?

Η δημιουργία γραμμωτών κωδίκων σημαίνει τη μετατροπή μιας συμβολοσειράς δεδομένων σε ένα οπτικό μοτίβο που μπορούν να διαβάσουν οι σαρωτές. Το Aspose.BarCode διαχειρίζεται αυτόματα την κωδικοποίηση, την απόδοση και τη δημιουργία της εικόνας, επιτρέποντάς σας να εστιάσετε στη λογική της εφαρμογής αντί στην επεξεργασία εικόνας χαμηλού επιπέδου.

## Why generate multiple barcodes on a single image?
- **Space‑saving labels** – συνδυάστε ταυτότητες προϊόντος, παρτίδας και αποστολής σε μία ετικέτα.  
- **Multi‑scan workflows** – ενσωματώστε QR, Data Matrix και Code 128 για διαφορετικούς σταθμούς σάρωσης.  
- **Simplified asset tracking** – εμφανίστε SKU, δεδομένα RFID και σειριακούς αριθμούς μαζί για γρήγορους ελέγχους.  

## Prerequisites

Πριν ξεκινήσετε το tutorial, βεβαιωθείτε ότι διαθέτετε τα παρακάτω:

- Βασική κατανόηση του προγραμματισμού Java.  
- Εγκατεστημένο Java Development Kit (JDK) στο σύστημά σας.  
- Βιβλιοθήκη Aspose.BarCode for Java που έχετε κατεβάσει και ρυθμίσει. Μπορείτε να τη κατεβάσετε [εδώ](https://releases.aspose.com/barcode/java/).  
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA.

## Import Namespaces

Στο έργο Java, εισάγετε τα απαραίτητα namespaces για να έχετε πρόσβαση στη λειτουργικότητα του Aspose.BarCode. Προσθέστε τις παρακάτω δηλώσεις import στην αρχή της κλάσης Java:

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

## Step 1: Set the Resource Directory

Ορίστε τη διαδρομή προς τον φάκελο πόρων όπου θα αποθηκευτούν οι παραγόμενοι γραμμωτοί κώδικες. Αυτός ο φάκελος είναι κρίσιμος για την οργάνωση και διαχείριση των εικόνων των γραμμωτών κωδίκων.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Step 2: Create a Collection of Barcodes

Αρχικοποιήστε ένα `HashMap` για να αποθηκεύσετε τα δεδομένα των γραμμωτών κωδίκων. Κάθε καταχώρηση στη συλλογή αντιπροσωπεύει έναν γραμμωτό κώδικα με τον αντίστοιχο τύπο κωδικοποίησης.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Step 3: Generate Barcode Images

Περιηγηθείτε στη συλλογή και δημιουργήστε εικόνες γραμμωτών κωδίκων χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Αποθηκεύστε τις εικόνες σε ένα `ArrayList` για περαιτέρω επεξεργασία.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Step 4: Create a Combined Image

Καθορίστε το μέγιστο πλάτος και το συνολικό ύψος των εικόνων των γραμμωτών κωδίκων. Δημιουργήστε ένα `BufferedImage` για να συνδυάσετε τις μεμονωμένες εικόνες σε μία τελική εικόνα εξόδου.

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

## Step 5: Save the Result

Αποθηκεύστε την τελική συνδυασμένη εικόνα σε μια καθορισμένη τοποθεσία αρχείου.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## How to generate QR code Java style?

Αν χρειάζεστε ένα παράδειγμα **generate qr code java**, απλώς αντικαταστήστε την καταχώρηση στη συλλογή με `EncodeTypes.QR`. Ο ίδιος βρόχος θα αποδώσει έναν υψηλής ανάλυσης QR κώδικα που μπορεί να αποθηκεύσει URLs, στοιχεία επαφής ή οποιαδήποτε αλφαριθμητικά δεδομένα.

## How to generate Code 128 barcode in Java?

Το παραπάνω απόσπασμα δείχνει ήδη πώς να **generate code 128 barcode** χρησιμοποιώντας `EncodeTypes.CODE_128`. Ο Code 128 είναι ιδανικός για τη λογιστική, καθώς υποστηρίζει ολόκληρο το σύνολο ASCII και προσφέρει συμπαγή κωδικοποίηση.

## Using a java barcode generation library beyond Aspose

Ενώ το Aspose.BarCode είναι μια πλήρης **java barcode generation library**, μπορείτε επίσης να εξερευνήσετε ανοιχτού κώδικα εναλλακτικές όπως ZXing ή Barcode4J για ελαφριές περιπτώσεις. Ωστόσο, το Aspose προσφέρει ενσωματωμένη υποστήριξη για έξοδο υψηλής ανάλυσης, πολλαπλούς συμβολισμούς και εύκολη σύνθεση εικόνων — όλα σε ένα πακέτο.

## Common Use Cases for Generating Multiple Barcodes

- **Packaging labels** – συνδυάστε κωδικούς προϊόντος, παρτίδας και αποστολής σε μία ετικέτα.  
- **Event tickets** – ενσωματώστε QR, Data Matrix και Code 128 για διαφορετικούς σταθμούς σάρωσης.  
- **Inventory management** – εμφανίστε SKU, δεδομένα RFID και σειριακούς αριθμούς μαζί για γρήγορο έλεγχο.

## Troubleshooting & Tips

- **Image size issues** – προσαρμόστε τη μεταβλητή `offset` για να αυξήσετε ή να μειώσετε το κενό μεταξύ των γραμμωτών κωδίκων.  
- **Unsupported symbology** – βεβαιωθείτε ότι η έκδοση του Aspose.BarCode υποστηρίζει τον επιθυμητό τύπο γραμμωτού κώδικα.  
- **Performance** – επαναχρησιμοποιήστε ένα ενιαίο αντικείμενο `Graphics` αν δημιουργείτε πολλές εικόνες σε βρόχο.  
- **Memory management** – όταν διαχειρίζεστε μεγάλο αριθμό γραμμωτών κωδίκων, σκεφτείτε να γράφετε προσωρινά κάθε εικόνα στο δίσκο για να αποφύγετε υπερβολική χρήση heap.

## Frequently Asked Questions

### Q1: Can I customize the appearance of individual barcodes in the generated image?

A1: Ναι, το Aspose.BarCode παρέχει εκτενείς επιλογές προσαρμογής της εμφάνισης των γραμμωτών κωδίκων, επιτρέποντάς σας να διαμορφώσετε το στυλ κάθε κώδικα σύμφωνα με τις προτιμήσεις σας.

### Q2: Is Aspose.BarCode compatible with different barcode symbologies?

A2: Απόλυτα! Το Aspose.BarCode υποστηρίζει ένα ευρύ φάσμα συμβολισμών, συμπεριλαμβανομένων των CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 και AZTEC, όπως φαίνεται σε αυτό το tutorial.

### Q3: How can I integrate Aspose.BarCode into my Java project?

A3: Απλώς κατεβάστε τη βιβλιοθήκη Aspose.BarCode for Java από [εδώ](https://releases.aspose.com/barcode/java/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

### Q4: Can I use Aspose.BarCode for commercial applications?

A4: Ναι, μπορείτε να αποκτήσετε άδεια από [εδώ](https://purchase.aspose.com/buy) για εμπορική χρήση του Aspose.BarCode.

### Q5: Are there any trial options available for Aspose.BarCode?

A5: Φυσικά! Μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.BarCode αποκτώντας δωρεάν δοκιμαστική άδεια [εδώ](https://releases.aspose.com/).

**Additional Questions**

**Q: How do I generate a QR code specifically in Java?**  
A: Χρησιμοποιήστε `EncodeTypes.QR` κατά τη δημιουργία του αντικειμένου `BarcodeGenerator`, όπως φαίνεται στο παράδειγμα της συλλογής.

**Q: Does Aspose.BarCode support high‑resolution output for printing?**  
A: Ναι, μπορείτε να καθορίσετε το DPI κατά την αποθήκευση της εικόνας για να καλύψετε απαιτήσεις εκτύπωσης υψηλής ποιότητας.

---

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}