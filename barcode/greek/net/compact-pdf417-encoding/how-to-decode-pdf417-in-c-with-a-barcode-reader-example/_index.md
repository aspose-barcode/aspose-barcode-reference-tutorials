---
category: general
date: 2026-09-19
description: Πώς να αποκωδικοποιήσετε το PDF417 σε C# – μάθετε να διαβάζετε γραμμωτούς
  κώδικες από εικόνα χρησιμοποιώντας ένα σύντομο παράδειγμα αναγνώστη γραμμωτών κωδίκων
  που εξάγει πλήρη δεδομένα Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: el
lastmod: 2026-09-19
og_description: Πώς να αποκωδικοποιήσετε το PDF417 σε C# με ένα παράδειγμα ανάγνωσης
  barcode βήμα‑βήμα. Εξάγετε κάθε πεδίο Macro PDF417 από μια εικόνα σε δευτερόλεπτα.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Πώς να αποκωδικοποιήσετε το PDF417 σε C# – πλήρης οδηγός ανάγνωσης barcode
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: How to decode PDF417 in C# with a barcode reader example
url: /el/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποκωδικοποιήσετε PDF417 σε C# με παράδειγμα αναγνώστη barcode

Αν χρειάζεστε να αποκωδικοποιήσετε PDF417 σε C#, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε από αρχείο εικόνας. Θα μάθετε να διαβάζετε barcodes από εικόνα, να έχετε πρόσβαση στα εκτεταμένα πεδία Macro PDF417 και να ενσωματώνετε τη λύση σε οποιοδήποτε έργο .NET.

Η αποκωδικοποίηση barcodes PDF417 είναι συχνή στη λογιστική, τα εισιτήρια και την επαλήθευση ταυτότητας. Αυτό το tutorial καλύπτει όλα όσα απαιτούνται για μια παραγωγική υλοποίηση, συμπεριλαμβανομένων των προαπαιτούμενων βιβλιοθηκών, του πλήρους κώδικα και συμβουλών για την αντιμετώπιση ειδικών περιπτώσεων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- .NET 6.0 ή νεότερη εγκατεστημένη  
- Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει C#)  
- Το πακέτο **Aspose.BarCode for .NET** NuGet (έκδοση 23.11 ή νεότερη)  

Μπορείτε να προσθέσετε το πακέτο με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

Η κλάση `BarCodeReader` από αυτή τη βιβλιοθήκη υποστηρίζει τον τύπο αποκωδικοποίησης `MacroPdf417` που απαιτείται για πλήρη εξαγωγή PDF417.

## Βήμα 1: Πώς να αποκωδικοποιήσετε PDF417 σε C# – αρχικοποίηση του αναγνώστη

Το πρώτο βήμα δημιουργεί μια παρουσία `BarCodeReader` που στοχεύει σε εικόνα Macro PDF417. Η σημαία `DecodeType.MacroPdf417` λέει στη βιβλιοθήκη να αναλύσει τα εκτεταμένα πεδία Macro.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Γιατί είναι σημαντικό:** Η αρχικοποίηση με `MacroPdf417` ενεργοποιεί την ιδιότητα `Extended.Pdf417` σε κάθε `BarCodeResult`, δίνοντάς σας πρόσβαση σε μεταδεδομένα επιπέδου αρχείου όπως τα IDs τμημάτων και οι χρονικές σφραγίδες.

## Βήμα 2: Ανάγνωση barcodes από εικόνα

Μια εικόνα PDF417 μπορεί να περιέχει πολλαπλά τμήματα macro. Η μέθοδος `ReadBarCodes()` επιστρέφει μια συλλογή όλων των εντοπισμένων barcodes, ώστε να μπορείτε να τα επεξεργαστείτε με ασφάλεια.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Συμβουλή:** Αν περιμένετε μόνο ένα barcode, μπορείτε να διακόψετε μετά την πρώτη επανάληψη, αλλά η επανάληψη σε όλα τα αποτελέσματα εγγυάται ότι θα συλλάβετε κάθε τμήμα σε έγγραφα πολλαπλών σελίδων.

## Βήμα 3: Αποκωδικοποίηση barcode PDF417 – εξαγωγή βασικών και εκτεταμένων δεδομένων

Μέσα στον βρόχο, εμφανίστε τόσο τις γενικές πληροφορίες barcode όσο και τα πεδία ειδικά για Macro. Το αντικείμενο `Extended.Pdf417` περιέχει κάθε κομμάτι μεταδεδομένων που ορίζεται από το πρότυπο PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
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

**Εξήγηση βασικών πεδίων**

| Πεδίο | Σημασία |
|-------|----------|
| `MacroPdf417FileID` | Αναγνωριστικό που ομαδοποιεί όλα τα τμήματα που ανήκουν στο ίδιο λογικό αρχείο |
| `MacroPdf417SegmentID` | Δείκτης του τρέχοντος τμήματος (αρχίζει από 0) |
| `MacroPdf417SegmentsCount` | Συνολικός αριθμός τμημάτων που αναμένονται για το αρχείο |
| `MacroPdf417FileName` | Προαιρετικό όνομα αρχείου ενσωματωμένο στο macro |
| `MacroPdf417Checksum` | CRC‑16 checksum για την ακεραιότητα των δεδομένων |
| `MacroPdf417FileSize` | Αρχικό μέγεθος αρχείου σε bytes |
| `MacroPdf417TimeStamp` | Χρονική σφραγίδα όταν δημιουργήθηκε το macro |
| `MacroPdf417Addressee` | Προοριζόμενος παραλήπτης των δεδομένων macro |
| `MacroPdf417Sender` | Αποστολέας των δεδομένων macro |
| `MacroPdf417Terminator` | Boolean σημαία που υποδεικνύει το τελικό τμήμα |

Η πρόσβαση σε αυτά τα πεδία σας επιτρέπει να ανασυνθέσετε το αρχικό έγγραφο, να ελέγξετε την ακεραιότητα ή να δρομολογήσετε τα δεδομένα βάσει πληροφοριών αποστολέα/παραλήπτη.

## Βήμα 4: Πλήρες παράδειγμα C# barcode reader – συνδυάστε τα όλα

Παρακάτω βρίσκεται το πλήρες, εκτελέσιμο πρόγραμμα. Αντικαταστήστε το `YOUR_DIRECTORY` με το φάκελο που περιέχει το αρχείο `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
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

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Αναμενόμενη έξοδος κονσόλας (παράδειγμα)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Οι ακριβείς τιμές θα διαφέρουν ανάλογα με το περιεχόμενο του Macro PDF417 barcode σας.

## Διαχείριση κοινών ειδικών περιπτώσεων

| Κατάσταση | Συνιστώμενη προσέγγιση |
|-----------|------------------------|
| **Δεν εντοπίστηκε barcode** | Ελέγξτε τη διαδρομή της εικόνας, βεβαιωθείτε ότι το αρχείο δεν είναι κατεστραμμένο και ότι το barcode είναι ορατό (αρκετή αντίθεση). |
| **Μερικά τμήματα macro** | Χρησιμοποιήστε το `MacroPdf417SegmentsCount` για να εντοπίσετε ελλιπή μέρη. Μπορείτε να ζητήσετε τα υπόλοιπα τμήματα από το σύστημα προέλευσης και να ξανατρέξετε τον αποκωδικοποιητή. |
| **Μεγάλες εικόνες που προκαλούν πίεση μνήμης** | Φορτώστε την εικόνα σε ένα `System.Drawing.Bitmap` με μειωμένη ανάλυση πριν τη περάσετε στο `BarCodeReader`. |
| **Μη‑Macro PDF417** | Αλλάξτε το `DecodeType.MacroPdf417` σε `DecodeType.Pdf417` αν χρειάζεστε μόνο το απλό κείμενο του barcode. |

## Pro tips

- **Επεξεργασία σε παρτίδες:** Τυλίξτε τη λογική του αναγνώστη σε μια μέθοδο που δέχεται λίστα διαδρομών αρχείων. Επαναχρησιμοποιήστε μία ενιαία παρουσία `BarCodeReader` ανά νήμα για μείωση του κόστους κατανομής.  
- **Απόδοση:** Για σενάρια υψηλής διακίνησης, ενεργοποιήστε την ιδιότητα `ReaderOptions` `ReadQuality` για ισορροπία ταχύτητας έναντι ακρίβειας.  
- **Ασφάλεια:** Επικυρώστε το `CodeText` πριν το χρησιμοποιήσετε σε λειτουργίες συστήματος αρχείων ώστε να αποτρέψετε επιθέσεις διαπέρασης διαδρομών.

## Συμπέρασμα

Σε αυτό το tutorial μάθατε πώς να αποκωδικοποιήσετε PDF417 σε C# διαβάζοντας barcodes από εικόνα, εξάγοντας κάθε πεδίο Macro PDF417 και δημιουργώντας ένα πλήρες παράδειγμα C# barcode reader. Η λύση λειτουργεί με τη νεότερη βιβλιοθήκη Aspose.BarCode, διαχειρίζεται macro πολλαπλών τμημάτων και παρέχει πρακτικές οδηγίες για πραγματικά έργα.

Στη συνέχεια, εξερευνήστε σχετικές θεματικές όπως **ανάγνωση QR codes**, **επεξεργασία barcodes σε παρτίδες** και **δημιουργία PDF417 barcodes** για να επεκτείνετε το εργαλείο αυτοματοποίησης εγγράφων σας. Μη διστάσετε να πειραματιστείτε με διαφορετικές πηγές εικόνας, να ενσωματώσετε τον κώδικα σε υπηρεσίες ASP.NET ή να τον επεκτείνετε ώστε να αποθηκεύει τα εξαγόμενα μεταδεδομένα σε βάση δεδομένων. Καλό κώδικα!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση σας.

- [Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα barcode reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Πώς να δημιουργήσετε εικόνα PDF417 barcode σε C# με Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Ανάγνωση barcode από εικόνα – Παράδειγμα C# barcode reader](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}