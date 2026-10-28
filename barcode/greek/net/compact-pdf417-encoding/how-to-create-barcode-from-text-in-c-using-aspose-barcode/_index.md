---
category: general
date: 2026-10-28
description: Δημιουργήστε barcode από κείμενο σε C# με το Aspose.BarCode. Μάθετε πώς
  να δημιουργείτε εικόνα barcode PDF417, να ορίζετε στήλες, να ρυθμίζετε τη διάσταση
  X και να ενεργοποιείτε τη συμπαγή λειτουργία.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: el
lastmod: 2026-10-28
og_description: Δημιουργήστε barcode από κείμενο σε C# χρησιμοποιώντας το Aspose.BarCode.
  Αυτό το σεμινάριο δείχνει πώς να δημιουργήσετε μια εικόνα barcode PDF417, να προσαρμόσετε
  το μέγεθος, τις στήλες και τη λειτουργία συμπαγούς μορφής.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Δημιουργήστε γραμμωτό κώδικα από κείμενο σε C# – οδηγός βήμα‑προς‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Πώς να δημιουργήσετε γραμμωτό κώδικα από κείμενο σε C# χρησιμοποιώντας το Aspose.BarCode
url: /el/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε barcode από κείμενο σε C# χρησιμοποιώντας το Aspose.BarCode

Αν χρειάζεστε **create barcode from text** σε μια εφαρμογή .NET, αυτός ο οδηγός παρέχει μια έτοιμη λύση. Θα δείτε πώς να **generate PDF417 barcode** εικόνες, να ελέγξετε το πλάτος του μονάδας, τον αριθμό των στηλών και να ενεργοποιήσετε τη συμπαγή λειτουργία χωρίς να φύγετε από το IDE.

Το tutorial καλύπτει όλα όσα απαιτούνται για κώδικα **generate barcode C#**, από την εγκατάσταση της βιβλιοθήκης μέχρι την αποθήκευση του τελικού αρχείου PNG. Στο τέλος μπορείτε να ενσωματώσετε ένα υψηλής πυκνότητας PDF417 barcode σε αναφορές, εισιτήρια ή ετικέτες αποθέματος.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιονδήποτε επεξεργαστή που υποστηρίζει .NET)  
* Πρόσβαση στο Internet για λήψη του πακέτου NuGet Aspose.BarCode for .NET  

Αυτά τα στοιχεία είναι επαρκή για να μεταγλωττίσετε και να εκτελέσετε το παράδειγμα σε Windows, Linux ή macOS.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Η βιβλιοθήκη που τροφοδοτεί τη δημιουργία barcode είναι **Aspose.BarCode for .NET**. Εγκαταστήστε την με το .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο προσθέτει το namespace `Aspose.BarCode`, το οποίο περιέχει την κλάση `BarcodeGenerator` που χρησιμοποιείται σε όλο το tutorial.

## Βήμα 2: Δημιουργία έργου κονσόλας και προσθήκη του κώδικα

Δημιουργήστε ένα νέο έργο κονσόλας και αντικαταστήστε το παραγόμενο `Program.cs` με τον παρακάτω κώδικα. Το πρόγραμμα δείχνει πώς να **create barcode from text** και να το αποθηκεύσετε ως **PDF417 barcode image**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Γιατί κάθε γραμμή είναι σημαντική

* **`EncodeTypes.Pdf417`** επιλέγει τη συμβολική μορφή PDF417, η οποία είναι ιδανική για κωδικοποίηση μεγάλων ποσοτήτων δεδομένων σε δισδιάστατη μορφή.  
* **`XDimension.Pixels = 2`** μειώνει το πλάτος της μονάδας, κάνοντας το barcode πιο πυκνό και πιο κατάλληλο για περιορισμένο χώρο.  
* **`Pdf417.Columns = 3`** ελέγχει τον αριθμό των κάθετων στηλών δεδομένων· ένας μικρότερος αριθμός δημιουργεί ένα ψηλότερο αλλά πιο στενό barcode.  
* **`Pdf417.Truncate = true`** ενεργοποιεί τη συμπαγή λειτουργία, κόβοντας τις αχρησιμοποίητες στήλες στη δεξιά πλευρά. Αυτή είναι η βασική ρύθμιση που μετατρέπει ένα κανονικό PDF417 σε **compact PDF417 barcode image**.  

## Βήμα 3: Κατασκευή και εκτέλεση του έργου

Εκτελέστε τις παρακάτω εντολές στον φάκελο του έργου:

```bash
dotnet build
dotnet run
```

Όταν το πρόγραμμα ολοκληρωθεί, θα δείτε ένα μήνυμα στην κονσόλα που επιβεβαιώνει τη θέση του αρχείου. Ανοίξτε το `CompactPdf417.png` με οποιονδήποτε προβολέα εικόνων για να επαληθεύσετε το αποτέλεσμα.

**Αναμενόμενο αποτέλεσμα** – ένα PNG υψηλής αντίθεσης που εμφανίζει ένα compact PDF417 barcode που κωδικοποιεί τη συμβολοσειρά `Åspóse.Barcóde©`. Η σάρωση της εικόνας με έναν τυπικό αναγνώστη barcode επιστρέφει το αρχικό κείμενο, επιβεβαιώνοντας ότι η **generate pdf417 barcode** ολοκληρώθηκε με επιτυχία.

## Βήμα 4: Προσαρμογή του barcode για διαφορετικά σενάρια

Αν και το παράδειγμα χρησιμοποιεί σταθερό αριθμό στηλών και X‑dimension, μπορείτε να προσαρμόσετε το γεννήτρια για άλλες απαιτήσεις:

| Σενάριο | Προσαρμογή |
|----------|------------|
| Μεγαλύτερο φορτίο δεδομένων | Αυξήστε το `Pdf417.Columns` ή ορίστε το `Pdf417.Rows` χειροκίνητα |
| Μεγαλύτερη αξιοπιστία σάρωσης | Αυξήστε το `XDimension.Pixels` σε 3 ή 4 |
| Διαφορετική μορφή εικόνας | Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg` ή `Bmp` |
| Διαφανές φόντο | Ορίστε `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Αυτές οι επιλογές σας επιτρέπουν να δημιουργήσετε λύσεις **generate barcode C#** που ταιριάζουν σε εφαρμογές κινητών, αναφορές επιφάνειας εργασίας ή web services.

## Βήμα 5: Διαχείριση ακραίων περιπτώσεων και βέλτιστες πρακτικές

* **Unicode support** – Η γεννήτρια κωδικοποιεί αυτόματα χαρακτήρες Unicode, αλλά βεβαιωθείτε ότι η πηγή σας είναι κωδικοποιημένη σε UTF‑8 εάν την διαβάζετε από αρχείο.  
* **Large text** – Το PDF417 μπορεί να κωδικοποιήσει έως 1.850 αλφαριθμητικούς χαρακτήρες. Εάν υπερβείτε αυτό το όριο, η βιβλιοθήκη ρίχνει εξαίρεση· χωρίστε τα δεδομένα σε πολλαπλά barcodes ή μεταβείτε σε συμβολική μορφή υψηλότερης χωρητικότητας.  
* **Error handling** – Τυλίξτε τον κώδικα δημιουργίας σε μπλοκ `try/catch` για να πιάσετε το `BarCodeException` και να παρέχετε ένα φιλικό μήνυμα σφάλματος.  
* **Performance** – Η δημιουργία πολλών barcodes σε βρόχο ωφελείται από την επαναχρησιμοποίηση μιας μόνο παρουσίας `BarcodeGenerator` και την ενημέρωση μόνο του `CodeText` μεταξύ των επαναλήψεων.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Πλήρης λίστα πηγαίου κώδικα

Παρακάτω βρίσκεται το πλήρες, αυτόνομο πρόγραμμα που μπορείτε να αντιγράψετε στο `Program.cs`. Δεν απαιτούνται επιπλέον αρχεία.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Η εκτέλεση αυτού του προγράμματος δημιουργεί το **pdf417 barcode image** που φαίνεται στην παρακάτω εικονογράφηση.

![Compact PDF417 barcode δημιουργημένο από κείμενο χρησιμοποιώντας C#](/images/compact-pdf417.png){.img-fluid alt="παράδειγμα δημιουργίας barcode από κείμενο που εμφανίζει μια compact PDF417 barcode εικόνα"}

*Περιγραφή εικόνας: Το αρχείο PNG εμφανίζει ένα compact PDF417 barcode που κωδικοποιεί τη συμβολοσειρά “Åspóse.Barcóde©”.*  

## Συμπέρασμα

Τώρα ξέρετε πώς να **create barcode from text** σε C# και να παράγετε μια **PDF417 barcode image** με προσαρμοσμένες διαστάσεις και συμπαγή λειτουργία. Το παράδειγμα δείχνει τα βασικά βήματα για **generate barcode C#**, τη διαχείριση δεδομένων Unicode και την προσαρμογή των οπτικών παραμέτρων για διαφορετικά σενάρια ανάπτυξης.

Στη συνέχεια, εξερευνήστε σχετικές θεματικές όπως **generate QR code in C#**, **add barcode to PDF documents**, ή **embed barcodes in ASP.NET Core APIs**. Κάθε μία από αυτές βασίζεται στα ίδια θεμελιώδη στοιχεία `BarcodeGenerator` που καλύπτονται εδώ.

Καλό προγραμματισμό και απολαύστε την ενσωμάτωση barcode στις .NET λύσεις σας!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία PDF417 Barcode σε C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Πώς να δημιουργήσετε PDF417 barcode με Aspose.BarCode σε C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Πώς να δημιουργήσετε εικόνα PDF417 barcode σε C# – πλήρης οδηγός](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}