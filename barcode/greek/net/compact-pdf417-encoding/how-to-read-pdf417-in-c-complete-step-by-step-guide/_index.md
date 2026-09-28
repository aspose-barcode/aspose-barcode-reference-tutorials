---
category: general
date: 2026-09-28
description: Διαβάστε το barcode PDF417 c# γρήγορα με το Aspose.BarCode. Αποκωδικοποιήστε
  πολλαπλά barcodes από μία εικόνα, εξάγετε τα πεδία Macro‑PDF417 και διαχειριστείτε
  την περιστροφή ή την επεξεργασία σε παρτίδες.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Διαβάστε το barcode PDF417 c# γρήγορα με το Aspose.BarCode. Αυτός
  ο οδηγός δείχνει πώς να αποκωδικοποιήσετε πολλαπλά barcodes από μία εικόνα, να εξάγετε
  όλες τις ιδιότητες Macro‑PDF417 και να διαχειριστείτε περιστραμμένες ή παρτίδες
  εικόνων.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Διαβάστε το barcode PDF417 c# – πλήρες παράδειγμα κώδικα & οδηγός
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Πώς να διαβάσετε το barcode PDF417 c# – πλήρης οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε το barcode PDF417 c# – πλήρης οδηγός βήμα‑βήμα

Έχετε αναρωτηθεί ποτέ **πώς να διαβάσετε PDF417** από μια εικόνα χρησιμοποιώντας C#; Δεν είστε ο μόνος. Οι περισσότεροι προγραμματιστές συναντούν δυσκολίες όταν πρέπει να εξάγουν τα επεκταμένα πεδία Macro‑PDF417 από ένα σαρωμένο έγγραφο. Τα καλά νέα; Με λίγες μόνο γραμμές κώδικα μπορείτε να **διαβάσετε το barcode PDF417 c#**, να αποκωδικοποιήσετε πολλαπλά barcodes στην ίδια εικόνα και να πάρετε κάθε κρυφή ιδιότητα που προσφέρει η προδιαγραφή.

## Γρήγορες απαντήσεις
- **Μπορεί το Aspose.BarCode να αποκωδικοποιήσει Macro‑PDF417;** Ναι – απλώς ενεργοποιήστε `DecodeType.MacroPdf417` και η βιβλιοθήκη επιστρέφει όλα τα επεκταμένα πεδία.  
- **Πόσα barcodes μπορούν να διαβαστούν από μία εικόνα;** Απεριόριστα· το API επιστρέφει μια συλλογή από αντικείμενα `BarCodeResult`.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια για χρήση σε παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Θα ανιχνευτούν τα περιστραμμένα barcodes;** Η ενσωματωμένη αντιστάθμιση περιστροφής λειτουργεί για barcodes που καλύπτουν τουλάχιστον 30 % του πλάτους της εικόνας.  
- **Υποστηρίζεται η επεξεργασία σε παρτίδες;** Απόλυτα – τυλίξτε τον αναγνώστη σε έναν βρόχο `foreach` και απελευθερώστε κάθε αντικείμενο με `using`.

## Τι είναι το read PDF417 barcode c#;
`read pdf417 barcode c#` αναφέρεται στη διαδικασία χρήσης μιας βιβλιοθήκης .NET για την αποκωδικοποίηση συμβόλων PDF417 (συμπεριλαμβανομένου του Macro‑PDF417) από αρχεία εικόνας απευθείας σε κώδικα C#. Το Aspose.BarCode SDK παρέχει ένα API μονής κλήσης που διαχειρίζεται τη φόρτωση εικόνας, την ανίχνευση barcode και την εξαγωγή όλων των πεδίων που ορίζονται από το ISO.

## Γιατί να χρησιμοποιήσετε το Aspose.BarCode για την αποκωδικοποίηση PDF417;
Το Aspose.BarCode υποστηρίζει **30+ συμβολισμούς barcode** και μπορεί να επεξεργαστεί εικόνες έως **5000 × 5000 px** σε λιγότερο από **0.1 s** σε τυπικό εξοπλισμό διακομιστή. Παρέχει επίσης έτοιμη υποστήριξη περιστροφής, παραμόρφωσης και επεξεργασίας ανεστραμμένων barcode, εξαλείφοντας την ανάγκη για προσαρμοσμένη προεπεξεργασία εικόνας. Επιπλέον, η βιβλιοθήκη περιλαμβάνει ενσωματωμένη υποστήριξη για ανάγνωση επεκταμένων πεδίων Macro‑PDF417, καθιστώντας την μια ολοκληρωμένη λύση για σύνθετα σενάρια σάρωσης.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Core και .NET Framework).  
* Visual Studio 2022 (ή οποιονδήποτε επεξεργαστή προτιμάτε).  
* Το πακέτο NuGet **Aspose.BarCode for .NET** – αυτή είναι η βιβλιοθήκη που στην πραγματικότητα αναλύει το PDF417.  
* Μια δείγμα εικόνας που περιέχει ένα Macro‑PDF417 barcode (για παράδειγμα `ExtPDF417Meta.png`).  

Δεν απαιτείται επιπλέον ρύθμιση· η βιβλιοθήκη παρέχει όλους τους αποκωδικοποιητές που χρειάζεστε.

## Πώς να διαβάσετε το PDF417 barcode c#;

Φορτώστε την εικόνα με `BarCodeReader`, καθορίστε `DecodeType.MacroPdf417` και επαναλάβετε τη συλλογή `BarCodeResult` που επιστρέφεται – αυτή είναι η πλήρης λύση σε λιγότερο από δέκα γραμμές κώδικα. Ο αναγνώστης εξάγει αυτόματα τόσο τα απλά σύμβολα PDF417 όσο και τα επεκταμένα δεδομένα Macro‑PDF417, έτσι λαμβάνετε τα αναγνωριστικά αρχείων, αριθμούς τμημάτων, χρονικές σφραγίδες και αθροίσματα ελέγχου χωρίς πρόσθετη ανάλυση.

### Βήμα 1: εγκατάσταση Aspose.BarCode

Ανοίξτε το φάκελο του έργου σας σε ένα τερματικό και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Αυτή η εντολή κατεβάζει την πιο πρόσφατη σταθερή έκδοση (από τον Ιούλιο 2026 είναι η 23.12). Εάν προτιμάτε την κονσόλα Package Manager μέσα στο Visual Studio, χρησιμοποιήστε:

```powershell
Install-Package Aspose.BarCode
```

> **Συμβουλή:** κλειδώστε την έκδοση (`23.12.0`) στο αρχείο `.csproj` σας για να αποφύγετε τυχαίες αλλαγές που σπάζουν τη λειτουργία αργότερα.

### Βήμα 2: δημιουργία σκελετού εφαρμογής κονσόλας

Δημιουργήστε ένα νέο έργο κονσόλας εάν δεν το έχετε ήδη:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Αντικαταστήστε το αυτόματα δημιουργημένο `Program.cs` με τον κώδικα παρακάτω. Θα εξηγήσουμε κάθε τμήμα στις επόμενες ενότητες.

### Βήμα 3: γράψτε τον πλήρη κώδικα “πώς να διαβάσετε PDF417”

`BarCodeReader` είναι η κύρια κλάση που διαβάζει την εικόνα, εντοπίζει τα barcodes και επιστρέφει μια συλλογή από αντικείμενα `BarCodeResult`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — η κύρια κλάση που είναι υπεύθυνη για την ανάγνωση και αποκωδικοποίηση barcodes από εικόνες.  
* `DecodeType.MacroPdf417` — μια σημαία που λέει στο SDK να αντιμετωπίζει ειδικά το Macro‑PDF417 ενώ εξακολουθεί να επιστρέφει απλά σύμβολα PDF417.  
* `Extended.Pdf417.MacroPdf417` — το αντικείμενο που περιέχει κάθε προαιρετικό πεδίο που ορίζεται από το ISO/IEC 15438, όπως `FileID`, `SegmentID` και `Checksum`.

Το μπλοκ `using` εγγυάται ότι οι εγγενείς πόροι απελευθερώνονται, αποτρέποντας διαρροές μνήμης σε υπηρεσίες που τρέχουν για μεγάλο χρονικό διάστημα.

### Βήμα 4: εκτελέστε την εφαρμογή και επαληθεύστε την έξοδο

Από το τερματικό:

```bash
dotnet run
```

Θα πρέπει να δείτε κάτι όπως:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Εάν η εικόνα περιέχει περισσότερα από ένα barcode, ο βρόχος εκτυπώνει μια γραμμή διαχωριστικού (`----------------------------------------`) και συνεχίζει με το επόμενο αποτέλεσμα—ακριβώς όπως φαίνεται η λειτουργία **read multiple barcodes** στην πράξη.

## Συχνές ερωτήσεις & ειδικές περιπτώσεις

### Τι γίνεται αν η εικόνα έχει τόσο σύμβολα Macro‑PDF417 όσο και κανονικά PDF417;

Η ίδια κλήση `BarCodeReader` θα επιστρέψει και τα δύο. Μπορείτε να τα διακρίνετε ελέγχοντας το `result.CodeType` (`MacroPdf417` vs `Pdf417`). Οι επεκταμένες ιδιότητες θα είναι `null` για ένα απλό PDF417, έτσι ο έλεγχος `if (macro != null)` αποτρέπει ένα `NullReferenceException`.

### Το barcode μου είναι περιστραμμένο ή παραμορφωμένο—θα λειτουργήσει ακόμα ο αναγνώστης;

Το Aspose.BarCode περιλαμβάνει ενσωματωμένη αντιστάθμιση περιστροφής και παραμόρφωσης. Εφόσον το barcode καλύπτει τουλάχιστον το 30 % του πλάτους της εικόνας, ο αποκωδικοποιητής συνήθως θα πετύχει. Για ακραίες περιπτώσεις μπορείτε να ενεργοποιήσετε `reader.Options.AllowInvertedBarcodes = true;` πριν καλέσετε το `ReadBarCodes()`.

### Πώς να διαχειριστώ μεγάλες παρτίδες εικόνων;

Τυλίξτε τη λογική ανάγνωσης σε έναν βρόχο `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Το πρότυπο `using` εξασφαλίζει ότι οι εγγενείς πόροι κάθε εικόνας απελευθερώνονται πριν την επόμενη επανάληψη, διατηρώντας τη χρήση μνήμης χαμηλή.

## Πλήρης λίστα πηγαίου κώδικα (έτοιμη για αντιγραφή‑επικόλληση)

Παρακάτω βρίσκεται ολόκληρο το πρόγραμμα σε ένα μπλοκ για γρήγορη αντιγραφή‑επικόλληση. Δεν υπάρχουν κρυφές εξαρτήσεις—μόνο το πακέτο NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Ανακεφαλαίωση – τι καλύψαμε

* **Πώς να διαβάσετε το PDF417 barcode c#** χρησιμοποιώντας Aspose.BarCode.  
* Τα ακριβή βήματα για **διαβάσετε πολλαπλά barcodes** από μία εικόνα.  
* Πώς να **read barcode image c#** και να εξάγετε κάθε πεδίο Macro‑PDF417.  
* Συμβουλές για περιστροφή, επεξεργασία σε παρτίδες και διαχείριση ελλιπών επεκταμένων δεδομένων.

## Επόμενα βήματα & σχετικά θέματα

* **Encode PDF417** – δημιουργήστε τα δικά σας Macro‑PDF417 barcodes με `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – χρησιμοποιώντας την ίδια κλάση `BarCodeReader`.  
* **Integrate with ASP.NET Core** – εκθέστε ένα web endpoint που δέχεται μια ανεβασμένη εικόνα και επιστρέφει JSON με τα αποκωδικοποιημένα πεδία.  

### Πρόσθετοι χρήσιμοι σύνδεσμοι
- [Πώς να διαβάσετε DataMatrix Barcodes με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Πώς να δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Διαβάστε DataMatrix barcode C# – Δημιουργία DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Μη διστάσετε να πειραματιστείτε: αλλάξτε τη διαδρομή της εικόνας, τοποθετήστε ένα απλό PDF417 στον ίδιο φάκελο ή τροποποιήστε τις σημαίες `DecodeType` για να δείτε πώς συμπεριφέρεται η βιβλιοθήκη. Όσο περισσότερο παίζετε, τόσο πιο άνετοι θα γίνετε με σενάρια **read barcode image c#**.

Έχετε μια δύσκολη εικόνα που αρνείται να αποκωδικοποιηθεί; Αφήστε ένα σχόλιο παρακάτω ή ανοίξτε ένα issue στο αποθετήριο GitHub του δείγματος έργου. Καλή προγραμματιστική!

## Συχνές ερωτήσεις

**Q: Μπορώ να το χρησιμοποιήσω σε εμπορική εφαρμογή;**  
A: Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.BarCode σε εμπορικά έργα εφόσον έχετε έγκυρη άδεια· μια δωρεάν δοκιμή είναι διαθέσιμη για αξιολόγηση.

**Q: Ο αναγνώστης υποστηρίζει εικόνες με κωδικό πρόσβασης;**  
A: Το SDK λειτουργεί με οποιαδήποτε τυπική μορφή εικόνας· η προστασία με κωδικό δεν ισχύει για εικόνες raster, μόνο για PDFs, που διαχειρίζονται από ξεχωριστό στοιχείο Aspose.PDF.

**Q: Ποιες εκδόσεις .NET υποστηρίζονται;**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ και .NET 6+ υποστηρίζονται πλήρως από την τρέχουσα έκδοση του Aspose.BarCode.

**Q: Πώς μπορώ να βελτιώσω την απόδοση για πολύ μεγάλες παρτίδες εικόνων;**  
A: Ενεργοποιήστε `reader.Options.Quality = QualityMode.HighPerformance` και επεξεργαστείτε τις εικόνες παράλληλα χρησιμοποιώντας `Parallel.ForEach`, ενώ εξακολουθείτε να τυλίγετε κάθε `BarCodeReader` σε μπλοκ `using`.

**Q: Υπάρχει τρόπος να λάβω μόνο τα πεδία Macro‑PDF417 χωρίς να επαναλαμβάνω όλα τα αποτελέσματα;**  
A: Ναι – μετά την κλήση του `ReadBarCodes()`, φιλτράρετε τη συλλογή με `result => result.CodeType == DecodeType.MacroPdf417` και στη συνέχεια προσπελάστε την ιδιότητα `Extended.Pdf417.MacroPdf417`.

---

**Τελευταία ενημέρωση:** 2026-09-28  
**Δοκιμή με:** Aspose.BarCode 23.12 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε εικόνα Barcode Pdf417 σε C με Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Δημιουργία Pdf417 Barcode με Aspose Barcode – Οδηγός βήμα‑βήμα](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Διαβάστε πολλαπλά Barcodes C – Πλήρης οδηγός με Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}