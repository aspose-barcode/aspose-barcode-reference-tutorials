---
category: general
date: 2026-07-21
description: Πώς να διαβάσετε τον κωδικό PDF417 σε C# χρησιμοποιώντας ένα σύντομο
  παράδειγμα αναγνώστη barcode. Μάθετε γρήγορα πώς να διαβάζετε το barcode από εικόνα
  με βήμα‑βήμα κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: el
lastmod: 2026-07-21
og_description: Πώς να διαβάσετε τον κώδικα PDF417 σε C# με ένα πρακτικό παράδειγμα.
  Ανακαλύψτε πώς να διαβάσετε τον κώδικα από εικόνα και να ενσωματώσετε αμέσως το
  παράδειγμα αναγνώστη κώδικα σε C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Πώς να διαβάσετε PDF417 σε C# – Πλήρης οδηγός ανάγνωσης barcode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα ανάγνωσης barcode
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαβάσετε PDF417 σε C# – Πλήρες Παράδειγμα Αναγνώστη Barcode

Έχετε αναρωτηθεί ποτέ **πώς να διαβάσετε PDF417** σε ένα .NET project χωρίς να ψάχνετε ατελείωτη τεκμηρίωση; Δεν είστε οι μόνοι. Είτε σαρώνετε άδειες οδήγησης, boarding passes, είτε προσαρμοσμένες ετικέτες αποθέματος, η αξιόπιστη εξαγωγή αυτών των δεδομένων είναι μια πραγματική ανάγκη.  

Σε αυτόν τον οδηγό θα περάσουμε από ένα **c# barcode reader example** που εξάγει κάθε κομμάτι των Macro PDF417 μεταδεδομένων από ένα μόνο αρχείο εικόνας. Στο τέλος θα έχετε μια έτοιμη για εκτέλεση console εφαρμογή που **διαβάζει barcode από εικόνα** και εκτυπώνει όλα τα εκτεταμένα πεδία που μπορεί να χρειαστείτε.

## Τι Θα Χρειαστείτε

- .NET 6.0 SDK ή νεότερο (μπορείτε επίσης να στοχεύσετε .NET Framework 4.7+ – ο κώδικας λειτουργεί το ίδιο)
- Visual Studio 2022, VS Code, ή οποιονδήποτε επεξεργαστή C# προτιμάτε
- Το **Aspose.BarCode for .NET** NuGet πακέτο (η κλάση `BarCodeReader` προέρχεται από αυτή τη βιβλιοθήκη)
- Ένα αρχείο εικόνας που περιέχει ένα Macro PDF417 barcode (για την επίδειξη θα χρησιμοποιήσουμε το `ExtPDF417Meta.png`)

> **Συμβουλή επαγγελματία:** Αν δεν έχετε κάποιο δείγμα PDF417, η Aspose παρέχει μερικές δοκιμαστικές εικόνες στο GitHub repo τους – απλώς κατεβάστε μία και τοποθετήστε τη στον φάκελο του project σας.

## Βήμα 1: Εγκατάσταση της Βιβλιοθήκης Barcode

Ανοίξτε ένα τερματικό στον φάκελο του project και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο προσθέτει τις κλάσεις `BarCodeReader`, `DecodeType` και την ιδιότητα `Extended` που θα χρειαστούμε αργότερα. Δεν απαιτείται επιπλέον διαμόρφωση· η βιβλιοθήκη λειτουργεί αμέσως για τις περισσότερες μορφές εικόνας (PNG, JPEG, BMP κ.λπ.).

## Βήμα 2: Δημιουργία Μινιμαλ Console Εφαρμογής

Δημιουργήστε ένα νέο console project αν δεν το έχετε κάνει ήδη:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Αντικαταστήστε το παραγόμενο `Program.cs` με τον παρακάτω κώδικα. Παρατηρήστε πώς κάθε τμήμα είναι σχολιασμένο ώστε να μπορείτε να ακολουθήσετε τη λογική ακόμη και αν είστε νέοι στην επεξεργασία barcode.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Γιατί Αυτό Λειτουργεί

- **`DecodeType.MacroPdf417`** λέει στον αναγνώστη να περιμένει τη μορφή Macro PDF417, η οποία μεταφέρει επιπλέον μεταδεδομένα (ID αρχείου, αριθμός τμημάτων, χρονικές σφραγίδες κ.λπ.).
- Το αντικείμενο **`Extended.Pdf417`** γεμίζει μόνο για Macro PDF417 barcodes, επομένως η πρόσβαση σε αυτές τις ιδιότητες είναι ασφαλής μετά την κλήση `ReadBarCodes()`.
- Η χρήση ενός **`using`** block εγγυάται ότι οι χειριστές αρχείων απελευθερώνονται, αποτρέποντας προβλήματα κλειδώματος αρχείων στα Windows.

## Βήμα 3: Εκτέλεση της Εφαρμογής

Συμπιέστε και εκτελέστε:

```bash
dotnet run
```

Αν η εικόνα περιέχει έγκυρο Macro PDF417 barcode, θα δείτε έξοδο παρόμοια με:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Αν δεν εμφανιστεί τίποτα, ελέγξτε ξανά τη διαδρομή της εικόνας και βεβαιωθείτε ότι το barcode είναι πράγματι μια παραλλαγή Macro PDF417. Τα κανονικά PDF417 (χωρίς την επέκταση macro) θα αποκωδικοποιηθούν επίσης, αλλά οι ιδιότητες `Extended` θα είναι κενές.

## Διαχείριση Ακραίων Περιπτώσεων

### Πολλαπλά Barcodes σε Μία Εικόνα

Μερικές φορές μια σάρωση περιέχει περισσότερα από ένα τμήματα PDF417 (σκεφτείτε ένα πολυ-σελίδες έγγραφο κωδικοποιημένο σε πολλά σύμβολα). Ο βρόχος `foreach` ήδη διαenumerates *όλα* τα ανιχνευμένα barcodes, οπότε δεν χρειάζεστε επιπλέον λογική – απλώς συλλέξτε τα τμήματα και επανενώστε τα αργότερα αν χρειαστεί.

### Απουσία Εκτεταμένων Δεδομένων

Δεν κάθε PDF417 μεταφέρει πληροφορίες macro. Σε αυτή την περίπτωση το `result.Extended.Pdf417` θα είναι δημιουργημένο αλλά τα πεδία του θα έχουν προεπιλεγμένες τιμές (μηδέν, κενό string ή `false`). Μπορείτε να το προστατέψετε ως εξής:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Συμβουλές Απόδοσης

- **Επεξεργασία παρτίδας:** Αν έχετε φάκελο με εικόνες, τυλίξτε τη δημιουργία του `BarCodeReader` μέσα σε βρόχο που επαναχρησιμοποιεί την ίδια παρουσία με `barcodeReader.SetImage(imagePath)`. Αυτό μειώνει το κόστος κατανομής μνήμης.
- **Παράλληλη εκτέλεση:** Για μεγάλα φορτία εργασίας, εξετάστε το `Parallel.ForEach` στη λίστα αρχείων, αλλά θυμηθείτε ότι ο αναγνώστης Aspose είναι thread‑safe μόνο όταν κάθε νήμα χρησιμοποιεί τη δική του παρουσία `BarCodeReader`.

## Πλήρης Λίστα Πηγαίου Κώδικα (Έτοιμη για Αντιγραφή‑Επικόλληση)

Παρακάτω βρίσκεται ολόκληρο το πρόγραμμα ξανά, έτοιμο να τοποθετηθεί στο `Program.cs`. Δεν χρειάζονται επιπλέον αρχεία εκτός από την εικόνα.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Σύνοψη: Πώς να Διαβάσετε PDF417 σε C# Γρήγορα

- Εγκαταστήστε **Aspose.BarCode** μέσω NuGet.
- Στοχεύστε έναν `BarCodeReader` στην εικόνα σας με `DecodeType.MacroPdf417`.
- Περάστε από το `ReadBarCodes()` και εξάγετε τόσο τα βασικά όσο και τα εκτεταμένα πεδία.
- Διαχειριστείτε την απουσία macro δεδομένων με χάρη και σκεφτείτε βελτιώσεις απόδοσης για μαζικές σαρώνες.

## Επόμενα Βήματα & Σχετικά Θέματα

- **Read barcode from image** χρησιμοποιώντας άλλες μορφές (QR, DataMatrix) – απλώς αλλάξτε το enum `DecodeType`.
- **Encode PDF417** με `BarCodeGenerator` αν χρειάζεται να δημιουργήσετε barcodes προγραμματιστικά.
- Εξερευνήστε **επίπεδα διόρθωσης σφαλμάτων** και πώς επηρεάζουν την αξιοπιστία της σάρωσης.
- Ενσωματώστε αυτή τη λογική σε ένα ASP.NET Core API για να εκθέσετε την ανάγνωση barcode ως web service.

Πειραματιστείτε ελεύθερα: αλλάξτε την εικόνα, παίξτε με τη σημαία `DecodeType`, ή τροφοδοτήστε τα macro δεδομένα σε μια βάση δεδομένων. Το βασικό μοτίβο παραμένει το ίδιο, και τώρα έχετε ένα ισχυρό **c# barcode reader example** στο toolbox σας.

Καλή προγραμματιστική δουλειά, και οι σαρώνες σας να είναι πάντα καθαρές!

## Τι Θα Πρέπει Να Μάθετε Στη Σειρά;

Οι παρακάτω οδηγοί καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}