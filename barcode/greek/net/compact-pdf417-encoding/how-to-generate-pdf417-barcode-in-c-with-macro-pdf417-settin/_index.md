---
category: general
date: 2026-10-15
description: Μάθετε πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# χρησιμοποιώντας
  παραμέτρους Macro‑PDF417, ορίστε τις διαστάσεις του κώδικα και αποθηκεύστε το ως
  PNG. Συμπεριλαμβάνεται πλήρες παράδειγμα κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: el
lastmod: 2026-10-15
og_description: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με πλήρη διαμόρφωση
  Macro‑PDF417, έλεγχο διαστάσεων και έξοδο PNG. Ακολουθήστε το πλήρες παράδειγμα.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – οδηγός βήμα‑προς‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με ρυθμίσεις Macro‑PDF417
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με ρυθμίσεις Macro‑PDF417

Αν χρειάζεστε **πώς να δημιουργήσετε γραμμωτό κώδικα PDF417** για μια ροή εργασίας εγγράφων, αυτός ο οδηγός σας δείχνει τα ακριβή βήματα. Θα δείτε πώς να ρυθμίσετε τις παραμέτρους Macro‑PDF417, να ορίσετε τις διαστάσεις του γραμμωτού κώδικα και να εξάγετε το αποτέλεσμα ως εικόνα PNG—όλα σε ένα ενιαίο, εκτελέσιμο πρόγραμμα C#.

Η δημιουργία ενός γραμμωτού κώδικα PDF417 δεν απαιτεί πολλαπλές βιβλιοθήκες ή πολύπλοκη μετα‑επεξεργασία. Χρησιμοποιώντας το Aspose.Barcode για .NET μπορείτε να ελέγξετε κάθε πτυχή του γραμμωτού κώδικα, από το πλάτος της μονάδας μέχρι το checksum, και να παράγετε μια εικόνα υψηλής ποιότητας έτοιμη για εκτύπωση ή σάρωση.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 (ή νεότερο) SDK εγκατεστημένο  
* Visual Studio 2022 ή οποιοδήποτε IDE C# προτιμάτε  
* Πακέτο NuGet Aspose.Barcode για .NET (`Install-Package Aspose.Barcode`)  

Αυτά τα προαπαιτούμενα διασφαλίζουν ότι ο κώδικας θα μεταγλωττιστεί χωρίς πρόσθετη διαμόρφωση.

## Βήμα 1: Δημιουργία γεννήτριας γραμμωτού κώδικα για έναν Macro‑PDF417 γραμμωτό κώδικα

Η πρώτη λειτουργία δημιουργεί ένα αντικείμενο `BarcodeGenerator` που στοχεύει στη μορφή `EncodeTypes.MacroPdf417`. Ο κατασκευαστής λαμβάνει τα δεδομένα που θέλετε να κωδικοποιήσετε—σε αυτήν την περίπτωση, τη συμβολοσειρά `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Η δημιουργία της γεννήτριας ρυθμίζει το εσωτερικό αντικείμενο `Parameters`, το οποίο θα χρησιμοποιήσετε για να προσαρμόσετε τις ιδιότητες του **C# PDF417 barcode**.

## Βήμα 2: Ορισμός βασικής εμφάνισης γραμμωτού κώδικα – ορισμός διαστάσεων γραμμωτού κώδικα

Ο έλεγχος του οπτικού μεγέθους ενός γραμμωτού κώδικα βελτιώνει την αξιοπιστία της σάρωσης. Η ιδιότητα `XDimension.Pixels` ορίζει το πλάτος της μονάδας (σημείου), ενώ το `Pdf417.Columns` καθορίζει πόσες στήλες θα περιέχει ο γραμμωτός κώδικας.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Ο ορισμός αυτών των διαστάσεων διασφαλίζει ότι ο γραμμωτός κώδικας ταιριάζει σε τυπικά μεγέθη ετικετών και πληροί τις προδιαγραφές των σαρωτών.

## Βήμα 3: Παροχή αναγνώρισης αρχείου Macro‑PDF417

Το Macro‑PDF417 επεκτείνει τον τυπικό γραμμωτό κώδικα PDF417 με μεταδεδομένα επιπέδου αρχείου. Πρέπει να ορίσετε ένα μοναδικό αναγνωριστικό αρχείου, αναγνωριστικό τμήματος, συνολικό αριθμό τμημάτων και ένα ανθρώπινα αναγνώσιμο όνομα αρχείου.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Αυτές οι **Macro PDF417 parameters** επιτρέπουν στα συστήματα downstream να ανασυνθέσουν το αρχικό αρχείο από πολλαπλά τμήματα γραμμωτού κώδικα.

## Βήμα 4: Προσθήκη πρόσθετων macro μεταδεδομένων – συμπερίληψη checksum γραμμωτού κώδικα

Πέρα από την ταυτοποίηση, το Macro‑PDF417 μπορεί να αποθηκεύσει checksum, μέγεθος αρχείου, χρονική σήμανση, παραλήπτη, αποστολέα και σημαία τερματισμού. Η παροχή ενός checksum βελτιώνει τους ελέγχους ακεραιότητας των δεδομένων κατά την αποκωδικοποίηση.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Η συμπερίληψη ενός **barcode checksum** και άλλων μεταδεδομένων κάνει τον γραμμωτό κώδικα αυτοπεριγραφικό, κάτι που είναι πολύτιμο για αυτοματοποιημένες γραμμές επεξεργασίας εγγράφων.

## Βήμα 5: Αποθήκευση του παραγόμενου γραμμωτού κώδικα ως εικόνα PNG – επιλογή μορφής εικόνας γραμμωτού κώδικα

Το τελικό βήμα γράφει τον γραμμωτό κώδικα σε αρχείο. Η μέθοδος `Save` δέχεται μια διαδρομή αρχείου και ένα enum `BarCodeImageFormat`. Το PNG παρέχει συμπίεση χωρίς απώλειες, διατηρώντας τις αιχμηρές άκρες για αξιόπιστη σάρωση.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Μετά την εκτέλεση, το αρχείο `MacroPdf417.png` περιέχει έναν καθαρό γραμμωτό κώδικα PDF417 έτοιμο για ενσωμάτωση σε PDF, εκτύπωση σε ετικέτες ή εμφάνιση σε οθόνες.

## Αναμενόμενο αποτέλεσμα

Ανοίγοντας το `C:/Barcodes/MacroPdf417.png` εμφανίζεται ένας ορθογώνιος γραμμωτός κώδικας με το κωδικοποιημένο κείμενο “Sample text”. Ο γραμμωτός κώδικας περιλαμβάνει τα macro μεταδεδομένα που ορίσατε, τα οποία μπορείτε να επαληθεύσετε με οποιονδήποτε σαρωτή PDF417 που υποστηρίζει Macro‑PDF417. Οι διαστάσεις της εικόνας αντανακλούν το πλάτος της μονάδας (2 px) και τον αριθμό στηλών (5), προσφέροντας έναν συμπαγή αλλά ευανάγνωστο γραμμωτό κώδικα.

## Συνηθισμένες παραλλαγές και περιπτώσεις άκρων

| Κατάσταση | Προσαρμογή |
|-----------|------------|
| **Διαφορετικό μήκος δεδομένων** | Αντικαταστήστε το `"Sample text"` με οποιαδήποτε συμβολοσειρά UTF‑8· η γεννήτρια προσαρμόζει αυτόματα το μέγεθος του γραμμωτού κώδικα. |
| **Υψηλότερη ανάλυση** | Αυξήστε το `XDimension.Pixels` σε 3 ή 4 για μεγαλύτερες μονάδες, χρήσιμο για εκτυπωτές χαμηλής ανάλυσης. |
| **Περισσότερα τμήματα** | Αλλάξτε το `MacroPdf417SegmentsCount` ώστε να ταιριάζει με το συνολικό αριθμό τμημάτων γραμμωτού κώδικα που σκοπεύετε να δημιουργήσετε. |
| **Εναλλακτική μορφή εικόνας** | Χρησιμοποιήστε `BarCodeImageFormat.Jpeg` ή `BarCodeImageFormat.Bmp` εάν το σύστημα σας προτιμά αυτές τις μορφές. |
| **Προσαρμοσμένη διόρθωση σφαλμάτων** | Τροποποιήστε το `generator.Parameters.Barcode.Pdf417.ErrorLevel` (εύρος 0‑8) για να ανταλλάξετε την πυκνότητα των δεδομένων με την ανοχή σφαλμάτων. |

**Συμβουλή:** Πάντα να επικυρώνετε τον παραγόμενο γραμμωτό κώδικα με έναν φυσικό σαρωτή πριν τον αναπτύξετε στην παραγωγή. Οι σαρωτές μπορεί να έχουν περιορισμούς firmware σχετικά με το πλάτος της μονάδας ή τον αριθμό στηλών.

## Πλήρης κώδικας πηγής

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Η εκτέλεση αυτού του προγράμματος δημιουργεί το `MacroPdf417.png` στο φάκελο `C:/Barcodes`. Η κονσόλα επιβεβαιώνει την επιτυχή δημιουργία.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# με πλήρη έλεγχο Macro‑PDF417, πώς να **ορίσετε τις διαστάσεις του γραμμωτού κώδικα**, πώς να ενσωματώσετε **checksum γραμμωτού κώδικα** και άλλα macro μεταδεδομένα, και πώς να εξάγετε το αποτέλεσμα χρησιμοποιώντας μια επιλεγμένη **μορφή εικόνας γραμμωτού κώδικα**. Το πλήρες παράδειγμα μπορεί να αντιγραφεί σε οποιοδήποτε έργο .NET, να τροποποιηθεί για διαφορετικά δεδομένα και να ενσωματωθεί σε μεγαλύτερες γραμμές αυτοματοποίησης εγγράφων.

### Επόμενα βήματα

* Εξερευνήστε τα επίπεδα διόρθωσης σφαλμάτων του **C# PDF417 barcode** για να βελτιώσετε την αξιοπιστία σάρωσης.  
* Συνδυάστε πολλαπλά τμήματα Macro‑PDF417 για την κωδικοποίηση μεγάλων αρχείων όπως PDF ή εικόνες.  
* Αλλάξτε τη **μορφή εικόνας γραμμωτού κώδικα** σε SVG για κλιμακούμενα διανυσματικά γραφικά σε εφαρμογές web.  

Νιώστε ελεύθεροι να πειραματιστείτε με τις παραμέτρους και να μοιραστείτε τα αποτελέσματά σας στα σχόλια ή στα φόρουμ της κοινότητας. Καλό κώδικα!

## Τι Θα Πρέπει Να Μάθετε Στη Σειρά;

Οι παρακάτω εκπαιδευτικές οδηγίες καλύπτουν στενά σχετικές θεματικές που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία γραμμωτού κώδικα C# με Macro PDF417 – πλήρες παράδειγμα](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 – Πλήρης οδηγός προγραμματισμού](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με προσαρμοσμένες διαστάσεις](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}