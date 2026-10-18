---
category: general
date: 2026-10-18
description: Μάθετε πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode.
  Αυτό το σεμινάριο καλύπτει τη δημιουργία βασικού, συμπαγούς, μακρο και μικρο PDF417
  με πλήρη κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: el
lastmod: 2026-10-18
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode. Ακολουθήστε
  αυτόν τον οδηγό για να δημιουργήσετε βήμα-βήμα βασικούς, συμπαγείς, μακρο και μικρο
  PDF417 γραμμωτούς κώδικες.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Δημιουργία κώδικα PDF417 σε C# – πλήρες σεμινάριο Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Δημιουργία γραμμικού κώδικα PDF417 σε C# με χρήση του Aspose.BarCode – οδηγός
  βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία barcode PDF417 σε C# με Aspose.BarCode – οδηγός βήμα‑βήμα

Αν χρειάζεστε **να δημιουργήσετε barcode PDF417** σε μια εφαρμογή .NET, αυτό το tutorial σας καθοδηγεί μέσα από τη διαδικασία από την αρχή μέχρι το τέλος. Θα δείτε πώς να δημιουργήσετε ένα βασικό barcode, να ενεργοποιήσετε τη συμπαγή λειτουργία, να προσθέσετε μεταδεδομένα macro και να παραγάγετε μια μικρο‑παραλλαγή — όλα με σαφείς εξηγήσεις και εκτελέσιμο κώδικα.

Η δημιουργία barcode PDF417 είναι κοινή σε λογιστικές, εισιτήρια και διαχείριση εγγράφων. Στο τέλος αυτού του οδηγού θα μπορείτε να ενσωματώσετε τη δημιουργία barcode σε οποιοδήποτε έργο C# χωρίς εξωτερικά εργαλεία.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 ή νεότερη (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
* Visual Studio 2022 ή οποιοδήποτε IDE για C#
* **Aspose.BarCode for .NET** πακέτο NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Δικαίωμα εγγραφής σε φάκελο όπου θα αποθηκευτούν τα παραγόμενα αρχεία PNG

Δεν απαιτείται πρόσθετη ρύθμιση· η βιβλιοθήκη διαχειρίζεται όλες τις λεπτομέρειες κωδικοποίησης χαμηλού επιπέδου.

## Βήμα 1: Δημιουργία βασικού barcode PDF417

Το πρώτο βήμα δημιουργεί ένα κανονικό barcode PDF417 με προσαρμοσμένο μέγεθος και αριθμό στηλών.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Γιατί είναι σημαντικές αυτές οι ρυθμίσεις**

* `XDimension.Pixels` ελέγχει το φυσικό μέγεθος κάθε στοιχείου του barcode. Μια τιμή 2 παράγει καθαρή εικόνα στις περισσότερες οθόνες και εκτυπωτές.
* `Pdf417.Columns` καθορίζει πόσες στήλες δεδομένων περιέχει το barcode. Λιγότερες στήλες μειώνουν το πλάτος· περισσότερες στήλες αυξάνουν τη χωρητικότητα των δεδομένων.

Η εκτέλεση του κώδικα δημιουργεί το `Pdf417Basic.png`, το οποίο μοιάζει με ένα τυπικό σύμβολο PDF417 με τρεις στήλες δεδομένων και μια πλήρη στήλη μεταδεδομένων στα δεξιά.

## Βήμα 2: Ενεργοποίηση συμπαγούς (truncated) λειτουργίας

Η συμπαγής λειτουργία αφαιρεί τη δεξιά στήλη μεταδεδομένων, καθιστώντας το barcode πιο στενό. Αυτό είναι χρήσιμο όταν ο χώρος είναι περιορισμένος αλλά τα δεδομένα μπορούν να ανακατασκευαστούν από τις υπόλοιπες γραμμές.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Γιατί να κάνετε truncate;**  
Όταν το `Truncate` είναι `true`, ο δημιουργός παραλείπει την προαιρετική δεξιά στήλη που αποθηκεύει διόρθωση σφαλμάτων και μεταδεδομένα επιπέδου αρχείου. Το αποτέλεσμα καταλαμβάνει λιγότερες στήλες ενώ παραμένει αναγνώσιμο από τους περισσότερους αναγνώστες PDF417.

## Βήμα 3: Δημιουργία Macro PDF417 barcode με μεταδεδομένα επιπέδου αρχείου

Το Macro PDF417 επεκτείνει το τυπικό φορμά με αναγνωριστικά τμημάτων, επιτρέποντας σε ένα μεγάλο έγγραφο να διασπαστεί σε πολλαπλά barcodes. Αυτό είναι χρήσιμο για κωδικοποίηση μεγάλων συμβολοσειρών ή αρχείων πολλαπλών σελίδων.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Επεξήγηση πεδίων macro**

| Ιδιότητα | Σκοπός |
|----------|--------|
| `MacroPdf417FileID` | Μοναδικός ταυτοποιητής για ολόκληρο το αρχείο· όλα τα τμήματα μοιράζονται αυτήν την τιμή. |
| `MacroPdf417SegmentID` | Δείκτης του τρέχοντος τμήματος (αρχίζει από 1). |
| `MacroPdf417SegmentsCount` | Συνολικός αριθμός τμημάτων που συνθέτουν το πλήρες σύνολο δεδομένων. |

Ένας σαρωτής που υποστηρίζει Macro PDF417 μπορεί να επανασυνθέσει τα αρχικά δεδομένα διαβάζοντας όλα τα τμήματα και χρησιμοποιώντας αυτά τα αναγνωριστικά.

## Βήμα 4: Δημιουργία Micro PDF417 barcode για σύντομα δεδομένα

Το Micro PDF417 είναι μια συμπαγής έκδοση σχεδιασμένη για μικρά payloads (μέχρι 90 χαρακτήρες). Περιορίζει το εύρος στηλών σε 1‑4, καθιστώντας το barcode κατάλληλο για μικρές ετικέτες ή συσκευές με περιορισμένο χώρο προβολής.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Πότε να χρησιμοποιήσετε Micro PDF417**  
Χρησιμοποιήστε αυτήν την παραλλαγή όταν το payload είναι σύντομο και χρειάζεστε το μικρότερο δυνατό barcode. Είναι ιδανικό για ετικέτες αποθέματος, κάρτες πρόσβασης ή οποιοδήποτε σενάριο όπου η οθόνη είναι περιορισμένη.

## Πλήρες λειτουργικό παράδειγμα

Παρακάτω υπάρχει μια αυτόνομη εφαρμογή console που δημιουργεί και τους τέσσερις τύπους barcode σε μία εκτέλεση. Αντιγράψτε τον κώδικα σε ένα νέο έργο C#, αντικαταστήστε το `YOUR_DIRECTORY` με μια υπάρχουσα διαδρομή φακέλου και τρέξτε το.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Αναμενόμενο αποτέλεσμα**

Η εκτέλεση του προγράμματος δημιουργεί τέσσερα αρχεία PNG στον καθορισμένο φάκελο:

* `Pdf417Basic.png` – τυπικό barcode με τρεις στήλες
* `CompactPdf417.png` – ίδια δεδομένα, περικομμένη δεξιά στήλη
* `MacroPdf417.png` – macro barcode με μεταδεδομένα τμημάτων
* `MicroPdf417.png` – συμπαγές micro barcode για σύντομες συμβολοσειρές

Ανοίξτε οποιαδήποτε εικόνα με προβολέα εικόνων· θα δείτε τα χαρακτηριστικά μοτίβα PDF417. Σαρώνοντας τα με έναν κινητό αναγνώστη barcode (π.χ., ZXing, Scandit) θα επιστρέψουν τις αρχικές συμβολοσειρές κειμένου.

## Συχνές ερωτήσεις και συμβουλές

* **Τι γίνεται αν το barcode φαίνεται θολό;**  
  Αυξήστε το `XDimension.Pixels` σε 3 ή 4. Μεγαλύτερα μεγέθη μονάδων παράγουν εικόνες υψηλότερης ανάλυσης, με κόστος μεγαλύτερου αρχείου.

* **Μπορώ να εξάγω SVG αντί για PNG;**  
  Ναι. Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Svg` στις κλήσεις `Save`.

* **Πρέπει να ορίσω χειροκίνητα το επίπεδο διόρθωσης σφαλμάτων;**  
  Το Aspose.BarCode επιλέγει αυτόματα το βέλτιστο επίπεδο. Για εξειδικευμένες περιπτώσεις μπορείτε να ρυθμίσετε το `Pdf417.ErrorCorrectionLevel`.

* **Πώς να ενσωματώσω το barcode σε έγγραφο PDF;**  
  Χρησιμοποιήστε το `Aspose.Pdf` για να προσθέσετε το παραγόμενο PNG ή SVG ως στοιχείο εικόνας σε σελίδα PDF.

* **Η βιβλιοθήκη είναι thread‑safe;**  
  Κάθε αντικείμενο `BarcodeGenerator` είναι ανεξάρτητο· μπορείτε να δημιουργείτε generators σε πολλαπλά νήματα χωρίς κοινή κατάσταση.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε barcode PDF417** σε C# χρησιμοποιώντας το Aspose.BarCode, καλύπτοντας τις βασικές, συμπαγείς, macro και micro παραλλαγές.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να εξοικειωθείτε με πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην δική σας υλοποίηση.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}