---
category: general
date: 2026-11-23
description: Μάθετε πώς να χρησιμοποιείτε το BarCodeReader σε C# για να διαβάζετε
  γραμμικούς κώδικες από μια εικόνα, συμπεριλαμβανομένης της αποκωδικοποίησης Macro
  PDF417, με ένα πλήρες παράδειγμα κώδικα και σαφείς εξηγήσεις.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: el
lastmod: 2026-11-23
og_description: Πώς να χρησιμοποιήσετε το BarCodeReader σε C# για να διαβάζετε γραμμικούς
  κώδικες από μια εικόνα. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα για να αποκωδικοποιήσετε
  Macro PDF417 και άλλες μορφές με κώδικα έτοιμο για εκτέλεση.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Πώς να χρησιμοποιήσετε το BarCodeReader σε C# – διαβάστε γρήγορα γραμμωτούς
  κώδικες από εικόνες
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Πώς να χρησιμοποιήσετε το BarCodeReader σε C# για την ανάγνωση γραμμωτών κωδίκων
  από εικόνες
url: /el/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το BarCodeReader σε C# για ανάγνωση barcode από εικόνες

Αν χρειάζεστε **πώς να χρησιμοποιήσετε το BarCodeReader** για γρήγορη σάρωση barcode, αυτός ο οδηγός σας δείχνει ακριβώς αυτό. Είτε δημιουργείτε σύστημα σημείου πώλησης είτε αυτοματοποιείτε την εισαγωγή εγγράφων, θα μάθετε πώς να διαβάζετε barcode από εικόνες σε έργα C# με λίγες μόνο γραμμές κώδικα.

Σε αυτό το tutorial θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που αποκωδικοποιεί ένα Macro PDF417 barcode, εξάγει τις εκτεταμένες ιδιότητές του και εκτυπώνει χρήσιμες πληροφορίες στην κονσόλα. Δεν απαιτείται εξωτερική τεκμηρίωση – όλα όσα χρειάζεστε είναι εδώ.

## Προαπαιτούμενα

* .NET 6.0 (ή νεότερη) εγκατεστημένο – ο κώδικας στοχεύει στην τελευταία έκδοση LTS.
* Μια αναφορά στο πακέτο NuGet **Aspose.BarCode** (ή οποιοδήποτε συμβατό) που παρέχει `BarCodeReader`.
* Ένα αρχείο εικόνας που περιέχει ένα Macro PDF417 barcode (το παράδειγμα χρησιμοποιεί `ExtPDF417Meta.png`).

> **Συμβουλή:** Αν χρησιμοποιείτε Visual Studio, προσθέστε το πακέτο μέσω `dotnet add package Aspose.BarCode` ή του UI του NuGet Package Manager.

## Βήμα 1: Δημιουργία ενός αντικειμένου BarCodeReader

Το πρώτο πράγμα που κάνετε όταν εργάζεστε με μια βιβλιοθήκη barcode είναι να δημιουργήσετε έναν αναγνώστη που δείχνει στην πηγή εικόνας και ενημερώνει το API για το(α) τύπο(ους) barcode που πρέπει να αναζητήσει.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Γιατί αυτό το βήμα είναι σημαντικό:*  
`BarCodeReader` ανοίγει την εικόνα, εκχωρεί φυσική μνήμη και προετοιμάζει αλγορίθμους αποκωδικοποίησης για το καθορισμένο `DecodeType`. Περιορίζοντας τον τύπο σε `MacroPdf417`, μειώνετε το φορτίο CPU και βελτιώνετε την ακρίβεια ανίχνευσης.

## Βήμα 2: Ανάγνωση όλων των barcode που βρέθηκαν στην εικόνα

Μια μόνο εικόνα μπορεί να περιέχει πολλαπλά barcode, ειδικά όταν δουλεύετε με macro‑κωδικοποιημένα δεδομένα. Η μέθοδος `ReadBarCodes` επιστρέφει μια συλλογή από αντικείμενα `BarCodeResult`, το καθένα αντιπροσωπεύει έναν εντοπισμένο κώδικα.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Γιατί αυτό το βήμα είναι σημαντικό:*  
Η επανάληψη στη συλλογή εξασφαλίζει ότι θα συλλάβετε κάθε εμφάνιση, κάτι που είναι ουσιώδες για σενάρια επεξεργασίας παρτίδας ή όταν ένα έγγραφο ενσωματώνει πολλούς κώδικες.

## Βήμα 3: Πρόσβαση στις εκτεταμένες ιδιότητες Macro PDF417

Το Macro PDF417 αποθηκεύει επιπρόσθετα μεταδεδομένα όπως αναγνωριστικά αρχείων, αριθμούς τμημάτων και συνολικό αριθμό τμημάτων. Αυτές οι τιμές εκτίθενται μέσω της ιδιότητας `Extended.Pdf417` του `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Γιατί αυτό το βήμα είναι σημαντικό:*  
Τα εκτεταμένα πεδία σας επιτρέπουν να ανασυνθέσετε έγγραφα πολλαπλών τμημάτων ή να επικυρώσετε ότι όλα τα μέρη ανήκουν στην ίδια πηγή. Παραλείποντας αυτό το βήμα θα λαμβάνετε μόνο το ακατέργαστο κείμενο, χάνοντας πολύτιμο πλαίσιο.

## Βήμα 4: Εξαγωγή των πιο χρήσιμων πληροφοριών

Τέλος, γράψτε τα δεδομένα στην κονσόλα (ή σε οποιονδήποτε logger) ώστε να μπορείτε να επαληθεύσετε τη λειτουργία ανάγνωσης. Το παράδειγμα εκτυπώνει τον τύπο κώδικα, το αποκωδικοποιημένο κείμενο και αρκετά macro πεδία.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Αναμενόμενη έξοδος κονσόλας**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Σημείωση:** Εάν η εικόνα δεν περιέχει Macro PDF417 barcode, η `ReadBarCodes()` επιστρέφει μια κενή συλλογή και το σώμα του βρόχου δεν εκτελείται ποτέ. Πάντα ελέγχετε για κενό αποτέλεσμα σε κώδικα παραγωγής.

## Ανάγνωση barcode από εικόνα σε C# – αντιμετώπιση κοινών σεναρίων

### 1. Αποκωδικοποίηση πολλαπλών μορφών barcode

Αν χρειάζεστε να εντοπίσετε περισσότερες από μία μορφές, περάστε ένα συνδυασμένο flag `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Διαχείριση μεγάλων εικόνων

Οι μεγάλες εικόνες μπορούν να προκαλέσουν υψηλή χρήση μνήμης. Μειώστε την ανάλυση της εικόνας πριν τη περάσετε στον αναγνώστη:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Διαχείριση σφαλμάτων

Τυλίξτε τη λογική ανάγνωσης σε μπλοκ try‑catch για να εμφανίσετε αποτυχίες αποκωδικοποίησης:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Πλήρες λειτουργικό παράδειγμα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε, επικολλήσετε και εκτελέσετε. Περιλαμβάνει όλα τα βήματα, τις απαραίτητες οδηγίες `using` και ένα απλό σκελετό διαχείρισης σφαλμάτων.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Η εκτέλεση του προγράμματος** εκτυπώνει κάθε εντοπισμένο Macro PDF417 barcode και τα εκτεταμένα πεδία του, ή σας ενημερώνει ότι δεν βρέθηκαν barcode.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να χρησιμοποιήσετε το BarCodeReader** για ανάγνωση barcode από εφαρμογές C# που επεξεργάζονται εικόνες, συμπεριλαμβανομένης της εξαγωγής μεταδεδομένων Macro PDF417. Η λύση καλύπτει την αρχικοποίηση, την επανάληψη, την πρόσβαση σε εκτεταμένες ιδιότητες και πρακτικές συμβουλές για διαχείριση πολλαπλών μορφών, μεγάλων εικόνων και σφαλμάτων.

Στη συνέχεια, μπορείτε να εξερευνήσετε:

* **Ανάγνωση QR codes** – αντικαταστήστε `DecodeType.MacroPdf417` με `DecodeType.QR`.
* **Αποθήκευση αποκωδικοποιημένων δεδομένων** σε βάση δεδομένων ή αρχείο JSON για επεξεργασία downstream.
* **Ενσωμάτωση με ASP.NET Core** για αποδοχή ανεβασμένων εικόνων μέσω web API.

Μη διστάσετε να πειραματιστείτε με διαφορετικούς τύπους barcode και πηγές εικόνας. Καλή προγραμματιστική!

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [c# tutorial ανάγνωσης barcode – ανάγνωση Macro PDF417 barcode βήμα‑βήμα χρησιμοποιώντας το GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Πώς να χρησιμοποιήσετε έναν δημιουργό barcode C# για Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Ανάγνωση barcode από εικόνα C# – πλήρης οδηγός με Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}