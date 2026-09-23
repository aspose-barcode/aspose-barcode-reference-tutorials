---
category: general
date: 2026-09-23
description: Το σεμινάριο δημιουργίας barcode σε C# δείχνει πώς να δημιουργείτε εικόνες
  barcode με προσαρμοσμένες αναλογίες διαστάσεων χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: el
lastmod: 2026-09-23
og_description: Ο οδηγός δημιουργίας barcode σε C# σας καθοδηγεί πώς να δημιουργήσετε
  εικόνες barcode, να προσαρμόσετε τις αναλογίες διαστάσεων και να εξάγετε αρχεία
  PNG χρησιμοποιώντας το Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Δημιουργήστε υψηλής ποιότητας γραμμωτούς κώδικες με έναν δημιουργό γραμμωτών
  κωδίκων C#.
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Πώς να χρησιμοποιήσετε έναν δημιουργό barcode C# για κώδικες DataBar
url: /el/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε μια γεννήτρια barcode C# για κώδικες DataBar

Αν χρειάζεστε μια **c# barcode generator** που μπορεί να παράγει DataBar stacked Omni‑Directional σύμβολα, αυτός ο οδηγός σας παρέχει μια πλήρη, έτοιμη προς εκτέλεση λύση. Θα δείτε πώς να δημιουργήσετε εικόνες barcode, να ελέγξετε τη διάσταση X και να αλλάξετε την αναλογία διαστάσεων χωρίς να φύγετε από το IDE.

Η δημιουργία barcode είναι μια κοινή απαίτηση για συστήματα απογραφής, ετικέτες αποστολής και εφαρμογές σημείου πώλησης. Στο τέλος αυτού του οδηγού θα μπορείτε να δημιουργήσετε αρχεία PNG με οποιαδήποτε αναλογία διαστάσεων επιλέξετε, και θα κατανοήσετε πώς να προσαρμόσετε τον κώδικα για άλλους τύπους barcode.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιονδήποτε επεξεργαστή C# προτιμάτε)  
* Μια αναφορά NuGet στο **Aspose.BarCode** – η βιβλιοθήκη που τροφοδοτεί την κλάση `BarcodeGenerator`

Δεν χρειάζεστε ξεχωριστή βιβλιοθήκη γραφικών· η Aspose.BarCode διαχειρίζεται την κωδικοποίηση εικόνας εσωτερικά.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Ανοίξτε ένα τερματικό στον φάκελο του έργου σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Η εντολή προσθέτει την πιο πρόσφατη σταθερή έκδοση της βιβλιοθήκης στο αρχείο του έργου σας, καθιστώντας την κλάση `BarcodeGenerator` διαθέσιμη για χρήση.

## Βήμα 2: Ορισμός του φακέλου εξόδου

Επιλέξτε έναν φάκελο όπου θα αποθηκευτούν τα παραγόμενα αρχεία PNG. Η χρήση απόλυτης ή σχετικής διαδρομής λειτουργεί με τον ίδιο τρόπο, αλλά μια σχετική διαδρομή διατηρεί το έργο φορητό.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Η δημιουργία του καταλόγου προγραμματιστικά αποτρέπει σφάλματα χρόνου εκτέλεσης εάν ο φάκελος λείπει.

## Βήμα 3: Δημιουργία μιας γεννήτριας barcode C# με δείγμα δεδομένων

Ο κατασκευαστής `BarcodeGenerator` απαιτεί δύο ορίσματα: τον τύπο barcode και τη συμβολοσειρά δεδομένων. Για ένα σύμβολο DataBar stacked Omni‑Directional χρησιμοποιείτε το `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Η συμβολοσειρά δεδομένων ακολουθεί τη μορφή GS1 Application Identifier. Η απαρίθμηση `EncodeTypes` περιέχει πάνω από 150 πρότυπα barcode· μπορείτε να μεταβείτε σε άλλον τύπο αλλάζοντας την τιμή της απαρίθμησης.

## Βήμα 4: Ορισμός της διάστασης X (μέγεθος pixel) για το barcode

Η διάσταση X ελέγχει το πλάτος της πιο στενής γραμμής. Μια τιμή pixel ίση με 2 παράγει μια καθαρή, υψηλής ανάλυσης εικόνα κατάλληλη για τις περισσότερες οθόνες.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Η ρύθμιση της διάστασης X είναι προαιρετική, αλλά σας παρέχει λεπτομερή έλεγχο της οπτικής πυκνότητας του barcode.

## Βήμα 5: Δημιουργία barcode με αναλογία διαστάσεων 15 και αποθήκευση ως PNG

Η ιδιότητα `AspectRatio` ανήκει στο υπο‑αντικείμενο `DataBar`. Η αλλαγή αυτής της τιμής τεντώνει ή συμπιέζει το barcode κάθετα διατηρώντας τα κωδικοποιημένα δεδομένα.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Η μέθοδος `Save` γράφει το barcode στη συγκεκριμένη διαδρομή αρχείου. Η απαρίθμηση `BarCodeImageFormat.Png` εξασφαλίζει συμπίεση χωρίς απώλειες.

![παράδειγμα εξόδου γεννήτριας barcode c#](generated_barcode_example.png)

*Εικόνα: barcode που δημιουργήθηκε με αναλογία διαστάσεων 15.*

## Βήμα 6: Αλλαγή της αναλογίας διαστάσεων σε 30 και δημιουργία δεύτερης εικόνας

Η επαναχρησιμοποίηση της ίδιας παρουσίας `BarcodeGenerator` αποφεύγει την εκχώρηση νέου αντικειμένου. Απλώς ενημερώστε το `AspectRatio` και καλέστε ξανά το `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Τώρα έχετε δύο αρχεία PNG που διαφέρουν μόνο στην κάθετη κλίμακα. Αυτή η τεχνική είναι χρήσιμη όταν χρειάζεστε τα ίδια δεδομένα να αποτυπώνονται για διαφορετικά μεγέθη ετικετών.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

### Αλλαγή σε άλλο τύπο barcode

Αν χρειάζεστε QR code, Code 128 ή PDF417, αντικαταστήστε την τιμή της απαρίθμησης στον κατασκευαστή:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Όλα τα άλλα βήματα διαμόρφωσης (διάσταση X, αποθήκευση) παραμένουν ίδια.

### Διαχείριση μη υποστηριζόμενων χαρακτήρων

Η `BarcodeGenerator` επαληθεύει τη συμβολοσειρά εισόδου σε σχέση με την επιλεγμένη συμβολή. Η παροχή μη έγκυρου χαρακτήρα προκαλεί `ArgumentException`. Τυλίξτε τη δημιουργία σε μπλοκ try‑catch για να παρέχετε φιλικό μήνυμα σφάλματος:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Εξαγωγή σε άλλες μορφές εικόνας

Η Aspose.BarCode υποστηρίζει BMP, JPEG, TIFF και SVG. Αλλάξτε το δεύτερο όρισμα της `Save` ανάλογα:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Έξοδος υψηλής ανάλυσης για εκτύπωση

Κατά την εκτύπωση σε εκτυπωτές υψηλής DPI, αυξήστε τη διάσταση X και προαιρετικά ορίστε την ιδιότητα `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Αυτές οι ρυθμίσεις παράγουν μεγαλύτερα αρχεία αλλά διατηρούν καθαρά άκρα στο φυσικό μέσο.

## Αναμενόμενη έξοδος

Η εκτέλεση του πλήρους προγράμματος δημιουργεί τα ακόλουθα αρχεία μέσα στο `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – ένας DataBar κώδικας τυπικού ύψους  
* `DatabarAspectRatio30.png` – μια κάθετα τεντωμένη έκδοση  

Και οι δύο εικόνες περιέχουν τα ίδια κωδικοποιημένα δεδομένα GS1, και μπορείτε να τα επαληθεύσετε με οποιαδήποτε εφαρμογή σάρωσης barcode.

## Πλήρης πηγαίος κώδικας

Αντιγράψτε τον παρακάτω κώδικα σε ένα νέο έργο κονσόλας (`dotnet new console`) και εκτελέστε το. Το πρόγραμμα εμφανίζει μηνύματα κατάστασης στην κονσόλα και γράφει τα αρχεία PNG στο δίσκο.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Η εκτέλεση του προγράμματος παράγει έξοδο κονσόλας παρόμοια με:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Συμπέρασμα

Τώρα έχετε μια **c# barcode generator** που μπορεί να δημιουργήσει σύμβολα DataBar stacked Omni‑Directional, να ρυθμίσει τη διάσταση X και να εξάγει αρχεία PNG με προσαρμοσμένες αναλογίες διαστάσεων. Το ίδιο μοτίβο λειτουργεί για οποιαδήποτε άλλη συμβολή barcode υποστηρίζεται από την Aspose.BarCode, καθιστώντας εύκολη την ενσωμάτωση δημιουργίας barcode σε λύσεις απογραφής, αποστολής ή σημείου πώλησης.

Αν θέλετε να εξερευνήσετε περαιτέρω, δοκιμάστε:

* Δημιουργία QR codes ή συμβόλων PDF417 (`how to generate barcode` για εφαρμογές κινητών)  
* Εξαγωγή σε SVG για κλιμακούμενα γραφικά web  
* Ενσωμάτωση των παραγόμενων εικόνων απευθείας σε τιμολόγια PDF χρησιμοποιώντας την Aspose.PDF  

Πειραματιστείτε με διαφορετικές τιμές `AspectRatio`, μεγέθη X‑dimension και μορφές εξόδου για να ταιριάξετε ακριβώς

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικά θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε barcode Aztec με προσαρμοσμένη αναλογία διαστάσεων χρησιμοποιώντας Aspose.BarCode για .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Πώς να προσαρμόσετε το μέγεθος Barcode – Αναλογία διαστάσεων Codablock F με Aspose.BarCode για .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Πώς να δημιουργήσετε και να προσαρμόσετε το ύψος Barcode για One-Dimensional Databar χρησιμοποιώντας Aspose.BarCode για .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}