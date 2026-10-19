---
date: 2026-10-19
description: Μάθετε πώς να δημιουργήσετε QR code java και να δημιουργήσετε πολλαπλά
  barcode σε μία εικόνα χρησιμοποιώντας Aspose.BarCode for Java. Περιλαμβάνει setup,
  code, και troubleshooting.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Δημιουργία πολλαπλών barcode σε μία εικόνα
og_description: Δημιουργήστε QR code java και συνδυάστε πολλούς τύπους barcode σε
  μία εικόνα με Aspose.BarCode for Java. Ακολουθήστε step‑by‑step guide, δείτε code
  snippets, και μάθετε troubleshooting tips.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Δημιουργία QR code java – δημιουργία πολλαπλών barcode σε μία εικόνα
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Δημιουργία QR code java – δημιουργία πολλαπλών barcode σε μία εικόνα
url: /el/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία QR code java – δημιουργία πολλαπλών barcode σε μία εικόνα

## Εισαγωγή

Σε αυτό το tutorial θα μάθετε **πώς να δημιουργήσετε QR code java** και να συγχωνεύσετε διάφορους τύπους barcode σε έναν ενιαίο καμβά χρησιμοποιώντας **Aspose.BarCode for Java**. Είτε χρειάζεστε μια συμπαγή ετικέτα QR, ένα barcode προϊόντος, ή έναν συνδυασμό 2‑D και γραμμικών συμβολοσειρών, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα—from την ρύθμιση του έργου μέχρι την αποθήκευση της τελικής συνδυασμένης εικόνας—ώστε να αρχίσετε να ενσωματώνετε τη δημιουργία barcode στις εφαρμογές Java σας αμέσως.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη πρέπει να χρησιμοποιήσω;** Το Aspose.BarCode for Java παρέχει το πιο πλήρες σύνολο συμβολοσειρών.  
- **Μπορώ να δημιουργήσω διαφορετικούς τύπους barcode μαζί;** Ναι, μπορείτε να συνδυάσετε CODE_39, QR, AZTEC και άλλα σε έναν ενιαίο καμβά.  
- **Χρειάζεται άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** Η Java 8 και νεότερες είναι πλήρως συμβατές.  
- **Μπορεί να ρυθμιστεί η μορφή εξόδου;** Μπορείτε να εξάγετε την συνδυασμένη εικόνα ως PNG, JPEG, BMP ή TIFF.

## Τι είναι create QR code java;

`create QR code java` αναφέρεται στη διαδικασία μετατροπής μιας αλφαριθμητικής συμβολοσειράς σε ένα δισδιάστατο πλέγμα που μπορεί να σαρωθεί από smartphones ή αναγνώστες barcode. Το Aspose.BarCode for Java εκτελεί την κωδικοποίηση και την απόδοση, ώστε να εστιάσετε στη λογική της επιχείρησης αντί στη διαχείριση εικόνας σε επίπεδο pixel.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode Java για generate barcodes java;

Το Aspose.BarCode υποστηρίζει **πάνω από 50 συμβολοσειρές barcode**—συμπεριλαμβανομένων QR, Data Matrix, Code 128, AZTEC και παραδοσιακών γραμμικών κωδίκων—κάνοντας το τη πιο ευέλικτη βιβλιοθήκη barcode για Java. Παράγει **εικόνες anti‑aliased έως 1200 dpi**, εξασφαλίζοντας καθαρά σάρωση στην οθόνη και στην εκτύπωση. Το API απαιτεί μόνο το JVM και προσφέρει ένα fluent μοντέλο ρυθμίσεων για προσαρμογή μεγέθους, χρώματος, περιθωρίων και διόρθωσης σφαλμάτων με λίγες γραμμές κώδικα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Καλή κατανόηση των βασικών της Java.  
- Εγκατεστημένο και ρυθμισμένο στο PATH το JDK 8 ή νεότερο.  
- Το JAR του Aspose.BarCode for Java (λήψη από τη σελίδα λήψης του Aspose.BarCode for Java).  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse για επεξεργασία και εκτέλεση του δείγματος.  

## Εισαγωγή namespaces

Οι δηλώσεις import φέρνουν τις κλάσεις του Aspose.BarCode όπως `BarcodeGenerator`, `EncodeTypes` και `BarCodeImageFormat` στο scope, επιτρέποντάς σας να τις αναφέρετε χωρίς πλήρη ονομασία.  
`BarcodeGenerator` είναι η κύρια κλάση που χρησιμοποιείται για τη ρύθμιση και δημιουργία εικόνων barcode.  
`EncodeTypes` είναι ένα enum στο Aspose.BarCode που καθορίζει τη συμβολοσειρά barcode που θα δημιουργηθεί.  
`BarCodeImageFormat` ορίζει τη μορφή εξόδου της εικόνας για το δημιουργημένο barcode.

## Βήμα 1: ορισμός του καταλόγου πόρων

Ο **κατάλογος πόρων** είναι ο φάκελος στο σύστημα αρχείων όπου θα γραφτούν όλες οι παραγόμενες εικόνες barcode. Ορίζοντας το μία φορά διατηρεί το έργο σας οργανωμένο και διευκολύνει τον καθαρισμό παλαιών αρχείων.

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

## Βήμα 2: δημιουργία συλλογής barcode

Ένα `HashMap<String, EncodeTypes>` αποθηκεύει τη συμβολοσειρά δεδομένων κάθε barcode μαζί με τη συμβολοσειρά που θέλετε να χρησιμοποιήσετε. Το `HashMap` είναι μια συλλογή Java που αντιστοιχίζει κλειδιά σε τιμές. Αυτή η συλλογή οδηγεί τον βρόχο δημιουργίας που ακολουθεί. Το `EncodeTypes` είναι ένα enum που καθορίζει ποιος τύπος barcode θα δημιουργηθεί.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Βήμα 3: δημιουργία εικόνων barcode

Ο βρόχος δημιουργίας επαναλαμβάνεται πάνω από το `HashMap`, δημιουργεί ένα `BarcodeGenerator` για κάθε καταχώρηση και καλεί το `generateBarCodeImage()` για να λάβει ένα `BufferedImage`. Το `generateBarCodeImage()` δημιουργεί ένα `BufferedImage` που περιέχει το αποδοθέν barcode. Το `BufferedImage` είναι μια κλάση Java που αντιπροσωπεύει μια εικόνα στη μνήμη. Όλες οι εικόνες προστίθενται σε ένα `ArrayList<BufferedImage>` για μεταγενέστερη σύνθεση. Το `ArrayList` είναι μια υλοποίηση λίστας με δυνατότητα αλλαγής μεγέθους στη Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Βήμα 4: δημιουργία συνδυασμένης εικόνας

Αρχικά, ο αλγόριθμος υπολογίζει το **μέγιστο πλάτος** μεταξύ όλων των εικόνων barcode και το **συνολικό ύψος** που απαιτείται για την κατακόρυφη στοίβαξη τους με προαιρετικό κενό. Στη συνέχεια δημιουργεί ένα `BufferedImage` αυτού του μεγέθους και σχεδιάζει κάθε barcode στον καμβά χρησιμοποιώντας ένα αντικείμενο `Graphics2D`. Το `Graphics2D` είναι μια κλάση Java που παρέχει δυνατότητες 2D απόδοσης για το σχήμα και τις εικόνες.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Βήμα 5: αποθήκευση του αποτελέσματος

Τέλος, η σύνθετη εικόνα γράφεται στο δίσκο με `ImageIO.write`, χρησιμοποιώντας τη μορφή που καθορίσατε (PNG, JPEG, BMP ή TIFF). Το `ImageIO.write` γράφει ένα `BufferedImage` σε αρχείο στη συγκεκριμένη μορφή. Η διαδρομή του αρχείου είναι σχετική με τον κατάλογο πόρων που ορίστηκε νωρίτερα.

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

## Συνηθισμένες περιπτώσεις χρήσης για δημιουργία πολλαπλών barcode

- **Ετικέτες συσκευασίας** – συνδυάστε κωδικούς προϊόντος, παρτίδας και αποστολής σε μία ετικέτα για μείωση του κόστους εκτύπωσης.  
- **Εισιτήρια εκδηλώσεων** – ενσωματώστε QR, Data Matrix και Code 128 αναγνωριστές για διαφορετικούς σταθμούς σάρωσης σε έναν χώρο.  
- **Διαχείριση αποθεμάτων** – εμφανίστε SKU, δεδομένα RFID και σειριακούς αριθμούς μαζί για γρήγορο έλεγχο και ιχνηλασιμότητα.

## Αντιμετώπιση προβλημάτων & συμβουλές

- **Προβλήματα μεγέθους εικόνας** – προσαρμόστε τη μεταβλητή `offset` για να αυξήσετε ή να μειώσετε το κενό μεταξύ των barcode.  
- **Μη υποστηριζόμενη συμβολοσειρά** – ελέγξτε ότι η έκδοση του Aspose.BarCode υποστηρίζει τον επιθυμητό τύπο barcode· οι νεότερες εκδόσεις προσθέτουν επιπλέον 2‑D κώδικες.  
- **Απόδοση** – επαναχρησιμοποιήστε ένα μόνο αντικείμενο `Graphics2D` όταν δημιουργείτε πολλές εικόνες σε βρόχο για ελαχιστοποίηση του κόστους κατανομής αντικειμένων.  

## Συχνές ερωτήσεις

**Ε: Μπορώ να προσαρμόσω την εμφάνιση των μεμονωμένων barcode στην παραγόμενη εικόνα;**  
Α: Ναι. Χρησιμοποιήστε τις ιδιότητες του `BarcodeGenerator` όπως `setBarColor`, `setBackgroundColor` και `setXDimension` για να μορφοποιήσετε κάθε barcode ανεξάρτητα πριν το προσθέσετε στον καμβά.

**Ε: Το Aspose.BarCode είναι συμβατό με διαφορετικές συμβολοσειρές barcode;**  
Α: Απόλυτα. Η βιβλιοθήκη υποστηρίζει πάνω από 50 συμβολοσειρές, συμπεριλαμβανομένων CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 και AZTEC, όπως φαίνεται σε αυτό το tutorial.

**Ε: Πώς ενσωματώνω το Aspose.BarCode στο έργο Java μου;**  
Α: Κατεβάστε το JAR από τη σελίδα λήψης του Aspose.BarCode for Java, προσθέστε το στο classpath του έργου σας και εισάγετε τα απαιτούμενα namespaces όπως φαίνεται στην ενότητα “Εισαγωγή namespaces”.

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.BarCode για εμπορικές εφαρμογές;**  
Α: Ναι. Αγοράστε άδεια από τη σελίδα αγοράς άδειας Aspose.BarCode για να αφαιρέσετε τους περιορισμούς της δοκιμής και να λάβετε πλήρη υποστήριξη παραγωγής.

**Ε: Υπάρχουν επιλογές δοκιμής για το Aspose.BarCode;**  
Α: Φυσικά. Μια δωρεάν δοκιμαστική άδεια είναι διαθέσιμη από τη σελίδα δωρεάν δοκιμής Aspose.BarCode, παρέχοντάς σας πλήρη πρόσβαση στο API για αξιολόγηση.

**Ε: Πώς δημιουργώ έναν υψηλής ανάλυσης QR code για εκτύπωση;**  
Α: Ορίστε την ιδιότητα `setResolutionDpi` στο `BarcodeGenerator` πριν καλέσετε το `generateBarCodeImage()`, στη συνέχεια αποθηκεύστε το αποτέλεσμα σε μορφή χωρίς απώλειες όπως PNG.

**Ε: Τι πρέπει να κάνω αν η συνδυασμένη εικόνα φαίνεται κομμένη;**  
Α: Επαληθεύστε ότι οι υπολογισμοί `offset` και μεγέθους καμβά λαμβάνουν σωστά υπόψη όλα τα ύψη των barcode· η αύξηση του ύψους του καμβά ή η μείωση του μεγέθους των μεμονωμένων barcode λύνει τα περισσότερα προβλήματα κοπής.

---

**Τελευταία ενημέρωση:** 2026-10-19  
**Δοκιμασμένο με:** Aspose.BarCode for Java 24.11  
**Συγγραφέας:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Σχετικά Tutorials

- [How to Create Barcode Image Java – Add Border with Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [How to Generate Barcode Java: Save to Streams with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [How to Generate Barcode Java and Print Barcode with Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}