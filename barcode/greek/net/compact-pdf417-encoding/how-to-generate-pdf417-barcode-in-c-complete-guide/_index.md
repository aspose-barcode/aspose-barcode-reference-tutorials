---
category: general
date: 2026-09-26
description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode. Ακολουθήστε
  αυτό το βήμα‑βήμα οδηγό για να ρυθμίσετε τις στήλες, να ενεργοποιήσετε τη συμπαγή
  λειτουργία και να αποθηκεύσετε ως PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: el
lastmod: 2026-09-26
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# χρησιμοποιώντας το Aspose.BarCode.
  Αυτός ο οδηγός σας δείχνει πώς να ορίσετε στήλες, να ενεργοποιήσετε τη συμπαγή λειτουργία
  και να εξάγετε το αποτέλεσμα ως εικόνα PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Δημιουργία barcode PDF417 σε C# – βήμα‑βήμα οδηγός
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – πλήρης οδηγός
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – πλήρης οδηγός

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα PDF417** σε μια εφαρμογή .NET, αυτό το σεμινάριο σας δείχνει μια έτοιμη προς εκτέλεση λύση. Θα δείτε πώς να ρυθμίσετε το μέγεθος του κώδικα, τον αριθμό στηλών και τη συμπαγή λειτουργία, και στη συνέχεια να αποθηκεύσετε το αποτέλεσμα ως αρχείο PNG υψηλής ποιότητας.

Η δημιουργία γραμμωτού κώδικα είναι μια κοινή απαίτηση για συστήματα απογραφής, πλατφόρμες έκδοσης εισιτηρίων και κωδικοποίηση εγγράφων. Στο τέλος αυτού του οδηγού θα έχετε ένα αυτόνομο πρόγραμμα C# που παράγει έναν συμπαγή γραμμωτό κώδικα PDF417 χρησιμοποιώντας τη βιβλιοθήκη **pdf417 barcode generator C#** της Aspose.

## Τι θα χρειαστείτε

- .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
- Ένα έγκυρο άδεια Aspose.BarCode for .NET (η δωρεάν αξιολόγηση λειτουργεί για δοκιμές)
- Ένα IDE ή επεξεργαστή όπως το Visual Studio 2022, Rider ή VS Code
- Βασική εξοικείωση με έργα κονσόλας C#

> **Συμβουλή:** Αν χρησιμοποιήσετε τη δωρεάν αξιολόγηση, η παραγόμενη εικόνα θα περιέχει ένα μικρό υδατογράφημα Aspose. Μια αγορασμένη άδεια αφαιρεί το υδατογράφημα και ξεκλειδώνει το πλήρες σύνολο λειτουργιών.

## Βήμα 1: Ρύθμιση της βιβλιοθήκης Aspose.BarCode

Δημιουργήστε ένα νέο έργο κονσόλας και προσθέστε το πακέτο NuGet Aspose.BarCode.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Το πακέτο παρέχει την κλάση `BarcodeGenerator`, η οποία αποτελεί τον πυρήνα της ροής εργασίας **pdf417 barcode generator C#**.

## Βήμα 2: Γράψτε το πλήρες πρόγραμμα δημιουργίας γραμμωτού κώδικα

Ανοίξτε το `Program.cs` και αντικαταστήστε το περιεχόμενό του με τον παρακάτω κώδικα. Το πρόγραμμα δείχνει κάθε απαιτούμενο βήμα, από την αρχικοποίηση του γεννήτρια μέχρι την αποθήκευση της εικόνας.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Γιατί κάθε γραμμή είναι σημαντική

| Γραμμή | Σκοπός |
|------|---------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Δημιουργεί μια γεννήτρια PDF417 και ορίζει το κωδικοποιημένο κείμενο. Το PDF417 υποστηρίζει μεγάλα σύνολα δεδομένων και Unicode, καθιστώντας το κατάλληλο για σύνθετους ταυτοποιητές. |
| `XDimension.Pixels = 2` | Ελέγχει την οπτική πυκνότητα. Μικρότερες τιμές παράγουν πιο λεπτές γραμμές· μεγαλύτερες τιμές βελτιώνουν την αναγνωσιμότητα σε οθόνες χαμηλής ανάλυσης. |
| `Pdf417.Columns = 3` | Αντικαθιστά τον αυτόματο υπολογισμό στηλών. Σταθερές στήλες είναι χρήσιμες όταν πρέπει να ταιριάξετε τον κώδικα σε προκαθορισμένο χώρο. |
| `Pdf417.Truncate = true` | Ενεργοποιεί τη συμπαγή λειτουργία, η οποία αφαιρεί περιττή συμπλήρωση και μειώνει το συνολικό μέγεθος. |
| `Save(..., BarCodeImageFormat.Png)` | Γράφει τον κώδικα σε αρχείο PNG, μορφή χωρίς απώλειες ιδανική για περαιτέρω επεξεργασία ή ενσωμάτωση σε PDF. |

## Βήμα 3: Εκτελέστε το πρόγραμμα και επαληθεύστε το αποτέλεσμα

Δομήστε και εκτελέστε το έργο:

```bash
dotnet run
```

Θα πρέπει να δείτε ένα μήνυμα κονσόλας που επιβεβαιώνει τη θέση του αρχείου, και ένα αρχείο με όνομα **CompactPdf417.png** θα εμφανιστεί στον φάκελο του έργου.

![Παράδειγμα παραγόμενου γραμμωτού κώδικα PDF417](images/compact-pdf417.png){.img-responsive alt="Παράδειγμα παραγόμενου γραμμωτού κώδικα PDF417"}

*Η εικόνα δείχνει έναν συμπαγή γραμμωτό κώδικα PDF417 που κωδικοποιεί τη συμβολοσειρά “Åspóse.Barcóde©”.*  

Αν ανοίξετε το PNG σε προβολέα εικόνων, θα παρατηρήσετε τρεις στήλες στοιβαγμένων μπλοκ δεδομένων, κάθε γραμμή 2 pixel πλάτος. Η σάρωση του κώδικα με έναν τυπικό αναγνώστη PDF417 επιστρέφει το αρχικό κείμενο, επιβεβαιώνοντας ότι η γεννήτρια λειτουργεί όπως αναμένεται.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Πρόβλημα | Αιτία | Διόρθωση |
|-------|--------|-----|
| Ο κώδικας εμφανίζεται θολός | Το XDimension έχει οριστεί πολύ χαμηλό για το επιθυμητό DPI | Αυξήστε το `XDimension.Pixels` σε 3 ή 4, ή αποδώστε σε υψηλότερη ανάλυση χρησιμοποιώντας `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Οι χαρακτήρες Unicode χάνονται | Η συμβολοσειρά εισόδου δεν είναι κωδικοποιημένη ως UTF‑8 | Βεβαιωθείτε ότι το αρχείο πηγής είναι αποθηκευμένο με κωδικοποίηση UTF‑8· η γεννήτρια διαχειρίζεται αυτόματα το Unicode όταν ο τύπος της συμβολοσειράς είναι `string`. |
| Το Truncate προκαλεί εξαίρεση | Το μέγεθος των δεδομένων υπερβαίνει το μέγιστο για τον επιλεγμένο αριθμό στηλών | Αυξήστε είτε το `Pdf417.Columns` είτε ορίστε `Pdf417.Truncate = false` ώστε η γεννήτρια να διαθέσει αρκετό χώρο. |
| Η άδεια δεν εφαρμόστηκε | Η έκδοση αξιολόγησης προσθέτει υδατογράφημα | Εφαρμόστε ένα έγκυρο αρχείο άδειας μέσω `Aspose.BarCode.License` πριν δημιουργήσετε τη γεννήτρια. |

## Επέκταση της λύσης

Μόλις έχετε τη βασική ροή **generate PDF417 barcode**, μπορείτε να εξερευνήσετε πρόσθετες λειτουργίες:

- **Επίπεδο διόρθωσης σφαλμάτων** – Ρυθμίστε το `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` για να αυξήσετε την ανθεκτικότητα σε ζημιές.
- **Προσαρμογή χρώματος** – Χρησιμοποιήστε τα `generator.Parameters.Barcode.ForegroundColor` και `BackgroundColor` για να ταιριάξετε με τις οδηγίες branding.
- **Ενσωμάτωση σε PDF** – Συνδυάστε το Aspose.PDF με το Aspose.BarCode για να τοποθετήσετε τον κώδικα απευθείας μέσα σε ένα έγγραφο PDF.
- **Δημιουργία παρτίδας** – Επαναλάβετε πάνω σε μια συλλογή ταυτοποιητών για να παραγάγετε πολλαπλά αρχεία PNG σε μία εκτέλεση.

Όλες αυτές οι επιλογές τεκμηριώνονται στην αναφορά API του Aspose.BarCode και ακολουθούν το ίδιο μοτίβο που παρουσιάστηκε παραπάνω.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# χρησιμοποιώντας το Aspose.BarCode, να ρυθμίσετε στήλες, να ενεργοποιήσετε τη συμπαγή λειτουργία και να εξάγετε το αποτέλεσμα ως εικόνα PNG. Το πλήρες παράδειγμα λειτουργεί αμέσως και μπορεί να προσαρμοστεί για μεγαλύτερα έργα, όπως συστήματα έκδοσης εισιτηρίων, ετικέτες απογραφής ή ασφαλή κωδικοποίηση εγγράφων.

Στη συνέχεια, δοκιμάστε τις προχωρημένες ρυθμίσεις του **pdf417 barcode generator C#** όπως η διόρθωση σφαλμάτων και η προσαρμογή χρώματος, ή ενσωματώστε τον κώδικα σε μια αναφορά PDF με το Aspose.PDF. Πειραματιστείτε με διαφορετικές τιμές `XDimension` και αριθμούς στηλών για να βρείτε την ιδανική ισορροπία μεταξύ μεγέθους και αξιοπιστίας σάρωσης για τη συγκεκριμένη περίπτωση χρήσης σας. Καλή προγραμματιστική!

## Τι Θα Μάθετε Στη Σύντομη Μελλοντική Περίοδο;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετικούς θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες λειτουργίες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# – πλήρης οδηγός με συμπαγή διάταξη](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Παράδειγμα Aspose barcode: δημιουργία Macro PDF417 σε C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Πώς να αποθηκεύσετε γραμμωτό κώδικα σε C# – Δημιουργία PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}