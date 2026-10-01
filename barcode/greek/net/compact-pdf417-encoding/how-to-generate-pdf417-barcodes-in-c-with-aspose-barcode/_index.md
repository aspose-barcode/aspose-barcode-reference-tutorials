---
category: general
date: 2026-09-10
description: Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C# χρησιμοποιώντας
  το Aspose.BarCode. Ακολουθήστε έναν οδηγό βήμα‑προς‑βήμα για τη δημιουργία Macro
  PDF417, τη ρύθμιση των παραμέτρων και την εξαγωγή ως PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: el
lastmod: 2026-09-10
og_description: Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C# με το Aspose.BarCode.
  Μάθετε τη πλήρη διαδικασία από τη ρύθμιση έως την αποθήκευση μιας εικόνας Macro
  PDF417 PNG.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C# – πλήρης οδηγός Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C# με το Aspose.BarCode
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C# με Aspose.BarCode

Αν χρειάζεστε **πώς να δημιουργήσετε pdf417** σε ένα έργο .NET, αυτό το tutorial δείχνει τη πλήρη ροή εργασίας. Θα δείτε πώς να δημιουργήσετε έναν Macro PDF417 γραμμωτό κώδικα, να ρυθμίσετε λεπτομερώς τις ρυθμίσεις του και να εξάγετε το αποτέλεσμα ως εικόνα PNG—όλα με το Aspose.BarCode για .NET.

Η δημιουργία γραμμωτών κωδίκων PDF417 είναι συνηθισμένη στη λογιστική, τα εισιτήρια και τις ασφαλείς ροές εργασίας εγγράφων. Στο τέλος αυτού του οδηγού θα έχετε έναν έτοιμο προς χρήση γεννήτρια γραμμωτών κωδίκων C# που μπορείτε να ενσωματώσετε σε οποιαδήποτε εφαρμογή.

## Τι θα χρειαστείτε

- **Visual Studio 2022** (ή οποιοδήποτε IDE C#)  
- **.NET 6.0** ή νεότερο  
- **Aspose.BarCode for .NET** πακέτο NuGet (`Install-Package Aspose.BarCode`)  
- Βασική εξοικείωση με τη σύνταξη C#  

> **Συμβουλή:** Χρησιμοποιήστε την πιο πρόσφατη έκδοση του Aspose.BarCode για να αποκτήσετε τις νεότερες δυνατότητες Macro PDF417 και διορθώσεις σφαλμάτων.

---

## Πώς να δημιουργήσετε γραμμωτούς κώδικες PDF417 σε C#

Παρακάτω υπάρχει ένα πλήρως εκτελέσιμο παράδειγμα που δημιουργεί έναν **Macro PDF417** γραμμωτό κώδικα, ρυθμίζει τα πεδία macro‑specific και αποθηκεύει την εικόνα.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Γιατί κάθε βήμα είναι σημαντικό

1. **Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode to use the macro version of PDF417, which supports splitting a large payload across multiple symbols.  
2. **Adjust basic appearance** – `XDimension` controls the module (dot) width; `Columns` defines how many columns each symbol will contain, influencing both size and readability.  
3. **Set macro‑specific fields** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification to re‑assemble the original data on the scanner side.  
4. **Export the image** – `BarCodeImageFormat.Png` provides a lossless image that works well for web, print, and mobile scenarios.

---

## Ρύθμιση του Aspose.BarCode για .NET (Γεννήτρια γραμμωτών κώδικων C#)

Πριν μπορέσετε να εκτελέσετε τον παραπάνω κώδικα, πρέπει να προσθέσετε τη βιβλιοθήκη Aspose.BarCode στο έργο σας:

```bash
dotnet add package Aspose.BarCode
```

*Το πακέτο NuGet περιλαμβάνει όλες τις εξαρτήσεις, οπότε δεν απαιτούνται επιπλέον DLLs.*  
Αν στοχεύετε .NET Framework, η ίδια εντολή `Install-Package Aspose.BarCode` λειτουργεί από το Package Manager Console.

### Συνηθισμένα λάθη

- **Missing license** – By default Aspose runs in evaluation mode, which adds a watermark to the barcode. Register a license file (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) to remove it.  
- **Incorrect `EncodeTypes`** – Using `EncodeTypes.Pdf417` instead of `EncodeTypes.MacroPdf417` will ignore all macro fields, breaking multi‑segment reconstruction.

---

## Διαμόρφωση παραμέτρων Macro PDF417 γραμμωτού κώδικα

Τα macro πεδία σας επιτρέπουν να χωρίσετε ένα μεγάλο έγγραφο σε πολλαπλά σύμβολα PDF417. Ακολουθεί μια γρήγορη αναφορά:

| Ιδιότητα | Σκοπός | Τυπικό εύρος |
|----------|--------|--------------|
| `MacroPdf417FileID` | Μοναδικό αναγνωριστικό για ολόκληρο το αρχείο | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Δείκτης του τρέχοντος τμήματος (ξεκινά από 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Συνολικός αριθμός τμημάτων στο αρχείο | 1‑255 |
| `MacroPdf417FileName` | Προαιρετικό ανθρώπινα αναγνώσιμο όνομα | 0‑255 χαρακτήρες |
| `MacroPdf417Checksum` | CCITT‑16 checksum για ανίχνευση σφαλμάτων | 0‑65535 |
| `MacroPdf417FileSize` | Αρχικό μέγεθος αρχείου σε bytes | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Χρονική σήμανση δημιουργίας (προαιρετικό) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Προαιρετικά μεταδεδομένα για δρομολόγηση | Any string |
| `MacroPdf417Terminator` | Δείχνει το τελικό τμήμα (`Set` ή `Unset`) | `Pdf417MacroTerminator` enum |

Ρυθμίστε αυτές τις τιμές ώστε να ταιριάζουν με τα δεδομένα που κωδικοποιείτε. Για παράδειγμα, αν χωρίσετε ένα αρχείο 2 MB σε 20 τμήματα, ορίστε `MacroPdf417FileSize` σε `2_000_000` και `MacroPdf417SegmentsCount` σε `20`.

## Εξαγωγή του γραμμωτού κώδικα ως εικόνα PNG (εξαγωγή εικόνας γραμμωτού κώδικα)

Η αποθήκευση του γραμμωτού κώδικα ως PNG είναι η πιο κοινή μορφή εξαγωγής επειδή διατηρεί τις αιχμηρές άκρες και υποστηρίζει διαφάνεια. Το Aspose.BarCode υποστηρίζει επίσης JPEG, BMP, GIF και TIFF—επιλέξτε αυτή που ταιριάζει στη διαδικασία σας.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Συμβουλές για υψηλής ποιότητας έξοδο**

- Αυξήστε το `XDimension.Pixels` για μεγαλύτερα modules όταν εκτυπώνετε σε υψηλής ανάλυσης μέσα.  
- Χρησιμοποιήστε `BarCodeImageFormat.Tiff` με συμπίεση CCITT Group 4 για PDF συμβατά με φαξ.  
- Ορίστε `generator.Parameters.ImageOptions.Resolution` αν χρειάζεστε συγκεκριμένο DPI (π.χ., 300 dpi για εκτύπωση).

## Δοκιμή και αντιμετώπιση προβλημάτων του PDF417 γραμμωτού κώδικα

1. **Visual verification** – Open `MacroPdf417.png` in any image viewer. You should see a stacked set of vertical bars with a small text caption (the encoded data).  
2. **Scanner test** – Use a mobile barcode scanner app that supports PDF417. Scan the image; the app should return the original “Sample text” plus macro metadata (file ID, segment ID, etc.).  
3. **Error handling** – If the scanner reports “checksum error,” double‑check `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly on the last segment.  
4. **Performance** – Generating many segments in a loop can be CPU‑intensive. Re‑use a single `BarcodeGenerator` instance and only update the macro fields between saves to improve throughput.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να δημιουργήσετε PDF417** γραμμωτούς κώδικες σε C# χρησιμοποιώντας το Aspose.BarCode, από την εγκατάσταση της βιβλιοθήκης μέχρι τη διαμόρφωση των πεδίων Macro PDF417 και την εξαγωγή μιας καθαρής εικόνας PNG. Η πλήρης λύση δείχνει:

- Ρύθμιση μιας **γεννήτριας γραμμωτών κωδίκων C#** με τον τύπο Macro PDF417  
- Προσαρμογή **παραμέτρων PDF417 γραμμωτού κώδικα** για δεδομένα πολλαπλών τμημάτων  
- Εκτέλεση **εξαγωγής εικόνας γραμμωτού κώδικα** για downstream χρήση  

Από εδώ μπορείτε να εξερευνήσετε προχωρημένα θέματα όπως η ενσωμάτωση του γραμμωτού κώδικα σε έγγραφα PDF, η δημιουργία συνοδών QR‑code ή η αυτοματοποίηση μαζικής επεξεργασίας μεγάλων αρχείων.

**Επόμενα βήματα**

- Δοκιμάστε διαφορετικές τιμές `BarCodeImageFormat` (π.χ., `Tiff` για εκτυπώσεις υψηλής ανάλυσης).  
- Συνδυάστε Macro PDF417 με άλλες συμβολές στο ίδιο έγγραφο χρησιμοποιώντας `generator.Parameters.Barcode.Symbology`.  
- Ανασκοπήστε την [Aspose.BarCode documentation](https://docs.aspose.com/barcode/net/) για πιο βαθιές επιλογές προσαρμογής όπως επίπεδο διόρθωσης σφαλμάτων και τρόπους κωδικοποίησης.

Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Οι παρακάτω οδηγίες καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία γραμμωτού κώδικα με κείμενο – Πλήρης οδηγός Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [προσαρμογή μεγέθους γραμμωτού κώδικα – Οδηγός C# για δημιουργία PDF417 γραμμωτών κωδίκων](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Πώς να δημιουργήσετε PDF417 γραμμωτό κώδικα – Πλήρης προγραμματιστικός οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}