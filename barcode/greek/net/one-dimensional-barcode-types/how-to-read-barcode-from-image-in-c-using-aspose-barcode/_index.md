---
category: general
date: 2026-10-18
description: Μάθετε πώς να διαβάζετε γραμμωτό κώδικα από εικόνα σε C# με το Aspose.BarCode,
  καλύπτοντας την εξαγωγή μεταδεδομένων Macro PDF417 και παρέχοντας πλήρες παράδειγμα
  κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: el
lastmod: 2026-10-18
og_description: Πώς να διαβάσετε γραμμωτό κώδικα από εικόνα χρησιμοποιώντας C# Aspose.BarCode.
  Ακολουθήστε αυτόν τον βήμα‑βήμα οδηγό για να εξάγετε τα μεταδεδομένα Macro PDF417
  και να αντιμετωπίσετε κοινές περιπτώσεις.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Πώς να διαβάσετε γραμμωτό κώδικα από εικόνα σε C# – πλήρης οδηγός Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να διαβάσετε γραμμωτό κώδικα από εικόνα σε C# χρησιμοποιώντας το Aspose.BarCode
url: /el/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε barcode από εικόνα σε C# χρησιμοποιώντας Aspose.BarCode

Αν χρειάζεστε **πώς να διαβάσετε barcode από εικόνα** σε μια εφαρμογή .NET, αυτός ο οδηγός δείχνει τα ακριβή βήματα με το Aspose.BarCode. Είτε επεξεργάζεστε σαρωμένα έγγραφα, αποδείξεις ή ετικέτες αποθεμάτων, θα δείτε πώς να διαβάσετε το barcode, να εξάγετε τα μεταδεδομένα Macro PDF417 και να διαχειριστείτε τυπικές περιπτώσεις άκρων.

Η ανάγνωση ενός barcode από εικόνα είναι μια καθημερινή εργασία, αλλά η εξαγωγή των επεκταμένων πεδίων Macro PDF417 προσθέτει ένα επίπεδο πολυπλοκότητας. Αυτό το tutorial καλύπτει τη πλήρη ροή εργασίας, από τη ρύθμιση του έργου μέχρι ένα πλήρως εκτελέσιμο παράδειγμα, ώστε να μπορείτε να αντιγράψετε‑και‑επικολλήσετε τον κώδικα και να δείτε άμεσα αποτελέσματα.

## Τι θα μάθετε

- Πώς να ρυθμίσετε το Aspose.BarCode για έργα C#.  
- Ο σωστός τρόπος δημιουργίας του **C# barcode reader** για εικόνα Macro PDF417.  
- Πώς να επαναλάβετε πάνω σε κάθε ανιχνευμένο barcode και να εμφανίσετε βασικές πληροφορίες.  
- Πώς να αποκτήσετε πρόσβαση στα **Macro PDF417 metadata** όπως file ID, segment ID και checksum.  
- Συμβουλές για τη διαχείριση ελλιπών μεταδεδομένων, μεγάλων εικόνων και κοινών σφαλμάτων αποκωδικοποίησης.  

**Προαπαιτούμενα**

- .NET 6.0 (ή νεότερη) εγκατεστημένη.  
- Βασική εξοικείωση με C# και Visual Studio (οποιοδήποτε IDE λειτουργεί).  
- Ένα αρχείο εικόνας που περιέχει barcode Macro PDF417 (π.χ., `ExtPDF417Meta.png`).  

## Βήμα 1: Εγκατάσταση Aspose.BarCode

Ανοίξτε ένα τερματικό στο φάκελο του έργου σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο περιλαμβάνει την κλάση **BarCodeReader**, η οποία υλοποιεί τη λειτουργικότητα του **C# barcode reader** που απαιτείται για αυτό το tutorial.

## Βήμα 2: Ρύθμιση του περιβάλλοντος ανάπτυξης

Δημιουργήστε μια νέα εφαρμογή console αν δεν έχετε ήδη μία:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Προσθέστε τις οδηγίες `using` στην κορυφή του `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Αυτοί οι χώροι ονομάτων εκθέτουν την **BarCodeReader class** και την απαραίτητη απαρίθμηση `DecodeType` για την αποκωδικοποίηση Macro PDF417.

## Βήμα 3: Αρχικοποίηση του BarCodeReader για Macro PDF417

Ο πυρήνας του **πώς να διαβάσετε barcode από εικόνα** είναι η δημιουργία μιας στιγμής `BarCodeReader` που στοχεύει στον συγκεκριμένο `DecodeType`. Για Macro PDF417 πρέπει να περάσετε `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Γιατί είναι σημαντικό:**  
Η επιλογή `DecodeType.MacroPdf417` λέει στη βιβλιοθήκη να ψάξει για τη μορφή Macro PDF417, η οποία περιέχει επιπλέον πεδία πέρα από τα βασικά δεδομένα του barcode. Αν χρησιμοποιήσετε το γενικό `DecodeType.Pdf417`, αυτά τα επιπλέον πεδία θα αγνοηθούν.

## Βήμα 4: Επανάληψη πάνω στα ανιχνευμένα barcodes

Μια μόνο εικόνα μπορεί να περιέχει πολλαπλά barcodes. Η μέθοδος `ReadBarCodes()` επιστρέφει μια συλλογή `BarCodeResult`. Περάστε από αυτά για να εμφανίσετε τις βασικές πληροφορίες κάθε barcode:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

Το `CodeTypeName` σας λέει την ακριβή συμβολική μορφή του barcode (π.χ., “MacroPdf417”), ενώ το `CodeText` περιέχει το αποκωδικοποιημένο κείμενο.

## Βήμα 5: Εξαγωγή και εμφάνιση των μεταδεδομένων Macro PDF417

Όταν το barcode είναι Macro PDF417, η ιδιότητα `Extended.Pdf417` παρέχει ένα πλούσιο σύνολο πεδίων μεταδεδομένων. Πρόσβαση σε αυτά απευθείας όπως φαίνεται παρακάτω:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Αυτά τα πεδία σας δίνουν όλα όσα χρειάζεστε για να ανασυνθέσετε το αρχικό αρχείο πολλαπλών τμημάτων, να επαληθεύσετε την ακεραιότητα και να συσχετίσετε το barcode με ένα συγκεκριμένο έγγραφο ή αποστολέα.

### Αναμενόμενη έξοδος κονσόλας

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Αν η εικόνα δεν περιέχει barcode Macro PDF417, το αντικείμενο `Extended.Pdf417` θα είναι `null`. Προστατέψτε τον κώδικα ώστε να αποφύγετε `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Βήμα 6: Διαχείριση κοινών σφαλμάτων και περιπτώσεων άκρων

### Μεγάλες εικόνες

Η ανάγνωση πολύ μεγάλων εικόνων μπορεί να καταναλώσει σημαντική μνήμη. Χρησιμοποιήστε την υπερφόρτωση του `BarcodeReader` που δέχεται `ReaderParameters` για να περιορίσετε το μέγιστο μέγεθος εικόνας:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Ελλιπή ή κατεστραμμένα μεταδεδομένα

Αν κάποιο από τα πεδία Macro λείπει, η αντίστοιχη ιδιότητα επιστρέφει `null` ή `0`. Καταγράψτε αυτές τις περιπτώσεις και αποφασίστε αν θα θεωρήσετε το barcode ως ελλιπές.

### Πολλαπλοί τύποι barcode σε μία εικόνα

Αν μια εικόνα μπορεί να περιέχει άλλες μορφές barcode, μπορείτε να περάσετε έναν πίνακα τιμών `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Αυτή η προσέγγιση διατηρεί τη λογική **πώς να διαβάσετε barcode από εικόνα** ευέλικτη χωρίς να θυσιάζει την απόδοση.

## Βήμα 7: Πλήρης κώδικας πηγής

Παρακάτω είναι το πλήρες, έτοιμο‑για‑εκτέλεση πρόγραμμα. Αντικαταστήστε το `YOUR_DIRECTORY/ExtPDF417Meta.png` με τη διαδρομή της δικής σας εικόνας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Τρέξτε το πρόγραμμα με:

```bash
dotnet run
```

Θα πρέπει να δείτε τον τύπο του barcode, το αποκωδικοποιημένο κείμενο και όλα τα διαθέσιμα πεδία Macro PDF417 να εκτυπώνονται στην κονσόλα.

## Συμπέρασμα

Σε αυτό το tutorial μάθατε **πώς να διαβάσετε barcode από εικόνα** χρησιμοποιώντας το Aspose.BarCode για C#. Ο οδηγός κάλυψε τη ρύθμιση του **C# barcode reader**,

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε πρόσθετα χαρακτηριστικά του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}