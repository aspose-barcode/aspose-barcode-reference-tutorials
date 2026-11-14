---
category: general
date: 2026-11-14
description: Μάθημα δημιουργίας barcode σε C# που δείχνει πώς να δημιουργήσετε DataBar
  Omnidirectional barcodes, να ορίσετε τη διάσταση X και να ρυθμίσετε το ύψος των
  γραμμών σε εικονοστοιχεία.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: el
lastmod: 2026-11-14
og_description: Το σεμινάριο δημιουργίας barcode σε C# εξηγεί βήμα‑βήμα πώς να δημιουργήσετε
  ένα barcode DataBar Omnidirectional, να ορίσετε το XDimension σε εικονοστοιχεία
  και να αλλάξετε το ύψος των γραμμών για έξοδο PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Οδηγός δημιουργίας barcode C# – δημιουργία κωδικών DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Δημιουργός barcode C# – οδηγός: DataBar Omnidirectional'
url: /el/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

Αν ψάχνετε για ένα **barcode generator C# tutorial**, βρεθήκατε στο σωστό μέρος. Αυτός ο οδηγός σας οδηγεί βήμα‑βήμα στη δημιουργία ενός DataBar Omnidirectional barcode, στη ρύθμιση του XDimension σε pixels και στην προσαρμογή του ύψους των γραμμών για την παραγωγή εικόνων PNG.

Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που καλύπτει τα πάντα, από την αρχικοποίηση του γεννήτριας μέχρι την αποθήκευση πολλαπλών εικόνων με διαφορετικά ύψη γραμμών. Δεν απαιτείται εξωτερική τεκμηρίωση — απλώς αντιγράψτε τον κώδικα, τρέξτε τον και θα έχετε δύο αρχεία barcode έτοιμα για χρήση.

## Prerequisites

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 ή νεότερη έκδοση εγκατεστημένη  
* Μια αναφορά στη βιβλιοθήκη barcode που παρέχει `BarcodeGenerator`, `EncodeTypes` και `BarCodeImageFormat` (π.χ., Aspose.BarCode for .NET)  
* Βασική εξοικείωση με τη σύνταξη C# και το Visual Studio ή το αγαπημένο σας IDE  

> **Pro tip:** Αν χρησιμοποιείτε Aspose.BarCode, προσθέστε το πακέτο NuGet `Aspose.BarCode` στο έργο σας.

## Barcode generator C# tutorial – step 1: create the generator

Το πρώτο βήμα είναι η δημιουργία ενός αντικειμένου `BarcodeGenerator` με τον τύπο κωδικοποίησης `DatabarOmniDirectional` και τα δεδομένα που θέλετε να κωδικοποιήσετε.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` tells the library to produce a barcode that can be read from any direction, which is ideal for retail packaging and logistics.

## Set XDimension pixels for the barcode

Η X‑διάσταση ορίζει το πλάτος του μικρότερου μονάδας (το “pixel”) στο barcode. Ορίζοντάς το σε pixels έχετε ακριβή έλεγχο της οπτικής πυκνότητας του barcode.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* A value of `2` pixels yields a barcode that is sharp enough for most scanners while keeping the image file size modest.

## Adjust bar height and save images

Το ύψος των γραμμών καθορίζει πόσο ψηλές εμφανίζονται. Μπορείτε να δημιουργήσετε πολλαπλές εικόνες με διαφορετικά ύψη αλλάζοντας την ιδιότητα `BarHeight.Pixels` και καλώντας ξανά τη μέθοδο `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Η τιμή `BarCodeImageFormat.Png` του enum εξασφαλίζει ότι το αποτέλεσμα είναι αρχείο PNG χωρίς απώλειες, το οποίο συνιστάται για γραφικά barcode επειδή διατηρεί ακριβείς διαστάσεις.

## Change bar height to create multiple images

Συχνά χρειάζεται το ίδιο barcode σε διαφορετικά μεγέθη — π.χ., ένα για μικρή ετικέτα και ένα για μεγάλο πόστερ. Αλλάξτε το ύψος των γραμμών και επαναχρησιμοποιήστε το ίδιο αντικείμενο γεννήτριας:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* If the bar height is set too low (e.g., below 10 px), some scanners may struggle to read the code. Always test the generated images with your target scanner hardware.

## Full source code

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑επικολλήσετε σε ένα νέο project κονσόλας. Περιλαμβάνει όλες τις απαιτούμενες οδηγίες `using` και δείχνει και τις δύο παραλλαγές ύψους γραμμών.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Τρέξτε το πρόγραμμα, αντικαταστήστε το `YOUR_DIRECTORY` με μια έγκυρη διαδρομή φακέλου, και θα βρείτε δύο αρχεία PNG:

* `DatabarBarHeight30Pixels.png` – γραμμές 30 px ύψους  
* `DatabarBarHeight60Pixels.png` – γραμμές 60 px ύψους  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Common questions

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG is preferred for lossless quality. |
| **What if I need a different XDimension?** | Adjust `generator.Parameters.Barcode.XDimension.Pixels` to any integer. Larger values increase overall barcode width. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | It is, provided the printed size meets the scanner’s minimum module size (usually 0.33 mm). The pixel‑based XDimension helps you meet that requirement. |
| **How do I embed the barcode in a PDF?** | After saving the PNG, use a PDF library (e.g., iTextSharp) to insert the image into a PDF page. |

## Conclusion

This **barcode generator C# tutorial** showed you how to create a DataBar Omnidirectional barcode, set the XDimension in pixels, and generate PNG files with different bar heights. You now have a reusable code snippet that you can adapt for any C# project that requires barcode creation.

### What’s next?

* Explore other `EncodeTypes` such as `Code128` or `QR` to broaden your barcode repertoire.  
* Combine the generated PNG with a PDF generation library to produce printable invoices.  
* Experiment with `generator.Parameters.Barcode.Color` to add custom colors while staying within scanner specifications.

Feel free to modify the example, try additional bar heights, or switch the output format. Happy coding!


## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}