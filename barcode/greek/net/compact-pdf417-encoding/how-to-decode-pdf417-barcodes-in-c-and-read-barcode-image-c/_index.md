---
category: general
date: 2026-10-28
description: Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# γρήγορα. Μάθετε
  να διαβάζετε εικόνα γραμμωτού κώδικα σε C# χρησιμοποιώντας το Aspose.BarCode με
  ένα πλήρες, εκτελέσιμο παράδειγμα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: el
lastmod: 2026-10-28
og_description: Πώς να αποκωδικοποιήσετε γραμμικούς κώδικες PDF417 σε C# με το Aspose.BarCode.
  Αυτός ο οδηγός σας δείχνει πώς να διαβάσετε εικόνα γραμμικού κώδικα σε C# βήμα‑βήμα,
  με πλήρη κώδικα.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Πώς να αποκωδικοποιήσετε κωδικούς PDF417 σε C# – ανάγνωση εικόνας barcode
  – οδηγός C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Πώς να αποκωδικοποιήσετε κωδικούς PDF417 σε C# και να διαβάσετε εικόνα barcode
  σε C#
url: /el/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποκωδικοποιήσετε κωδικούς PDF417 σε C# και να διαβάσετε εικόνα barcode C#

Αν χρειάζεστε **how to decode pdf417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας παρέχει μια έτοιμη προς εκτέλεση λύση. Θα δείτε ακριβώς πώς να **read barcode image c#** χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode, να εξάγετε τα πεδία macro‑PDF417 και να τα εμφανίσετε στην κονσόλα.

Η αποκωδικοποίηση κωδικών PDF417 εμφανίζεται συχνά σε συστήματα logistics, έκδοσης εισιτηρίων και επαλήθευσης ταυτότητας. Στο τέλος αυτού του οδηγού θα μπορείτε να φορτώσετε οποιαδήποτε εικόνα που περιέχει έναν Macro PDF417 barcode, να την αποκωδικοποιήσετε και να έχετε πρόσβαση στις τιμές file ID, segment ID και segment count που είναι απαραίτητες για τη συναρμολόγηση εγγράφων πολλαπλών τμημάτων.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE C#)  
* Ένα πακέτο NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  
* Ένα αρχείο εικόνας που περιέχει έναν Macro PDF417 barcode (το παράδειγμα χρησιμοποιεί `ExtPDF417Meta.png`)

Μπορείτε να προσθέσετε το πακέτο NuGet με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Ρύθμιση του έργου και εισαγωγή namespaces

Δημιουργήστε ένα νέο console project και εισάγετε τα απαιτούμενα namespaces. Οι οδηγίες `using` σας δίνουν πρόσβαση στα `BarCodeReader`, `DecodeType` και στα αντικείμενα result‑extension.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Γιατί αυτό το βήμα είναι σημαντικό** – Η εισαγωγή των σωστών namespaces αποτρέπει σφάλματα κατά τη μεταγλώττιση και καθιστά διαθέσιμη τη διεπαφή API για τη συνακόλουθη λογική αποκωδικοποίησης.

## Βήμα 2: Καθορισμός της διαδρομής της εικόνας

Ορίστε τη πλήρη ή σχετική διαδρομή προς την εικόνα barcode. Η αποθήκευση της διαδρομής σε μια μεταβλητή κάνει τον κώδικα επαναχρησιμοποιήσιμο για διαφορετικές εικόνες.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Συμβουλή:** Χρησιμοποιήστε `Path.Combine` εάν δημιουργείτε τη διαδρομή από πολλαπλά μέρη· διαχειρίζεται τους διαχωριστές καταλόγου σε διαφορετικά λειτουργικά συστήματα.

## Βήμα 3: Δημιουργία ενός `BarCodeReader` διαμορφωμένου για αποκωδικοποίηση Macro PDF417

Δημιουργήστε ένα `BarCodeReader` με τη διαδρομή της εικόνας και τη σημαία `DecodeType.MacroPdf417`. Αυτό ενημερώνει τη βιβλιοθήκη να ψάχνει ειδικά για σύμβολα Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Γιατί αυτό το βήμα είναι σημαντικό** – Η επιλογή του κατάλληλου `DecodeType` βελτιώνει την απόδοση επειδή η μηχανή παραλείπει μορφές barcode που δεν σχετίζονται.

## Βήμα 4: Ανάγνωση όλων των barcode και εμφάνιση των macro πληροφοριών

Κάντε επανάληψη σε κάθε `BarCodeResult` που επιστρέφεται από το `reader.ReadBarCodes()`. Το αντικείμενο result περιέχει τόσο γενικά πεδία (`CodeTypeName`, `CodeText`) όσο και επεκτάσεις ειδικές για Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Τι κάνει κάθε γραμμή

| Line | Explanation |
|------|-------------|
| `result.CodeTypeName` | Ανθρώπινα αναγνώσιμο όνομα του ανιχνευμένου τύπου barcode (π.χ., “MacroPdf417”). |
| `result.CodeText` | Τα ακατέργαστα δεδομένα που κωδικοποιούνται στο barcode. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Αναγνωριστικό που συνδέει όλα τα τμήματα ενός εγγράφου macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Δείκτης του τρέχοντος τμήματος μέσα στο συνολικό έγγραφο. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Συνολικός αριθμός τμημάτων που αναμένονται για το έγγραφο. |

> **Pro tip:** Αποθηκεύστε τα macro πεδία σε μια βάση δεδομένων εάν χρειάζεται να επανασυνθέσετε το πλήρες έγγραφο αργότερα. Το `File ID` σας επιτρέπει να ομαδοποιήσετε τμήματα που ανήκουν στην ίδια πηγή.

## Βήμα 5: Εκτέλεση του προγράμματος και επαλήθευση της εξόδου

Δομήστε και εκτελέστε την console εφαρμογή:

```bash
dotnet run
```

Η τυπική έξοδος της κονσόλας φαίνεται ως εξής:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Εάν η εικόνα περιέχει πολλαπλά σύμβολα Macro PDF417, η επανάληψη εκτυπώνει καθένα διαδοχικά.

### Διαχείριση κοινών περιπτώσεων άκρων

| Situation | Recommended handling |
|-----------|----------------------|
| **Δεν βρέθηκε barcode** | Ελέγξτε `reader.ReadBarCodes().Any()` πριν από την επανάληψη και εμφανίστε ένα φιλικό μήνυμα. |
| **Κατεστραμμένη εικόνα** | Τυλίξτε τη δημιουργία του `BarCodeReader` σε ένα μπλοκ `try/catch` για `BarCodeException`. |
| **Πολλαπλές μορφές barcode** | Χρησιμοποιήστε `DecodeType.AllSupported` και φιλτράρετε τα αποτελέσματα με `result.CodeTypeName == "MacroPdf417"`. |
| **Μεγάλες εικόνες** | Μειώστε το μέγεθος της εικόνας πριν την αποκωδικοποίηση για βελτίωση της απόδοσης· η βιβλιοθήκη δέχεται αντικείμενο `Bitmap`. |

## Πλήρης κώδικας πηγής

Παρακάτω βρίσκεται το πλήρες, αυτόνομο πρόγραμμα. Αντιγράψτε το στο `Program.cs` ενός νέου console project και αντικαταστήστε το `YOUR_DIRECTORY/ExtPDF417Meta.png` με την πραγματική διαδρομή προς την εικόνα σας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Συμπέρασμα

Τώρα γνωρίζετε **how to decode pdf417** κωδικούς σε C# και πώς να **read barcode image c#** χρησιμοποιώντας το Aspose.BarCode. Ο οδηγός σας οδήγησε μέσω της ρύθμισης του έργου, της φόρτωσης της εικόνας, της διαμόρφωσης του αναγνώστη, της εξαγωγής αποτελεσμάτων και της διαχείρισης περιπτώσεων άκρων. Με αυτή τη βάση μπορείτε να ενσωματώσετε την αποκωδικοποίηση PDF417 σε συστήματα απογραφής, επαληθευτές εισιτηρίων ή οποιαδήποτε ροή εργασίας που βασίζεται σε macro‑κωδικοποιημένα δεδομένα.

### Επόμενα βήματα

* Εξερευνήστε άλλες μορφές barcode αλλάζοντας το `DecodeType` (π.χ., `DecodeType.QR`, `DecodeType.Code128`).  
* Συνδυάστε πολλαπλά αποκωδικοποιημένα τμήματα για την ανακατασκευή του αρχικού εγγράφου.  
* Χρησιμοποιήστε την κλάση `BarCodeGenerator` για να δημιουργήσετε δοκιμαστικά PDF417 barcodes άμεσα.  

Νιώστε ελεύθεροι να πειραματιστείτε με διαφορετικές πηγές εικόνας, να προσαρμόσετε την έξοδο της κονσόλας ή να ενσωματώσετε τη λογική αποκωδικοποίησης σε ένα web API για επεξεργασία σε πραγματικό χρόνο. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να αποκωδικοποιήσετε PDF417 σε C# με παράδειγμα barcode reader](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Πώς να δημιουργήσετε PDF417 barcodes σε C# με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Πώς να διαβάσετε barcode από εικόνα c# χρησιμοποιώντας Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}