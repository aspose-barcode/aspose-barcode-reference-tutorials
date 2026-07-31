---
category: general
date: 2026-07-30
description: Διαβάστε πολλαπλούς κωδικούς γραμμής C# χρησιμοποιώντας το Aspose.BarCode.
  Μάθετε βήμα‑βήμα πώς να αποκωδικοποιήσετε PDF417, να εντοπίσετε τη συμπαγή λειτουργία
  και να διαχειριστείτε πολλούς κωδικούς γραμμής σε μία εικόνα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read multiple barcodes c#
- BarCodeReader C#
- PDF417 decoding
- barcode compact mode
- C# barcode library
language: el
lastmod: 2026-07-30
og_description: Διαβάστε πολλαπλούς γραμμικούς κώδικες C# με το Aspose.BarCode. Αυτός
  ο οδηγός σας δείχνει πώς να αποκωδικοποιήσετε όλους τους γραμμικούς κώδικες σε μια
  εικόνα, να ελέγξετε τη λειτουργία compact και να ενσωματώσετε σε εφαρμογές .NET.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Ανάγνωση πολλαπλών γραμμωτών κωδίκων C# – Πλήρης οδηγός για PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  headline: Read Multiple Barcodes C# – Complete Guide with PDF417
  type: TechArticle
- description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  name: Read Multiple Barcodes C# – Complete Guide with PDF417
  steps:
  - name: Why This Code Works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No Barcodes Detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely Large Images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑Safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Ανάγνωση Πολλαπλών Γραμμωτών Κωδίκων C# – Πλήρης Οδηγός με PDF417
url: /el/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ανάγνωση Πολλαπλών Barcode C# – Πλήρης Οδηγός με PDF417

Έχετε αναρωτηθεί ποτέ πώς να **διαβάσετε πολλαπλά barcode C#** από μία μόνο εικόνα; Ίσως έχετε μια δέσμη ετικετών αποστολής, ένα κολάζ εισιτηρίων ή ένα έγγραφο PDF417 που περιέχει αρκετούς κώδικες σε μία φωτογραφία. Στην καθημερινή μου δουλειά, αντιμετώπισα ακριβώς αυτό το πρόβλημα—μέχρι που ανακάλυψα το `BarCodeReader` του Aspose.BarCode. Αυτό το tutorial θα σας καθοδηγήσει στη αποκωδικοποίηση κάθε barcode σε μια εικόνα, στον εντοπισμό του αν κάθε PDF417 είναι σε συμπαγή (truncated) λειτουργία, και στη σωστή διαχείριση των αποτελεσμάτων.

Θα προσθέσουμε επίσης μερικές επιπλέον συμβουλές—όπως τι να κάνετε όταν η εικόνα περιέχει διαφορετικές συμβολές barcode, ή όταν μια σάρωση δεν επιστρέφει κανένα αποτέλεσμα. Στο τέλος θα έχετε μια έτοιμη για εκτέλεση εφαρμογή console που **διαβάζει πολλαπλά barcode C#** σαν επαγγελματίας.

## Τι Θα Χρειαστείτε

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω στο μηχάνημά σας:

- **.NET 6.0** SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+, αλλά το .NET 6 είναι η ιδανική επιλογή).
- **Aspose.BarCode for .NET** πακέτο NuGet (`Install-Package Aspose.BarCode`).
- Ένα δείγμα εικόνας που περιέχει **PDF417** barcode—κατά προτίμηση μια που συνδυάζει συμπαγή και πλήρους μεγέθους σύμβολα. Το tutorial χρησιμοποιεί το `CompactPdf417.png`, αλλά οποιοδήποτε PNG/JPEG θα δουλέψει.
- Το αγαπημένο σας IDE (Visual Studio, Rider ή VS Code).  

Αυτό είναι όλο—χωρίς επιπλέον DLLs, χωρίς εγγενείς εξαρτήσεις. Το Aspose.BarCode είναι καθαρά managed code, οπότε μπορείτε να το ενσωματώσετε σε οποιοδήποτε .NET project.

![Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Κείμενο alt εικόνας: Ανάγνωση πολλαπλών barcode C# – στιγμιότυπο οθόνης console που εμφανίζει την κατάσταση συμπαγούς λειτουργίας για barcode PDF417.*

## Βήμα 1 – Εγκατάσταση και Αναφορά της Βιβλιοθήκης BarCodeReader C#

Πρώτα απ' όλα, χρειάζεστε την κλάση **BarCodeReader C#** που τροφοδοτεί την αποκωδικοποίηση. Ανοίξτε το τερματικό σας (ή το Package Manager Console) και τρέξτε:

```powershell
dotnet add package Aspose.BarCode
```

Ή, αν βρίσκεστε μέσα στον NuGet manager του Visual Studio, απλώς ψάξτε για *Aspose.BarCode* και πατήστε **Install**. Αυτό θα κατεβάσει την πιο πρόσφατη σταθερή έκδοση (από τον Ιούλιο 2026 είναι η 23.9), η οποία υποστηρίζει PDF417, QR, DataMatrix και δεκάδες άλλες συμβολές.

Γιατί είναι σημαντικό: η βιβλιοθήκη αφαιρεί το βάρος της επεξεργασίας εικόνας, της διόρθωσης σφαλμάτων και της αναγνώρισης συμβόλων. Θα μπορούσατε να γράψετε το δικό σας scanner, αλλά θα ξοδέψετε εβδομάδες κυνηγώντας edge‑cases. Το Aspose σας προσφέρει μια δοκιμασμένη, **C# barcode library** που έχει ενημερωθεί για σύγχρονες .NET εκδόσεις.

## Βήμα 2 – Δημιουργία Ελάχιστου Project Console

Δημιουργήστε μια νέα εφαρμογή console ώστε να εστιάσουμε μόνο στη λογική του barcode χωρίς περιττό UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Αντικαταστήστε το παραγόμενο `Program.cs` με το πλήρες παράδειγμα παρακάτω. Μπορείτε να κρατήσετε το προεπιλεγμένο namespace ή να το μετονομάσετε—δεν απαιτείται κάτι ιδιαίτερο.

## Βήμα 3 – Υλοποίηση του Πλήρους “Read Multiple Barcodes C#”

Παρακάτω υπάρχει ένα **πλήρες, εκτελέσιμο** δείγμα κώδικα. Καλύπτει όλα τα τέσσερα βήματα από το αρχικό απόσπασμα, προσθέτει διαχείριση σφαλμάτων και εκτυπώνει χρήσιμες διαγνώσεις.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Γιατί Λειτουργεί Αυτός ο Κώδικας

- **`BarCodeReader`** είναι το κεντρικό στοιχείο του **BarCodeReader C#** API. Ανοίγει την εικόνα, εφαρμόζει προεπεξεργασία και ψάχνει για σύμβολα του τύπου που καθορίζετε.
- **`ReadBarCodes()`** επιστρέφει έναν πίνακα, όχι μόνο ένα μοναδικό αποτέλεσμα. Αυτό είναι το κλειδί για **ανάγνωση πολλαπλών barcode C#**—η μέθοδος συλλέγει αυτόματα κάθε αντιστοίχηση που βρίσκει.
- **`result.Extended.Pdf417.IsTruncated`** μας λέει αν το PDF417 είναι σε *συμπαγή* (δηλαδή truncated) λειτουργία. Αυτή η σημαία υπάρχει μόνο για PDF417, γι' αυτό χρησιμοποιούμε τον τελεστή null‑conditional (`?.`) ώστε να αποφύγουμε εξαιρέσεις αν εμφανιστεί άλλη συμβολή.
- Ο βρόχος `foreach` εκτυπώνει τόσο το αποκωδικοποιημένο κείμενο όσο και την κατάσταση συμπαγούς λειτουργίας, παρέχοντας έναν γρήγορο έλεγχο.

## Βήμα 4 – Διαχείριση Διαφορετικών Τύπων Barcode (Προαιρετικό)

Αν η εικόνα σας μπορεί να περιέχει περισσότερα από PDF417, απλώς αλλάξτε το δεύτερο όρισμα του `BarCodeReader` σε `DecodeType.AllSupported`. Ο βρόχος παραμένει ίδιος, αλλά θα πρέπει να ελέγχετε αν το `result.Extended` είναι null για μη‑PDF417 σύμβολα:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

Αυτή η μικρή τροποποίηση μετατρέπει τη **C# barcode library** σας σε έναν καθολικό scanner, ιδανικό για παρτίδες με μικτές συμβολές.

## Βήμα 5 – Edge Cases και Συμβουλές Καλών Πρακτικών

### 1️⃣ Δεν Εντοπίστηκαν Barcode  
Αν το `ReadBarCodes()` επιστρέψει έναν κενό πίνακα, οι πιο συνηθισμένοι λόγοι είναι:

- Λάθος διαδρομή αρχείου ή έλλειψη δικαιωμάτων ανάγνωσης.
- Ποιότητα εικόνας πολύ χαμηλή (θολή, χαμηλή αντίθεση). Σκεφτείτε προεπεξεργασία με `reader.ImagePreprocessingOptions` (π.χ., `reader.ImagePreprocessingOptions.Denoise = true;`).

### 2️⃣ Πολύ Μεγάλες Εικόνες  
Η επεξεργασία μιας φωτογραφίας 10 MP μπορεί να καταναλώσει πολύ μνήμη. Μπορείτε να περιορίσετε την περιοχή σάρωσης:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Ασφάλεια σε Πολυνηματική Εκτέλεση  
`BarCodeReader` υλοποιεί `IDisposable` και **δεν** είναι thread‑safe. Δημιουργήστε ξεχωριστές στιγμές ανά νήμα αν χρειάζεστε παράλληλη επεξεργασία.

### 4️⃣ Άδεια Χρήσης  
Το Aspose.BarCode λειτουργεί σε δοκιμαστική λειτουργία αμέσως, αλλά θα δείτε υδατογράφημα στην έξοδο εικόνας. Για παραγωγική χρήση, ορίστε την άδεια νωρίς:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Καταγραφή (Logging)  
Όταν ενσωματώνετε αυτόν τον κώδικα σε μεγαλύτερη υπηρεσία, αντικαταστήστε το `Console.WriteLine` με έναν δομημένο logger (Serilog, NLog). Έτσι μπορείτε να καταγράψετε τα `CodeText`, `CodeType` και `IsTruncated` ως πεδία για downstream analytics.

## Πλήρες Παράδειγμα Εργασίας

Συνδυάζοντας όλα τα παραπάνω, εδώ είναι το *ολόκληρο* πρόγραμμα που μπορείτε να αντιγράψετε‑επικολλήσετε στο `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            const string imagePath = "YOUR_DIRECTORY


## Τι Θα Πρέπει Να Μάθετε Στη Σύντομη Μελλοντική Στιγμή;


Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε πρόσθετα χαρακτηριστικά του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας projects.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}