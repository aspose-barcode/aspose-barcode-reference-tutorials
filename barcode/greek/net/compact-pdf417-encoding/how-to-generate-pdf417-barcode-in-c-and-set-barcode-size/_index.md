---
category: general
date: 2026-08-22
description: Μάθετε πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode,
  να ορίσετε το μέγεθος του κώδικα, να προσαρμόσετε τις στήλες και να ενεργοποιήσετε
  τη συμπαγή λειτουργία.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: el
lastmod: 2026-08-22
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode. Αυτός
  ο οδηγός δείχνει πώς να ορίσετε το μέγεθος του κώδικα, να ελέγξετε τις στήλες και
  να ενεργοποιήσετε τη συμπαγή λειτουργία για μικρότερη εικόνα.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Δημιουργία barcode PDF417 σε C# – ορισμός μεγέθους, στηλών και συμπαγούς
  λειτουργίας
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# και να ορίσετε το μέγεθός
  του
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε PDF417 barcode σε C# και να ορίσετε το μέγεθος του barcode

Αν χρειάζεστε **να δημιουργήσετε PDF417 barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός σας καθοδηγεί μέσα από τη διαδικασία. Θα δείτε ακριβώς **πώς να δημιουργήσετε PDF417** με το Aspose.BarCode, να προσαρμόσετε το **set barcode size**, και να παραγάγετε ένα συμπαγές PNG που μπορεί να ενσωματωθεί σε αναφορές ή κινητές εφαρμογές.

Η δημιουργία ενός barcode δεν απαιτεί ξεχωριστό πρόγραμμα επεξεργασίας γραφικών. Στο τέλος αυτού του tutorial θα έχετε μια πλήρως λειτουργική μέθοδο C# που παράγει μια εικόνα PDF417 με τις ακριβείς διαστάσεις που χρειάζεστε, έτοιμη για επεξεργασία downstream.

## Τι θα μάθετε

* Εγκαταστήστε και αναφέρετε τη βιβλιοθήκη Aspose.BarCode.
* Δημιουργήστε έναν PDF417 barcode generator και καθορίστε το κωδικοποιημένο κείμενο.
* **Set barcode size** μέσω ρύθμισης του X‑dimension και του αριθμού στηλών.
* Ενεργοποιήστε τη συμπαγή (truncated) λειτουργία για να μειώσετε το σύμβολο.
* Αποθηκεύστε το αποτέλεσμα ως αρχείο PNG.
* Αντιμετωπίστε κοινά προβλήματα όπως μη αναγνώσιμα κώδικα και υπερβολικά μεγάλες εικόνες.

### Προαπαιτούμενα

* .NET 6.0 ή νεότερο (το API λειτουργεί επίσης με .NET Framework 4.6+).
* Βασική εξοικείωση με C# και Visual Studio (ή οποιοδήποτε IDE για C#).
* Ένα έγκυρο license Aspose.BarCode (η δωρεάν αξιολόγηση λειτουργεί για δοκιμές).

> **Pro tip:** Εάν σκοπεύετε να δημιουργήσετε πολλά barcodes σε βρόχο, επαναχρησιμοποιήστε μια μοναδική παρουσία `BarcodeGenerator` και αλλάξτε μόνο την ιδιότητα `CodeText`. Αυτό μειώνει τις εκχωρήσεις μνήμης.

## Δημιουργία PDF417 barcode με Aspose.BarCode

Το πρώτο βήμα είναι η δημιουργία μιας παρουσίας του `BarcodeGenerator` για τη συμβολική PDF417. Αυτό το αντικείμενο είναι το σημείο εισόδου για όλες τις λειτουργίες barcode.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Γιατί είναι σημαντικό*: `EncodeTypes.Pdf417` ενημερώνει τη βιβλιοθήκη να χρησιμοποιήσει το πρότυπο PDF417, το οποίο υποστηρίζει μεγάλα όγκους δεδομένων και διόρθωση σφαλμάτων. Ο κατασκευαστής δέχεται επίσης τα δεδομένα που θέλετε να κωδικοποιήσετε, εξαλείφοντας την ανάγκη για ξεχωριστή ανάθεση `CodeText` αργότερα.

## Ορισμός μεγέθους barcode και αριθμού στηλών

Τα σύμβολα PDF417 αποτελούνται από σειρές και στήλες μικρών ορθογωνίων μονάδων. Ο έλεγχος του πλάτους της μονάδας (X‑dimension) και του αριθμού των στηλών σας επιτρέπει να ρυθμίσετε ακριβώς τις συνολικές διαστάσεις.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Επεξήγηση*:  
* **X‑dimension** (`Pixels`) καθορίζει το πλάτος κάθε μονάδας. Μικρότερες τιμές παράγουν πιο πυκνό barcode, ενώ μεγαλύτερες τιμές αυξάνουν την αναγνωσιμότητα σε σαρωτές χαμηλής ανάλυσης.  
* **Columns** ελέγχει τη οριζόντια διάταξη. Λιγότερες στήλες κάνουν το barcode ψηλότερο· περισσότερες στήλες το κάνουν πιο πλατύ. Ρυθμίστε αυτές τις δύο παραμέτρους μαζί για να πετύχετε το ακριβές **set barcode size** που χρειάζεστε.

## Ενεργοποίηση συμπαγούς λειτουργίας για μικρότερο barcode

Το PDF417 περιλαμβάνει μια λειτουργία “compact” (ή truncated) που αφαιρεί περιττές επενδύσεις και μειώνει το συνολικό αποτύπωμα. Αυτό είναι ιδιαίτερα χρήσιμο όταν έχετε περιορισμένο χώρο οθόνης.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Γιατί να ενεργοποιήσετε την περικοπή;*  
Όταν το `Truncate` είναι `true`, ο δημιουργός παραλείπει το μοτίβο τερματισμού και ορισμένες λέξεις κώδικα διόρθωσης σφαλμάτων που δεν απαιτούνται για τις περισσότερες περιπτώσεις σάρωσης. Η προκύπτουσα εικόνα είναι περίπου 15‑20 % μικρότερη χωρίς να θυσιάζεται η ακεραιότητα των δεδομένων για τυπικές περιπτώσεις χρήσης.

## Αποθήκευση του barcode ως εικόνα PNG

Αφού ρυθμίσετε το μέγεθος και τη λειτουργία, γράψτε το barcode στο δίσκο. Το PNG είναι lossless, διασφαλίζοντας ότι οι άκρες των μονάδων παραμένουν οξείς.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Το αρχείο `CompactPdf417.png` θα περιέχει ένα καθαρό σύμβολο PDF417 που ταιριάζει με τις διαστάσεις που ορίσατε στα προηγούμενα βήματα.

### Αναμενόμενο αποτέλεσμα

Ανοίγοντας το αποθηκευμένο PNG θα πρέπει να εμφανίζεται ένα PDF417 barcode προσανατολισμένο κατακόρυφα, αποτελούμενο από τρεις στήλες, κάθε μονάδα 2 px πλάτος, και συνολικό μέγεθος περίπου **120 × 240 px** (πλάτος × ύψος). Η σάρωση της εικόνας με οποιονδήποτε τυπικό αναγνώστη PDF417 επιστρέφει το αρχικό κείμενο “Sample text for PDF417”.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Σύμπτωμα | Πιθανή αιτία | Διόρθωση |
|----------|--------------|----------|
| Το barcode δεν είναι αναγνώσιμο | Το X‑dimension είναι πολύ μικρό για τον σαρωτή | Αυξήστε το `XDimension.Pixels` σε 3 ή 4 |
| Η εικόνα είναι πολύ πλατιά για το UI | Έχουν οριστεί πάρα πολλές στήλες | Μειώστε το `Pdf417.Columns` ή ενεργοποιήστε το `Truncate` |
| Εξαίρεση `ArgumentOutOfRangeException` | Αρνητικός ή μηδενικός αριθμός στηλών | Βεβαιωθείτε ότι το `Columns` είναι θετικός ακέραιος (ελάχιστο 1) |
| Το αρχείο PNG είναι κενό | Η διαδρομή εξόδου δεν υπάρχει ή δεν έχει δικαίωμα εγγραφής | Επαληθεύστε ότι ο φάκελος υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής |

> **Pro tip:** Χρησιμοποιήστε το `barcodeGenerator.ValidateParameters()` πριν καλέσετε το `Save()` για να εντοπίσετε σφάλματα διαμόρφωσης νωρίς.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω υπάρχει ένα αυτόνομο πρόγραμμα κονσόλας που ενσωματώνει όλα τα παραπάνω βήματα. Αντιγράψτε το σε ένα νέο έργο C#, επαναφέρετε το πακέτο NuGet Aspose.BarCode και εκτελέστε το για να δείτε το αποτέλεσμα.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Η εκτέλεση του προγράμματος** παράγει το `CompactPdf417.png` στον φάκελο εργασίας του εκτελέσιμου. Σαρώστε την εικόνα με μια κινητή εφαρμογή (π.χ., “Barcode Scanner”) για να επαληθεύσετε ότι το κωδικοποιημένο κείμενο ταιριάζει με το αρχικό string.

## Επόμενα βήματα και συναφή θέματα

* **Αύξηση επιπέδου διόρθωσης σφαλμάτων** – προσαρμόστε το `Pdf417.ErrorLevel` για περιβάλλοντα με θορυβώδεις σάρωσες.  
* **Αλλαγή προσανατολισμού** – ορίστε το `Pdf417.Rotate` σε `RotationAngle.Rotate90` εάν χρειάζεστε οριζόντια διάταξη.  
* **Ενσωμάτωση του barcode σε PDF** – συνδυάστε το Aspose.PDF με το Aspose.BarCode για να τοποθετήσετε την εικόνα απευθείας σε ένα έγγραφο.  
* **Δημιουργία άλλων 2‑Δ barcode** – η ίδια κλάση `BarcodeGenerator` υποστηρίζει DataMatrix, QR και Aztec κώδικες· απλώς αντικαταστήστε το `EncodeTypes.Pdf417` με τη ζητούμενη συμβολική.

Με την εξοικείωση στις τεχνικές **generate PDF417 barcode**, μπορείτε να αυτοματοποιήσετε την έκδοση εισιτηρίων, την ετικετοθέτηση αποθεμάτων και τη ασφαλή μετάδοση δεδομένων σε ένα ευρύ φάσμα εφαρμογών .NET.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **generate PDF417 barcode** σε C#, ακριβώς **set barcode size**, να ρυθμίσετε τις στήλες, να ενεργοποιήσετε τη συμπαγή λειτουργία και να αποθηκεύσετε το αποτέλεσμα ως PNG. Εφαρμόστε αυτές τις ρυθμίσεις για να ταιριάζουν σε οποιονδήποτε περιορισμό UI ή απαίτηση σάρωσης, και επεκτείνετε την προσέγγιση σε άλλες μορφές barcode όπως απαιτείται. Καλό προγραμματισμό!

## Τι Θα Πρέπει Να Μάθετε Στη Σειρά;

Τα παρακάτω tutorials καλύπτουν στενά σχετικά θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να εξοικειωθείτε με πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}