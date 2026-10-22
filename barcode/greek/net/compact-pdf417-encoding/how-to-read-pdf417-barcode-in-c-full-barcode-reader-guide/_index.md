---
category: general
date: 2026-10-21
description: Πώς να διαβάσετε τον κωδικό PDF417 σε C# χρησιμοποιώντας έναν αναγνώστη
  barcode από εικόνα. Ακολουθήστε αυτό το βήμα‑βήμα παράδειγμα αναγνώστη barcode σε
  C# για αξιόπιστη αποκωδικοποίηση.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: el
lastmod: 2026-10-21
og_description: Πώς να διαβάσετε γραμμωτό κώδικα PDF417 σε C# με ένα πλήρες παράδειγμα
  αναγνώστη γραμμωτού κώδικα. Μάθετε να αποκωδικοποιείτε εικόνες Macro PDF417 και
  να έχετε πρόσβαση σε όλα τα επεκταμένα πεδία.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Πώς να διαβάσετε τον γραμμωτό κώδικα PDF417 σε C# – λεπτομερής οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Πώς να διαβάσετε τον κωδικό PDF417 σε C# – πλήρης οδηγός ανάγνωσης κωδίκων
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε το barcode PDF417 σε C# – πλήρης οδηγός ανάγνωσης barcode

Αν χρειάζεστε **πώς να διαβάσετε το barcode PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας παρουσιάζει μια έτοιμη προς εκτέλεση λύση. Θα δείτε πώς να **διαβάσετε barcode από εικόνα C#** χρησιμοποιώντας μια δημοφιλής βιβλιοθήκη barcode και να λάβετε κάθε χαρακτηριστικό Macro PDF417 χωρίς επιπλέον εργαλεία.

Το tutorial καλύπτει όλα όσα απαιτούνται για ένα **παράδειγμα αναγνώστη barcode C#**: ρύθμιση έργου, επεξήγηση κώδικα και συμβουλές για την αντιμετώπιση ειδικών περιπτώσεων. Στο τέλος μπορείτε να επικολλήσετε τον κώδικα σε ένα έργο κονσόλας και να ξεκινήσετε την αποκωδικοποίηση εικόνων PDF417 αμέσως.

## Τι θα χρειαστείτε

Πριν ξεκινήσετε, επιβεβαιώστε τις παρακάτω προαπαιτήσεις:

| Προαπαιτούμενο | Αιτία |
|----------------|-------|
| .NET 6.0 SDK or later | Παρέχει το runtime για την εφαρμογή κονσόλας C# |
| Visual Studio 2022 (or any C# IDE) | Διευκολύνει τη δημιουργία έργου και τον εντοπισμό σφαλμάτων |
| Aspose.BarCode for .NET (NuGet package) | Παρέχει τις κλάσεις `BarCodeReader` και `DecodeType` |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | Λειτουργεί ως είσοδος για την αποκωδικοποίηση |

Μπορείτε να εγκαταστήσετε τη βιβλιοθήκη με το dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Πώς να διαβάσετε το barcode PDF417 από μια εικόνα σε C#

Ο πυρήνας της ροής εργασίας **read barcode from image C#** αποτελείται από τρεις ενέργειες:

1. Αρχικοποιήστε το `BarCodeReader` για το συγκεκριμένο `DecodeType`.
2. Επανάληψη μέσω της συλλογής `BarCodeResult` που επιστρέφεται.
3. Πρόσβαση τόσο στα βασικά όσο και στα επεκταμένα πεδία PDF417.

Παρακάτω βρίσκεται ο πλήρης, εκτελέσιμος κώδικας. Αποθηκεύστε τον ως `Program.cs` μέσα σε ένα έργο κονσόλας.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Εξήγηση κάθε βήματος

* **Βήμα 1 – Αρχικοποίηση του αναγνώστη**  
  Ο κατασκευαστής `BarCodeReader` λαμβάνει τη διαδρομή του αρχείου εικόνας και ένα `DecodeType`. Το `DecodeType.MacroPdf417` λέει στη βιβλιοθήκη να αναζητήσει σύμβολα Macro PDF417, τα οποία περιέχουν πρόσθετα μεταδεδομένα πέρα από τα συνηθισμένα barcode PDF417.

* **Βήμα 2 – ReadBarCodes()**  
  Αυτή η μέθοδος επιστρέφει ένα `IEnumerable<BarCodeResult>` που μπορεί να περιέχει πολλαπλά barcode εάν η εικόνα περιέχει περισσότερα από ένα. Ο βρόχος `foreach` εγγυάται ότι κάθε ανιχνευμένο σύμβολο επεξεργάζεται.

* **Βήμα 3 – Βασικές πληροφορίες**  
  Το `CodeTypeName` προσδιορίζει τη μορφή του barcode (π.χ., “MacroPDF417”). Το `CodeText` περιέχει τη ακατέργαστη συμβολοσειρά δεδομένων που κωδικοποιείται στο σύμβολο.

* **Βήμα 4 – Επεκταμένα πεδία**  
  Το Macro PDF417 προσθέτει ένα σύνολο επεκταμένων ιδιοτήτων κάτω από `barcodeResult.Extended.Pdf417`. Αυτά τα πεδία εκθέτουν δεδομένα επιπέδου αρχείου όπως `FileID`, `SegmentID` και `FileName`. Η άμεση πρόσβαση σε αυτά σας επιτρέπει να ανακατασκευάσετε έγγραφα πολλαπλών τμημάτων ή να επαληθεύσετε την ακεραιότητα.

#### Αναμενόμενη έξοδος κονσόλας

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Οι ακριβείς τιμές αντανακλούν το περιεχόμενο που κωδικοποιήθηκε στο `MacroPdf417.png`. Εάν η εικόνα περιέχει ένα μόνο τμήμα, το `SegmentsCount` θα είναι 1 και το `SegmentID` θα είναι 0.

## Ρύθμιση του περιβάλλοντος αναγνώστη barcode C#

Ένα αξιόπιστο **παράδειγμα αναγνώστη barcode C#** εξαρτάται από μια καθαρή διαμόρφωση έργου:

1. **Δημιουργήστε ένα νέο έργο κονσόλας**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Προσθέστε το πακέτο Aspose.BarCode** (όπως φαίνεται παραπάνω).  
3. **Αντιγράψτε το αρχείο εικόνας** στον φάκελο του έργου ή αναφερθείτε σε αυτό με απόλυτη διαδρομή.  
4. **Δομήστε και εκτελέστε**  
   ```bash
   dotnet run
   ```

Εάν η κατασκευή αποτύχει με σφάλμα έλλειψης αναφοράς, ελέγξτε ότι οι δηλώσεις `using Aspose.BarCode;` ταιριάζουν με την εγκατεστημένη έκδοση του πακέτου. Το API της βιβλιοθήκης είναι σταθερό μεταξύ .NET 6 και .NET 8, έτσι μπορείτε να αναβαθμίσετε το runtime χωρίς αλλαγές κώδικα.

## Αποκωδικοποίηση του Macro PDF417 barcode

Όταν καλείτε το `ReadBarCodes()`, η βιβλιοθήκη εκτελεί τα εξής εσωτερικά:

* **Προεπεξεργασία εικόνας** – μετατρέπει το bitmap σε δυαδικό πίνακα, διορθώνοντας την περιστροφή και το θόρυβο.  
* **Ανίχνευση προτύπου** – σαρώσει για τα πρότυπα έναρξης/λήξης PDF417 και εξάγει το πλάτος του μονάδας.  
* **Διόρθωση σφαλμάτων** – εφαρμόζει κώδικες Reed‑Solomon για την ανάκτηση κατεστραμμένων codewords.  
* **Εξαγωγή Macro** – αναλύει την επεκταμένη κεφαλίδα τμήματος PDF417 και γεμίζει το αντικείμενο `Extended.Pdf417`.

Η κατανόηση αυτής της αλυσίδας βοηθά να αποφασίσετε πότε να προσαρμόσετε τις επιλογές αποκωδικοποιητή. Για παράδειγμα, εάν οι εικόνες σας έχουν χαμηλή αντίθεση, μπορείτε να ενεργοποιήσετε την ιδιότητα `ReadQuality` του `BarCodeReader` (διαθέσιμη σε μεταγενέστερες εκδόσεις) για να βελτιώσετε τα ποσοστά ανίχνευσης.

## Ερμηνεία των επεκταμένων πεδίων PDF417

Τα επεκταμένα πεδία αντιστοιχούν άμεσα στην προδιαγραφή Macro PDF417:

| Πεδίο | Σημασία |
|-------|----------|
| `MacroPdf417FileID` | Μοναδικό αναγνωριστικό για ολόκληρο το αρχείο σε όλα τα τμήματα |
| `MacroPdf417SegmentID` | Δείκτης μηδενικής βάσης του τρέχοντος τμήματος |
| `MacroPdf417SegmentsCount` | Συνολικός αριθμός τμημάτων που αποτελούν το αρχείο |
| `MacroPdf417FileName` | Αρχικό όνομα αρχείου που αποθηκεύτηκε κατά την κωδικοποίηση |
| `MacroPdf417Checksum` | 16‑bit checksum για επαλήθευση ακεραιότητας |
| `MacroPdf417FileSize` | Μέγεθος του αρχικού αρχείου σε bytes |
| `MacroPdf417TimeStamp` | Χρονική σήμανση UTC όταν δημιουργήθηκε το barcode |
| `MacroPdf417Addressee` | Προοριζόμενος παραλήπτης του εγγράφου |
| `MacroPdf417Sender` | Αποστολέας του εγγράφου |
| `MacroPdf417Terminator` | Λέξη-κλειδί “END” που σηματοδοτεί το τελευταίο τμήμα |

Μπορείτε να χρησιμοποιήσετε αυτές τις τιμές για να ανακατασκευάσετε ένα PDF πολλαπλών τμημάτων, να επαληθεύσετε ότι δεν λείπει κανένα τμήμα ή να καταγράψετε πληροφορίες ελέγχου για σκοπούς συμμόρφωσης.

## Συνηθισμένα προβλήματα και αντιμετώπιση

| Συμπτωμα | Πιθανή αιτία | Διόρθωση |
|----------|--------------|----------|
| Δεν εμφανίζεται έξοδος | Λάθος διαδρομή εικόνας ή μη υποστηριζόμενη μορφή | Χρησιμοποιήστε απόλυτη διαδρομή και βεβαιωθείτε ότι το αρχείο είναι PNG/JPEG που υποστηρίζεται από το Aspose.BarCode |
| `CodeType` shows “PDF417” instead of “MacroPDF417” | Η εικόνα περιέχει ένα κανονικό σύμβολο PDF417, όχι μια παραλλαγή macro | Επαληθεύστε ότι το barcode προέλευσης κωδικοποιήθηκε με επεκτάσεις Macro PDF417 |
| Κάποια πεδία είναι κενά | Το barcode δημιουργήθηκε χωρίς αυτά τα macro πεδία | Κωδικοποιήστε το barcode με πλήρες macro payload, ή χειριστείτε τις τιμές null στον κώδικα |
| Decoder throws `ArgumentException` | Λάθος `DecodeType` καθορίστηκε | Αλλάξτε το `DecodeType.MacroPdf417` σε `DecodeType.Pdf417` εάν χρειάζεστε μόνο τα τυπικά δεδομένα PDF417 |

**Συμβουλή:** Τυλίξτε την πρόσβαση στα πεδία με ελέγχους null εάν προαναμένετε barcode χωρίς macro. Το αντικείμενο `Extended.Pdf417` επιστρέφει προεπιλεγμένες τιμές (π.χ., `0` για αριθμητικά πεδία) όταν τα δεδομένα λείπουν.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Συνοπτική παρουσίαση πλήρους παραδείγματος

Συνδυάζοντας όλα, το τελικό πρόγραμμα αποτελείται από τις οδηγίες using, τη μέθοδο `Main` και τον βρόχο τεσσάρων βημάτων που εμφανίστηκε νωρίτερα. Δεν απαιτούνται επιπλέον αρχεία ρυθμίσεων. Συγκεντρώστε και εκτελέστε το έργο για να δείτε την έξοδο της κονσόλας με όλες τις ιδιότητες Macro PDF417.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να διαβάσετε το barcode PDF417** σε C# χρησιμοποιώντας ένα συνοπτικό **παράδειγμα αναγνώστη barcode C#**. Ο οδηγός σας οδήγησε στη ρύθμιση του περιβάλλοντος, στην υλοποίηση του κώδικα και στην ερμηνεία κάθε επεκταμένου πεδίου Macro PDF417. Με αυτή τη βάση μπορείτε να ενσωματώσετε την σάρωση barcode σε συστήματα απογραφής, ροές εργασίας διαχείρισης εγγράφων ή κινητές υποδομές.

### Επόμενο

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να διαβάσετε PDF417 σε C# – πλήρης οδηγός ανάγνωσης barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Πώς να αποκωδικοποιήσετε PDF417 σε C# με παράδειγμα αναγνώστη barcode](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Πώς να δημιουργήσετε εικόνα barcode PDF417 σε C# με επιλογές Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}