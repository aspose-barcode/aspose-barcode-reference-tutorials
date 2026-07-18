---
category: general
date: 2026-07-18
description: πώς να ορίσετε το επίπεδο σφάλματος σε κώδικα PDF417 χρησιμοποιώντας
  το Aspose.BarCode. Μάθετε να δημιουργείτε κώδικα PDF417 με προσαρμοσμένο κείμενο
  και να ρυθμίζετε τη διόρθωση σφαλμάτων σε λίγα λεπτά.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: el
lastmod: 2026-07-18
og_description: πώς να ορίσετε το επίπεδο σφάλματος σε γραμμωτό κώδικα PDF417 γρήγορα.
  Αυτό το σεμινάριο σας καθοδηγεί στη δημιουργία ενός γραμμωτού κώδικα PDF417 με προσαρμοσμένο
  κείμενο και διαφορετικά επίπεδα διόρθωσης σφαλμάτων.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Πώς να ορίσετε το επίπεδο σφάλματος σε κώδικα PDF417 – Οδηγός βήμα‑προς‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Πώς να ορίσετε το επίπεδο σφάλματος στον κωδικό PDF417 – Πλήρης οδηγός
url: /el/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Ορίσετε το Επίπεδο Σφάλματος σε Barcode PDF417 – Πλήρης Οδηγός

Έχετε αναρωτηθεί ποτέ **πώς να ορίσετε το σφάλμα** όταν δημιουργείτε ένα barcode PDF417; Δεν είστε μόνοι—πολλοί προγραμματιστές αντιμετωπίζουν αυτό το πρόβλημα όταν χρειάζονται ένα πιο ανθεκτικό barcode για σάρωση σε δύσκολες συνθήκες. Τα καλά νέα; Η ρύθμιση του επιπέδου διόρθωσης σφαλμάτων είναι παιχνιδάκι με το Aspose.BarCode, και θα μάθετε επίσης **πώς να δημιουργήσετε PDF417** με το δικό σας προσαρμοσμένο κείμενο.

Σε αυτό το tutorial θα περάσουμε από κάθε βήμα, από τη δημιουργία ενός barcode generator με ειδικούς χαρακτήρες μέχρι την αποθήκευση δύο αρχείων PNG που δείχνουν διαφορετικά επίπεδα διόρθωσης σφαλμάτων. Στο τέλος θα είστε άνετοι με **τη δημιουργία barcode PDF417**, την προσαρμογή του X‑dimension, του αριθμού στηλών, και, το πιο σημαντικό, **τη ρύθμιση του σφάλματος** σε επίπεδα που ταιριάζουν στην περίπτωση χρήσης σας.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί και με .NET Framework)
- Aspose.BarCode for .NET εγκατεστημένο (`Install-Package Aspose.BarCode` μέσω NuGet)
- Ένας φάκελος στον δίσκο όπου μπορούν να γραφτούν οι εικόνες (αντικαταστήστε το `YOUR_DIRECTORY/` στο παράδειγμα)
- Βασικές γνώσεις C#—αν έχετε γράψει ποτέ `Console.WriteLine`, είστε έτοιμοι

> **Pro tip:** Αν στοχεύετε σε σάρωση από κινητές συσκευές, επιλέξτε υψηλότερο επίπεδο σφάλματος (Level 5) για να αντέξει σε βρωμιά, γρατσουνιές ή συνθήκες χαμηλού φωτισμού.

## Βήμα 1: Δημιουργία Barcode Generator με Προσαρμοσμένο Κείμενο

Το πρώτο που χρειάζεστε είναι ένα αντικείμενο `BarcodeGenerator` που ξέρει ότι πρέπει να παραγάγει ένα **barcode PDF417** και που μεταφέρει το ακριβές κείμενο που θέλετε να κωδικοποιήσετε. Παρατηρήστε τη χρήση τονισμένων χαρακτήρων και του συμβόλου ©—αυτό αποδεικνύει ότι ο generator μπορεί να διαχειριστεί Unicode από την αρχή.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Γιατί είναι σημαντικό:* Η σημαία `EncodeTypes.Pdf417` λέει στο Aspose ότι δουλεύετε με ένα 2‑D stacked barcode, ενώ το όρισμα string γίνεται το φορτίο δεδομένων. Αν παραλείψετε αυτό το βήμα, θα καταλήξετε με ένα προεπιλεγμένο barcode Code128 αντί για το υψηλής χωρητικότητας PDF417 που χρειάζεστε.

## Βήμα 2: Λεπτομερής Ρύθμιση Οπτικών Παραμέτρων

Ένα barcode PDF417 δεν είναι μόνο δεδομένα· είναι επίσης ένα οπτικό μοτίβο. Η ρύθμιση του **X‑dimension** (το πλάτος της μικρότερης γραμμής) και του αριθμού **στηλών** σας επιτρέπει να ελέγξετε το φυσικό μέγεθος και την αναγνωσιμότητα του barcode.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Γιατί είναι σημαντικό:* Ένα μικρότερο X‑dimension δημιουργεί πιο συμπαγή εικόνα, αλλά μπορεί να γίνει ακατάγνωστο σε σαρωτές χαμηλής ανάλυσης. Τρεις στήλες δίνουν μια ισορροπημένη αναλογία για τις περισσότερες ετικέτες.

## Βήμα 3: Ορισμός Επιπέδου Διόρθωσης Σφάλματος σε 2 και Αποθήκευση

Η διόρθωση σφάλματος είναι η καρδιά του **πώς να ορίσετε το σφάλμα** για PDF417. Το enum `Pdf417ErrorLevel` κυμαίνεται από `Level0` (χωρίς επιπλέον δεδομένα) μέχρι `Level5` (μέγιστη πλεονασμός). Εδώ ξεκινάμε με **Level 2**, που προσθέτει μια μέτρια ποσότητα ανθεκτικότητας χωρίς να φουσκώνει πολύ την εικόνα.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Αφού εκτελέσετε αυτό το απόσπασμα, θα βρείτε το `Pdf417ErrorLevel2.png` στον φάκελό σας. Ανοίξτε το και θα δείτε ένα καθαρό barcode τριών στηλών που περιέχει ακόμη μια αξιοπρεπή ποσότητα πλεονασμού.

## Βήμα 4: Αύξηση Διόρθωσης Σφάλματος σε Level 5 και Νέα Αποθήκευση

Μερικές φορές χρειάζεται το barcode να αντέξει πιο σκληρή ζημιά—σκεφτείτε το πάτωμα μιας αποθήκης όπου οι ετικέτες γρατσουνίζονται. Η μετάβαση σε **Level 5** μεγιστοποιεί τη διόρθωση σφάλματος με κόστος μια ελαφρώς μεγαλύτερη εικόνα.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Τώρα έχετε δύο αρχεία PNG δίπλα-δίπλα: ένα με μέτρια διόρθωση σφάλματος, το άλλο με τη μέγιστη. Συγκρίνετε τα· η έκδοση Level 5 θα έχει περισσότερα σκούρα modules, που είναι ακριβώς αυτό που προσθέτει ο αλγόριθμος για την προστασία των δεδομένων.

![παράδειγμα ρύθμισης επιπέδου σφάλματος σε barcode PDF417](image.png)

*Περιγραφή εικόνας (alt text): παράδειγμα ρύθμισης επιπέδου σφάλματος σε barcode PDF417 – δείχνει δύο αρχεία PNG με διαφορετικά επίπεδα διόρθωσης σφάλματος.*

## Αναμενόμενο Αποτέλεσμα

| Όνομα αρχείου                | Επίπεδο σφάλματος | Προσεγγ. διαστάσεις (px) |
|------------------------------|-------------------|--------------------------|
| `Pdf417ErrorLevel2.png`      | Level 2           | 150 × 80                 |
| `Pdf417ErrorLevel5.png`      | Level 5           | 180 × 95                 |

Και οι δύο εικόνες κωδικοποιούν τη συμβολοσειρά **“Åspóse.Barcóde©”** και μπορούν να σαρωθούν με οποιονδήποτε τυπικό αναγνώστη PDF417 (π.χ., ZXing, Scandit). Η εικόνα Level 5 αντέχει έως ~30 % ζημιά, ενώ η Level 2 περίπου ~15 %.

## Συχνές Ερωτήσεις & Ακραίες Περιπτώσεις

### Τι γίνεται αν το κείμενό μου περιέχει αλλαγές γραμμής;
Το PDF417 κωδικοποιεί αυτόματα χαρακτήρες line‑feed (`\n`). Απλώς συμπεριλάβετε τους στη συμβολοσειρά:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Μπορώ να χρησιμοποιήσω διαφορετική μορφή εικόνας;
Απόλυτα. Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Svg` ανάλογα με τη ροή εργασίας σας.

### Επηρεάζει η αλλαγή του X‑dimension τη διόρθωση σφάλματος;
Έμμεσα, ναι. Ένα μεγαλύτερο X‑dimension δημιουργεί μεγαλύτερα modules, κάτι που μπορεί να βελτιώσει την αξιοπιστία σάρωσης, αλλά **δεν** αλλάζει το λογικό επίπεδο διόρθωσης σφάλματος. Ρυθμίστε και τις δύο παραμέτρους ανεξάρτητα για βέλτιστα αποτελέσματα.

### Πώς να δημιουργήσετε barcode PDF417 σε Web API;
Τυλίξτε τον ίδιο κώδικα σε έναν ελεγκτή ASP.NET Core και επιστρέψτε το PNG ως `FileResult`. Η βασική λογική παραμένει αμετάβλητη, πράγμα που σημαίνει ότι **πώς να δημιουργήσετε PDF417** παραμένει συνεπές σε desktop και web περιβάλλοντα.

## Περίληψη

Καλύψαμε **πώς να ορίσετε το σφάλμα** για ένα barcode PDF417, δείξαμε **πώς να δημιουργήσετε PDF417** με προσαρμοσμένο Unicode κείμενο, και σας δείξαμε πώς να ρυθμίσετε οπτικές παραμέτρους όπως το X‑dimension και τον αριθμό στηλών. Αντικαθιστώντας το `Pdf417ErrorLevel.Level2` με `Level5` ελέγχετε την ανταλλαγή μεταξύ μεγέθους εικόνας και ανθεκτικότητας.

## Επόμενα Βήματα

- Πειραματιστείτε με **barcode με προσαρμοσμένο κείμενο** που περιλαμβάνει URLs ή κωδικούς προϊόντων.
- Δοκιμάστε διαφορετικούς αριθμούς στηλών (`generator.Parameters.Barcode.Pdf417.Columns = 5`) για να δείτε πώς αλλάζει το σχήμα.
- Συνδυάστε PDF417 με άλλους τύπους barcode στο ίδιο έγγραφο για λύσεις multi‑modal σάρωσης.
- Εξερευνήστε την [επίσημη τεκμηρίωση του Aspose](https://docs.aspose.com/barcode/net/) για προχωρημένα χαρακτηριστικά όπως macro PDF417 ή compact mode.

Μη διστάσετε να αφήσετε ένα σχόλιο αν αντιμετωπίσετε δυσκολίες, ή να μοιραστείτε τα δικά σας αποτελέσματα σάρωσης. Καλή δημιουργία barcode!

## Τι Πρέπει να Μάθετε Στη Σύντομη Μελλοντική

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [Πώς να Δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να δημιουργήσετε Aztec barcode με διόρθωση σφάλματος σε .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Πώς να Δημιουργήσετε DataMatrix Barcodes (ECC 200) με Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}