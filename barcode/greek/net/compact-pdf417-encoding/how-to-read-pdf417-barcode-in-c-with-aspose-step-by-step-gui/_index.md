---
category: general
date: 2026-10-24
description: Μάθετε πώς να διαβάζετε γραμμωτό κώδικα PDF417 σε C# χρησιμοποιώντας
  το Aspose.BarCode. Αυτό το σεμινάριο καλύπτει την ανάγνωση εικόνας γραμμωτού κώδικα,
  την εξαγωγή πεδίων Macro PDF417 και τη διαχείριση κοινών σεναρίων.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: el
lastmod: 2026-10-24
og_description: Πώς να διαβάσετε το barcode PDF417 σε C# χρησιμοποιώντας το Aspose.BarCode.
  Ακολουθήστε αυτό το πλήρες σεμινάριο για να αποκωδικοποιήσετε εικόνες, να ανακτήσετε
  τα μεταδεδομένα Macro PDF417 και να αποφύγετε κοινά προβλήματα.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Πώς να διαβάσετε τον γραμμωτό κώδικα PDF417 σε C# με το Aspose – πλήρης
  οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Πώς να διαβάσετε τον κωδικό PDF417 σε C# με το Aspose – οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε το PDF417 barcode σε C# με Aspose – βήμα‑βήμα οδηγός

Αν χρειάζεστε **πώς να διαβάσετε το PDF417 barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να διαβάσετε το PDF417 barcode σε C# χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Είτε επεξεργάζεστε σαρωμένα έγγραφα, λήψεις από κινητό, είτε εικόνες που εισάγονται κατά παρτίδες, ο παρακάτω κώδικας αποκωδικοποιεί το barcode και εξάγει κάθε ιδιότητα Macro PDF417 που μπορεί να χρειαστείτε.

Η ανάγνωση μιας εικόνας barcode σε C# μπορεί να φαίνεται δύσκολη, ειδικά όταν το barcode περιέχει εκτεταμένα μεταδεδομένα. Αυτό το tutorial αφαιρεί τις εικασίες παρέχοντας ένα πλήρες, εκτελέσιμο παράδειγμα, εξηγώντας κάθε γραμμή και καλύπτοντας περιπτώσεις όπως ελλιπή τμήματα macro ή κατεστραμμένες εικόνες. Στο τέλος, θα μπορείτε να ενσωματώσετε την αποκωδικοποίηση PDF417 σε οποιοδήποτε έργο C# με σιγουριά.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET)  
* Άδεια ή δωρεάν αξιολόγηση του **Aspose.BarCode for .NET** – μπορείτε να αποκτήσετε προσωρινό κλειδί από την ιστοσελίδα της Aspose  
* Ένα αρχείο εικόνας που περιέχει ένα Macro PDF417 barcode (π.χ., `ExtPDF417Meta.png`)

> **Pro tip:** Αν θέλετε μόνο να πειραματιστείτε, η Aspose προσφέρει δοκιμαστική έκδοση 30 ημερών που περιλαμβάνει πλήρη λειτουργικότητα για ανάγνωση barcode.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Ανοίξτε το φάκελο του έργου σας σε τερματικό και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο προσθέτει το namespace `Aspose.BarCode.ReadRecognition`, το οποίο περιέχει την κλάση `BarCodeReader` που χρησιμοποιείται για την αποκωδικοποίηση εικόνων.

## Βήμα 2: Δημιουργία BarCodeReader για εικόνα PDF417

Ο κατασκευαστής `BarCodeReader` δέχεται δύο ορίσματα: τη διαδρομή του αρχείου εικόνας και το `DecodeType` που θέλετε να στοχεύσετε. Η χρήση του `DecodeType.MacroPdf417` λέει στην Aspose να ψάξει για σύμβολα Macro PDF417 και να γεμίσει αυτόματα τις εκτεταμένες ιδιότητες.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Γιατί να χρησιμοποιήσετε `DecodeType.MacroPdf417`;

* **Macro PDF417** αποθηκεύει πρόσθετα πεδία (αναγνωριστικό αρχείου, αριθμός τμημάτων, χρονικές σήμανσεις κ.λπ.) που δεν υπάρχουν στο τυπικό PDF417.  
* Η ιδιότητα `Extended` του `BarCodeResult` γεμίζει μόνο όταν ζητήσετε τον τύπο macro, εξοικονομώντας σας ένα ξεχωριστό βήμα ανάλυσης.

## Βήμα 3: Επανάληψη σε όλα τα ανιχνευμένα barcodes

Μια μόνο εικόνα μπορεί να περιέχει πολλαπλά σύμβολα PDF417 (για παράδειγμα, όταν ένα έγγραφο χωρίζεται σε πολλές σελίδες). Η μέθοδος `ReadBarCodes()` επιστρέφει ένα `IEnumerable<BarCodeResult>` το οποίο μπορείτε να διασχίσετε.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Αν η εικόνα δεν περιέχει κανένα barcode, ο βρόχος απλώς δεν εκτελείται και το πρόγραμμα τερματίζει ήρεμα. Αυτή η συμπεριφορά κάνει τον κώδικα ασφαλή για επεξεργασία παρτίδων όπου κάποια αρχεία μπορεί να μην έχουν barcode.

## Βήμα 4: Εξαγωγή των εκτεταμένων ιδιοτήτων Macro PDF417

Η ιδιότητα `Extended.Pdf417` ομαδοποιεί όλα τα πεδία ειδικά για macro. Κάθε πεδίο αντιστοιχεί άμεσα στην προδιαγραφή PDF417, ώστε να μπορείτε να τα αποθηκεύσετε σε βάση δεδομένων, να τα καταγράψετε ή να τα χρησιμοποιήσετε για περαιτέρω επικύρωση.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Τι σημαίνει κάθε ιδιότητα

| Ιδιότητα | Περιγραφή |
|----------|-----------|
| **MacroPdf417FileID** | Μοναδικό αναγνωριστικό για ολόκληρο το πολυ‑τμηματικό έγγραφο. |
| **MacroPdf417SegmentID** | Δείκτης του τρέχοντος τμήματος (ξεκινώντας από 0). |
| **MacroPdf417SegmentsCount** | Συνολικός αριθμός τμημάτων που ανήκουν στο αρχείο. |
| **MacroPdf417FileName** | Προαιρετικό όνομα αρχείου ενσωματωμένο στο barcode. |
| **MacroPdf417Checksum** | CRC‑16 checksum για το μπλοκ δεδομένων macro. |
| **MacroPdf417FileSize** | Αρχικό μέγεθος αρχείου σε bytes. |
| **MacroPdf417TimeStamp** | Χρονική σήμανση όταν δημιουργήθηκε το macro barcode. |
| **MacroPdf417Addressee** | Προοριζόμενος παραλήπτης του εγγράφου. |
| **MacroPdf417Sender** | Αποστολέας του εγγράφου. |
| **MacroPdf417Terminator** | Σημαία τερματισμού που υποδεικνύει το τέλος της ακολουθίας macro. |

Αυτά τα πεδία είναι ιδιαίτερα χρήσιμα όταν ανασυνθέτετε ένα μεγάλο PDF ή εικόνα που είχε χωριστεί σε πολλά σύμβολα PDF417 για εκτύπωση σε μέσο χαμηλής ανάλυσης.

## Βήμα 5: Διαχείριση κοινών περιπτώσεων

### Ελλιπή πεδία macro

Μερικές φορές ένα PDF417 barcode δημιουργείται χωρίς τα προαιρετικά πεδία macro. Η πρόσβαση σε μια ελλιπή ιδιότητα επιστρέφει `null` ή `0`. Προστατέψτε τον κώδικά σας αν σκοπεύετε να αποθηκεύσετε τις τιμές:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Κατεστραμμένες ή χαμηλής ποιότητας εικόνες

Αν η εικόνα είναι θολή, μπορείτε να βελτιώσετε την ανίχνευση ενεργοποιώντας τις επιλογές ποιότητας του `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Αυτές οι ρυθμίσεις είναι προαιρετικές αλλά μπορούν να αυξήσουν δραματικά το ποσοστό επιτυχίας για σαρωμένα έγγραφα.

### Πολλαπλές μορφές barcode σε μία εικόνα

Αν υποψιάζεστε ότι μπορεί να υπάρχουν και άλλοι τύποι barcode, χρησιμοποιήστε το `DecodeType.AllSupported` και φιλτράρετε τα αποτελέσματα:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Πλήρες εκτελέσιμο παράδειγμα

Αντιγράψτε το παρακάτω πρόγραμμα σε ένα νέο έργο console (`dotnet new console`) και τρέξτε το. Αντικαταστήστε τη μεταβλητή `imagePath` με τη θέση της δικής σας εικόνας Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Αναμενόμενη έξοδος** (οι τιμές θα διαφέρουν ανάλογα με την εικόνα σας):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Αν η εικόνα δεν περιέχει σύμβολα Macro PDF417, το πρόγραμμα δεν γράφει τίποτα και τερματίζει σιωπηλά—ιδανικό για εργασίες batch που επεξεργάζονται πολλά αρχεία.

## Συχνές ερωτήσεις

**Q: Μπορώ να διαβάσω ένα τυπικό PDF417 (μη‑macro) με τον ίδιο κώδικα;**  
A: Ναι. Αλλάξτε το `DecodeType.MacroPdf417` σε `DecodeType.Pdf417`. Η ιδιότητα `Extended` θα είναι κενή, αλλά τα `CodeText` και `CodeTypeName` παραμένουν διαθέσιμα.

**Q: Υποστηρίζει το Aspose.BarCode ανάγνωση από ροή (stream) αντί για διαδρομή αρχείου;**  
A: Απόλυτα. Χρησιμοποιήστε την υπερφόρτωση `new BarCodeReader(Stream, DecodeType)` και περάστε ένα `FileStream` ή `MemoryStream`. Αυτό είναι χρήσιμο όταν η εικόνα προέρχεται από web API.

**Q: Πώς μπορώ να επικυρώσω το checksum;**  
A: Η ιδιότητα `MacroPdf417Checksum` περιέχει την ακατέργαστη τιμή CRC‑16. Μπορείτε να επανυπολογίσετε το checksum στο ανασυγκροτημένο αρχείο και να το συγκρίνετε για να διασφαλίσετε την ακεραιότητα των δεδομένων.

## Επόμενα βήματα και συναφή θέματα

* **Γράψτε PDF417 barcodes** – εξερευνήστε το `BarCodeGenerator` για δημιουργία macro barcodes για δοκιμές.  
* **Συνδυάστε πολλαπλά τμήματα** – μετά την ανάγνωση όλων των τμημάτων, ταξινομήστε τα κατά `MacroPdf417SegmentID` και συνενώστε το `CodeText` για να ανασυνθέσετε το αρχικό payload.  
* **Βελτιστοποίηση απόδοσης** – για σενάρια υψηλής διακίνησης, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarCodeReader` σε πολλές εικόνες και

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Πώς να δημιουργήσετε macro PDF417 barcode σε C# χρησιμοποιώντας Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Ανάγνωση barcode από εικόνα C# – πλήρης οδηγός με Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}