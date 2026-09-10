---
category: general
date: 2026-07-15
description: Πώς να διαβάσετε το barcode PDF417 σε C# και να διαβάσετε πολλαπλά barcodes
  από μια εικόνα. Μάθετε πώς να διαβάζετε εικόνα barcode σε C# με λεπτομερή κώδικα
  και συμβουλές.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: el
lastmod: 2026-07-15
og_description: Πώς να διαβάσετε τον κώδικα PDF417 σε C# γρήγορα. Αυτός ο οδηγός σας
  δείχνει πώς να διαβάσετε πολλαπλούς κώδικες από μία εικόνα και να αποκωδικοποιήσετε
  κάθε ιδιότητα.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα κώδικα & Εξήγηση
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
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
title: Πώς να διαβάσετε PDF417 σε C# – Πλήρης οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαβάσετε PDF417 σε C# – Πλήρης Οδηγός Βήμα‑Βήμα

Έχετε αναρωτηθεί ποτέ **πώς να διαβάσετε PDF417** από μια εικόνα χρησιμοποιώντας C#; Δεν είστε οι μόνοι. Οι περισσότεροι προγραμματιστές συναντούν δυσκολίες όταν πρέπει να εξάγουν τα επεκταμένα πεδία Macro‑PDF417 από ένα σαρωμένο έγγραφο. Τα καλά νέα; Με λίγες μόνο γραμμές κώδικα μπορείτε να αποκωδικοποιήσετε ένα PDF417, να διαβάσετε πολλαπλά barcode στην ίδια εικόνα και να πάρετε κάθε κρυφή ιδιότητα που προσφέρει η προδιαγραφή.

Σε αυτό το tutorial θα περάσουμε από ένα πραγματικό παράδειγμα που δείχνει **πώς να διαβάσετε PDF417**, πώς να **διαβάσετε πολλαπλά barcode** από ένα μόνο αρχείο, και γιατί ο κώδικας **read barcode image C#** φαίνεται όπως είναι. Στο τέλος θα έχετε μια έτοιμη για εκτέλεση εφαρμογή console που εκτυπώνει κάθε πληροφορία που μπορεί να χρειαστείτε — ID αρχείου, ID τμήματος, checksum, χρονικές σφραγίδες, ό,τι θέλετε.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Core και .NET Framework).  
* Visual Studio 2022 (ή οποιονδήποτε επεξεργαστή προτιμάτε).  
* Το πακέτο NuGet **Aspose.BarCode for .NET** – αυτή είναι η βιβλιοθήκη που πραγματικά αναλύει PDF417.  
* Μια δείγμα εικόνας που περιέχει ένα Macro‑PDF417 barcode (π.χ. `ExtPDF417Meta.png`).  

Δεν απαιτείται πρόσθετη διαμόρφωση· η βιβλιοθήκη περιλαμβάνει όλους τους αποκωδικοποιητές που χρειάζεστε.

## Βήμα 1: Εγκατάσταση Aspose.BarCode

Ανοίξτε το φάκελο του έργου σας σε ένα τερματικό και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Αυτή η εντολή κατεβάζει την πιο πρόσφατη σταθερή έκδοση (ως Ιούλιο 2026 είναι η 23.12). Αν προτιμάτε την Package Manager Console μέσα στο Visual Studio, χρησιμοποιήστε:

```powershell
Install-Package Aspose.BarCode
```

> **Συμβουλή:** κλειδώστε την έκδοση (`23.12.0`) στο `.csproj` σας για να αποφύγετε τυχαίες αλλαγές που θα σπάσουν τη λειτουργία αργότερα.

## Βήμα 2: Δημιουργία Σκελετού Εφαρμογής Console

Δημιουργήστε ένα νέο έργο console αν δεν έχετε ήδη ένα:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Αντικαταστήστε το αυτόματα δημιουργημένο `Program.cs` με τον κώδικα παρακάτω. Θα εξηγήσουμε κάθε τμήμα στις επόμενες ενότητες.

## Βήμα 3: Γράψτε τον Πλήρη Κώδικα “Πώς να Διαβάσετε PDF417”

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

### Γιατί Λειτουργεί Αυτός ο Κώδικας

* **`BarCodeReader`** είναι η κεντρική κλάση που διαβάζει την εικόνα, ανιχνεύει barcode και επιστρέφει μια συλλογή αντικειμένων `BarCodeResult`.  
* Η μεταβίβαση του **`DecodeType.MacroPdf417`** λέει στη βιβλιοθήκη να αντιμετωπίζει ειδικά το Macro‑PDF417· εξακολουθεί να επιστρέφει απλά σύμβολα PDF417, το οποίο ικανοποιεί την απαίτηση **read multiple barcodes**.  
* Το αντικείμενο **`Extended.Pdf417.MacroPdf417`** περιέχει κάθε προαιρετικό πεδίο που ορίζεται από το πρότυπο ISO/IEC 15438 – εκεί παίρνετε `FileID`, `SegmentID`, `Checksum`, κλπ.  
* Το μπλοκ `using` εγγυάται ότι οι εγγενείς πόροι απελευθερώνονται, αποτρέποντας διαρροές μνήμης σε υπηρεσίες που τρέχουν για μεγάλο χρονικό διάστημα.

## Βήμα 4: Εκτέλεση της Εφαρμογής και Επαλήθευση του Αποτελέσματος

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

Αν η εικόνα περιέχει περισσότερα από ένα barcode, ο βρόχος θα εκτυπώσει μια γραμμή διαχωριστή (`----------------------------------------`) και θα συνεχίσει με το επόμενο αποτέλεσμα — ακριβώς όπως φαίνεται η λειτουργία **read multiple barcodes** στην πράξη.

## Συχνές Ερωτήσεις & Ακραίες Περιπτώσεις

### Τι γίνεται αν η εικόνα έχει τόσο Macro‑PDF417 όσο και κανονικά σύμβολα PDF417;

Η ίδια κλήση `BarCodeReader` θα επιστρέψει και τα δύο. Μπορείτε να τα διακρίνετε ελέγχοντας το `result.CodeType` (`MacroPdf417` vs `Pdf417`). Οι επεκταμένες ιδιότητες θα είναι `null` για ένα απλό PDF417, έτσι ο έλεγχος `if (macro != null)` αποτρέπει ένα `NullReferenceException`.

### Το barcode μου είναι περιστραμμένο ή παραμορφωμένο — θα λειτουργήσει ακόμα ο αναγνώστης;

Το Aspose.BarCode περιλαμβάνει ενσωματωμένη αντιστάθμιση περιστροφής και παραμόρφωσης. Όσο το barcode είναι τουλάχιστον 30 % του πλάτους της εικόνας, ο αποκωδικοποιητής συνήθως θα πετύχει. Για ακραίες περιπτώσεις μπορείτε να ενεργοποιήσετε `reader.Options.AllowInvertedBarcodes = true;` πριν καλέσετε το `ReadBarCodes()`.

### Πώς να διαχειριστώ μεγάλες παρτίδες εικόνων;

Τυλίξτε τη λογική ανάγνωσης σε έναν βρόχο `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Το πρότυπο `using` εξασφαλίζει ότι οι εγγενείς πόροι κάθε εικόνας απελευθερώνονται πριν την επόμενη επανάληψη, διατηρώντας τη χρήση μνήμης χαμηλή.

## Πλήρης Λίστα Πηγαίου Κώδικα (Έτοιμη για Αντιγραφή‑Επικόλληση)

Παρακάτω βρίσκεται ολόκληρο το πρόγραμμα σε ένα μπλοκ για γρήγορη αντιγραφή‑επικόλληση. Δεν υπάρχουν κρυφές εξαρτήσεις — μόνο το πακέτο NuGet Aspose.BarCode.

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

## Ανακεφαλαίωση – Τι Καλύψαμε

* **How to read PDF417** χρησιμοποιώντας Aspose.BarCode σε C#.  
* Τα ακριβή βήματα για **read multiple barcodes** από μια μόνο εικόνα.  
* Πώς να **read barcode image C#** και να εξάγετε κάθε πεδίο Macro‑PDF417.  
* Συμβουλές για περιστροφή, επεξεργασία παρτίδων και διαχείριση ελλιπών επεκταμένων δεδομένων.

## Επόμενα Βήματα & Σχετικά Θέματα

* **Encode PDF417** – δημιουργήστε τα δικά σας Macro‑PDF417 barcode με το `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – χρησιμοποιώντας την ίδια κλάση `BarCodeReader`.  
* **Integrate with ASP.NET Core** – εκθέστε ένα web endpoint που δέχεται μια ανεβασμένη εικόνα και επιστρέφει JSON με τα αποκωδικοποιημένα πεδία.  

Μη διστάσετε να πειραματιστείτε: αλλάξτε τη διαδρομή της εικόνας, τοποθετήστε ένα απλό PDF417 στον ίδιο φάκελο, ή τροποποιήστε τις σημαίες `DecodeType` για να δείτε πώς συμπεριφέρεται η βιβλιοθήκη. Όσο περισσότερο παίζετε, τόσο πιο άνετοι θα γίνετε με σενάρια **read barcode image C#**.

Έχετε μια δύσκολη εικόνα που δεν αποκωδικοποιείται; Αφήστε ένα σχόλιο παρακάτω ή ανοίξτε ένα ζήτημα στο αποθετήριο GitHub του δείγματος έργου. Καλή προγραμματιστική!

## Τι Πρέπει Να Μάθετε Στη Σύντομη Μελλοντική;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να Διαβάσετε DataMatrix Barcodes με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Πώς να Δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Διαβάστε DataMatrix barcode C# – Δημιουργία DataMatrix Mode (Αυτόματο)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}