---
category: general
date: 2026-10-15
description: Πώς να διαβάζετε εικόνες barcode σε C# γρήγορα χρησιμοποιώντας το BarCodeReader.
  Μάθετε πώς να διαβάζετε πολλαπλά barcode και δείτε ένα παράδειγμα αναγνώστη barcode
  σε C# που λειτουργεί με Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: el
lastmod: 2026-10-15
og_description: Πώς να διαβάσετε γραμμωτό κώδικα σε C# χρησιμοποιώντας το BarCodeReader.
  Αυτό το μάθημα παρουσιάζει ένα πλήρες παράδειγμα αναγνώστη γραμμωτού κώδικα σε C#
  που διαχειρίζεται πολλαπλούς κώδικες και εξάγει μεταδεδομένα Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Πώς να διαβάσετε γραμμωτό κώδικα σε C# – παράδειγμα βήμα‑προς‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να διαβάσετε εικόνες barcode σε C# – πλήρης οδηγός με παράδειγμα
url: /el/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε εικόνες barcode σε C# – πλήρης οδηγός παραδείγματος

Αν χρειάζεστε **πώς να διαβάσετε barcode** δεδομένα από μια εικόνα σε εφαρμογή .NET, αυτός ο οδηγός σας παρέχει μια έτοιμη λύση. Θα δείτε ένα πλήρες **c# barcode reader example** που λειτουργεί με σύμβολα Macro‑PDF417 και μπορεί να **διαβάσει πολλαπλά barcode** από μία εικόνα.

Η ανάγνωση barcode είναι κοινή απαίτηση για συστήματα απογραφής, επικύρωση εισιτηρίων και επεξεργασία εγγράφων. Στο τέλος αυτού του tutorial θα μπορείτε να:

* Αρχικοποιήσετε το `BarCodeReader` για οποιαδήποτε υποστηριζόμενη μορφή.  
* Εξάγετε βασικές πληροφορίες όπως τύπο κώδικα και κείμενο αποκωδικοποίησης.  
* Ανακτήσετε μεταδεδομένα ειδικά για Macro‑PDF417 (αναγνωριστικό αρχείου, τμήμα, checksum, …).  
* Διαχειριστείτε εικόνες που περιέχουν πολλαπλά barcode χωρίς επιπλέον κώδικα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερη έκδοση εγκατεστημένη.  
* Περιβάλλον ανάπτυξης (Visual Studio 2022, VS Code ή Rider).  
* Το **Aspose.BarCode for .NET** NuGet πακέτο (`Aspose.BarCode`) – παρέχει την κλάση `BarCodeReader` που χρησιμοποιείται στο παράδειγμα.  
* Ένα αρχείο εικόνας που περιέχει ένα Macro‑PDF417 barcode (π.χ., `MacroPdf417.png`).  

Μπορείτε να εγκαταστήσετε το NuGet πακέτο με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

## Πώς να διαβάσετε barcode με BarCodeReader σε C#

Ο πυρήνας της λύσης βρίσκεται σε τέσσερα σύντομα βήματα. Κάθε βήμα είναι τυλιγμένο σε μπλοκ `using` για να εξασφαλιστεί η άμεση απελευθέρωση των μη διαχειριζόμενων πόρων.

### Βήμα 1: Αρχικοποίηση του `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Γιατί είναι σημαντικό:**  
Το `BarCodeReader` δέχεται διαδρομή αρχείου και ένα `DecodeType`. Η καθορισμένη τιμή `DecodeType.MacroPdf417` λέει στη βιβλιοθήκη να ψάχνει μόνο για σύμβολα Macro‑PDF417, βελτιώνοντας την ταχύτητα ανίχνευσης και μειώνοντας τα ψευδώς θετικά αποτελέσματα.

### Βήμα 2: Ανάγνωση όλων των barcode που υπάρχουν στην εικόνα

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Γιατί είναι σημαντικό:**  
Η μέθοδος `ReadBarCodes()` επιστρέφει έναν πίνακα που μπορεί να περιέχει ένα ή πολλά αντικείμενα `BarCodeResult`. Εδώ φαίνεται η δυνατότητα **read multiple barcodes** – δεν χρειάζεται ξεχωριστός βρόχος για κάθε πιθανό barcode.

### Βήμα 3: Εμφάνιση βασικών λεπτομερειών barcode

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Γιατί είναι σημαντικό:**  
Το `CodeTypeName` σας λέει ποια συμβολική μορφή εντοπίστηκε (π.χ., “MacroPDF417”), ενώ το `CodeText` περιέχει το αποκωδικοποιημένο περιεχόμενο. Αυτά τα δύο πεδία είναι τα πιο συχνά χρησιμοποιούμενα σε επόμενη λογική.

### Βήμα 4: Ανάκτηση και εμφάνιση μεταδεδομένων ειδικών για Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Γιατί είναι σημαντικό:**  
Το Macro‑PDF417 επεκτείνει τη συνηθισμένη μορφή PDF417 με μεταδεδομένα επιπέδου εγγράφου. Η πρόσβαση στην ιδιότητα `Extended.Pdf417` σας δίνει όλα όσα χρειάζεστε για να ανασυνθέσετε το αρχικό αρχείο, να επικυρώσετε την ακεραιότητα ή να κατευθύνετε τα δεδομένα στον κατάλληλο παραλήπτη.

### Πλήρες εκτελέσιμο πρόγραμμα

Παρακάτω υπάρχει μια αυτόνομη εφαρμογή κονσόλας που συνδυάζει και τα τέσσερα βήματα. Αντιγράψτε τον κώδικα σε ένα νέο αρχείο `.cs`, προσαρμόστε το `imagePath` και τρέξτε `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Αναμενόμενη έξοδος στην κονσόλα

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Αν η εικόνα περιέχει περισσότερα από ένα σύμβολα Macro‑PDF417, το πρόγραμμα εκτυπώνει ξεχωριστό μπλοκ για κάθε barcode, επιδεικνύοντας τη δυνατότητα **read multiple barcodes** χωρίς επιπλέον κώδικα.

## Διαχείριση κοινών περιπτώσεων άκρων

| Κατάσταση | Τι πρέπει να κάνετε | Λόγος |
|-----------|--------------------|-------|
| **File not found** | Τυλίξτε τη δημιουργία του `BarCodeReader` σε μπλοκ `try/catch (FileNotFoundException)` και εμφανίστε ένα φιλικό μήνυμα. | Αποτρέπει το κλείσιμο της εφαρμογής και ενημερώνει τον χρήστη για το χαμένο αρχείο. |
| **No barcode detected** | Ελέγξτε `results.Length == 0` (όπως φαίνεται στο πλήρες πρόγραμμα) και χειριστείτε το ήρεμα. | Παρέχει σαφή ανατροφοδότηση όταν η εικόνα δεν περιέχει υποστηριζόμενη συμβολική μορφή. |
| **Different barcode type** | Αλλάξτε το `DecodeType.MacroPdf417` σε `DecodeType.AllSupportedTypes` ή σε άλλη συγκεκριμένη τιμή enum. | Επιτρέπει στον ίδιο κώδικα να λειτουργεί με QR, Code128, DataMatrix κ.λπ., διατηρώντας τη δυνατότητα **read multiple barcodes**. |
| **Large images** | Ορίστε `reader.AutoSize = true` ή μειώστε την κλίμακα της εικόνας πριν τη δώσετε στον αναγνώστη. | Βελτιώνει την απόδοση και μειώνει την πίεση μνήμης στο CLR. |
| **Thread‑safe usage** | Δημιουργήστε ξεχωριστό αντικείμενο `BarCodeReader` ανά νήμα· η κλάση δεν είναι thread‑safe. | Αποτρέπει συνθήκες αγώνα σε σκανέρ πολλαπλών νημάτων ή web services. |

## Pro tips για κώδικα παραγωγής

* **Dispose νωρίς:** Η δήλωση `using` εξασφαλίζει ότι οι εγγενείς πόροι (π.χ., buffers εικόνας) απελευθερώνονται άμεσα. Σε υπηρεσίες που τρέχουν συνεχώς, απελευθερώστε τον αναγνώστη μόλις ολοκληρωθεί η επεξεργασία κάθε εικόνας.  
* **Batch processing**


## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην δική σας υλοποίηση.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}