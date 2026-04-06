---
date: 2026-02-07
description: Μάθετε πώς να χρησιμοποιείτε το Aspose Barcode Java για να δημιουργήσετε
  έναν κωδικό CODE_128, να παράγετε εικόνα κωδικού Java και να ορίσετε ακριβείς μονάδες
  μεγέθους — ιδανικό για κωδικούς σε σύστημα αποθεμάτων ή για δημιουργία ετικετών
  αποστολής.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 'aspose barcode java: Δημιουργία γραμμωτού κώδικα CODE_128 με μονάδα μεγέθους'
url: /el/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java: Δημιουργία CODE_128 barcode με μονάδα μεγέθους

## Εισαγωγή

Σε αυτό το βήμα‑βήμα tutorial θα **use aspose barcode java** για να δημιουργήσετε ένα CODE_128 barcode, να δημιουργήσετε μια barcode image java, και να ελέγξετε με ακρίβεια τη μονάδα μεγέθους του αποτελέσματος. Είτε δημιουργείτε ένα barcode για σύστημα αποθεμάτων, ένα γεννήτρια ετικετών αποστολής, ή οποιαδήποτε εφαρμογή βασισμένη σε Java που χρειάζεται αξιόπιστα barcodes, το Aspose.BarCode for Java σας παρέχει πλήρη ευελιξία με λίγες μόνο γραμμές κώδικα.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.BarCode for Java (aspose barcode java).  
- **Ποιος τύπος barcode καλύπτεται;** CODE_128 (create code128 barcode java).  
- **Πώς ορίζω τη μονάδα μεγέθους;** Use the `BarHeight` property with `.setPoint()`.  
- **Μπορώ να δημιουργήσω barcode image java σε άλλες μορφές;** Yes – PNG, JPEG, BMP, etc.  
- **Ποια είναι τα προαπαιτούμενα;** JDK installed, Aspose.BarCode library, and a Java IDE.

## Τι είναι **create code128 barcode java**?

Η δημιουργία ενός CODE_128 barcode σε Java σημαίνει την δημιουργία ενός αντικειμένου της κλάσης `BarcodeGenerator` με την enum `EncodeTypes.CODE_128` και την παροχή της συμβολοσειράς δεδομένων που θέλετε να κωδικοποιήσετε. Αυτή η συμβολική είναι ευρέως χρησιμοποιούμενη στη λογιστική επειδή υποστηρίζει το πλήρες σύνολο χαρακτήρων ASCII και προσφέρει υψηλή πυκνότητα δεδομένων—κάνοντας την ιδανική για barcode σε σενάρια συστημάτων αποθεμάτων.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για **generate barcode image java**?

- **Full control over dimensions** – μπορείτε να ορίσετε το ύψος των γραμμών, το μέγεθος του μονάδας, και την ανάλυση της εικόνας.  
- **No external dependencies** – καθαρή Java, λειτουργεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει το JDK.  
- **Rich customization** – χρώματα, γραμματοσειρές, περιθώρια, και ακόμη κωδικοί QR υποστηρίζονται.  
- **High performance** – δημιουργεί εικόνες σε χιλιοστά του δευτερολέπτου, κατάλληλο για επεξεργασία παρτίδων και δημιουργία ροών εργασίας barcode ετικετών αποστολής.  

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη εγκατεστημένη στο σύστημά σας.  
2. **Aspose.BarCode for Java library** – κατεβάστε το τελευταίο JAR από την ιστοσελίδα Aspose (δοκιμαστική ή με άδεια).  
3. **A Java IDE** – όπως IntelliJ IDEA, Eclipse, ή VS Code με επεκτάσεις Java.  

## Εισαγωγή Namespaces

Προσθέστε τις απαιτούμενες εισαγωγές στην αρχή της κλάσης Java ώστε να έχετε πρόσβαση στο API του Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Πώς να **generate barcode image java** με Aspose.BarCode?

Ακολουθεί η πλήρης ροή εργασίας. Κάθε βήμα εξηγείται με απλή γλώσσα, και τα αρχικά μπλοκ κώδικα διατηρούνται ακριβώς όπως ήταν.

### Βήμα 1: Ορισμός του Καταλόγου Πόρων

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Αντικαταστήστε το `"Your Document Directory"` με το απόλυτο μονοπάτι όπου θέλετε να αποθηκευτεί η εικόνα barcode. Αυτός ο φάκελος θα περιέχει τα παραγόμενα αρχεία PNG/JPEG που μπορείτε αργότερα να ενσωματώσετε σε τιμολόγια, δελτία αποστολής ή αναφορές αποθεμάτων.

### Βήμα 2: Δημιουργία του Αντικειμένου Barcode

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Εδώ **create code128 barcode java** περνώντας το `EncodeTypes.CODE_128` και τη συμβολοσειρά δεδομένων `"1234567"`.

### Βήμα 3: Ορισμός Ύψους Γραμμής (Μονάδα Μεγέθους)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

Η μέθοδος `setPoint()` ορίζει το ύψος σε points (1 point = 1/72 ίντσα). Ρυθμίστε αυτήν την τιμή ώστε να καλύπτει τις απαιτήσεις διάταξής σας—μεγαλύτερες τιμές παράγουν πιο ψηλές γραμμές, κάτι που συχνά χρειάζεται για ετικέτες αποστολής υψηλής ανάλυσης.

### Βήμα 4: Αποθήκευση της Εικόνας

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

Η κλήση `save()` γράφει το παραγόμενο barcode στον φάκελο που καθορίσατε. Η μορφή της εικόνας προκύπτει από την επέκταση του αρχείου (JPEG σε αυτήν την περίπτωση). Μπορείτε να μεταβείτε σε PNG, BMP ή TIFF απλώς αλλάζοντας την επέκταση.

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Image not created** | `dataDir` η διαδρομή είναι λανθασμένη ή λείπουν δικαιώματα εγγραφής. | Επαληθεύστε ότι ο φάκελος υπάρχει και ότι η εφαρμογή σας έχει δικαιώματα εγγραφής. |
| **Barcode appears too small** | Το ύψος γραμμής ορισμένο σε points είναι πολύ χαμηλό για το επιλεγμένο DPI. | Αυξήστε την τιμή που περνάτε στο `setPoint()` ή προσαρμόστε το DPI της εικόνας μέσω `bb.getParameters().getImage().setResolution()`. |
| **Unsupported characters** | Το CODE_128 υποστηρίζει μόνο ASCII· εσείς περάσατε Unicode. | Χρησιμοποιήστε διαφορετική συμβολική (π.χ., QR_CODE) για δεδομένα μη‑ASCII. |

## Συχνές Ερωτήσεις

**Q: Είναι το Aspose.BarCode for Java κατάλληλο τόσο για δημιουργία όσο και για αναγνώριση barcode;**  
A: Ναι, η βιβλιοθήκη υποστηρίζει τόσο τη δημιουργία όσο και την αναγνώριση μιας ευρείας γκάμας συμβολικών.

**Q: Μπορώ να προσαρμόσω την εμφάνιση των παραγόμενων εικόνων barcode;**  
A: Απόλυτα. Μπορείτε να αλλάξετε χρώματα, να προσθέσετε λεζάντες, να τροποποιήσετε περιθώρια, και ακόμη να ενσωματώσετε λογότυπα χρησιμοποιώντας το εκτενές API `Parameters`.

**Q: Πώς μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.BarCode for Java;**  
A: Επισκεφθείτε [here](https://purchase.aspose.com/temporary-license/) για να ζητήσετε προσωρινή άδεια αξιολόγησης.

**Q: Πού μπορώ να βρω υποστήριξη για το Aspose.BarCode for Java;**  
A: Το φόρουμ κοινότητας Aspose.BarCode είναι το καλύτερο μέρος για βοήθεια. Ελέγξτε το [forum](https://forum.aspose.com/c/barcode/13) για απαντήσεις και για να θέσετε νέες ερωτήσεις.

**Q: Ποιες συμβολικές barcode υποστηρίζονται στο Aspose.BarCode for Java;**  
A: Η βιβλιοθήκη υποστηρίζει δεκάδες συμβολικές, συμπεριλαμβανομένων των CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, και πολλών άλλων.

### Πρόσθετες Συμβουλές (Pro tip)

- **Batch processing:** Τυλίξτε τα παραπάνω βήματα σε ένα βρόχο για να δημιουργήσετε εκατοντάδες barcodes για μαζικές μεταφορτώσεις αποθεμάτων.  
- **Resolution control:** Χρησιμοποιήστε `bb.getParameters().getImage().setResolution(300)` για να παραγάγετε εικόνες 300 dpi, που είναι ιδανικές για ετικέτες εκτύπωσης υψηλής ποιότητας.  

---

**Τελευταία ενημέρωση:** 2026-02-07  
**Δοκιμή με:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}