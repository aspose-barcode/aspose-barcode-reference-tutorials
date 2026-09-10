---
date: 2026-05-04
description: Μάθετε πώς να προσθέτετε λεζάντα σε εικόνες barcode σε Java χρησιμοποιώντας
  το Aspose.Barcode Java. Αυτό το παράδειγμα δημιουργίας barcode σε Java δείχνει πώς
  να δημιουργήσετε εικόνα barcode σε Java με ευκολία.
keywords:
- aspose barcode java
- how to add caption
- barcode generator java
- save barcode image
linktitle: Προσθήκη λεζάντας στον κωδικό γραμμής
second_title: Aspose.BarCode Java API
title: Πώς να προσθέσετε λεζάντα σε γραμμωτό κώδικα στη Java χρησιμοποιώντας το Aspose.Barcode
  Java
url: /el/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Προσθέσετε Λεζάντα σε Barcode σε Java Χρησιμοποιώντας το Aspose.Barcode Java

## Εισαγωγή

Αν χρειάζεστε **πώς να προσθέσετε λεζάντα** σε ένα barcode για καλύτερη αναγνωσιμότητα και branding, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε βήμα-βήμα τις ακριβείς ενέργειες για να προσθέσετε λεζάντες πάνω και κάτω από μια εικόνα barcode χρησιμοποιώντας το **Aspose.Barcode Java**. Στο τέλος, θα έχετε ένα πλήρως μορφοποιημένο barcode που όχι μόνο κωδικοποιεί δεδομένα αλλά εμφανίζει και χρήσιμο κείμενο—ιδανικό για ετικέτες προϊόντων, συστήματα αποθεμάτων ή οποιοδήποτε σενάριο όπου οι χρήστες επωφελούνται από επιπλέον συμφραζόμενα.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Barcode Java.  
- **Μπορώ να αλλάξω τη γραμματοσειρά και το χρώμα;** Ναι—και η οικογένεια γραμματοσειράς της λεζάντας και το χρώμα κειμένου είναι προσαρμόσιμα.  
- **Ποιοι τύποι barcode λειτουργούν;** Όλες οι συμβολές που υποστηρίζονται από το Aspose.Barcode (π.χ., CODE_128, QR, DataMatrix).  
- **Χρειάζομαι άδεια για δοκιμή;** Διατίθεται δωρεάν δοκιμαστική έκδοση· απαιτείται εμπορική άδεια για παραγωγή.  
- **Πόσο διαρκεί η υλοποίηση;** Συνήθως λιγότερο από 10 λεπτά μόλις προστεθεί η βιβλιοθήκη.

## Τι είναι μια λεζάντα σε ένα barcode;
Μια λεζάντα είναι απλό κείμενο που εμφανίζεται είτε πάνω είτε κάτω από το γραφικό του barcode. Μπορεί να μεταφέρει ονόματα προϊόντων, τιμές ή οποιαδήποτε άλλη πληροφορία που συμπληρώνει τα κωδικοποιημένα δεδομένα.

## Γιατί να προσθέσετε λεζάντες με το Aspose.Barcode Java;
- **Βελτιωμένη εμπειρία χρήστη:** Οι χρήστες μπορούν άμεσα να διαβάσουν το νόημα ενός barcode χωρίς σάρωση.  
- **Συνέπεια μάρκας:** Μπορείτε να εφαρμόσετε τις δικές σας γραμματοσειρές, χρώματα και στοίχιση ώστε να ταιριάζουν με τα εταιρικά στυλ.  
- **Πλήρης έλεγχος:** Το API του Aspose.Barcode σας επιτρέπει να εναλλάσσετε την ορατότητα, να ορίζετε στοίχιση και να μορφοποιείτε κάθε λεζάντα ανεξάρτητα.  
- **Απρόσκοπτη ενσωμάτωση:** Λειτουργεί ομαλά με τη ροή εργασίας **barcode generator java** και σας επιτρέπει να **αποθηκεύσετε την εικόνα barcode** στη μορφή που χρειάζεστε.

## Προαπαιτούμενα

- Java Development Kit (JDK) εγκατεστημένο.  
- Βιβλιοθήκη Aspose.BarCode for Java ληφθείσα και προστιθέμενη στο έργο σας. Μπορείτε να βρείτε τον σύνδεσμο λήψης [εδώ](https://releases.aspose.com/barcode/java/).  
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.

## Εισαγωγή Πακέτων

Στο αρχείο πηγαίου κώδικα Java, εισάγετε τις απαιτούμενες κλάσεις του Aspose.BarCode και την κλάση AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Βήμα 1: Ρύθμιση Εγγράφου και Καταλόγων Πόρων

Καθορίστε πού θέλετε να αποθηκεύσετε την παραγόμενη εικόνα barcode. Προσαρμόστε τις διαδρομές ώστε να ταιριάζουν με το περιβάλλον σας.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Βήμα 2: Δημιουργία Παράδειγματος Barcode Generator

Δημιουργήστε ένα αντικείμενο `BarcodeGenerator` με την επιθυμητή συμβολή (π.χ., CODE_128) και το κείμενο κώδικα που θέλετε να κωδικοποιήσετε.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Βήμα 3: Διαμόρφωση Λεζάντας Πάνω από το Barcode

Ορίστε τη λεζάντα που εμφανίζεται πάνω από το barcode. Μπορείτε να ελέγξετε τη στοίχιση, το κείμενο, την ορατότητα, την οικογένεια γραμματοσειράς, το μέγεθος και το χρώμα.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Βήμα 4: Διαμόρφωση Λεζάντας Κάτω από το Barcode

Ανάλογα, ορίστε τη λεζάντα κάτω από το barcode. Μη διστάσετε να χρησιμοποιήσετε διαφορετική στοίχιση ή μορφοποίηση αν χρειάζεται.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().setSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Βήμα 5: Αποθήκευση της Εικόνας Barcode

Τέλος, γράψτε το barcode (με λεζάντες) σε αρχείο εικόνας. Η μορφή προκύπτει από την επέκταση του αρχείου.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Μπορείτε να επαναλάβετε τα παραπάνω βήματα για να πειραματιστείτε με διαφορετικές γραμματοσειρές, χρώματα ή στοίχιση, ή για να δημιουργήσετε πολλαπλές εικόνες barcode σε βρόχο.

## Κοινά Προβλήματα & Συμβουλές

- **Η λεζάντα δεν είναι ορατή;** Βεβαιωθείτε ότι καλείται `setVisible(true)` για τη λεζάντα που θέλετε να εμφανίσετε.  
- **Λάθος χρώματα;** Χρησιμοποιήστε τις σταθερές `java.awt.Color` ή δημιουργήστε προσαρμοσμένα χρώματα με `new Color(r, g, b)`.  
- **Προβλήματα διαδρομής;** Επαληθεύστε ότι το `dataDir` δείχνει σε έναν υπάρχοντα φάκελο με δικαιώματα εγγραφής· διαφορετικά, το `bb.save()` θα ρίξει `IOException`.  
- **Συμβουλή απόδοσης:** Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarcodeGenerator` όταν δημιουργείτε πολλά barcodes· αλλάξτε μόνο το `EncodeTypes` ή το `codetext` όπως χρειάζεται.

## Συχνές Ερωτήσεις (FAQs)

### Μπορώ να προσαρμόσω το στυλ γραμματοσειράς των λεζαντών του barcode;
Ναι, μπορείτε να προσαρμόσετε την οικογένεια γραμματοσειράς, το μέγεθος και το χρώμα και των δύο λεζαντών, πάνω και κάτω από το barcode.

### Είναι το Aspose.BarCode συμβατό με διαφορετικές συμβολές barcode;
Απολύτως! Το Aspose.BarCode υποστηρίζει ένα ευρύ φάσμα συμβολών, εξασφαλίζοντας ευελιξία στη δημιουργία barcode.

### Πώς μπορώ να ενσωματώσω το Aspose.BarCode στο Java project μου;
Μπορείτε να ακολουθήσετε τον λεπτομερή οδηγό ενσωμάτωσης που είναι διαθέσιμος [εδώ](https://reference.aspose.com/barcode/java/) για βήμα‑βήμα οδηγίες.

### Υπάρχει δωρεάν δοκιμαστική έκδοση για το Aspose.BarCode για Java;
Ναι, μπορείτε να αποκτήσετε πρόσβαση στη δωρεάν δοκιμαστική έκδοση [εδώ](https://releases.aspose.com/) για να εξερευνήσετε όλες τις δυνατότητες πριν από την αγορά.

### Πού μπορώ να λάβω βοήθεια αν αντιμετωπίσω προβλήματα;
Το φόρουμ κοινότητας Aspose.BarCode είναι ένας εξαιρετικός χώρος για υποστήριξη και συζήτηση. Επισκεφθείτε το φόρουμ [εδώ](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}