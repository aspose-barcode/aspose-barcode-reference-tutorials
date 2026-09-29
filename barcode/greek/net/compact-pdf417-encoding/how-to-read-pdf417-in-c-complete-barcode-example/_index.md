---
category: general
date: 2026-07-27
description: Πώς να διαβάσετε γρήγορα το barcode PDF417 σε C#. Μάθετε να διαβάζετε
  πολλαπλά barcodes, να αποκωδικοποιείτε εικόνες και να λαμβάνετε τα μεταδεδομένα
  Macro PDF417 σε ένα πλήρες παράδειγμα barcode σε C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: el
lastmod: 2026-07-27
og_description: Πώς να διαβάσετε τον κωδικό PDF417 σε C# με αυτόν τον οδηγό βήμα‑βήμα.
  Αποκωδικοποιήστε εικόνες, διαχειριστείτε πολλαπλούς κωδικούς και εξάγετε τα μεταδεδομένα
  Macro PDF417 σε ένα έτοιμο παράδειγμα.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα barcode
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Πώς να διαβάσετε PDF417 σε C# – Πλήρες παράδειγμα γραμμωτού κώδικα
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να Διαβάσετε PDF417 σε C# – Πλήρες Παράδειγμα Barcode

Έχετε αναρωτηθεί **πώς να διαβάσετε το barcode PDF417** σε μια εφαρμογή C# χωρίς να τσακώσετε τα μαλλιά σας; Δεν είστε οι μόνοι. Είτε δημιουργείτε έναν σαρωτή λογιστικής, έναν ελεγκτή εισιτηρίων, είτε απλώς χρειάζεστε να εξάγετε δεδομένα από ένα PDF417‑κωδικοποιημένο αναγνωριστικό, η διαδικασία μπορεί αρχικά να φαίνεται μυστηριώδης.

Σε αυτό το tutorial θα περάσουμε από ένα **c# barcode example** που διαβάζει μια εικόνα PDF417, διαχειρίζεται **read multiple barcodes** εάν υπάρχουν, και εξάγει όλα τα χρήσιμα μεταδεδομένα Macro PDF417 που ίσως χρειαστείτε.

## Τι Θα Κατασκευάσετε

Στο τέλος αυτού του οδηγού θα έχετε ένα μικρό πρόγραμμα κονσόλας που:

1. Φορτώνει μια εικόνα barcode από το δίσκο.  
2. Αποκωδικοποιεί **PDF417** (συμπεριλαμβανομένων των Macro PDF417) barcodes.  
3. Εκτυπώνει βασικές πληροφορίες όπως τύπο κώδικα και κείμενο.  
4. Εξάγει το πλήρες σύνολο πεδίων Macro PDF417 (File ID, Segment ID, checksum, κ.λπ.).  

Χωρίς εξωτερικές υπηρεσίες, μόνο ένα πακέτο NuGet και μερικές γραμμές C#.

## Προαπαιτούμενα – Τι Χρειάζεστε Πριν Ξεκινήσετε

- **.NET 6.0** ή νεότερο (ο κώδικας λειτουργεί επίσης σε .NET Framework 4.6+).  
- Μια πρόσφατη έκδοση της βιβλιοθήκης **Aspose.BarCode for .NET** – εγκαταστήστε την μέσω NuGet (`Install-Package Aspose.BarCode`).  
- Ένα αρχείο εικόνας που περιέχει barcode PDF417 (το demo χρησιμοποιεί `ExtPDF417Meta.png`).  
- Βασική κατανόηση των εφαρμογών κονσόλας C# (αν έχετε γράψει “Hello World”, είστε έτοιμοι).

> **Pro tip:** Αν δεν έχετε δείγμα PDF417, δημιουργήστε ένα στην ιστοσελίδα demo της Aspose ή χρησιμοποιήστε μια εφαρμογή smartphone που μπορεί να δημιουργήσει ετικέτες PDF417.

## Βήμα 1: Ρύθμιση του Έργου και Εγκατάσταση της Βιβλιοθήκης

Πρώτα, δημιουργήστε ένα νέο έργο κονσόλας:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Αυτό φέρνει τις εξαρτήσεις του **c# barcode example** που χρειαζόμαστε. Ανοίξτε το `Program.cs` και αντικαταστήστε τον προεπιλεγμένο κώδικα με το σκελετό παρακάτω:

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Βήμα 2: Αρχικοποίηση του Barcode Reader για PDF417

Η καρδιά της λύσης είναι η κλάση `BarCodeReader`. Της λέμε ποιο αρχείο να σαρώσει και ποιον τύπο barcode μας ενδιαφέρει — σε αυτήν την περίπτωση `DecodeType.Pdf417` ή την παραλλαγή macro `DecodeType.MacroPdf417`. Η χρήση του macro τύπου εξασφαλίζει ότι θα πιάσουμε τα εκτεταμένα πεδία.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Γιατί να χρησιμοποιήσετε `MacroPdf417` αντί για απλό `Pdf417`; Το Macro PDF417 μεταφέρει επιπλέον μεταδεδομένα (File ID, αριθμός τμημάτων, χρονικές σφραγίδες κ.λπ.) που πολλές πραγματικές εφαρμογές εξαρτώνται — σκεφτείτε τα φορτωτικά manifest που χωρίζονται σε πολλές σελίδες.

## Βήμα 3: Ανάγνωση Όλων των Barcodes που Βρέθηκαν στην Εικόνα

Μια μόνο εικόνα μπορεί να περιέχει **read multiple barcodes** — ίσως ένα QR code δίπλα σε PDF417. Η μέθοδος `ReadBarCodes()` επιστρέφει ένα `IEnumerable<BarCodeResult>` που μπορούμε να διατρέξουμε.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Αν η εικόνα περιέχει μόνο ένα PDF417, η επανάληψη εκτελείται μία φορά, διατηρώντας τον κώδικα ευέλικτο για μελλοντικά σενάρια όπου μπορεί να χρειαστείτε **read multiple barcodes** από την ίδια σάρωση.

## Βήμα 4: Εμφάνιση Βασικών Πληροφοριών Barcode

Πριν βυθιστούμε στα macro πεδία, είναι χρήσιμο να δείξουμε τον τύπο barcode και το αποκωδικοποιημένο κείμενο. Αυτό σας βοηθά να επαληθεύσετε ότι ο αναγνώστης αναγνώρισε πράγματι ένα PDF417 και όχι κάποια άλλη συμβολική.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

Η ιδιότητα `CodeTypeName` θα διαβάσει *MacroPdf417* (ή *Pdf417* αν δεν έχει οριστεί η σημαία macro), ενώ το `CodeText` περιέχει τα ακατέργαστα δεδομένα που κωδικοποιήθηκαν στο barcode.

## Βήμα 5: Εξαγωγή Μεταδεδομένων Macro PDF417

Η ιδιότητα `Extended` σας δίνει μια βαθιά ματιά στη δομή PDF417‑specific. Κάθε πεδίο που τυπώνουμε παρακάτω αντιστοιχεί άμεσα στην προδιαγραφή macro του PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Κάθε γραμμή εξάγει ένα διαφορετικό κομμάτι του macro payload:

- **FileID** – ένας μοναδικός αναγνωριστής για ολόκληρο το σύνολο εγγράφων.  
- **SegmentID** – ποιο τμήμα του πολυ‑τμηματικού αρχείου βλέπετε.  
- **SegmentsCount** – συνολικός αριθμός τμημάτων που αναμένονται.  
- **FileName, Checksum, FileSize** – χρήσιμα για την επαλήθευση της ακεραιότητας του μεταφερόμενου αρχείου.  
- **TimeStamp, Addressee, Sender** – προαιρετικά πεδία που πολλές λογιστικές συστήματα ενσωματώνουν.  

Αν κάποιο από αυτά τα πεδία λείπει στο barcode προέλευσης, η βιβλιοθήκη επιστρέφει `null` ή `0`, τα οποία μπορείτε να διαχειριστείτε όπως χρειάζεται.

## Βήμα 6: Εκτέλεση του Πλήρους Παραδείγματος

Συνδυάζοντας όλα τα παραπάνω, εδώ είναι το πλήρες, έτοιμο‑για‑εκτέλεση πρόγραμμα:

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Αναμενόμενη Έξοδος

Όταν τρέξετε το πρόγραμμα με ένα έγκυρο `ExtPDF417Meta.png`, θα πρέπει να δείτε κάτι παρόμοιο με:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Αν η εικόνα περιέχει περισσότερα από ένα barcode,

## Τι Πρέπει να Μάθετε Στη Σύντομη Μελλοντική

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}