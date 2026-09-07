---
category: general
date: 2026-09-07
description: Μάθετε πώς να αποκωδικοποιείτε τους κωδικούς PDF417 σε C# χρησιμοποιώντας
  το BarCodeReader. Αυτός ο οδηγός βήμα‑βήμα εξηγεί επίσης πώς να διαβάζετε τα δεδομένα
  PDF417 αποδοτικά.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: el
lastmod: 2026-09-07
og_description: Πώς να αποκωδικοποιήσετε τους κώδικες PDF417 σε C# χρησιμοποιώντας
  το BarCodeReader. Ακολουθήστε αυτό το σεμινάριο για να μάθετε πώς να διαβάζετε δεδομένα
  PDF417 και να εξάγετε τα πεδία MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Πώς να αποκωδικοποιήσετε τους κωδικούς PDF417 σε C# – πλήρης οδηγός
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# με το BarCodeReader
url: /el/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# με το BarCodeReader

Αν χρειάζεστε **πώς να αποκωδικοποιήσετε PDF417** γραμμωτούς κώδικες σε μια εφαρμογή .NET, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα στη διαδικασία. Θα ανακαλύψετε επίσης **πώς να διαβάσετε PDF417** δεδομένα όπως τα αναγνωριστικά αρχείου και τμήματος MacroPdf417, όλα με λίγες γραμμές C#.

Η αποκωδικοποίηση PDF417 είναι συχνή όταν εργάζεστε με εισιτήρια μεταφοράς, άδειες οδήγησης ή ετικέτες αποστολής. Στο τέλος αυτού του σεμιναρίου θα έχετε ένα εκτελέσιμο πρόγραμμα κονσόλας που εκτυπώνει κάθε πεδίο MacroPdf417 που εκτίθεται από το SDK GroupDocs.Barcode.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο (ο κώδικας μεταγλωττίζεται με .NET Core και .NET Framework)
* Visual Studio 2022 ή οποιοδήποτε IDE που υποστηρίζει C#
* Το πακέτο NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Ένα αρχείο εικόνας που περιέχει έναν γραμμωτό κώδικα Macro PDF417 (π.χ., `ExtPDF417Meta.png`)

> **Συμβουλή επαγγελματία:** Εγκαταστήστε το πακέτο μέσω του CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C#

Οι παρακάτω ενότητες χωρίζουν τη λύση σε λογικά βήματα. Κάθε βήμα περιλαμβάνει τον ακριβή κώδικα που χρειάζεστε και μια σύντομη εξήγηση του γιατί είναι σημαντικό.

### Βήμα 1: Προετοιμασία του έργου και εισαγωγή namespaces

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Γιατί;*  
`GroupDocs.Barcode` παρέχει την κλάση `BarCodeReader`, ενώ το `GroupDocs.Barcode.Common` περιέχει την απαραίτητη αρίθμηση `DecodeType` για την αποκωδικοποίηση PDF417.

### Βήμα 2: Ορισμός διαδρομής εικόνας

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Γιατί;*  
Ο αναγνώστης λειτουργεί με οποιαδήποτε μορφή εικόνας που υποστηρίζεται από το .NET (`.png`, `.jpg`, `.bmp`). Η παροχή της σωστής διαδρομής εξασφαλίζει ότι το SDK μπορεί να εντοπίσει το αρχείο.

### Βήμα 3: Αρχικοποίηση του αναγνώστη γραμμωτού κώδικα για αποκωδικοποίηση MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Γιατί;*  
`DecodeType.MacroPdf417` ενημερώνει το SDK να ψάξει για τη διευρυμένη μορφή Macro PDF417, η οποία μεταφέρει πρόσθετα μεταδεδομένα όπως τα αναγνωριστικά αρχείου και τμήματος. Η χρήση της δήλωσης `using` εγγυάται ότι οι μη διαχειριζόμενοι πόροι απελευθερώνονται άμεσα.

### Βήμα 4: Ανάγνωση όλων των γραμμωτών κωδίκων που βρέθηκαν στην εικόνα

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Γιατί;*  
Μια εικόνα μπορεί να περιέχει πολλαπλούς γραμμωτούς κώδικες. Η μέθοδος `ReadBarCodes()` επιστρέφει μια συλλογή, επιτρέποντάς σας να επεξεργαστείτε κάθε έναν ξεχωριστά.

### Βήμα 5: Ανάκτηση και εμφάνιση συγκεκριμένων δεδομένων Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Γιατί;*  
Το αντικείμενο `Extended.Pdf417` εκθέτει όλα τα πεδία Macro PDF417 που ορίζονται από την προδιαγραφή. Η εκτύπωσή τους σας επιτρέπει να επαληθεύσετε ότι η διαδικασία αποκωδικοποίησης πέτυχε και σας παρέχει τα δεδομένα που χρειάζεστε για επεξεργασία σε επόμενα στάδια.

### Πλήρες εκτελέσιμο παράδειγμα

Συνδυάστε τα αποσπάσματα παραπάνω σε ένα ενιαίο αρχείο `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Αναμενόμενη έξοδος κονσόλας** (οι τιμές θα διαφέρουν ανάλογα με το περιεχόμενο του γραμμωτού κώδικα):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Εάν η εικόνα δεν περιέχει γραμμωτό κώδικα Macro PDF417, η συλλογή `ReadBarCodes()` θα είναι κενή και δεν θα εκτυπωθεί τίποτα.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

| Κατάσταση | Πώς να προσαρμόσετε τον κώδικα |
|-----------|------------------------------|
| **Standard (μη‑macro) PDF417** | Αλλάξτε το `DecodeType.MacroPdf417` σε `DecodeType.Pdf417`. Το αντικείμενο `Extended.Pdf417` θα είναι `null`, επομένως προστατέψτε τον κώδικα από αναφορές σε null. |
| **Multiple images** | Τυλίξτε την αρχικοποίηση του αναγνώστη μέσα σε βρόχο `foreach (var path in imagePaths)`. |
| **Large images** | Ορίστε `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` για να περιορίσετε τη χρήση μνήμης. |
| **Performance‑critical batch** | Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarCodeReader` με `reader.SetImage(path)` αντί να δημιουργείτε νέο αντικείμενο για κάθε αρχείο. |

## Λίστα ελέγχου αντιμετώπισης προβλημάτων

* **Καμία έξοδος:** Επαληθεύστε ότι το `imagePath` δείχνει σε ένα έγκυρο αρχείο και ότι η εικόνα περιέχει πραγματικά έναν γραμμωτό κώδικα PDF417. |
* **Null `Extended.Pdf417`:** Πιθανότατα χρησιμοποιήσατε `DecodeType.Pdf417` αντί για `MacroPdf417`. |
* **Exception `FileNotFoundException`:** Βεβαιωθείτε ότι ο τρέχων φάκελος ταιριάζει με τη διαδρομή ή χρησιμοποιήστε απόλυτη διαδρομή. |
* **Low confidence score:** Αυξήστε την ποιότητα της εικόνας ή προσαρμόστε τις ρυθμίσεις `reader.Options.Quality`. |

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να αποκωδικοποιήσετε PDF417** γραμμωτούς κώδικες σε C# και **πώς να διαβάσετε μεταδεδομένα PDF417** όπως τα αναγνωριστικά αρχείου Macro, τα αναγνωριστικά τμημάτων και τις χρονικές σφραγίδες. Το πλήρες παράδειγμα δείχνει την αρχικοποίηση του `BarCodeReader`, την επιλογή του σωστού τύπου αποκωδικοποίησης, την επανάληψη στα αποτελέσματα και την εξαγωγή κάθε διαθέσιμου πεδίου MacroPdf417.

Από εδώ μπορείτε να:

* Ενσωματώσετε τα εξαγόμενα δεδομένα σε σύστημα logistics ή επικύρωσης εισιτηρίων.
* Επεκτείνετε την εφαρμογή κονσόλας ώστε να γράφει τα αποτελέσματα σε βάση δεδομένων ή αρχείο JSON.
* Εξερευνήσετε άλλες μορφές γραμμωτών κωδίκων που υποστηρίζει το GroupDocs.Barcode (QR, DataMatrix, Code128 κ.λπ.) αλλάζοντας την αρίθμηση `DecodeType`.

Καλή προγραμματιστική δουλειά, και μη διστάσετε να πειραματιστείτε με διαφορετικές εικόνες και ρυθμίσεις γραμμωτών κωδίκων για να κατακτήσετε την αποκωδικοποίηση PDF417 στα .NET έργα σας!

## Τι Θα Μάθετε Στη Σειρά;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετικούς τομείς που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να Διαβάσετε PDF417 σε C# – Πλήρης Οδηγός Βήμα‑Βήμα](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Πώς να Διαβάσετε PDF417 σε C# – Πλήρες Παράδειγμα Barcode Reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Πώς να Δημιουργήσετε Γραμμωτό Κώδικα PDF417 – Πλήρης Οδηγός Προγραμματισμού](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}