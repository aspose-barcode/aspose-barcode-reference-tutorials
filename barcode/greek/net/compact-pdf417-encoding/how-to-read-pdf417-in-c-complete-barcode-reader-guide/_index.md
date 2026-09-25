---
category: general
date: 2026-08-09
description: Πώς να διαβάσετε PDF417 σε C# χρησιμοποιώντας το BarCodeReader. Μάθετε
  να διαβάζετε αρχεία PNG με barcode, να διαχειρίζεστε πολλαπλά barcode και να εξάγετε
  εκτεταμένα μεταδεδομένα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: el
lastmod: 2026-08-09
og_description: Πώς να διαβάσετε PDF417 σε C# με το Aspose.BarCode. Αυτό το σεμινάριο
  σας δείχνει πώς να διαβάζετε αρχεία PNG με barcode, να επεξεργάζεστε πολλαπλά barcode
  σε μία εικόνα και να ανακτάτε εκτεταμένα μεταδεδομένα PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Πώς να διαβάσετε PDF417 σε C# – οδηγός ανάγνωσης γραμμωτού κώδικα
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Πώς να διαβάσετε PDF417 σε C# – πλήρης οδηγός ανάγνωσης γραμμωτού κώδικα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε PDF417 σε C# – πλήρης οδηγός ανάγνωσης barcode

Αν χρειάζεστε **πώς να διαβάσετε PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας παρέχει μια έτοιμη προς εκτέλεση λύση. Θα δείτε πώς να διαβάσετε ένα barcode PNG, να επεξεργαστείτε πολλά barcodes στην ίδια εικόνα και να εξάγετε τα επεκταμένα πεδία PDF417 που κρύβουν πολλά scanners.

Η ανάγνωση barcode PDF417 είναι κοινή στη λογιστική, τα εισιτήρια και τη διαχείριση εγγράφων. Στο τέλος αυτού του tutorial μπορείτε να αποκωδικοποιήσετε μια εικόνα Macro PDF417, να εμφανίσετε κάθε αποτέλεσμα και να χρησιμοποιήσετε τις επιπλέον πληροφορίες (file ID, segment count, timestamps κ.λπ.) στη δική σας επιχειρηματική λογική.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
- Visual Studio 2022 ή οποιοδήποτε IDE C#
- **Aspose.BarCode for .NET** (δωρεάν δοκιμή ή αδειοδοτημένο πακέτο NuGet)
- Μια εικόνα PNG που περιέχει ένα barcode Macro PDF417 (το δείγμα αρχείου ονομάζεται `ExtPDF417Meta.png`)

> **Pro tip:** Εγκαταστήστε τη βιβλιοθήκη με την κονσόλα NuGet:  
> `dotnet add package Aspose.BarCode`

## Πώς να διαβάσετε PDF417 με BarCodeReader σε C#

Ο πυρήνας της λύσης είναι η κλάση `BarCodeReader`. Δέχεται μια διαδρομή εικόνας και ένα enum `DecodeType` που λέει στη μηχανή ποια συμβολική γραφή να αναζητήσει.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
}
```

### Γιατί λειτουργεί αυτό

- **`DecodeType.MacroPdf417`** λέει στον αναγνώστη να ψάξει για την παραλλαγή Macro PDF417, η οποία αποθηκεύει τα επιπλέον πεδία που βλέπετε στο βήμα 4.
- Το μπλοκ `using` απελευθερώνει αυτόματα τον αναγνώστη, απελευθερώνοντας τους χειριστές αρχείων.
- Η μέθοδος `ReadBarCodes()` επιστρέφει **όλα** τα barcodes που ταιριάζουν με τον ζητούμενο τύπο, ικανοποιώντας την απαίτηση *read multiple barcodes* ακόμη και αν η εικόνα περιέχει μόνο ένα.

Η εκτέλεση του προγράμματος εκτυπώνει έξοδο παρόμοια με:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Χρήση του αναγνώστη barcode C# για ανάγνωση πολλαπλών barcode

Αν μια εικόνα περιέχει αρκετά σύμβολα Macro PDF417 (π.χ., μια σκαναρισμένη σελίδα με μια παρτίδα εισιτηρίων), ο ίδιος βρόχος `foreach` επεξεργάζεται το καθένα. Δεν απαιτείται επιπλέον κώδικας· ο αναγνώστης συγκεντρώνει τα αποτελέσματα εσωτερικά.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Συνηθισμένα προβλήματα

- **Image format:** Ο αναγνώστης υποστηρίζει PNG, JPEG, BMP και TIFF. Αν δοκιμάσετε μια μορφή που δεν μπορεί να αποκωδικοποιήσει, θα λάβετε μια κενή συλλογή. Γι' αυτό το tutorial τονίζει το *read barcode PNG*.
- **Resolution:** Οι εικόνες χαμηλής ανάλυσης (< 300 dpi) μπορεί να προκαλέσουν χαμένα τμήματα. Ανεβάστε την ανάλυση ή ζητήστε σάρωση υψηλότερης ποιότητας όταν είναι δυνατόν.
- **Macro flag:** Η παράλειψη του `DecodeType.MacroPdf417` περιορίζει τη μηχανή σε απλό PDF417 και απορρίπτει τα επεκταμένα δεδομένα. Πάντα να καθορίζετε τον τύπο macro όταν χρειάζεστε τα πεδία *read barcode extended*.

## Ανάγνωση αρχείων barcode PNG – βέλτιστες πρακτικές

Η εργασία με αρχεία PNG είναι απλή επειδή η μορφή διατηρεί τα pixel δεδομένα χωρίς απώλειες. Ακολουθεί μια σύντομη λίστα ελέγχου:

1. Επαληθεύστε ότι το αρχείο υπάρχει πριν δημιουργήσετε τον αναγνώστη.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Χρησιμοποιήστε `Image.FromFile` μόνο όταν χρειάζεται προεπεξεργασία (περιστροφή, περικοπή). Η `BarCodeReader` μπορεί να ανοίξει το αρχείο απευθείας, αποφεύγοντας επιπλέον κατανομή μνήμης.
3. Αν το PNG περιέχει διαφάνεια, ο αναγνώστης λειτουργεί ακόμη επειδή το barcode αποδίδεται σε αδιαφανή pixel.

## Πρόσβαση στα επεκταμένα μεταδεδομένα PDF417

Το αντικείμενο `Extended.Pdf417` εκθέτει κάθε προαιρετικό πεδίο που ορίζεται από την προδιαγραφή PDF417. Μπορείτε να αντιστοιχίσετε αυτά τα πεδία σε ένα domain model, να τα αποθηκεύσετε σε μια βάση δεδομένων ή να τα χρησιμοποιήσετε για επικύρωση.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Συμπληρώστε το μοντέλο:



## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να διαβάσετε DataMatrix Barcodes με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Πώς να δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Διαβάστε DataMatrix barcode C# – Δημιουργία DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}