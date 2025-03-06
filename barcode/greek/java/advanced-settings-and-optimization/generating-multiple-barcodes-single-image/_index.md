---
title: Δημιουργία πολλαπλών γραμμικών κωδίκων σε μια μεμονωμένη εικόνα σε Java με το Aspose.BarCode
linktitle: Δημιουργία πολλαπλών γραμμωτών κωδίκων σε μία εικόνα
second_title: Aspose.BarCode Java API
description: Δημιουργήστε πολλαπλούς γραμμωτούς κώδικες σε μια εικόνα χωρίς κόπο χρησιμοποιώντας το Aspose.BarCode για Java. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτη ενσωμάτωση.
weight: 19
url: /el/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία πολλαπλών γραμμικών κωδίκων σε μια μεμονωμένη εικόνα σε Java με το Aspose.BarCode

## Εισαγωγή

Στον δυναμικό κόσμο του προγραμματισμού Java, η αποτελεσματική δημιουργία και διαχείριση γραμμωτού κώδικα είναι ζωτικής σημασίας για διάφορες εφαρμογές. Το Aspose.BarCode για Java απλοποιεί αυτή τη διαδικασία, επιτρέποντας στους προγραμματιστές να δημιουργούν απρόσκοπτα πολλαπλούς γραμμικούς κώδικες σε μία εικόνα. Αυτό το σεμινάριο θα σας καθοδηγήσει στα βήματα για να το πετύχετε χρησιμοποιώντας το Aspose.BarCode σε περιβάλλον Java.

## Προαπαιτούμενα

Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Βασική κατανόηση προγραμματισμού Java.
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
- Λήψη και ρύθμιση της βιβλιοθήκης Aspose.BarCode για Java. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/barcode/java/).
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA.

## Εισαγωγή χώρων ονομάτων

Στο έργο σας Java, εισαγάγετε τους απαραίτητους χώρους ονομάτων για πρόσβαση στη λειτουργία Aspose.BarCode. Προσθέστε τις ακόλουθες δηλώσεις εισαγωγής στην αρχή της τάξης Java:

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

## Βήμα 1: Ορίστε τον Κατάλογο πόρων

Καθορίστε τη διαδρομή προς τον κατάλογο πόρων όπου θα αποθηκευτούν οι δημιουργημένοι γραμμικοί κώδικες. Αυτός ο κατάλογος είναι ζωτικής σημασίας για την οργάνωση και τη διαχείριση των εικόνων γραμμωτού κώδικα.

```java
// Η διαδρομή προς τον κατάλογο πόρων.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Βήμα 2: Δημιουργήστε μια Συλλογή Barcodes

Εκκινήστε ένα HashMap για να αποθηκεύσετε τα δεδομένα του γραμμικού κώδικα. Κάθε καταχώρηση στη συλλογή αντιπροσωπεύει έναν γραμμωτό κώδικα με τον αντίστοιχο τύπο κωδικοποίησης.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Βήμα 3: Δημιουργήστε εικόνες γραμμωτού κώδικα

Επαναλάβετε τη συλλογή και δημιουργήστε εικόνες γραμμικού κώδικα χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Αποθηκεύστε τις εικόνες σε μια ArrayList για περαιτέρω επεξεργασία.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Βήμα 4: Δημιουργήστε μια συνδυασμένη εικόνα

Προσδιορίστε το μέγιστο πλάτος και το συνολικό ύψος των εικόνων γραμμικού κώδικα. Δημιουργήστε ένα BufferedImage για να συνδυάσετε μεμονωμένες εικόνες γραμμικού κώδικα σε μια ενιαία εικόνα εξόδου.

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
## Βήμα 5: Αποθηκεύστε το αποτέλεσμα

Αποθηκεύστε την τελική συνδυασμένη εικόνα σε μια καθορισμένη θέση αρχείου.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## συμπέρασμα

Συγχαρητήρια! Δημιουργήσατε με επιτυχία πολλούς γραμμωτούς κώδικες σε μία εικόνα χρησιμοποιώντας το Aspose.BarCode για Java. Αυτή η ισχυρή βιβλιοθήκη απλοποιεί τον χειρισμό γραμμωτού κώδικα, καθιστώντας την ένα ανεκτίμητο εργαλείο για προγραμματιστές Java.

## Συχνές ερωτήσεις

### Ε1: Μπορώ να προσαρμόσω την εμφάνιση μεμονωμένων γραμμωτών κωδικών στην εικόνα που δημιουργείται;

A1: Ναι, το Aspose.BarCode παρέχει εκτεταμένες επιλογές προσαρμογής για την εμφάνιση του γραμμικού κώδικα, επιτρέποντάς σας να προσαρμόσετε το στυλ κάθε γραμμικού κώδικα στις προτιμήσεις σας.

### Ε2: Είναι το Aspose.BarCode συμβατό με διαφορετικές συμβολολογίες γραμμωτού κώδικα;

Α2: Απολύτως! Το Aspose.BarCode υποστηρίζει ένα ευρύ φάσμα συμβολολογιών, συμπεριλαμβανομένων των CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 και AZTEC, όπως φαίνεται σε αυτό το σεμινάριο.

### Ε3: Πώς μπορώ να ενσωματώσω το Aspose.BarCode στο έργο Java;

 A3: Απλώς κατεβάστε τη βιβλιοθήκη Aspose.BarCode για Java από[εδώ](https://releases.aspose.com/barcode/java/) και ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

### Ε4: Μπορώ να χρησιμοποιήσω το Aspose.BarCode για εμπορικές εφαρμογές;

 A4: Ναι, μπορείτε να αποκτήσετε άδεια από[εδώ](https://purchase.aspose.com/buy) για να χρησιμοποιήσετε το Aspose.BarCode για εμπορικούς σκοπούς.

### Ε5: Υπάρχουν διαθέσιμες δοκιμαστικές επιλογές για το Aspose.BarCode;

 Α5: Σίγουρα! Μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.BarCode αποκτώντας μια δωρεάν δοκιμαστική άδεια[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
