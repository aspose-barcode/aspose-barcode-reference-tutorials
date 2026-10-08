---
category: general
date: 2026-09-22
description: Μάθετε πώς να διαβάζετε κωδικούς PDF417 σε C# με ένα πλήρες παράδειγμα
  αναγνώστη κωδικών. Αυτό το σεμινάριο σας δείχνει πώς να διαβάζετε εικόνα κωδικού
  σε C# γρήγορα και αξιόπιστα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: el
lastmod: 2026-09-22
og_description: Πώς να διαβάσετε κωδικούς PDF417 σε C# χρησιμοποιώντας ένα σύντομο
  παράδειγμα αναγνώστη barcode. Ακολουθήστε τον οδηγό για να αποκωδικοποιήσετε εικόνες
  Macro PDF417 και να εξάγετε μεταδεδομένα.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Πώς να διαβάσετε κωδικούς PDF417 σε C# – πλήρες παράδειγμα αναγνώστη barcode
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Πώς να διαβάζετε κωδικούς PDF417 σε C# – πλήρης οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε κωδικούς PDF417 σε C# – πλήρης οδηγός βήμα‑βήμα

Αν χρειάζεστε **how to read pdf417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει τον ακριβή κώδικα και τη λογική που χρειάζεστε. Μέχρι το τέλος των πρώτων δύο προτάσεων θα γνωρίζετε πώς να διαβάσετε εικόνα barcode σε C# χρησιμοποιώντας την δημοφιλή κλάση `BarCodeReader`, και θα έχετε ένα έτοιμο παράδειγμα που εξάγει κάθε κομμάτι των μεταδεδομένων Macro PDF417.

Η ανάγνωση κωδικών PDF417 είναι μια κοινή απαίτηση όταν επεξεργάζεστε ετικέτες αποστολής, κάρτες επιβίβασης ή ασφαλή έγγραφα. Αυτό το οδηγός καλύπτει τα πάντα, από τη ρύθμιση του αναγνώστη μέχρι τη διαχείριση ειδικών περιπτώσεων, ώστε να μπορείτε να ενσωματώσετε τη σάρωση barcode με σιγουριά.

## Τι θα πετύχετε

- Αποκωδικοποίηση ενός αρχείου εικόνας Macro PDF417.
- Εκτύπωση βασικών πληροφοριών barcode (τύπος και κείμενο).
- Πρόσβαση σε όλα τα εκτεταμένα πεδία Macro PDF417 όπως το file ID, ο αριθμός τμημάτων και η χρονική σήμανση.
- Κατανόηση κοινών παγίδων κατά την εργασία με κωδικούς PDF417 πολλαπλών τμημάτων.

**Προαπαιτούμενα**

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+).
- Μια αναφορά στο barcode SDK που παρέχει `BarCodeReader`, `DecodeType` και `BarCodeResult` (π.χ., Aspose.BarCode, Dynamsoft ή οποιαδήποτε βιβλιοθήκη που εκθέτει το ίδιο API).
- Ένα αρχείο εικόνας (`ExtPDF417Meta.png`) που περιέχει ένα Macro PDF417 barcode.

> **Συμβουλή:** Τοποθετήστε την εικόνα σε φάκελο σχετικό με τη ρίζα του έργου σας και ορίστε την ιδιότητα **Copy to Output Directory** σε *Copy if newer* ώστε η διαδρομή να λειτουργεί κατά το debugging.

![How to read PDF417 barcode using C#](https://example.com/placeholder-image.png)

## Πώς να διαβάσετε κωδικό PDF417 σε C# – ο πλήρης κώδικας

Παρακάτω είναι ένα αυτόνομο πρόγραμμα που μπορείτε να επικολλήσετε σε μια εφαρμογή κονσόλας. Δημιουργεί έναν barcode reader, επαναλαμβάνει κάθε αποκωδικοποιημένο αποτέλεσμα και εκτυπώνει τόσο τα τυπικά όσο και τα εκτεταμένα πεδία Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### Γιατί κάθε βήμα είναι σημαντικό

1. **Δημιουργία του αναγνώστη με `DecodeType.MacroPdf417`** – Το Macro PDF417 είναι μια ειδική παραλλαγή που μπορεί να μεταφέρει μεταδεδομένα επιπέδου αρχείου. Η καθορισμένη decode type εξασφαλίζει ότι το SDK αναλύει αυτά τα επιπλέον πεδία αντί να αντιμετωπίζει τον κώδικα ως απλό PDF417.
2. **Επανάληψη με `ReadBarCodes()`** – Μια εικόνα μπορεί να περιέχει περισσότερα από ένα barcode (π.χ., ένα QR code δίπλα σε PDF417). Η βρόχος εγγυάται ότι θα συλλάβετε κάθε αποτέλεσμα.
3. **Εκτύπωση `CodeTypeName` και `CodeText`** – Αυτές είναι οι πιο συχνά χρησιμοποιούμενες ιδιότητες· παρέχουν το όνομα της συμβολικής μορφής και το ανθρώπινα αναγνώσιμο payload.
4. **Πρόσβαση στο `Extended.Pdf417`** – Το αντικείμενο `Extended` εμφανίζεται μόνο για decode types σχετιζόμενα με PDF417. Κάθε ιδιότητα αντιστοιχεί απευθείας στην προδιαγραφή Macro PDF417, επιτρέποντάς σας να ανακατασκευάσετε το αρχικό αρχείο ή να επικυρώσετε τη σειρά των τμημάτων.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

### Ανάγνωση μη‑macro PDF417 barcode

Αν οι πηγαίες εικόνες σας περιέχουν κανονικούς κωδικούς PDF417 (χωρίς macro μεταδεδομένα), αντικαταστήστε το `DecodeType.MacroPdf417` με `DecodeType.Pdf417`. Το υπόλοιπο του κώδικα παραμένει ίδιο, αλλά το τμήμα `Extended.Pdf417` θα είναι κενό επειδή αυτά τα πεδία απλώς δεν υπάρχουν.

### Διαχείριση PDF417 πολλαπλών τμημάτων

Macro PDF417 μπορεί να χωρίσει ένα μεγάλο έγγραφο σε πολλά τμήματα barcode. Για να επανασυνθέσετε το αρχικό αρχείο πρέπει:

1. Συλλέξτε το `Pdf417MacroSegmentID` κάθε τμήματος.
2. Ταξινομήστε τα τμήματα κατά το ID τους.
3. Επαληθεύστε ότι το `Pdf417MacroSegmentsCount` ταιριάζει με τον αριθμό των ληφθέντων τμημάτων.
4. Συνενώστε το `CodeText` κάθε τμήματος με τη σωστή σειρά.
5. Προαιρετικά επικυρώστε το `Pdf417MacroChecksum`.

Παρακάτω είναι ένα σύντομο απόσπασμα που δείχνει τη λογική επανασυναρμολόγησης:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Αντιμετώπιση κατεστραμμένων εικόνων

- **Χαμηλή αντίθεση** – Αυξήστε την προεπεξεργασία της εικόνας (π.χ., εξίσωση ιστογράμματος) πριν τη μεταβιβάσετε στο `BarCodeReader`.
- **Περιστροφή** – Χρησιμοποιήστε `barcodeReader.SetRotateAngle(90)` ή ενεργοποιήστε την αυτόματη περιστροφή εάν το SDK το υποστηρίζει.
- **Μερικές σάρωσες** – Βεβαιωθείτε ότι η ανάλυση της εικόνας είναι τουλάχιστον 300 dpi· διαφορετικά το SDK μπορεί να χάσει μικρά τμήματα.

## Παράδειγμα c# barcode reader – βέλτιστες πρακτικές

| Πρακτική | Αιτία |
|----------|--------|
| **Κλείσιμο του αναγνώστη με `using`** | Εγγυάται ότι οι εγγενείς πόροι απελευθερώνονται άμεσα, αποτρέποντας διαρροές μνήμης. |
| **Επικύρωση ότι `result.Extended` δεν είναι null** | Ορισμένα SDK επιστρέφουν `null` για μη‑macro κωδικούς· ο έλεγχος αποτρέπει ένα `NullReferenceException`. |
| **Καταγραφή του `Pdf417MacroFileID`** | Αυτό το αναγνωριστικό είναι μοναδικό ανά αρχείο και χρήσιμο για ελεγκτικά ίχνη. |
| **Τυλίξτε την αποκωδικοποίηση σε try/catch** | Σφάλματα I/O (απουσία αρχείου) ή μη υποστηριζόμενες μορφές προκαλούν εξαιρέσεις που πρέπει να αντιμετωπίζονται με χάρη. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Αναμενόμενη έξοδος

Αν εκτελέσετε το πλήρες πρόγραμμα με ένα σωστά μορφοποιημένο `ExtPDF417Meta.png`, θα εμφανίσει έξοδο παρόμοια με:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Αν η εικόνα περιέχει πολλαπλά τμήματα, η βρόχος θα εκτυπώσει τα μεταδεδομένα κάθε τμήματος διαδοχικά.

## Συμπέρασμα

Τώρα γνωρίζετε **how to read pdf417** barcodes σε C# και έχετε ένα **c# barcode reader example** που εξάγει κάθε πεδίο Macro PDF417. Η λύση καλύπτει βασική αποκωδικοποίηση, εξαγωγή μεταδεδομένων, επανασυναρμολόγηση πολλαπλών τμημάτων και διαχείριση σφαλμάτων, παρέχοντάς σας μια έτοιμη για παραγωγή βάση για οποιαδήποτε ροή επεξεργασίας εγγράφων.

### Επόμενα βήματα

- Εξερευνήστε τεχνικές **read barcode image C#** για άλλες συμβολές (QR, DataMatrix) χρησιμοποιώντας το ίδιο API `BarCodeReader`.
- Ενσωματώστε τον αποκωδικοποιητή barcode σε μια υπηρεσία ASP.NET Core για επεξεργασία ανεβάσματος σε πραγματικό χρόνο.
- Δοκιμάστε βιβλιοθήκες προεπεξεργασίας εικόνας (π.χ., `OpenCvSharp`) για να αυξήσετε το ποσοστό επιτυχίας σε σάρωση χαμηλής ποιότητας.

Καλό κώδικα, και μη διστάσετε να προσαρμόσετε το παράδειγμα ώστε να ταιριάζει στην ειδική σας περίπτωση!

## Τι Θα Πρέπει Να Μάθετε Στη Σειρά;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να Αποθηκεύσετε Barcode σε C# – Δημιουργία PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Πώς να Διαβάσετε PDF417 σε C# – Πλήρης Οδηγός Βήμα‑Βήμα](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Πώς να Ορίσετε Επίπεδο Σφάλματος σε PDF417 Barcode – Πλήρης Οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}