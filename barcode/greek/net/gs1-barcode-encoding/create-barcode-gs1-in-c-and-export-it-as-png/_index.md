---
category: general
date: 2026-09-29
description: Δημιουργήστε γραμμωτό κώδικα GS1 σε C# και δημιουργήστε εικόνες PNG γραμμωτού
  κώδικα χρησιμοποιώντας το BarcodeGenerator. Ακολουθήστε έναν οδηγό βήμα‑βήμα για
  να εξάγετε την εικόνα του γραμμωτού κώδικα αποδοτικά.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: el
lastmod: 2026-09-29
og_description: Δημιουργήστε κωδικό GS1 σε C# και δημιουργήστε αρχεία PNG κωδικού
  με το BarcodeGenerator. Ακολουθήστε αυτόν τον πλήρη οδηγό για να εξάγετε γρήγορα
  την εικόνα του κωδικού.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Δημιουργήστε γραμμωτό κώδικα GS1 σε C# – εξαγωγή ως PNG σε λίγα λεπτά
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Δημιουργία γραμμωτού κώδικα GS1 σε C# και εξαγωγή του ως PNG
url: /el/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία barcode GS1 σε C# και εξαγωγή του ως PNG

Αν χρειάζεστε **δημιουργήσετε barcode GS1** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε μια σύντομη λύση που δημιουργεί μια εικόνα barcode PNG και εξάγει την εικόνα barcode στο δίσκο, όλα με την κλάση Aspose.BarCode `BarcodeGenerator`.

Η δημιουργία ενός barcode GS1 είναι συχνή απαίτηση για συστήματα αποθεμάτων, αποστολών και σημείων πώλησης. Στο τέλος αυτού του οδηγού θα μπορείτε να γράψετε ένα μικρό πρόγραμμα C# που δημιουργεί ένα barcode MicroPDF417 συμβατό με GS1 και το αποθηκεύει ως αρχείο PNG υψηλής ποιότητας.

## Προαπαιτήσεις

* **.NET 6** (ή οποιαδήποτε μεταγενέστερη έκδοση .NET) εγκατεστημένη.
* **Visual Studio 2022** ή οποιοδήποτε IDE που υποστηρίζει C#.
* Το πακέτο NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – παρέχει το API `BarcodeGenerator` που χρησιμοποιείται στα παραδείγματα.
* Βασική εξοικείωση με τη σύνταξη C#.

> **Pro tip:** Χρησιμοποιήστε τη δωρεάν έκδοση community του Aspose.BarCode όταν πειραματίζεστε· η πλήρης έκδοση αφαιρεί τυχόν υδατογραφήματα αξιολόγησης.

## Βήμα 1 – Δημιουργία barcode GS1 με BarcodeGenerator

Το πρώτο που χρειάζεστε είναι να δημιουργήσετε ένα αντικείμενο `BarcodeGenerator` για τη μορφή *MicroPDF417* και να του δώσετε μια συμβολοσειρά δεδομένων GS1. Τα GS1 Application Identifiers (AIs) περικλείονται σε παρενθέσεις, π.χ. `(01)` για GTIN‑14 και `(21)` για αριθμό σειράς.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Γιατί είναι σημαντικό:**  
`EncodeTypes.MicroPdf417` αντιμετωπίζει αυτόματα την είσοδο ως δεδομένα GS1 όταν η συμβολοσειρά περιέχει έγκυρα AIs. Αυτό εξασφαλίζει ότι το παραγόμενο barcode συμμορφώνεται με την προδιαγραφή GS1 χωρίς επιπλέον ρύθμιση.

## Βήμα 2 – Ορισμός διαστάσεων barcode για βέλτιστο μέγεθος

Το οπτικό μέγεθος ενός barcode ελέγχεται από τη **X‑dimension** (το πλάτος μιας μονάδας). Η ρύθμιση του `XDimension.Pixels` σας επιτρέπει να ρυθμίσετε ακριβώς το τελικό μέγεθος της εικόνας διατηρώντας την αναγνωσιμότητα.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Πώς να δημιουργήσετε barcode PNG** – Η X‑dimension δεν επηρεάζει τα κωδικοποιημένα δεδομένα· αλλάζει μόνο τις φυσικές διαστάσεις της παραγόμενης εικόνας. Εάν χρειάζεστε μεγαλύτερο barcode για εκτύπωση υψηλής ανάλυσης, αυξήστε αυτήν την τιμή (π.χ., `3` ή `4`).

## Βήμα 3 – Δημιουργία barcode PNG και εξαγωγή εικόνας barcode

Τώρα μπορείτε να αποδώσετε το barcode και να το γράψετε σε αρχείο PNG. Η μέθοδος `Save` δέχεται τη διαδρομή προορισμού και τη ζητούμενη μορφή εικόνας.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Τι συμβαίνει στο παρασκήνιο:**  
`BarcodeGenerator.Save` μετατρέπει το barcode σε bitmap, εφαρμόζει την X‑dimension που ορίσατε προηγουμένως και κωδικοποιεί το bitmap ως αρχείο PNG. Το παραγόμενο αρχείο μπορεί να χρησιμοποιηθεί άμεσα σε ιστοσελίδες, να εκτυπωθεί σε ετικέτες ή να ενσωματωθεί σε PDF.

## Πλήρες παράδειγμα κώδικα

Παρακάτω υπάρχει μια πλήρης, αυτόνομη εφαρμογή κονσόλας που μπορείτε να αντιγράψετε, επικολλήσετε και εκτελέσετε. Δείχνει **πώς να δημιουργήσετε αρχεία barcode PNG**, **να εξάγετε εικόνα barcode**, και περιλαμβάνει βασικό χειρισμό σφαλμάτων.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Αναμενόμενο αποτέλεσμα

Όταν εκτελέσετε το πρόγραμμα, θα πρέπει να δείτε:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Ανοίγοντας το αρχείο PNG εμφανίζεται ένα καθαρό barcode **GS1 MicroPDF417** που κωδικοποιεί το GTIN‑14 `12345678901234` και τον αριθμό σειράς `ABC123`. Η σάρωση του με οποιονδήποτε scanner συμβατό με GS1 θα επιστρέψει την αρχική συμβολοσειρά δεδομένων.

## Συνηθισμένα προβλήματα και βέλτιστες πρακτικές

| Πρόβλημα | Γιατί συμβαίνει | Πώς να το αποφύγετε |
|----------|----------------|----------------------|
| **Λανθασμένη μορφοποίηση AI** | Η έλλειψη παρενθέσεων ή η λανθασμένη σειρά κάνει το barcode μη‑GS1. | Πάντα να περικλείετε κάθε AI σε παρενθέσεις, π.χ., `(01)`. |
| **Πολύ μικρή X‑dimension** | Το barcode γίνεται μη αναγνώσιμο σε συσκευές χαμηλής ανάλυσης. | Διατηρήστε `XDimension.Pixels` ≥ 2 για τους περισσότερους εκτυπωτές· αυξήστε το για έξοδο υψηλής DPI. |
| **Ο φάκελος εξόδου δεν υπάρχει** | `Save` προκαλεί `DirectoryNotFoundException`. | Χρησιμοποιήστε `Directory.CreateDirectory` πριν καλέσετε το `Save`. |
| **Χρήση λανθασμένου EncodeType** | Ορισμένοι τύποι (π.χ., `Code128`) δεν υποστηρίζουν δεδομένα GS1 από προεπιλογή. | Επιλέξτε `EncodeTypes.MicroPdf417` ή οποιονδήποτε τύπο συμβατό με GS1. |
| **Λείπει η αναφορά NuGet** | Σφάλματα χρόνου μεταγλώττισης όπως `The type or namespace name 'Aspose' could not be found`. | Εγκαταστήστε το πακέτο `Aspose.BarCode` μέσω NuGet. |

## Επέκταση του παραδείγματος

* **Διαφορετικές μορφές εικόνας** – Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Gif` ή `Bmp` εάν χρειάζεστε άλλη μορφή.
* **Έξοδος υψηλότερης ανάλυσης** – Ορίστε `generator.Parameters.ImageResolution.DpiX` και `DpiY` πριν από την αποθήκευση.
* **Ενσωμάτωση σε PDF** – Χρησιμοποιήστε το `Aspose.Pdf` για να τοποθετήσετε το PNG σε τιμολόγιο PDF ή ετικέτα.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε barcode GS1** σε C# χρησιμοποιώντας το Aspose.BarCode `BarcodeGenerator`, **να δημιουργήσετε barcode PNG**, και **να εξάγετε εικόνα barcode** στο σύστημα αρχείων. Ο οδηγός κάλυψε κάθε βήμα—από την αρχικοποίηση του generator με δεδομένα GS1, τη ρύθμιση της X‑dimension, έως την αποθήκευση του τελικού αρχείου PNG—ενώ αντιμετώπιζε κοινά σφάλματα και προσέφερε ιδέες επέκτασης.

Μη διστάσετε να πειραματιστείτε με άλλα GS1 Application Identifiers, διαφορετικές συμβολές barcode ή εικόνες υψηλότερης ανάλυσης. Όταν κυριαρχήσετε σε αυτά τα βασικά, η δημιουργία συμβατών barcode για αποθέματα, αποστολές ή λιανική πώληση γίνεται μια καθημερινή πρακτική στο .NET toolbox σας.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία εικόνων GS1 Barcode σε C# – Πώς να δημιουργήσετε Barcode C# γρήγορα](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Δημιουργία barcode PNG σε C# – οδηγός βήμα‑βήμα](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Δημιουργία εικόνας barcode σε C# – πλήρης οδηγός προγραμματισμού](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}