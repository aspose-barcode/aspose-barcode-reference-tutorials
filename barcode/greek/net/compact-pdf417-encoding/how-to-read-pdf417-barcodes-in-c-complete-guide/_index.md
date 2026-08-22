---
category: general
date: 2026-08-22
description: Πώς να διαβάσετε κωδικούς PDF417 σε C# με έναν οδηγό βήμα‑βήμα, καλύπτοντας
  πώς να διαβάσετε πολλαπλούς κωδικούς από μια εικόνα και να εξάγετε λεπτομέρειες
  MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: el
lastmod: 2026-08-22
og_description: Πώς να διαβάσετε γρήγορα κώδικες PDF417 σε C#. Αυτό το σεμινάριο σας
  δείχνει πώς να διαβάσετε πολλαπλούς κώδικες από μια εικόνα και να ανακτήσετε τις
  εκτεταμένες πληροφορίες MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Πώς να διαβάζετε κωδικούς PDF417 σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να διαβάσετε κωδικούς PDF417 σε C# – πλήρης οδηγός
url: /el/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε κωδικούς PDF417 σε C# – πλήρης οδηγός

Αν χρειάζεστε **πώς να διαβάσετε PDF417** μπαρ σε μια εφαρμογή .NET, αυτό το tutorial σας παρέχει μια έτοιμη λύση. Θα μάθετε πώς να διαβάζετε πολλαπλούς κωδικούς από μία εικόνα, να εξάγετε το πλήρες σύνολο δεδομένων MacroPdf417 και να το εμφανίσετε στην κονσόλα. Η προσέγγιση λειτουργεί με τη βιβλιοθήκη Aspose.BarCode for .NET και απαιτεί μόνο λίγες γραμμές κώδικα.

Η ανάγνωση κωδικών από εικόνα είναι μια συνηθισμένη εργασία σε συστήματα απογραφής, επικύρωση εισιτηρίων και διαχείριση εγγράφων. Στο τέλος αυτού του οδηγού θα μπορείτε να αποκωδικοποιήσετε οποιονδήποτε κωδικό PDF417 ή MacroPdf417, να χειριστείτε πολλούς κωδικούς σε μία εικόνα και να κατανοήσετε τα εκτεταμένα πεδία που παρέχει το MacroPdf417.

## Προαπαιτούμενα

- .NET 6.0 SDK ή νεότερο (ο κώδικας συντάσσεται επίσης με .NET Framework 4.7+)
- Visual Studio 2022 ή οποιονδήποτε επεξεργαστή C# προτιμάτε
- Πακέτο NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Ένα δείγμα εικόνας που περιέχει κωδικό MacroPdf417 (π.χ., `MacroPdf417.png`)

Δεν απαιτείται πρόσθετη ρύθμιση· η βιβλιοθήκη διαχειρίζεται την φόρτωση εικόνας και την αποκωδικοποίηση εσωτερικά.

## Πώς να διαβάσετε κωδικούς PDF417 από εικόνα σε C#

Ο πυρήνας της λύσης είναι η κλάση `BarCodeReader`. Ανοίγει την εικόνα, εντοπίζει όλους τους κωδικούς του καθορισμένου τύπου και επιστρέφει μια συλλογή αντικειμένων `BarCodeResult`. Ο παρακάτω κώδικας δείχνει ένα πλήρες πρόγραμμα κονσόλας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Γιατί κάθε γραμμή είναι σημαντική

| Βήμα | Σκοπός |
|------|--------|
| **1️⃣ Initialize** | Δημιουργεί ένα `BarCodeReader` δεσμευμένο στο αρχείο εικόνας και περιορίζει την ανίχνευση στη συμβολή MacroPdf417, κάτι που επιταχύνει την επεξεργασία. |
| **2️⃣ Iterate** | Η `ReadBarCodes()` επιστρέφει **όλους** τους κωδικούς που ταιριάζουν με τον ζητούμενο τύπο, επιτρέποντάς σας να **διαβάσετε πολλαπλούς κωδικούς** χωρίς επιπλέον βρόχους. |
| **3️⃣ Basic output** | Εμφανίζει το γενικό `CodeTypeName` και το ανθρώπινα αναγνώσιμο `CodeText`. Αυτό είναι χρήσιμο για καταγραφή ή γρήγορη επαλήθευση. |
| **4️⃣ Extended data** | Το MacroPdf417 μεταφέρει πρόσθετα μεταδεδομένα (αριθμός αρχείου, αριθμός τμημάτων, χρονικές σφραγίδες κ.λπ.). Το αντικείμενο `Extended.Pdf417` εκθέτει κάθε πεδίο άμεσα, ώστε να μπορείτε να το αποθηκεύσετε ή να επαληθεύσετε ολόκληρο το πακέτο δεδομένων. |

Η εκτέλεση του προγράμματος με μια έγκυρη εικόνα MacroPdf417 παράγει έξοδο κονσόλας παρόμοια με την παρακάτω:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Η έξοδος επιβεβαιώνει ότι η βιβλιοθήκη διάβασε επιτυχώς τον κωδικό, εξήγαγε το κείμενο και παρείχε κάθε πεδίο MacroPdf417.

## Ανάγνωση πολλαπλών κωδικών από μία εικόνα

Πολλά πραγματικά σενάρια τοποθετούν αρκετά σύμβολα PDF417 σε μία ετικέτα — σκεφτείτε ένα φορτωτικό δελτίο που περιέχει κωδικό μεταφορέα, αριθμό παρακολούθησης και δήλωση τελωνείου. Ο ίδιος κώδικας παραπάνω ήδη **διαβάζει πολλαπλούς κωδικούς** επειδή η `ReadBarCodes()` επιστρέφει ένα enumerable με όλα τα αποτελέσματα. Δεν απαιτείται πρόσθετη ρύθμιση· χρειάζεται μόνο να επαναλάβετε τα αποτελέσματα, όπως δείχνεται.

Αν θέλετε να περιορίσετε τον αναγνώστη σε τυπικό PDF417 (μη‑macro) ενώ εξακολουθείτε να διαχειρίζεστε πολλούς κωδικούς, αντικαταστήστε το `DecodeType.MacroPdf417` με `DecodeType.Pdf417`. Η υπόλοιπη λογική παραμένει αμετάβλητη.

## Κατανόηση των εκτεταμένων δεδομένων MacroPdf417

Το MacroPdf417 είναι μια επέκταση της κανονικής προδιαγραφής PDF417. Διασπά μεγάλα payloads σε πολλαπλά τμήματα και προσθέτει μια μικρή κεφαλίδα που περιγράφει ολόκληρο το αρχείο. Τα πιο σημαντικά πεδία είναι:

- **MacroPdf417FileID** – μοναδικό αναγνωριστικό που μοιράζεται από όλα τα τμήματα του ίδιου αρχείου.
- **MacroPdf417SegmentID** – ο αριθμός σειράς του τρέχοντος τμήματος.
- **MacroPdf417SegmentsCount** – συνολικός αριθμός τμημάτων που αναμένονται.
- **MacroPdf417FileName** – προαιρετικό όνομα αρχείου που μεταδίδεται με τον κωδικό.
- **MacroPdf417Checksum** – τιμή ελέγχου σφαλμάτων για ολόκληρο το αρχείο.
- **MacroPdf417FileSize** – μέγεθος του αρχικού δυαδικού payload.
- **MacroPdf417TimeStamp** – χρονική σφραγίδα ISO‑8601 όταν δημιουργήθηκε ο κωδικός.
- **MacroPdf417Addressee / Sender** – προαιρετικά κείμενα για δρομολόγηση.
- **MacroPdf417Terminator** – υποδεικνύει αν αυτό το τμήμα είναι το τελευταίο.

Όταν λάβετε όλα τα τμήματα, μπορείτε να επανασυνθέσετε το αρχικό αρχείο ταξινομώντας τα κατά `MacroPdf417SegmentID` και συνενώνοντας τις τιμές `CodeText`. Η λογική αυτή είναι απλή στην υλοποίηση μόλις έχετε τα πεδία διαθέσιμα.

## Συνηθισμένα προβλήματα και επαγγελματικές συμβουλές

- **Η ποιότητα της εικόνας μετρά** – εικόνες χαμηλής ανάλυσης ή έντονης συμπίεσης PNG/JPEG μπορούν να προκαλέσουν χαμένες ανιχνεύσεις. Χρησιμοποιήστε DPI τουλάχιστον 300 dpi για τυπωμένους κωδικούς.
- **Μικτές συμβολές** – αν η εικόνα περιέχει τόσο MacroPdf417 όσο και κανονικό PDF417, δημιουργήστε δύο αναγνώστες (έναν για κάθε `DecodeType`) ή χρησιμοποιήστε `DecodeType.AllSupported` και φιλτράρετε τα αποτελέσματα με `result.CodeTypeName`.
- **Χρήση μνήμης** – η δήλωση `using` απελευθερώνει άμεσα το `BarCodeReader`, αποτρέποντας μεγάλους buffer εικόνας να παραμένουν στη μνήμη.
- **Ασφάλεια νήματος** – το `BarCodeReader` δεν είναι thread‑safe. Δημιουργήστε ξεχωριστό στιγμιότυπο ανά νήμα αν αποκωδικοποιείτε εικόνες παράλληλα.
- **Διαχείριση σφαλμάτων** – τυλίξτε την κλήση `ReadBarCodes()` σε try/catch για να συλλάβετε `BarCodeException` σε κατεστραμμένες εικόνες.

## Συνοπτικό παράδειγμα πλήρους κώδικα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε σε ένα νέο έργο κονσόλας. Περιλαμβάνει όλες τις οδηγίες `using`, μια σταθερά για τη διαδρομή της εικόνας και το πρότυπο διαχείρισης πόρων.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Συγκεντρώστε με `dotnet build` και τρέξτε με `dotnet run`. Η κονσόλα θα εκτυπώσει τα βασικά δεδομένα κάθε κωδικού και το πλήρες payload MacroPdf417.

## Επόμενα βήματα

- **Ανασυνθέστε αρχεία multipart** – συλλέξτε όλα τα τμήματα, ταξινομήστε τα κατά `MacroPdf417SegmentID` και συνενώστε το `CodeText` για να δημιουργήσετε το αρχικό αρχείο.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην δική σας υλοποίηση.

- [Πώς να δημιουργήσετε κωδικό PDF417 – Συμπαγής κωδικοποίηση PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Πώς να διαβάσετε κωδικούς PDF417 με τουρκικούς χαρακτήρες σε Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Πώς να χρησιμοποιήσετε Aspose για κωδικό PDF417 (Κινέζικα) σε Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}