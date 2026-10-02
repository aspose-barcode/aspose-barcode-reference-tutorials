---
category: general
date: 2026-10-02
description: Μάθετε πώς να διαβάζετε barcode από εικόνα σε C# με ένα πλήρες παράδειγμα
  που δείχνει πώς να αποκωδικοποιήσετε το barcode PDF417 χρησιμοποιώντας το Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: el
lastmod: 2026-10-02
og_description: Διαβάστε γραμμωτό κώδικα από εικόνα c# με το Aspose.BarCode. Αυτό
  το σεμινάριο εξηγεί πώς να αποκωδικοποιήσετε τον κώδικα PDF417 και να εξάγετε εκτεταμένα
  μεταδεδομένα.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Ανάγνωση barcode από εικόνα c# – βήμα‑βήμα οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να διαβάσετε γραμμωτό κώδικα από εικόνα c# χρησιμοποιώντας το Aspose.BarCode
url: /el/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαβάσετε barcode από εικόνα c# χρησιμοποιώντας το Aspose.BarCode

Αν χρειάζεστε **διαβάσετε barcode από εικόνα c#**, αυτός ο οδηγός σας καθοδηγεί βήμα‑βήμα σε μια πλήρη, εκτελέσιμη λύση. Θα μάθετε πώς να αποκωδικοποιήσετε ένα barcode PDF417, να αποκτήσετε πρόσβαση στα εκτεταμένα δεδομένα macro του και να εκτυπώσετε τα αποτελέσματα στην κονσόλα.

Η ανάγνωση barcode από εικόνες είναι μια κοινή απαίτηση για συστήματα απογραφής, επαλήθευση εισιτηρίων και επεξεργασία εγγράφων. Αυτό το tutorial καλύπτει όλα όσα χρειάζεστε: απαιτούμενα πακέτα, εξήγηση κώδικα, διαχείριση edge‑case και το αναμενόμενο αποτέλεσμα. Δεν απαιτείται εξωτερική τεκμηρίωση· το παράδειγμα λειτουργεί αμέσως με το Aspose.BarCode .NET.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE C#)  
* Μια αναφορά NuGet στο **Aspose.BarCode** (έκδοση 23.10 ή νεότερη)  
* Ένα αρχείο εικόνας που περιέχει ένα barcode PDF417 – για παράδειγμα `ExtPDF417Meta.png`

Αν λείπει κάποιο από αυτά τα στοιχεία, εγκαταστήστε το .NET SDK, προσθέστε το πακέτο NuGet με `dotnet add package Aspose.BarCode` και τοποθετήστε την εικόνα σε έναν φάκελο που μπορείτε να αναφέρετε από το έργο σας.

## Πώς να διαβάσετε barcode από εικόνα c# – βήμα‑βήμα

Οι παρακάτω ενότητες χωρίζουν την υλοποίηση σε λογικά βήματα. Κάθε βήμα περιλαμβάνει ένα απόσπασμα κώδικα, μια εξήγηση του **γιατί** το βήμα είναι σημαντικό, και μια συμβουλή που μπορείτε να εφαρμόσετε σε πραγματικά έργα.

### Βήμα 1: Δημιουργία ενός `BarCodeReader` για εικόνα PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Γιατί είναι σημαντικό** – Ο κατασκευαστής `BarCodeReader` δέχεται τη διαδρομή της εικόνας και τον αναμενόμενο τύπο barcode. Η καθορισμένη τιμή `MacroPdf417` περιορίζει την αναζήτηση, βελτιώνοντας την απόδοση και μειώνοντας τα ψευδή θετικά όταν η εικόνα περιέχει πολλαπλές συμβολές.

**Συμβουλή:** Αν δεν είστε σίγουροι για τον τύπο barcode, χρησιμοποιήστε `DecodeType.AllSupportedTypes` και φιλτράρετε τα αποτελέσματα αργότερα.

### Βήμα 2: Επανάληψη σε όλα τα ανιχνευμένα barcode

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Γιατί είναι σημαντικό** – Μια εικόνα macro PDF417 μπορεί να περιέχει αρκετά τμήματα. Η μέθοδος `ReadBarCodes()` επιστρέφει μια συλλογή, επιτρέποντάς σας να επεξεργαστείτε κάθε τμήμα ξεχωριστά.

**Edge case:** Αν η εικόνα δεν περιέχει κανένα σύμβολο PDF417, η συλλογή είναι κενή και το σώμα του βρόχου δεν εκτελείται ποτέ. Σκεφτείτε να προσθέσετε έναν έλεγχο μετά το βρόχο για να ενημερώσετε τον χρήστη.

### Βήμα 3: Πρόσβαση στα εκτεταμένα μεταδεδομένα macro PDF417

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Γιατί είναι σημαντικό** – Η ιδιότητα `Extended.Pdf417` αποκαλύπτει πεδία που ορίζονται από την προδιαγραφή PDF417, όπως το file ID, το segment ID και το όνομα αρχείου. Αυτά τα δεδομένα είναι απαραίτητα όταν χρειάζεται να ανασυνθέσετε ένα έγγραφο πολλαπλών σελίδων από ξεχωριστές σάρωση barcode.

**Συμβουλή:** Πάντα ελέγξτε ότι το `barcodeResult.Extended` δεν είναι null πριν αποκτήσετε πρόσβαση στο `Pdf417`. Η βιβλιοθήκη επιστρέφει `null` για συμβολές που δεν υποστηρίζουν εκτεταμένα δεδομένα.

### Βήμα 4: Εξαγωγή του κειμένου barcode και των λεπτομερειών macro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Γιατί είναι σημαντικό** – Η έξοδος στην κονσόλα σας παρέχει άμεση ορατότητα τόσο στο αποκωδικοποιημένο κείμενο όσο και στα μεταδεδομένα macro. Αυτό είναι χρήσιμο για εντοπισμό σφαλμάτων και για επεξεργασία downstream, όπως η αποθήκευση των πληροφοριών σε μια βάση δεδομένων.

**Αναμενόμενη έξοδος** (υποθέτοντας ότι η δείγμα εικόνα περιέχει ένα τμήμα macro):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Αν η εικόνα περιέχει τρία τμήματα, ο βρόχος εκτυπώνει τρία μπλοκ, το καθένα με διαφορετικό `Segment ID`.

### Βήμα 5: Διαχείριση σφαλμάτων και εκκαθάριση πόρων

Η δήλωση `using` διαγράφει αυτόματα το `BarCodeReader`. Ωστόσο, θα πρέπει ακόμη να πιάσετε εξαιρέσεις που μπορεί να προκύψουν από ελλιπείς αρχεία ή μη υποστηριζόμενες μορφές:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Γιατί είναι σημαντικό** – Οι αξιόπιστες εφαρμογές δεν καταρρέουν επειδή λείπει ένα αρχείο ή η εικόνα είναι κατεστραμμένη. Η παροχή ενός σαφούς μηνύματος σφάλματος βοηθά εσάς ή την ομάδα υποστήριξης να διαγνώσετε το πρόβλημα γρήγορα.

## Πώς να αποκωδικοποιήσετε barcode PDF417 με το Aspose.BarCode

Η δευτερεύουσα λέξη‑κλειδί **how to decode pdf417 barcode** εμφανίζεται φυσικά σε αυτήν την ενότητα. Η αποκωδικοποίηση ενός barcode PDF417 ακολουθεί το ίδιο μοτίβο όπως παραπάνω, αλλά μπορείτε να παραλείψετε τη σημαία `MacroPdf417` αν χρειάζεστε μόνο το απλό κείμενο:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Γιατί μπορεί να επιλέξετε αυτή τη παραλλαγή** – Όταν το barcode δεν μεταφέρει πληροφορίες macro, η χρήση του `DecodeType.Pdf417` μειώνει το φόρτο επεξεργασίας και απλοποιεί τη διαχείριση του αποτελέσματος.

**Κοινή ερώτηση:** *Τι γίνεται αν το barcode είναι περιστραμμένο;*  
Το Aspose.BarCode ανιχνεύει αυτόματα την περιστροφή και τη διορθώνει, έτσι δεν χρειάζεστε επιπλέον κώδικα προεπεξεργασίας εικόνας.

## Πλήρες, εκτελέσιμο παράδειγμα

Αντιγράψτε ολόκληρο το πρόγραμμα παρακάτω σε ένα νέο έργο κονσόλας (`dotnet new console`) και αντικαταστήστε το `YOUR_DIRECTORY/ExtPDF417Meta.png` με την πραγματική διαδρομή προς την εικόνα σας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Η εκτέλεση του προγράμματος εκτυπώνει τον τύπο του barcode, το αποκωδικοποιημένο κείμενο και τυχόν μεταδεδομένα macro. Αν η εικόνα δεν περιέχει macro PDF417, το πρόγραμμα σας ενημερώνει με ευγένεια.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **διαβάσετε barcode από εικόνα c#** με το Aspose.BarCode, πώς να **αποκωδικοποιήσετε barcode PDF417**, και πώς να εξάγετε τα εκτεταμένα πεδία macro‑PDF417. Η λύση καλύπτει την αρχικοποίηση, την επανάληψη, την πρόσβαση στα μεταδεδομένα, τη διαχείριση σφαλμάτων, και μια παραλλαγή για απλή αποκωδικοποίηση PDF417.

Από εδώ μπορείτε να:

* Αποθηκεύσετε τα εξαγόμενα δεδομένα σε μια βάση δεδομένων SQL για μελλοντική ανάκτηση.  
* Συνδυάσετε πολλαπλά τμήματα για να ξαναδημιουργήσετε το αρχικό έγγραφο.  
* Εξερευνήσετε άλλες συμβολές που υποστηρίζονται από το Aspose.BarCode, such

## Τι Θα Μάθετε Στη Σειρά;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε σε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να Διαβάσετε PDF417 σε C# – Πλήρες Παράδειγμα Barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Πώς να Διαβάσετε PDF417 σε C# – Πλήρες Παράδειγμα Αναγνώστη Barcode](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Πώς να Δημιουργήσετε Εικόνα Barcode PDF417 σε C# με το Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}