---
category: general
date: 2026-10-12
description: Πώς να ορίσετε το ύψος του barcode και να δημιουργήσετε ένα DataBar barcode
  σε C# χρησιμοποιώντας το Aspose.BarCode. Ακολουθήστε έναν οδηγό βήμα προς βήμα με
  πλήρη κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: el
lastmod: 2026-10-12
og_description: Πώς να ορίσετε το ύψος του barcode σε C# και να δημιουργήσετε ένα
  DataBar barcode με το Aspose.BarCode. Μάθετε τον πλήρη κώδικα, γιατί κάθε βήμα είναι
  σημαντικό και πώς να αλλάξετε το ύψος του barcode.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Πώς να ορίσετε το ύψος του barcode και να δημιουργήσετε κωδικό DataBar σε
  C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να ορίσετε το ύψος του barcode και να δημιουργήσετε barcode DataBar σε
  C#
url: /el/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε το ύψος του barcode, δημιουργήστε barcode DataBar σε C#

Αν χρειάζεστε να **how to set barcode** διαστάσεις προγραμματιστικά, αυτός ο οδηγός σας δείχνει τα ακριβή βήματα. Θα μάθετε πώς να δημιουργήσετε ένα DataBar Omni‑directional barcode, να προσαρμόσετε το ύψος του και να αποθηκεύσετε και τις δύο εκδόσεις ως αρχεία PNG.

Η αλλαγή του ύψους των γραμμών ενός barcode είναι μια κοινή απαίτηση όταν ενσωματώνετε barcodes σε αποδείξεις, ετικέτες προϊόντων ή οθόνες κινητών. Το παρακάτω παράδειγμα χρησιμοποιεί τη βιβλιοθήκη Aspose.BarCode, η οποία υποστηρίζει όλο το φάσμα των συμβολισμών GS1 DataBar.

## Τι θα πετύχετε

* **how to set barcode** ύψος για ένα DataBar Omni‑directional barcode  
* κώδικα **generate barcode c#** που δημιουργεί δύο εικόνες με διαφορετικά ύψη  
* κατανοήσετε τα σύμβολα **how to create databar** και γιατί το ύψος των γραμμών είναι σημαντικό  
* εφαρμόσετε τη λογική **change barcode height** χωρίς να δημιουργήσετε ξανά τον γεννήτρια  

Δεν απαιτούνται εξωτερικά εργαλεία πέρα από το πακέτο NuGet Aspose.BarCode και ένα .NET 6+ runtime.

## Προαπαιτούμενα

* .NET 6 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοσδήποτε επεξεργαστής C#)  
* Aspose.BarCode για .NET – εγκατάσταση μέσω `dotnet add package Aspose.BarCode`  

> **Pro tip:** Χρησιμοποιήστε την δωρεάν δοκιμαστική άδεια από την Aspose αν δεν έχετε εμπορικό κλειδί· το API λειτουργεί με τον ίδιο τρόπο.

## Βήμα 1: Εγκατάσταση του πακέτου Aspose.BarCode

Ανοίξτε ένα τερματικό στον φάκελο του έργου σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο προσθέτει το namespace `Aspose.BarCode`, το οποίο περιέχει την κλάση `BarcodeGenerator` που θα χρησιμοποιήσουμε για να δημιουργήσουμε εικόνες **generate barcode c#**.

## Βήμα 2: Δημιουργία γεννήτριας DataBar barcode

Η πρώτη συγκεκριμένη ενέργεια για τις παραμέτρους **how to set barcode** είναι η δημιουργία ενός αντικειμένου `BarcodeGenerator` με την επιθυμητή συμβολή και τη συμβολοσειρά δεδομένων.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Γιατί είναι σημαντικό:* `EncodeTypes.DatabarOmniDirectional` παράγει ένα συμπαγές, παντοπρόσωπο DataBar που μπορεί να σαρωθεί από οποιαδήποτε γωνία—ιδανικό για μικρές ετικέτες.

## Βήμα 3: Ορισμός κοινών παραμέτρων barcode (συμπεριλαμβανομένου του αρχικού ύψους γραμμής)

Τώρα απαντάμε στο **how to set barcode** X‑dimension και στο ύψος γραμμής πριν αποθηκεύσουμε την πρώτη εικόνα.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

Το X‑dimension ελέγχει το συνολικό πλάτος κάθε γραμμής· μια ρύθμιση 2 pixel παράγει μια ευανάγνωστη, καθαρή εικόνα στις περισσότερες οθόνες. Το βήμα **change barcode height** αργότερα θα επαναχρησιμοποιήσει τον ίδιο γεννήτρια, εξοικονομώντας χρόνο και μνήμη.

## Βήμα 4: Αποθήκευση της πρώτης εικόνας barcode (ύψος 30 pixel)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Το αρχείο `DatabarHeight30.png` περιέχει τώρα ένα DataBar barcode με ύψος γραμμής 30 pixel.

## Βήμα 5: Αλλαγή μόνο του ύψους γραμμής σε 60 pixel

Για να δείξουμε το **change barcode height**, τροποποιούμε μόνο την ιδιότητα `BarHeight`. Όλες οι άλλες ρυθμίσεις παραμένουν αμετάβλητες, κάτι που είναι ο πιο αποδοτικός τρόπος για να παραχθούν πολλαπλά μεγέθη από έναν μόνο γεννήτρια.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Βήμα 6: Αποθήκευση της δεύτερης εικόνας barcode (ύψος 60 pixel)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Τώρα έχετε δύο αρχεία PNG, το καθένα με διαφορετικό ύψος γραμμής αλλά με τα ίδια δεδομένα και X‑dimension.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑επικολλήσετε σε μια νέα εφαρμογή κονσόλας (`dotnet new console`) και να το εκτελέσετε αμέσως.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Αναμενόμενη έξοδος

Η εκτέλεση του προγράμματος παράγει δύο αρχεία στον φάκελο εργασίας του εκτελέσιμου:

* `DatabarHeight30.png` – ένα DataBar barcode με γραμμές ύψους 30 pixel.  
* `DatabarHeight60.png` – το ίδιο barcode, αλλά κάθε γραμμή είναι διπλάσια σε ύψος.

Και οι δύο εικόνες μπορούν να ανοιχτούν σε οποιονδήποτε προβολέα εικόνων ή να ενσωματωθούν απευθείας σε PDF, σελίδες HTML ή εκτυπωμένες ετικέτες.

## Γιατί η προσαρμογή του ύψους γραμμής είναι σημαντική

* **Scanning reliability:** Ορισμένα scanners δυσκολεύονται με πολύ μικρές γραμμές σε μέσα χαμηλής ανάλυσης· η αύξηση του ύψους βελτιώνει την ανίχνευση.  
* **Design constraints:** Μια εφαρμογή κινητού μπορεί να χρειάζεται ένα συμπαγές barcode (30 px) ενώ μια εκτυπωμένη απόδειξη μπορεί να απαιτεί ένα μεγαλύτερο (60 px).  
* **Regulatory compliance:** Ορισμένες βιομηχανίες απαιτούν ελάχιστο ύψος γραμμής για σύμβολα GS1 DataBar.  

Με την επαναχρήση του ίδιου αντικειμένου `BarcodeGenerator`, αποφεύγετε το κόστος επανα-ανάλυσης της συμβολοσειράς δεδομένων, κάτι που είναι ιδιαίτερα ωφέλιμο σε περιβάλλοντα υψηλής απόδοσης.

## Συχνές παραλλαγές και ειδικές περιπτώσεις

| Κατάσταση | Συνιστώμενη τροποποίηση |
|-----------|--------------------------|
| Απαιτείται διαφορετικό X‑dimension | Αλλάξτε το `XDimension.Pixels` πριν από το πρώτο `Save`. |
| Θέλετε διαφορετική συμβολή (π.χ., DataBar Stacked) | Χρησιμοποιήστε το `EncodeTypes.DatabarStacked` κατά τη δημιουργία του `BarcodeGenerator`. |
| Πρέπει να ενσωματώσετε το barcode σε PDF | Χρησιμοποιήστε το `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` και προσθέστε το stream σε μια βιβλιοθήκη PDF. |
| Εκτέλεση σε .NET Framework 4.6 | Ο ίδιος κώδικας λειτουργεί· απλώς αναφερθείτε στην κατάλληλη συναρμολόγηση Aspose.BarCode. |

## Pro tips για αξιόπιστη δημιουργία barcode

* **Cache the generator** όταν δημιουργείτε πολλά barcodes με τα ίδια δεδομένα αλλά διαφορετικά μεγέθη.  
* **

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε και να προσαρμόσετε το ύψος του Barcode για One-Dimensional Databar χρησιμοποιώντας Aspose.BarCode για .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Πώς να δημιουργήσετε εικόνες PNG databar με C# και Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Πώς να δημιουργήσετε barcode με προσαρμοσμένο μέγεθος και να αποθηκεύσετε την εικόνα σε C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}