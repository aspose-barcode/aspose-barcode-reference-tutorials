---
category: general
date: 2026-10-18
description: Δημιουργήστε κωδικό databar expanded σε Java με το Aspose.BarCode. Μάθετε
  πώς να δημιουργείτε databar, να ορίζετε σειρές και να εξάγετε την εικόνα του barcode
  σε μορφή PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: el
lastmod: 2026-10-18
og_description: Δημιουργήστε γραμμωτό κώδικα Databar Expanded σε Java. Ακολουθήστε
  αυτόν τον οδηγό για να μάθετε πώς να δημιουργείτε Databar, να διαμορφώνετε γραμμές
  και να εξάγετε την εικόνα του γραμμωτού κώδικα ως PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: Δημιουργήστε γραμμωτό κώδικα Databar Expanded σε Java – βήμα‑βήμα οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: Δημιουργία κωδικού Databar Expanded σε Java – πλήρης οδηγός
url: /el/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία κωδικού γραμμής databar expanded σε Java – πλήρης οδηγός

Αν χρειάζεστε **να δημιουργήσετε κωδικό γραμμής databar expanded** σε Java, αυτό το tutorial σας δείχνει ακριβώς **πώς να δημιουργήσετε εικόνες databar** χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Θα μάθετε επίσης πώς να ρυθμίσετε **γραμμές δημιουργού κωδικού γραμμής** και **να εξάγετε αρχεία εικόνας κωδικού γραμμής** σε μορφή PNG.

Στις παρακάτω ενότητες θα βρείτε ένα πλήρες, εκτελέσιμο πρόγραμμα, εξηγήσεις βήμα‑βήμα για κάθε κλήση API και συμβουλές για την αντιμετώπιση κοινών περιπτώσεων, όπως μη υποστηριζόμενοι χαρακτήρες ή προσαρμοσμένα μεγέθη διάταξης. Στο τέλος αυτού του οδηγού θα μπορείτε να παράγετε τόσο κωδικούς Databar Expanded με 4 στήλες όσο και με 3 γραμμές και να τους αποθηκεύετε όπου χρειάζεται.

## Προαπαιτούμενα

* Java 17 ή νεότερη (ο κώδικας μεταγλωττίζεται με οποιοδήποτε JDK 11+)
* Maven ή Gradle για διαχείριση εξαρτήσεων
* Aspose.BarCode για Java – προσθέστε την τελευταία έκδοση στο `pom.xml` ή `build.gradle`
* Βασική εξοικείωση με τη μέθοδο `main` της Java και τις αντικειμενοστραφείς έννοιες

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **Συμβουλή:** Η δωρεάν άδεια αξιολόγησης λειτουργεί για ανάπτυξη· αντικαταστήστε την με αγορασμένη άδεια πριν την ανάπτυξη στην παραγωγή.

## Δημιουργία κωδικού γραμμής databar expanded – αρχική ρύθμιση

Το πρώτο βήμα είναι η δημιουργία ενός αντικειμένου `BarcodeGenerator` με τύπο `EncodeTypes.DatabarExpandedStacked` και ένα δείγμα payload. Αυτό το payload μπορεί να είναι οποιαδήποτε αλφαριθμητική συμβολοσειρά που ταιριάζει στην προδιαγραφή Databar.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*Γιατί είναι σημαντικό*: `EncodeTypes.DatabarExpandedStacked` λέει στη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική γραμματοσειρά Databar Expanded Stacked, η οποία υποστηρίζει μεγαλύτερες αλφαριθμητικές αλυσίδες από το κανονικό Databar.

## Πώς να δημιουργήσετε databar με προσαρμοσμένες στήλες

Databar Expanded σας επιτρέπει να ελέγχετε τον αριθμό των στηλών στη στοίβα διαρρύθμιση. Η ρύθμιση των στηλών είναι χρήσιμη όταν χρειάζεστε έναν συμπαγή κωδικό που εξακολουθεί να χωράει το απαιτούμενο πλάτος δεδομένων.

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*Εξήγηση*: `setColumns(4)` αναγκάζει τον δημιουργό να χωρίσει τον κωδικό σε τέσσερα κάθετα τμήματα. Η βιβλιοθήκη προσαρμόζει αυτόματα το πλάτος του μονάδας ώστε το συνολικό μέγεθος να παραμένει λογικό.

## Εξαγωγή εικόνας κωδικού γραμμής ως PNG – έκδοση 4‑στηλών

Μόλις οριστεί η διάταξη, μπορείτε να εξάγετε τον κωδικό σε αρχείο. Το PNG είναι η προτεινόμενη μορφή χωρίς απώλειες για τις περισσότερες UI περιπτώσεις.

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

Η μέθοδος `save` γράφει την εικόνα στον καθορισμένο φάκελο. Αν ο φάκελος δεν υπάρχει, η Java θα τον δημιουργήσει αυτόματα.

## Διαμόρφωση γραμμών δημιουργού κωδικού γραμμής

Εκτός από τις στήλες, η συμβολική γραμματοσειρά Databar Expanded Stacked υποστηρίζει διάταξη με βάση τις γραμμές. Η μετάβαση από στήλες σε γραμμές μπορεί να βελτιώσει την αναγνωσιμότητα σε εκτυπώσεις υψηλής ανάλυσης.

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*Γιατί να χρησιμοποιήσετε γραμμές;* Μια διάταξη 3‑γραμμών διαστέλλει τα δεδομένα κάθετα, κάτι που μπορεί να είναι πλεονεκτικό για στενά ετικέτες όπου ο οριζόντιος χώρος είναι περιορισμένος.

## Εξαγωγή εικόνας κωδικού γραμμής ως PNG – έκδοση 3‑γραμμών

Η αποθήκευση της δεύτερης διάταξης ακολουθεί το ίδιο μοτίβο όπως πριν. Η διατήρηση διαφορετικών ονομάτων αρχείων σας βοηθά να συγκρίνετε τις οπτικές διαφορές.

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### Αναμενόμενο αποτέλεσμα

Η εκτέλεση του προγράμματος παράγει δύο αρχεία PNG:

| Όνομα αρχείου                | Περιγραφή διάταξης                |
|------------------------------|-----------------------------------|
| `DatabarExpandedCols4.png`   | 4‑στήλες στοίβα κωδικού γραμμής   |
| `DatabarExpandedRows3.png`   | 3‑γραμμές στοίβα κωδικού γραμμής  |

Και οι δύο εικόνες εμφανίζουν την ίδια κωδικοποιημένη συμβολοσειρά, αλλά η οπτική πυκνότητα διαφέρει ανάλογα με τις ρυθμίσεις στήλης/γραμμής.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Πρόβλημα                     | Αιτία                                 | Διόρθωση |
|------------------------------|---------------------------------------|----------|
| Ο κωδικός γραμμής εμφανίζεται θολός | Αποθήκευση σε χαμηλό DPI               | Χρησιμοποιήστε `generator.getParameters().setResolution(300)` πριν από το `save`. |
| Το κείμενο περικόπτεται       | Το payload υπερβαίνει τη χωρητικότητα του Databar | Μειώστε το payload ή μεταβείτε σε `EncodeTypes.DatabarExpanded` (μη στοίβα). |
| `NullPointerException` στο `setRows` | Χρήση έκδοσης του Aspose.BarCode πριν από την 20.12 | Αναβαθμίστε στην πιο πρόσφατη έκδοση της βιβλιοθήκης. |

## Προχωρημένες παραλλαγές (προαιρετικό)

* **Αλλαγή χρωμάτων προσκηνίου/υπόβαθρου** – καλέστε `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` και `setBackColor(Color.WHITE)`.
* **Δημιουργία SVG αντί για PNG** – αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Svg`.
* **Ενσωμάτωση του κωδικού γραμμής σε PDF** – χρησιμοποιήστε το Aspose.PDF για να δημιουργήσετε ένα έγγραφο και προσθέστε το PNG ως εικόνα.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε κωδικό γραμμής databar expanded** σε Java, **πώς να δημιουργήσετε databar** με ρυθμίσεις στήλης και γραμμής, και πώς να **εξάγετε αρχεία εικόνας κωδικού γραμμής** σε μορφή PNG. Ο πλήρης πηγαίος κώδικας είναι έτοιμος για αντιγραφή, επικόλληση και εκτέλεση σε οποιοδήποτε έργο Java.

Νιώστε ελεύθεροι να πειραματιστείτε με άλλες διατάξεις, χρώματα ή μορφές εξόδου. Αν βρήκατε αυτόν τον οδηγό χρήσιμο, εξετάστε την τεκμηρίωση του Aspose.BarCode για θέματα όπως *micro‑PDF417*, *διόρθωση σφαλμάτων QR code* και *σάρωση κωδικών γραμμής*.

Καλό προγραμματισμό!

## Τι Θα Πρέπει Να Μάθετε Στη Σύντομη Μελλοντική;

Οι παρακάτω εκπαιδευτικές οδηγίες καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με εξηγήσεις βήμα‑βήμα για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε κωδικό γραμμής java: Δημιουργία ακριβούς εικόνας κωδικού γραμμής](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [Οδηγός databar expanded stacked barcode – πώς να το δημιουργήσετε και να το διαμορφώσετε σε C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Πώς να δημιουργήσετε πολυκατευθυντικό κωδικό Databar σε C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}