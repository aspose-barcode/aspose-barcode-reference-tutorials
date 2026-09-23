---
date: 2026-08-28
description: Μάθετε πώς να προσθέσετε συμπλήρωμα σε barcodes σε Java χρησιμοποιώντας
  το Aspose.BarCode. Αυτός ο οδηγός παρουσιάζει ένα παράδειγμα barcode generator Java
  για dynamic barcode generation και EAN‑13 με supplemental data.
keywords:
- how to add supplement
- barcode generator example java
- how to generate barcode java
- dynamic barcode generation java
lastmod: 2026-08-28
linktitle: Συμπλήρωση Δεδομένων
og_description: Μάθετε πώς να προσθέσετε συμπλήρωμα σε barcodes σε Java χρησιμοποιώντας
  το Aspose.BarCode. Αυτό το tutorial παρέχει ένα παράδειγμα barcode generator Java,
  βήματα dynamic barcode generation, και πώς να δημιουργήσετε barcode EAN‑13 με supplemental
  data.
og_image_alt: 'Developer guide: Adding supplement to Java barcode using Aspose.BarCode'
og_title: Πώς να προσθέσετε συμπλήρωμα κατά τη δημιουργία barcode σε Java
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to add supplement to barcodes in Java using Aspose.BarCode.
    This guide shows a barcode generator example Java for dynamic barcode generation
    and EAN‑13 with supplemental data.
  headline: How to add supplement when generating barcode in Java
  type: TechArticle
- description: Learn how to add supplement to barcodes in Java using Aspose.BarCode.
    This guide shows a barcode generator example Java for dynamic barcode generation
    and EAN‑13 with supplemental data.
  name: How to add supplement when generating barcode in Java
  steps:
  - name: define your document directory
    text: Set the folder where the generated image will be stored.
  - name: create barcode generator instance
    text: '`BarcodeGenerator` is Aspose.BarCode''s core object that creates barcode
      images from supplied data. Instantiate it with the desired **codetext** and
      **symbology**. Here we **create an EAN‑13 barcode** using the numeric string
      `"123456789123"`.'
  - name: set supplement data
    text: Add a 5‑digit supplemental string. This is useful for magazines, periodicals,
      or any case where extra information follows the main barcode.
  - name: set supplement space
    text: Adjust the gap between the main barcode and its supplement. The value is
      expressed in points.
  - name: save the barcode image
    text: Finally, write the image to disk. The format is inferred from the file extension
      (JPEG in this example). > **Pro tip:** You can change the file extension to
      `.png` or `.bmp` to get a different image format without extra code.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library is best for generating barcodes in Java?
  - answer: EAN‑13.
    question: Which symbology creates a 13‑digit numeric barcode?
  - answer: Yes, using the `Supplement` API.
    question: Can I add supplemental data to an EAN‑13 barcode?
  - answer: Call `generator.save("path/filename.jpg")`.
    question: How do I save the generated barcode as an image?
  - answer: Yes, a commercial license is needed; a free trial is available.
    question: Is a license required for production use?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode supplement
- Aspose.BarCode
- Java barcode generation
- EAN-13
title: Πώς να προσθέσετε συμπλήρωμα κατά τη δημιουργία barcode σε Java
url: /el/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε συμπλήρωμα κατά τη δημιουργία barcode σε Java

## Εισαγωγή

Στο σημερινό ταχύτατο ψηφιακό οικοσύστημα, πολλοί προγραμματιστές Java αναρωτιούνται **πώς να προσθέσουν συμπλήρωμα** σε ένα barcode αποδοτικά. Το Aspose.BarCode for Java προσφέρει ένα ισχυρό, εύχρηστο API που υποστηρίζει **δυναμική δημιουργία barcode**, συμπεριλαμβανομένης της δημιουργίας **EAN‑13 barcodes** με συμπληρωματικά δεδομένα. Είτε δημιουργείτε συστήματα αποθεμάτων, εφαρμογές λιανικού POS ή παρακολούθηση logistics, αυτό το tutorial σας καθοδηγεί μέσω ενός **barcode generator example Java** που αποθηκεύει την εικόνα του barcode στο δίσκο και σας επιτρέπει να προσαρμόσετε το τμήμα του συμπληρώματος.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη είναι η καλύτερη για τη δημιουργία barcode σε Java;** Aspose.BarCode for Java.  
- **Ποια συμβολική κωδικοποίηση δημιουργεί ένα 13‑ψήφιο αριθμητικό barcode;** EAN‑13.  
- **Μπορώ να προσθέσω συμπληρωματικά δεδομένα σε ένα EAN‑13 barcode;** Ναι, χρησιμοποιώντας το API `Supplement`.  
- **Πώς αποθηκεύω το δημιουργημένο barcode ως εικόνα;** Κλήση `generator.save("path/filename.jpg")`.  
- **Απαιτείται άδεια για χρήση σε παραγωγή;** Ναι, απαιτείται εμπορική άδεια· διατίθεται δωρεάν δοκιμαστική έκδοση.

## Τι είναι η δημιουργία barcode σε Java;

Η δημιουργία ενός barcode σημαίνει τη μετατροπή ακατέργαστων δεδομένων—αριθμών, γραμμάτων ή συνδυασμού—σε ένα οπτικό μοτίβο που μπορούν να διαβάσουν οι σαρωτές. Το Aspose.BarCode μπορεί να παράγει **εικόνες barcode υψηλής ανάλυσης** άμεσα, καθιστώντας το ιδανικό για σενάρια **δυναμικής δημιουργίας barcode σε Java** όπως η έκδοση εισιτηρίων σε πραγματικό χρόνο, η εκπλήρωση παραγγελιών ή η δημιουργία ετικετών εν κινήσει. Αυτή η δυνατότητα εξαλείφει την ανάγκη αποθήκευσης προ‑δημιουργημένων εικόνων και σας δίνει πλήρη έλεγχο στο μέγεθος, τη μορφή και την εμφάνιση.

## Γιατί να χρησιμοποιήσετε το Aspose.BarCode για Java;

Το Aspose.BarCode υποστηρίζει **πάνω από 30 συμβολισμούς barcode** και μπορεί να δημιουργήσει εικόνες έως **10.000 × 10.000 px** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, επιτρέποντας περιβάλλοντα υψηλής απόδοσης. Η βιβλιοθήκη λειτουργεί σε οποιοδήποτε runtime Java 8+, τρέχει σε Windows, Linux και macOS, και παρέχει ένα ενιαίο API για raster (PNG, JPEG, BMP) και vector (SVG, PDF) εξόδους.

## Προαπαιτούμενα

- **Java Development Kit (JDK)** – οποιαδήποτε πρόσφατη έκδοση (8 ή νεότερη).  
- **IDE** – IntelliJ IDEA, Eclipse ή ο αγαπημένος σας επεξεργαστής.  
- **Aspose.BarCode for Java** – κατεβάστε τη βιβλιοθήκη από την επίσημη ιστοσελίδα **[Aspose.BarCode for Java download](https://releases.aspose.com/barcode/java/)** και προσθέστε το JAR στην classpath του έργου σας.

## Εισαγωγή πακέτων

Μόλις η βιβλιοθήκη αναφερθεί, εισάγετε την κύρια κλάση που καθοδηγεί τη δημιουργία barcode.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Οδηγός βήμα‑βήμα

### Βήμα 1: ορίστε τον φάκελο εγγράφου σας

Ορίστε το φάκελο όπου θα αποθηκευτεί η παραγόμενη εικόνα.

```java
String dataDir = "Your Document Directory";
```

### Βήμα 2: δημιουργήστε ένα στιγμιότυπο του barcode generator

`BarcodeGenerator` είναι το κύριο αντικείμενο του Aspose.BarCode που δημιουργεί εικόνες barcode από τα παρεχόμενα δεδομένα. Δημιουργήστε το με το επιθυμητό **codetext** και **symbology**. Εδώ **δημιουργούμε ένα EAN‑13 barcode** χρησιμοποιώντας τη αριθμητική συμβολοσειρά `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Βήμα 3: ορίστε τα δεδομένα συμπληρώματος

Προσθέστε μια 5‑ψήφια συμβολοσειρά συμπληρώματος. Αυτό είναι χρήσιμο για περιοδικά, εφημερίδες ή οποιαδήποτε περίπτωση όπου πρόσθετες πληροφορίες ακολουθούν το κύριο barcode.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Βήμα 4: ορίστε το κενό του συμπληρώματος

Ρυθμίστε το κενό μεταξύ του κύριου barcode και του συμπληρώματός του. Η τιμή εκφράζεται σε points.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Βήμα 5: αποθηκεύστε την εικόνα του barcode

Τέλος, γράψτε την εικόνα στο δίσκο. Η μορφή προκύπτει από την επέκταση του αρχείου (JPEG σε αυτό το παράδειγμα).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Συμβουλή:** Μπορείτε να αλλάξετε την επέκταση του αρχείου σε `.png` ή `.bmp` για να λάβετε διαφορετική μορφή εικόνας χωρίς επιπλέον κώδικα.

## Πώς να δημιουργήσετε EAN‑13 barcode με συμπληρωματικά δεδομένα;

Φορτώστε το `BarcodeGenerator` με έναν κώδικα EAN‑13, καλέστε `setSupplement()` για να προσθέσετε τα επιπλέον ψηφία, προαιρετικά ρυθμίστε `setSupplementSpace()`, και στη συνέχεια καλέστε `save()` για να γράψετε την εικόνα. Αυτή η τετραβήματική διαδικασία παράγει ένα barcode σύμφωνο με τα πρότυπα, το οποίο διαβάζουν σωστά οι σαρωτές, ενώ τα συμπληρωματικά ψηφία εμφανίζονται ως μια μικρότερη ομάδα γραμμών στα δεξιά του κύριου κώδικα.

## Συνηθισμένες περιπτώσεις χρήσης για δυναμική δημιουργία barcode σε Java

- **Λιανική αποθήκευση:** Δημιουργήστε barcodes προϊόντων κατ' απαίτηση όταν προστίθενται νέα SKU.  
- **Έκδοση:** Προσθέστε αριθμούς τεύχους ως συμπληρωματικά δεδομένα σε barcodes περιοδικών.  
- **Logistics:** Δημιουργήστε ετικέτες αποστολής με barcodes εν κινήσει που περιλαμβάνουν αριθμούς παρτίδας ή δέσμης.  

## Συνηθισμένα προβλήματα και λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Η εικόνα δεν αποθηκεύτηκε** | `dataDir` δείχνει σε φάκελο που δεν υπάρχει | Βεβαιωθείτε ότι ο φάκελος υπάρχει ή δημιουργήστε τον προγραμματιστικά (`new File(dataDir).mkdirs();`). |
| **Μη έγκυρο μήκος συμπληρώματος** | Τα συμπληρώματα EAN‑13 πρέπει να είναι 2 ή 5 ψηφία | Παρέχετε ακριβώς 2 ή 5 χαρακτήρες· διαφορετικά θα ριχτεί εξαίρεση. |
| **Μη υποστηριζόμενοι χαρακτήρες** | Μη αριθμητικοί χαρακτήρες στο codetext του EAN‑13 | Χρησιμοποιήστε μόνο ψηφία 0‑9 για το EAN‑13· μεταβείτε σε άλλη συμβολική κωδικοποίηση για αλφαριθμητικά. |

## Συχνές ερωτήσεις

### Είναι το Aspose.BarCode συμβατό με όλες τις εκδόσεις Java;

Το Aspose.BarCode for Java έχει σχεδιαστεί να λειτουργεί με Java 8 έως Java 21, καλύπτοντας τόσο τις LTS όσο και τις πιο πρόσφατες εκδόσεις. Η επίσημη **[documentation](https://reference.aspose.com/barcode/java/)** παραθέτει τις ακριβείς υποστηριζόμενες εκδόσεις.

### Μπορώ να προσαρμόσω την εμφάνιση των παραγόμενων barcodes;

Ναι, το Aspose.BarCode παρέχει εκτενείς επιλογές στυλ όπως χρώματα προσκηνίου/παρασκηνίου, τύπους γραμματοσειρών για κείμενο αναγνώσιμο από άνθρωπο, πλάτος γραμμής και ρυθμίσεις περιθωρίων. Μπορείτε επίσης να ενσωματώσετε το barcode σε PDF, έγγραφα Word ή σελίδες HTML χρησιμοποιώντας το ίδιο API.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση;

Μια δωρεάν δοκιμαστική έκδοση είναι διαθέσιμη **[Aspose trial download page](https://releases.aspose.com/)**. Η δοκιμή περιλαμβάνει όλες τις λειτουργίες αλλά προσθέτει ένα μικρό υδατογράφημα στις παραγόμενες εικόνες.

### Πώς μπορώ να λάβω υποστήριξη για το Aspose.BarCode;

Επισκεφθείτε το **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** για να λάβετε βοήθεια από την κοινότητα και τους ειδικούς του προϊόντος. Η premium υποστήριξη προσφέρεται επίσης με εμπορικές άδειες.

### Πού μπορώ να αγοράσω το Aspose.BarCode για Java;

Μπορείτε να αγοράσετε άδεια **[Aspose purchase page](https://purchase.aspose.com/buy)**. Οι άδειες διατίθενται ως μονιμότερες ή συνδρομητικές, με επιλογές για προγραμματιστές, ομάδες και επιχειρήσεις.

## Πρόσθετες Συχνές Ερωτήσεις (μορφή φιλική προς AI)

**Q:** Ποιος είναι ο πιο εύκολος τρόπος για να ξεκινήσετε ένα **barcode generator example Java**;  
**A:** Προσθέστε το JAR του Aspose.BarCode στο έργο σας, εισάγετε το `BarcodeGenerator`, και ακολουθήστε τον οδηγό βήμα‑βήμα παραπάνω για να δημιουργήσετε και να αποθηκεύσετε ένα EAN‑13 barcode με συμπληρωματικά δεδομένα.

**Q:** Μπορώ να δημιουργήσω πολλαπλά barcodes σε βρόχο για επεξεργασία παρτίδας;  
**A:** Απόλυτα. Δημιουργήστε ένα νέο `BarcodeGenerator` μέσα στον βρόχο, ορίστε ένα μοναδικό `codetext` σε κάθε επανάληψη, και καλέστε `save()` με διαφορετικό όνομα αρχείου.

**Q:** Υποστηρίζει το API άλλες μορφές εικόνας όπως PNG ή SVG;  
**A:** Ναι. Η μορφή εξόδου προκύπτει από την επέκταση του αρχείου που παρέχετε (π.χ., `.png`, `.svg`). Δεν απαιτείται επιπλέον κώδικας.

**Q:** Πώς να διαχειριστώ μεγάλους όγκους χωρίς να καταναλώνω πολύ μνήμη;  
**A:** Δημιουργήστε και αποθηκεύστε κάθε barcode αμέσως, μετά απορρίψτε το στιγμιότυπο του generator πριν την επόμενη επανάληψη. Αυτό διατηρεί τη χρήση μνήμης χαμηλή ακόμη και όταν επεξεργάζεστε χιλιάδες εικόνες.

**Q:** Υπάρχει τρόπος να ενσωματώσετε το barcode απευθείας σε PDF;  
**A:** Ανακτήστε το barcode ως `byte[]` χρησιμοποιώντας `generator.generateBarCodeImage()` και ενσωματώστε το σε PDF με το Aspose.PDF ή οποιαδήποτε άλλη βιβλιοθήκη PDF.

**Τελευταία ενημέρωση:** 2026-08-28  
**Δοκιμάστηκε με:** Aspose.BarCode for Java 24.11  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε Barcode Java – Οδηγός πλήρους διαμόρφωσης](/barcode/java/barcode-configuration/)
- [Εφαρμογή επικύρωσης Checksum σε Java – Οδηγός Aspose.BarCode](/barcode/java/checksum-and-validation/applying-checksum-validation/)
- [Πώς να προσθέσετε λεζάντα σε Barcode σε Java χρησιμοποιώντας Aspose.Barcode Java](/barcode/java/text-and-styling/adding-caption-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}