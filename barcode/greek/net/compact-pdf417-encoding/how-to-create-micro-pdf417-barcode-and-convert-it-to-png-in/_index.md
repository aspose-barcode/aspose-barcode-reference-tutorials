---
category: general
date: 2026-10-12
description: Μάθετε πώς να δημιουργείτε μικρο‑κώδικα PDF417 και να μετατρέπετε τον
  κώδικα σε PNG χρησιμοποιώντας C#. Οδηγός βήμα‑προς‑βήμα με πλήρη κώδικα και συμβουλές.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: el
lastmod: 2026-10-12
og_description: Δημιουργήστε μικρό barcode PDF417 και μετατρέψτε το σε PNG με C#.
  Ακολουθήστε αυτόν τον πλήρη οδηγό για να δημιουργήσετε τόσο τις τυπικές όσο και
  τις εκδόσεις GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Δημιουργία μικρο‑κωδικού PDF417 και μετατροπή σε PNG – Εγχειρίδιο C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Πώς να δημιουργήσετε μικρό barcode PDF417 και να το μετατρέψετε σε PNG σε C#
url: /el/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε micro PDF417 barcode και να το μετατρέψετε σε PNG σε C#

Αν χρειάζεστε **να δημιουργήσετε micro PDF417 barcode** σε μια εφαρμογή .NET, αυτό το tutorial σας δείχνει ακριβώς πώς. Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που δημιουργεί τόσο ένα τυπικό Micro PDF417 barcode όσο και μια έκδοση συμβατή με GS1, και στη συνέχεια **να μετατρέψετε το barcode σε PNG** για downstream χρήση όπως εκτύπωση ή εμφάνιση στο web.

Η δημιουργία ενός barcode είναι περισσότερο από το να καλέσετε μια μόνο μέθοδο—η επιλογή του σωστού μεγέθους μονάδας, του αριθμού στηλών και της μορφής κωδικοποίησης καθορίζει την αξιοπιστία της σάρωσης. Στο τέλος αυτού του οδηγού θα καταλάβετε γιατί κάθε ρύθμιση είναι σημαντική και πώς να τις προσαρμόσετε στα δικά σας έργα.

## Προαπαιτούμενα

| Απαίτηση | Λόγος |
|-------------|--------|
| .NET 6.0 SDK ή νεότερο | Παρέχει το runtime για την εφαρμογή κονσόλας C# |
| Visual Studio 2022 (ή οποιοδήποτε IDE C#) | Διευκολύνει την επεξεργασία και την αποσφαλμάτωση |
| **Aspose.BarCode for .NET** πακέτο NuGet | Παρέχει τις κλάσεις `BarcodeGenerator`, `EncodeTypes` και `BarCodeImageFormat` |
| Δικαιώματα εγγραφής στον φάκελο εξόδου | Απαιτείται για κλήσεις `Save` που δημιουργούν αρχεία PNG |

Μπορείτε να προσθέσετε το πακέτο Aspose.BarCode μέσω του CLI:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Ρυθμίστε ένα ελάχιστο έργο κονσόλας

Δημιουργήστε ένα νέο έργο κονσόλας και αναφέρετε τη βιβλιοθήκη barcode. Το παρακάτω `Program.cs` περιέχει όλο τον κώδικα που χρειάζεστε· δεν απαιτούνται εξωτερικά αρχεία.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Γιατί κάθε γραμμή έχει σημασία

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Η πρώτη δημιουργεί ένα απλό Micro PDF417 barcode, ενώ η δεύτερη ακολουθεί τα πρότυπα GS1, ενσωματώνοντας Αναγνωριστικούς Εφαρμογών (AIs). Επιλέξτε ανάλογα με το αν το downstream σύστημά σας αναμένει δεδομένα GS1.
* **`XDimension.Pixels = 2`** – Ελέγχει το πλάτος της μονάδας. Μικρότερες τιμές δημιουργούν πιο πυκνή εικόνα αλλά μπορεί να γίνουν αδιάβαστες σε σαρωτές χαμηλής ανάλυσης. Δύο pixel είναι μια ασφαλής προεπιλογή για τις περισσότερες εκτυπωτές ετικετών.
* **`Pdf417.Columns = 4`** – Το Micro PDF417 σας επιτρέπει να περιορίσετε τις στήλες, μειώνοντας το συνολικό πλάτος. Τέσσερις στήλες διατηρούν το barcode συμπαγές χωρίς να θυσιάζουν τη χωρητικότητα δεδομένων για μικρά payloads.
* **`BarCodeImageFormat.Png`** – Το PNG διατηρεί την απώλεια ποιότητας, απαραίτητο για την καθαρότητα του barcode. Γι' αυτό **μετατρέπουμε το barcode σε PNG** αντί για JPEG.

## Βήμα 2: Εκτελέστε το πρόγραμμα και επαληθεύστε το αποτέλεσμα

1. Κατασκευάστε το έργο: `dotnet build`.
2. Εκτελέστε: `dotnet run`.

Θα πρέπει να δείτε μηνύματα κονσόλας παρόμοια με:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Ανοίξτε τα παραγόμενα αρχεία PNG με οποιονδήποτε προβολέα εικόνων. Και οι δύο εικόνες εμφανίζουν ένα καθαρό, υψηλής αντίθεσης barcode έτοιμο για σάρωση.

### Αναμενόμενο οπτικό αποτέλεσμα

| Τύπος barcode | Εμφάνιση |
|--------------|------------|
| **Micro PDF417** | Μικρό ορθογώνιο μοτίβο με 4 στήλες, αναγνώσιμο από τους περισσότερους σαρωτές 2‑D barcode. |
| **GS1 Micro PDF417** | Ίδιο μέγεθος αλλά κωδικοποιεί GS1 AIs· ένας σαρωτής που καταλαβαίνει το GS1 θα επιστρέψει το GTIN και τον σειριακό αριθμό. |

Αν ένας σαρωτής δεν μπορεί να διαβάσει την εικόνα, δοκιμάστε να αυξήσετε το `XDimension.Pixels` σε **3** ή **4**, ή μειώστε τον αριθμό στηλών για το τυπικό Micro PDF417.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Πρόβλημα | Αιτία | Διόρθωση |
|-------|-------|-----|
| Θολό barcode μετά την εκτύπωση | Ρυθμίσεις εκτυπωτή χαμηλής DPI | Εξάγετε PNG στα 300 dpi ή υψηλότερα, ή αφήστε το πρόγραμμα οδήγησης εκτυπωτή να διαχειριστεί την κλιμάκωση. |
| Ο σαρωτής επιστρέφει “invalid data” | Ελλιπής ή λανθασμένη μορφή GS1 AI | Βεβαιωθείτε ότι κάθε AI είναι ενσωματωμένο σε παρενθέσεις και ακολουθεί την προδιαγραφή GS1 (π.χ., `(01)` για GTIN‑14). |
| Δεν δημιουργείται το αρχείο εικόνας | Ο φάκελος εξόδου δεν έχει δικαιώματα εγγραφής | Εκτελέστε το πρόγραμμα με αυξημένα δικαιώματα ή επιλέξτε φάκελο όπως `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode πολύ μεγάλο για ετικέτα | Ο προεπιλεγμένος αριθμός στηλών είναι πολύ υψηλός | Μειώστε το `Pdf417.Columns` (π.χ., σε **3**) ή αυξήστε το `XDimension` για να μειώσετε το συνολικό μέγεθος. |

## Επέκταση του παραδείγματος

* **Διαφορετικές μορφές εικόνας** – Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg` ή `Bmp` αν η ροή εργασίας σας το απαιτεί. Το PNG παραμένει η καλύτερη επιλογή για απώλεια ποιότητας.
* **Δυναμικά δεδομένα** – Περάστε είσοδο χρήστη ή τιμές από τη βάση δεδομένων στον κατασκευαστή `BarcodeGenerator` για να δημιουργήσετε barcodes εν κινήσει.
* **Δημιουργία σε παρτίδες** – Τυλίξτε τη λογική δημιουργίας σε βρόχο που διαβάζει γραμμές από αρχείο CSV και αποθηκεύει κάθε barcode με μοναδικό όνομα αρχείου.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε micro PDF417 barcode** σε C# και **να μετατρέψετε το barcode σε PNG** για τόσο τυπικά όσο και σενάρια συμβατά με GS1. Ο πλήρης, εκτελέσιμος κώδικας δείχνει τις βασικές ρυθμίσεις—διάσταση X, αριθμός στηλών και τύπος κωδικοποίησης—ώστε να προσαρμόσετε τη λύση σε οποιοδήποτε έργο .NET που χρειάζεται συμπαγή, υψηλής ποιότητας 2‑D barcodes.

*Επόμενα βήματα*: εξερευνήστε άλλες συμβολές που υποστηρίζει το Aspose.BarCode (π.χ., QR, DataMatrix), πειραματιστείτε με διαφορετικές τιμές `XDimension` για εκτύπωση υψηλής ανάλυσης, ή ενσωματώστε τα παραγόμενα PNG σε ένα web API που παρέχει barcodes κατόπιν ζήτησης.

## Τι Θα Πρέπει Να Μάθετε Στη Σειρά;

Τα παρακάτω tutorials καλύπτουν στενά σχετικά θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε micro pdf417 barcode σε C# και να το αποθηκεύσετε ως PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Δημιουργία barcode PNG σε C# – πλήρης οδηγός για GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Δημιουργία Micro PDF417 Barcode σε C# – Πλήρης Οδηγός](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}