---
category: general
date: 2026-09-29
description: Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# χρησιμοποιώντας
  το Aspose.BarCode. Μάθετε ένα παράδειγμα αναγνώστη γραμμωτού κώδικα που δείχνει
  πώς να διαβάζετε εικόνες γραμμωτών κωδίκων και να εξάγετε μακροδεδομένα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: el
lastmod: 2026-09-29
og_description: Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# με το Aspose.BarCode.
  Αυτός ο οδηγός παρουσιάζει ένα έτοιμο παράδειγμα αναγνώστη γραμμωτού κώδικα για
  την ανάγνωση εικόνων γραμμωτών κωδίκων.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Πώς να αποκωδικοποιήσετε κώδικες PDF417 σε C# – πλήρες παράδειγμα αναγνώστη
  barcode
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Πώς να αποκωδικοποιήσετε τους κωδικούς PDF417 σε C# – βήμα‑βήμα οδηγός
url: /el/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποκωδικοποιήσετε γραμμωτούς κώδικες PDF417 σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **how to decode PDF417** γραμμωτούς κώδικες σε C#, αυτό το tutorial σας παρέχει μια πλήρη, εκτελέσιμη λύση. Θα δείτε ένα **barcode reader example** που επιδεικνύει **how to read barcode** εικόνες, εξάγει πληροφορίες macro και εκτυπώνει τα αποτελέσματα στην κονσόλα.

Η αποκωδικοποίηση PDF417 είναι κοινή κατά την επεξεργασία ετικετών αποστολής, εισιτηρίων ή κυβερνητικών ταυτοτήτων. Στο τέλος αυτού του οδηγού θα μπορείτε να διαβάσετε μια εικόνα γραμμωτού κώδικα PDF417, να έχετε πρόσβαση στα macro πεδία του και να αντιμετωπίσετε τυπικές περιπτώσεις άκρων. Δεν απαιτείται εξωτερική τεκμηρίωση – όλα όσα χρειάζεστε περιλαμβάνονται.

## Τι θα μάθετε

- Εγκαταστήστε τη βιβλιοθήκη Aspose.BarCode για .NET  
- Δημιουργήστε ένα `BarCodeReader` που **read PDF417 barcode** δεδομένα από αρχείο PNG ή JPEG  
- Επανάληψη (iterate) πάνω σε αντικείμενα `BarCodeResult` και ανάκτηση των macro‑PDF417 ιδιοτήτων  
- Εντοπισμός και επίλυση κοινών προβλημάτων όπως μη υποστηριζόμενες μορφές εικόνας ή ελλιπή macro δεδομένα  

## Προαπαιτούμενα

| Απαίτηση | Αιτία |
|-------------|--------|
| .NET 6.0 SDK or later | Παρέχει το runtime για έργα C# |
| Visual Studio 2022 (or any IDE that supports .NET) | Διευκολύνει τη δημιουργία και αποσφαλμάτωση έργων |
| NuGet package **Aspose.BarCode** | Παρέχει την κλάση `BarCodeReader` που χρησιμοποιείται στο παράδειγμα |
| A PDF417 macro image (e.g., `ExtPDF417Meta.png`) | Το αρχείο προέλευσης που θα αποκωδικοποιήσει ο αναγνώστης |

> **Συμβουλή:** Εάν δεν έχετε εικόνα PDF417, μπορείτε να δημιουργήσετε μία με το δωρεάν online demo του Aspose.BarCode ή να σαρώσετε μια πραγματική ετικέτα.

## Βήμα 1: Εγκατάσταση Aspose.BarCode μέσω NuGet

Ανοίξτε ένα τερματικό στον φάκελο της λύσης σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Η εντολή προσθέτει την πιο πρόσφατη σταθερή έκδοση του Aspose.BarCode στο έργο σας και ενημερώνει το αρχείο `.csproj`. Αυτή η βιβλιοθήκη υλοποιεί τη λειτουργία **read barcode image C#** για δεκάδες συμβολισμούς, συμπεριλαμβανομένου του PDF417.

## Βήμα 2: Δημιουργία BarCodeReader για **how to decode PDF417**

Ο πυρήνας της διαδικασίας **how to read barcode** είναι το `BarCodeReader`. Πρέπει να δώσετε στον αναγνώστη τόσο τη διαδρομή του αρχείου όσο και την αναμενόμενη συμβολισμού (`DecodeType.MacroPdf417`). Η παροχή του σωστού `DecodeType` βελτιώνει την ταχύτητα και την ακρίβεια της ανίχνευσης.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Γιατί αυτό είναι σημαντικό:**  
- `DecodeType.MacroPdf417` ενημερώνει τη μηχανή να αναζητήσει πεδία macro‑PDF417 (ID αρχείου, ID τμήματος κ.λπ.).  
- Η χρήση του `using` εξασφαλίζει ότι η υποκείμενη ροή εικόνας κλείνει, αποτρέποντας προβλήματα κλειδώματος αρχείων στα Windows.

## Βήμα 3: Επανάληψη πάνω στα εντοπισμένα γραμμωτούς κώδικες

Μια μόνο εικόνα μπορεί να περιέχει πολλαπλούς γραμμωτούς κώδικες. Η μέθοδος `ReadBarCodes()` επιστρέφει ένα `IEnumerable<BarCodeResult>` που μπορείτε να διατρέξετε σε βρόχο.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Εάν η εικόνα δεν περιέχει κανένα σύμβολο PDF417, το σώμα του βρόχου δεν εκτελείται ποτέ, και μπορείτε να διαχειριστείτε αυτήν την περίπτωση μετά το βρόχο (δείτε την ενότητα «Διαχείριση σφαλμάτων»).

## Βήμα 4: Πρόσβαση στα macro πεδία PDF417

Κάθε `BarCodeResult` εκθέτει μια ιδιότητα `Extended` με ένα υπο‑αντικείμενο `Pdf417`. Τα macro πεδία που χρειάζεστε πιο συχνά είναι:

| Ιδιότητα | Σημασία |
|----------|---------|
| `MacroPdf417FileID` | Αναγνωριστικό ολόκληρου του macro PDF417 αρχείου |
| `MacroPdf417SegmentID` | Αριθμός ακολουθίας του τρέχοντος τμήματος |
| `MacroPdf417FileName` | Προαιρετικό όνομα αρχείου που αποθηκεύεται στο macro |

Ακολουθεί ο πλήρης κώδικας που εκτυπώνει αυτές τις τιμές:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Αναμενόμενη έξοδος κονσόλας

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Εάν τα macro πεδία δεν υπάρχουν, η έξοδος θα εμφανίζει κενές γραμμές επειδή οι ιδιότητες είναι `null`. Αυτό είναι φυσιολογικό για γραμμωτούς κώδικες PDF417 χωρίς macro.

## Βήμα 5: Διαχείριση κοινών παγίδων (διαχείριση σφαλμάτων & περιπτώσεις άκρων)

### Δεν εντοπίστηκε γραμμωτός κώδικας

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Μη υποστηριζόμενη μορφή εικόνας

Το Aspose.BarCode υποστηρίζει PNG, JPEG, BMP, TIFF και GIF. Η προσπάθεια ανάγνωσης αρχείου RAW ή WebP προκαλεί `ArgumentException`. Μετατρέψτε την εικόνα σε υποστηριζόμενη μορφή πριν τη δώσετε στον αναγνώστη.

### Μεγάλα macro αρχεία

Το Macro‑PDF417 μπορεί να εκτείνεται σε πολλά τμήματα. Για να ανασυνθέσετε το αρχικό αρχείο πρέπει να συλλέξετε όλα τα τμήματα (ταξινομημένα κατά `MacroPdf417SegmentID`) και να συνενώσετε τα δεδομένα τους. Το παραπάνω παράδειγμα εκτυπώνει μόνο τα μεταδεδομένα κάθε τμήματος· μια παραγωγική υλοποίηση θα αποθήκευε κάθε τμήμα σε λεξικό και θα τα συναρμολογούσε μόλις διαβαστούν όλα τα τμήματα.

### Συμβουλή απόδοσης

Εάν επεξεργάζεστε χιλιάδες εικόνες, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarCodeReader` με τη μέθοδο `SetImage` αντί να δημιουργείτε νέο αντικείμενο για κάθε αρχείο. Αυτό μειώνει τις εκχωρήσεις μνήμης και επιταχύνει την αποκωδικοποίηση.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Πλήρες λειτουργικό παράδειγμα

Αντιγράψτε το παρακάτω πρόγραμμα σε ένα νέο έργο Console App (`dotnet new console`). Περιλαμβάνει όλα τα βήματα, τη διαχείριση σφαλμάτων και τα σχόλια.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Εκτέλεση του προγράμματος**

```bash
dotnet run
```

Θα πρέπει να δείτε τα macro πεδία να εκτυπώνονται στην κονσόλα, ταιριάζοντας με την αναμενόμενη έξοδο που εμφανίστηκε νωρίτερα.

## Συμπέρασμα

Σε αυτό το tutorial μάθατε **how to decode PDF417** γραμμωτούς κώδικες σε C# με ένα συνοπτικό **barcode reader example**. Με την εγκατάσταση του Aspose.BarCode, τη δημιουργία ενός `BarCodeReader` για `MacroPdf417`, την επανάληψη στα αποτελέσματα και την πρόσβαση στις macro ιδιότητες `Extended.Pdf417`, μπορείτε αξιόπιστα να **read PDF417 barcode** δεδομένα από οποιαδήποτε υποστηριζόμενη εικόνα.  

Από εδώ μπορείτε:

- Να υλοποιήσετε την συγκέντρωση τμημάτων για την ανακατασκευή αρχείων multi‑segment macro.  
- Να εξερευνήσετε άλλες συμβολισμούς (QR, Code128) χρησιμοποιώντας το ίδιο πρότυπο `BarCodeReader`.  
- Να ενσωματώσετε τον αποκωδικοποιητή σε ένα web API που επεξεργάζεται ανεβασμένες εικόνες (`read barcode image C#` σε περιβάλλον υπηρεσίας).  

Μη διστάσετε να πειραματιστείτε με διαφορετικές πηγές εικόνας, στρατηγικές διαχείρισης σφαλμάτων και βελτιστοποιήσεις απόδοσης. Καλή προγραμματιστική!

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να διαβάσετε PDF417 σε C# – πλήρης οδηγός barcode reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με Aspose – πλήρης οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με Aspose – πλήρης οδηγός βήμα‑βήμα](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}