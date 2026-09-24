---
category: general
date: 2026-08-15
description: Διαβάστε γραμμωτό κώδικα από εικόνα σε C# χρησιμοποιώντας το BarCodeReader.
  Μάθετε πώς να διαβάζετε πολλαπλούς γραμμωτούς κώδικες σε C#, πώς να διαβάζετε τον
  κώδικα PDF417 και δείτε ένα πλήρες παράδειγμα BarCodeReader σε C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: el
lastmod: 2026-08-15
og_description: Διαβάστε γραμμωτό κώδικα από εικόνα σε C# με έναν οδηγό βήμα‑βήμα.
  Ανακαλύψτε πώς να διαβάζετε πολλαπλούς γραμμωτούς κώδικες σε C#, να αποκωδικοποιείτε
  σύμβολα PDF417 και να εκτελείτε ένα πλήρες παράδειγμα C# BarCodeReader.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Ανάγνωση γραμμωτού κώδικα από εικόνα σε C# – Εγχειρίδιο BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Ανάγνωση barcode από εικόνα σε C# – Οδηγός BarCodeReader
url: /el/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάγνωση barcode από εικόνα σε C# – tutorial BarCodeReader

Αν χρειάζεστε **ανάγνωση barcode από εικόνα** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε με την κλάση `BarCodeReader`. Θα δείτε επίσης πώς να **διαβάσετε πολλαπλά barcodes C#**, να αποκωδικοποιήσετε ένα σύμβολο PDF417 και να αποκτήσετε ένα πλήρες **παράδειγμα C# BarCodeReader** που μπορείτε να αντιγράψετε στο έργο σας.

Το tutorial καλύπτει κάθε βήμα—από την προσθήκη του απαιτούμενου πακέτου NuGet μέχρι την εκτύπωση εκτεταμένων πεδίων PDF417—ώστε να ολοκληρώσετε με ένα εκτελέσιμο πρόγραμμα κονσόλας. Δεν απαιτείται εξωτερική τεκμηρίωση· όλος ο κώδικας και οι εξηγήσεις περιλαμβάνονται.

## Τι θα χρειαστείτε

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί με .NET Core και .NET Framework)
* Visual Studio 2022 ή οποιονδήποτε επεξεργαστή συμβατό με C#
* Το πακέτο NuGet `Aspose.BarCode` (ή την ισοδύναμη βιβλιοθήκη που παρέχει το `BarCodeReader`)
* Ένα αρχείο εικόνας που περιέχει ένα Macro PDF417 barcode (π.χ., `ExtPDF417Meta.png`)

Η ύπαρξη αυτών των προαπαιτούμενων διασφαλίζει ότι το δείγμα θα μεταγλωττιστεί χωρίς πρόσθετη ρύθμιση.

## Ανάγνωση barcode από εικόνα με BarCodeReader

Το πρώτο βήμα είναι η δημιουργία μιας στιγμής `BarCodeReader` που δείχνει στο αρχείο εικόνας και λέει στη βιβλιοθήκη ποιος τύπος barcode πρέπει να αναζητηθεί.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Γιατί λειτουργεί αυτό:**  
`BarCodeReader` ανοίγει την εικόνα, σαρώει για το καθορισμένο `DecodeType` και επιστρέφει μια συλλογή αντικειμένων `BarCodeResult`. Κάθε αποτέλεσμα περιέχει τα γενικά δεδομένα barcode (`CodeTypeName`, `CodeText`) και, για Macro PDF417, ένα αντικείμενο `Extended.Pdf417` που εκθέτει όλα τα πρόσθετα πεδία που ορίζονται από το πρότυπο.

## Ανάγνωση πολλαπλών barcodes C# σε μία εικόνα

Μερικές φορές μια εικόνα περιέχει περισσότερα από ένα barcode (π.χ., QR code δίπλα σε PDF417). Για να διαχειριστείτε αυτήν την περίπτωση, απλώς παραλείψτε το ρητό `DecodeType` ή περάστε `DecodeType.AllSupported` και κάντε βρόχο στα αποτελέσματα.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Γιατί το χρειάζεστε:**  
Η καθορισμένη τιμή `AllSupported` λέει στη μηχανή να δοκιμάσει κάθε μορφή barcode που γνωρίζει, εξασφαλίζοντας ότι θα συλλάβετε κάθε σύμβολο στην εικόνα. Αυτή είναι η προτεινόμενη προσέγγιση όταν δεν μπορείτε να προβλέψετε εκ των προτέρων τους τύπους barcode.

## Πώς να διαβάσετε barcode PDF417 χρησιμοποιώντας C#

Αν σας ενδιαφέρει μόνο η κλασική μορφή PDF417 (μη‑macro), αλλάξτε το `DecodeType` σε `Pdf417`. Το υπόλοιπο του κώδικα παραμένει ίδιο, εκτός από το ότι τα εκτεταμένα πεδία δεν είναι διαθέσιμα.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Γιατί έχει σημασία:**  
Η κλασική PDF417 δεν εκθέτει τις ιδιότητες που αφορούν το macro, επομένως το τμήμα `Extended.Pdf417` είναι περιττό. Η χρήση του ακριβούς `DecodeType` επίσης επιταχύνει τη σάρωση επειδή η βιβλιοθήκη παραλείπει αλγόριθμους που δεν υποστηρίζονται.

## Πλήρες παράδειγμα C# BarCodeReader που μπορείτε να αντιγράψετε

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που συνδυάζει τα τρία σενάρια σε μια ενιαία, εύκολη στην εκτέλεση εφαρμογή κονσόλας. Αντικαταστήστε το `YOUR_DIRECTORY/ExtPDF417Meta.png` με την πραγματική διαδρομή της εικόνας σας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Αναμενόμενη έξοδος

Όταν η δείγμα εικόνας περιέχει ένα Macro PDF417 barcode, η κονσόλα εκτυπώνει κάτι παρόμοιο με:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Αν η εικόνα περιέχει μόνο ένα κανονικό PDF417, η ενότητα “Macro PDF417” θα είναι κενή, και η ενότητα “Classic PDF417” θα εμφανίσει το αποκωδικοποιημένο κείμενο.

## Συμπέρασμα

Τώρα ξέρετε πώς να **διαβάζετε barcode από εικόνα** σε C# χρησιμοποιώντας το `BarCodeReader`, πώς να **διαβάζετε πολλαπλά barcodes C#** σε ένα αρχείο, και τα ακριβή βήματα για **ανάγνωση barcode PDF417**—και στις macro και στις κλασικές εκδοχές. Το πλήρες **παράδειγμα C# BarCodeReader** είναι έτοιμο να επικολληθεί σε οποιοδήποτε έργο .NET, και μπορείτε να το επεκτείνετε για να υποστηρίξετε άλλες μορφές ή να το ενσωματώσετε σε μια μεγαλύτερη αλυσίδα επεξεργασίας εικόνας.

**Επόμενα βήματα**

* Εξερευνήστε μοτίβα διαχείρισης σφαλμάτων όπως `try / catch` γύρω από το μπλοκ του αναγνώστη.  
* Πειραματιστείτε με το αντικείμενο `ReaderParameters` για να ρυθμίσετε την ταχύτητα και την ακρίβεια ανίχνευσης.  
* Συνδυάστε την ανάγνωση barcode με βιβλιοθήκες προεπεξεργασίας εικόνας (

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}