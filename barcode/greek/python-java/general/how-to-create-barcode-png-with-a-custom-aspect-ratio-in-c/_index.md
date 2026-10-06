---
category: general
date: 2026-10-05
description: Δημιουργήστε PNG barcode σε C# και μάθετε πώς να ορίσετε λόγο διαστάσεων
  15 για στοιβαγμένα DataBar παντοπρόσαπτα γραμμωτούς κώδικες.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: el
lastmod: 2026-10-05
og_description: Δημιουργήστε PNG barcode σε C# και ανακαλύψτε πώς να ορίσετε λόγο
  διαστάσεων 15 για τα στοιβαζόμενα DataBar omnidirectional barcodes σε λίγα βήματα.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Δημιουργία barcode PNG σε C# – ορισμός λόγου διαστάσεων 15 – οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Πώς να δημιουργήσετε PNG γραμμωτού κώδικα με προσαρμοσμένη αναλογία διαστάσεων
  σε C#
url: /el/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε PNG barcode με προσαρμοσμένη αναλογία διαστάσεων σε C#

Αν χρειάζεστε **να δημιουργήσετε PNG barcode** σε C#, αυτός ο οδηγός σας δείχνει **πώς να ορίσετε την αναλογία διαστάσεων** 15 για ένα στοίβαγμα DataBar omnidirectional barcode. Θα περάσουμε βήμα‑βήμα από κάθε κλήση API, θα εξηγήσουμε γιατί η αναλογία διαστάσεων είναι σημαντική και θα σας δώσουμε ένα πλήρες, εκτελέσιμο παράδειγμα που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο .NET.

Η δημιουργία εικόνας barcode είναι συχνή απαίτηση για συστήματα απογραφής, ετικέτες αποστολής και εφαρμογές σημείου πώλησης λιανικής. Στο τέλος αυτού του tutorial θα έχετε ένα αρχείο PNG που πληροί τις ακριβείς οπτικές προδιαγραφές του επιχειρηματικού σας συνεργάτη. Χωρίς εξωτερικά εργαλεία, χωρίς χειροκίνητη επεξεργασία εικόνας—μόνο κώδικας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 ή νεότερο (το παράδειγμα χρησιμοποιεί .NET 6 αλλά λειτουργεί με .NET 5+)
* Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET)
* Το πακέτο **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Δικαίωμα εγγραφής στον φάκελο όπου θέλετε να αποθηκεύσετε το αρχείο PNG

Αυτές οι απαιτήσεις είναι ελάχιστες· ο ίδιος κώδικας λειτουργεί σε .NET Core, .NET Framework ή μια εφαρμογή κονσόλας.

## Δημιουργία barcode PNG με Aspose.BarCode

Το πρώτο βήμα είναι η δημιουργία ενός αντικειμένου της κλάσης `BarcodeGenerator` με τον σωστό τύπο barcode. Σε αυτήν την περίπτωση χρησιμοποιούμε το `EncodeTypes.DatabarStackedOmniDirectional`, το οποίο παράγει ένα στοίβαγμα DataBar που μπορεί να διαβαστεί από οποιαδήποτε κατεύθυνση.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Γιατί είναι σημαντικό:* Ο κατασκευαστής δέχεται δύο ορίσματα—**τη συμβολολογία του barcode** και **τη συμβολοσειρά δεδομένων**. Η μορφή DataBar απαιτεί έναν αναγνωριστικό εφαρμογής GS1, γι' αυτό τα δείγμα δεδομένων ξεκινά με `(01)`.

## Πώς να ορίσετε την αναλογία διαστάσεων για ένα στοίβαγμα DataBar

Το οπτικό πλάτος ενός DataBar ελέγχεται από την ιδιότητα **aspect ratio**. Μια υψηλότερη αναλογία κάνει τις γραμμές πιο φαρδιές, κάτι που μπορεί να βελτιώσει την αξιοπιστία σάρωσης σε εκτυπωτές χαμηλής ανάλυσης.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Η `XDimension` ορίζει το μέγεθος ενός μεμονωμένου μονάδας (η μικρότερη γραμμή ή κενό). Η διατήρηση της τιμής στα 2 px προσφέρει καθαρή, υψηλής πυκνότητας εικόνα κατάλληλη για τους περισσότερους εκτυπωτές ετικετών.

## Ορισμός αναλογίας διαστάσεων 15 – ανάλυση κώδικα

Τώρα εφαρμόζουμε την απαίτηση **set aspect ratio 15**. Αυτό είναι το κεντρικό μέρος του tutorial και δείχνει την ακριβή κλήση API που χρειάζεστε.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Γιατί 15;* Η προεπιλεγμένη αναλογία διαστάσεων για stacked DataBar είναι 12. Η αύξησή της σε 15 επεκτείνει το πλάτος κάθε γραμμής κατά 25 %, κάτι που συχνά ταιριάζει με τις προδιαγραφές παρόχων λογιστικής που απαιτούν ευρύτερο barcode για ταχύτερη σάρωση.

## Αποθήκευση του barcode ως PNG

Με τον γεννήτρια ρυθμισμένο, το τελευταίο βήμα είναι η εγγραφή της εικόνας στο δίσκο. Η μέθοδος `Save` δέχεται διαδρομή αρχείου και έναν enum μορφής εικόνας.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Η μορφή PNG διατηρεί την απώλεια‑απώλειας ποιότητα, εξασφαλίζοντας ότι το barcode αποδίδεται ακριβώς όπως σχεδιάστηκε σε οποιαδήποτε οθόνη ή εκτυπωτή.

## Πλήρες παράδειγμα και αναμενόμενο αποτέλεσμα

Ακολουθεί το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε στη μέθοδο `Main` μιας εφαρμογής κονσόλας. Περιλαμβάνει όλα τα βήματα που περιγράφηκαν παραπάνω, καθώς και ένα μικρό μήνυμα επαλήθευσης.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Αναμενόμενο αποτέλεσμα**

Η εκτέλεση του προγράμματος δημιουργεί ένα αρχείο με όνομα `DatabarAspectRatio15.png` που περιέχει ένα καθαρό, ευρύ stacked DataBar barcode. Όταν ανοίξετε το PNG, θα δείτε ένα οριζόντια τεντωμένο barcode που εξακολουθεί να συμμορφώνεται με τις προδιαγραφές GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **δημιουργήστε PNG barcode που εμφανίζει ένα στοίβαγμα DataBar με αναλογία διαστάσεων 15**

### Συμβουλές και κοινά προβλήματα

| Κατάσταση | Σύσταση |
|-----------|----------|
| **Η εικόνα φαίνεται θολή** | Αυξήστε το `XDimension.Pixels` στα 3 px ή περισσότερο, αλλά κρατήστε το συνολικό μέγεθος εικόνας κάτω από 500 px για να αποφύγετε υπερβολικά μεγάλα αρχεία. |
| **Ο σαρωτής δεν μπορεί να διαβάσει τον κώδικα** | Επαληθεύστε ότι η συμβολοσειρά δεδομένων ακολουθεί τη μορφή GS1 (`(01)` πρόθεμα). Επίσης, βεβαιωθείτε ότι η ανάλυση του εκτυπωτή είναι τουλάχιστον 300 dpi. |
| **Απαιτείται διαφορετική μορφή αρχείου** | Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Gif`—το API υποστηρίζει όλες τις κύριες μορφές raster. |
| **Εκτέλεση σε web εφαρμογή** | Χρησιμοποιήστε `generator.Save(Stream, BarCodeImageFormat.Png)` για να γράψετε απευθείας στην HTTP απόκριση χωρίς να αγγίξετε το σύστημα αρχείων. |

### Επέκταση του παραδείγματος

* **Πολλαπλά barcodes σε μία εικόνα:** Δημιουργήστε επιπλέον στιγμιότυπα `BarcodeGenerator` και σχεδιάστε τα σε ένα ενιαίο `Bitmap` χρησιμοποιώντας `Graphics`.  
* **Προσθήκη κειμένου αναγνώσιμου από άνθρωπο:** Ορίστε `generator.Parameters.Caption.Visible = true` και προσαρμόστε τη γραμματοσειρά μέσω `generator.Parameters.Caption.Font`.  
* **Δυναμική αναλογία διαστάσεων:** Ανάγνωση της τιμής αναλογίας από αρχείο ρυθμίσεων ή βάση δεδομένων για να δημιουργείτε barcodes με διαφορετικά πλάτη κατά το χρόνο εκτέλεσης.

## Συμπέρασμα

Σε αυτό το tutorial μάθατε πώς να **δημιουργήσετε PNG barcode** σε C# και να ορίσετε με ακρίβεια την **αναλογία διαστάσεων** 15 για ένα stacked DataBar omnidirectional barcode. Ο πλήρης, εκτελέσιμος κώδικας δείχνει κάθε απαιτούμενη κλήση API, εξηγεί γιατί κάθε ρύθμιση είναι σημαντική και παρέχει πρακτικές συμβουλές για πραγματικές εφαρμογές.  

Στη συνέχεια, μπορείτε να εξερευνήσετε **πώς να ορίσετε την αναλογία διαστάσεων** για άλλους τύπους barcode (π.χ., QR Code ή Code 128) ή να ενσωματώσετε τον γεννήτρια σε μια υπηρεσία ASP .NET Core που επιστρέφει εικόνες barcode κατ' απαίτηση. Καλό κώδικα!

## Τι πρέπει να μάθετε στη συνέχεια;

Οι παρακάτω οδηγίες καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην δική σας υλοποίηση.

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}