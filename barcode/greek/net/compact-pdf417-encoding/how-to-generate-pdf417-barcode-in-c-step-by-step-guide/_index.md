---
category: general
date: 2026-09-10
description: Δημιουργήστε γρήγορα γραμμωτό κώδικα PDF417 σε C#. Μάθετε πώς να δημιουργείτε
  PDF417 και πώς να αλλάζετε το μέγεθος του γραμμωτού κώδικα με το Aspose.BarCode
  σε λίγες μόνο γραμμές.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: el
lastmod: 2026-09-10
og_description: Δημιουργήστε άμεσα barcode PDF417 σε C#. Αυτό το σεμινάριο δείχνει
  πώς να δημιουργήσετε PDF417 και πώς να αλλάξετε το μέγεθος του barcode χρησιμοποιώντας
  το Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Δημιουργία κώδικα PDF417 σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – βήμα‑βήμα οδηγός
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε ένα σύντομο, έτοιμο‑για‑εκτέλεση παράδειγμα που δημιουργεί έναν γραμμωτό κώδικα PDF417, σας επιτρέπει να ελέγχετε το μέγεθός του και αποθηκεύει το αποτέλεσμα ως εικόνα PNG.

Η δημιουργία ενός γραμμωτού κώδικα PDF417 είναι μια συχνή απαίτηση για συστήματα απογραφής, κάρτες επιβίβασης και παρακολούθηση εγγράφων. Σε αυτό το tutorial καλύπτουμε επίσης **πώς να αλλάξετε το μέγεθος του γραμμωτού κώδικα** ώστε ο κώδικας να προσαρμόζεται σε διαφορετικές ανάγκες εκτύπωσης ή εμφάνισης στην οθόνη.

## Προαπαιτούμενα

* .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+)
* Visual Studio 2022 ή οποιοδήποτε IDE C#
* Το πακέτο NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Βασική εξοικείωση με εφαρμογές κονσόλας C#

## Ρύθμιση έργου

1. Δημιουργήστε ένα νέο έργο κονσόλας:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Προσθέστε την αναφορά Aspose.BarCode (δείτε τα προαπαιτούμενα).  

3. Ανοίξτε το `Program.cs` και αντικαταστήστε το περιεχόμενό του με το πλήρες παράδειγμα παρακάτω.

## Βήμα 1: Δημιουργία γραμμωτού κώδικα PDF417

Το πρώτο βήμα είναι να δημιουργήσετε μια παρουσία `BarcodeGenerator` ρυθμισμένη για τη συμβολή **PDF417**. Αυτό το αντικείμενο είναι το σημείο εισόδου για όλες τις λειτουργίες γραμμωτού κώδικα.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Γιατί είναι σημαντικό* – Η τιμή του enum `EncodeTypes.Pdf417` λέει στο Aspose.BarCode να χρησιμοποιήσει το πρότυπο PDF417, ενώ το δεύτερο όρισμα παρέχει τα δεδομένα που θα κωδικοποιηθούν. Ο δημιουργός τώρα κρατά ένα πλήρες αντικείμενο γραμμωτού κώδικα που μπορείτε να προσαρμόσετε πριν το αποθηκεύσετε.

## Βήμα 2: Πώς να αλλάξετε το μέγεθος του γραμμωτού κώδικα (μέγεθος μονάδας)

Οι γραμμωτοί κώδικες PDF417 αποτελούνται από μικρές τετράγωνες μονάδες. Η ρύθμιση του μεγέθους της μονάδας αλλάζει τις συνολικές διαστάσεις της εικόνας χωρίς να τροποποιεί τα κωδικοποιημένα δεδομένα.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Γιατί είναι σημαντικό* – Ένα μεγαλύτερο `XDimension` παράγει έναν μεγαλύτερο γραμμωτό κώδικα κατάλληλο για εκτύπωση υψηλής ανάλυσης· μια μικρότερη τιμή είναι καλύτερη για εμφάνιση στην οθόνη. Η προεπιλογή είναι συνήθως 1 px, που μπορεί να φαίνεται στενή σε σύγχρονες οθόνες.

## Βήμα 3: Διαμόρφωση διάταξης – στήλες και γραμμές

Το PDF417 σας επιτρέπει να ορίσετε τον αριθμό των στηλών και των γραμμών, κάτι που επηρεάζει τόσο το σχήμα του γραμμωτού κώδικα όσο και την ικανότητα διόρθωσης σφαλμάτων.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Γιατί είναι σημαντικό* – Περισσότερες στήλες κάνουν τον γραμμωτό κώδικα πιο πλατύ, ενώ περισσότερες γραμμές τον κάνουν πιο ψηλό. Ρυθμίστε αυτές τις τιμές ώστε να ταιριάζουν στον διαθέσιμο χώρο στη διεπαφή χρήστη ή στην εκτυπωμένη ετικέτα.

## Βήμα 4: Αποθήκευση της εικόνας του γραμμωτού κώδικα

Τέλος, γράψτε τον γραμμωτό κώδικα σε αρχείο. Εδώ χρησιμοποιούμε PNG επειδή διατηρεί καθαρές άκρες και υποστηρίζει διαφάνεια.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Η εκτέλεση του προγράμματος δημιουργεί το `LayoutPdf417.png` στο φάκελο εξόδου του έργου. Η εικόνα θα φαίνεται ως εξής:

![παράδειγμα δημιουργίας γραμμωτού κώδικα PDF417 που εμφανίζει 4 στήλες και 9 γραμμές](https://example.com/images/pdf417-sample.png){#barcode-image alt="παράδειγμα δημιουργίας γραμμωτού κώδικα PDF417 που εμφανίζει 4 στήλες και 9 γραμμές"}

*Συμβουλή*: Αν χρειάζεστε διαφορετική μορφή εικόνας (JPEG, BMP, TIFF), αντικαταστήστε το `BarCodeImageFormat.Png` με την κατάλληλη τιμή enum.

## Πώς να δημιουργήσετε PDF417 – εναλλακτικές πηγές δεδομένων

Ο παραπάνω κώδικας χρησιμοποιεί μια σκληρά κωδικοποιημένη συμβολοσειρά `"Layout test"`. Σε πραγματικές περιπτώσεις συχνά αντλείτε δεδομένα από βάση δεδομένων, αρχείο ή είσοδο χρήστη.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Τα υπόλοιπα βήματα (μέγεθος, διάταξη, αποθήκευση) παραμένουν αμετάβλητα. Αυτό δείχνει **πώς να δημιουργήσετε PDF417** από δυναμικές πηγές χωρίς πρόσθετη πολυπλοκότητα.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Ο γραμμωτός κώδικας εμφανίζεται θολός | `XDimension` ορίζεται πολύ χαμηλό για την ανάλυση εξόδου | Αυξήστε το `XDimension.Pixels` ή αποθηκεύστε ως διανυσματική μορφή όπως SVG (`BarCodeImageFormat.Svg`) |
| Το κείμενο δεν χωράει στην επιλεγμένη διάταξη | Πάρα πολλοί χαρακτήρες για τις επιλεγμένες γραμμές/στήλες | Μειώστε τον αριθμό των γραμμών/στηλών ή χωρίστε τα δεδομένα σε πολλαπλούς γραμμωτούς κώδικες |
| Το αρχείο εικόνας δεν δημιουργήθηκε | Ο φάκελος εξόδου δεν υπάρχει ή λείπουν δικαιώματα εγγραφής | Βεβαιωθείτε ότι ο φάκελος υπάρχει (`Directory.CreateDirectory`) και η εφαρμογή εκτελείται με τα κατάλληλα δικαιώματα |

## Επαλήθευση του γραμμωτού κώδικα

Μετά τη δημιουργία της εικόνας, μπορείτε να την επαληθεύσετε χρησιμοποιώντας οποιαδήποτε εφαρμογή σάρωσης PDF417 (τα κινητά τηλέφωνα έχουν δωρεάν σαρωτές) ή τον ενσωματωμένο αναγνώστη Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Αν το αποτέλεσμα ταιριάζει με το αρχικό κείμενο, η διαδικασία **δημιουργίας γραμμωτού κώδικα PDF417** πέτυχε.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω είναι το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑και‑επικολλήσετε στο `Program.cs`. Περιλαμβάνει όλες τις οδηγίες using, διαχείριση σφαλμάτων και σχόλια.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Η εκτέλεση αυτού του προγράμματος εκτυπώνει:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Τώρα έχετε μια **πλήρη, αυτόνομη λύση** για τη δημιουργία γραμμωτών κώδικα PDF417 και τον έλεγχο του μεγέθους τους.

## Συμπέρασμα

Σε αυτό το tutorial μάθατε πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# χρησιμοποιώντας το Aspose.BarCode, πώς να **αλλάξετε το μέγεθος του γραμμωτού κώδικα** ρυθμίζοντας τη διάσταση X, και πώς να διαμορφώσετε στήλες και γραμμές για έλεγχο της διάταξης. Επίσης, είδατε πώς να επαληθεύσετε το αποτέλεσμα προγραμματιστικά και πώς να προσαρμόσετε τον κώδικα για δυναμικά δεδομένα.

Στη συνέχεια, μπορείτε να εξερευνήσετε:

* **Πώς να δημιουργήσετε PDF417** με ρύθμιση επιπέδου διόρθωσης σφαλμάτων (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Εξαγωγή σε **διανυσματικές μορφές** (SVG, EPS) για απεριόριστη κλιμάκωση
* Ενσωμάτωση του γραμμωτού κώδικα σε έγγραφο PDF με **Aspose.PDF**

Πειραματιστείτε με διαφορετικά μεγέθη μονάδων και επιλογές διάταξης για να ταιριάζουν στις συγκεκριμένες απαιτήσεις UI ή εκτύπωσης. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με Aspose – Πλήρης οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [προσαρμογή μεγέθους γραμμωτού κώδικα – οδηγός C# για δημιουργία γραμμωτών κώδικα PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Πώς να αποθηκεύσετε γραμμωτό κώδικα σε C# – Δημιουργία γραμμωτών κώδικα PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}