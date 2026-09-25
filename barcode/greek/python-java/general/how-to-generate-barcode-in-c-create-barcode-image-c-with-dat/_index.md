---
category: general
date: 2026-08-22
description: Πώς να δημιουργήσετε barcode σε C# χρησιμοποιώντας το Aspose.BarCode.
  Μάθετε να δημιουργείτε εικόνα barcode σε C# βήμα‑βήμα, να απενεργοποιήσετε το 2‑Δ
  στοιχείο και να αποθηκεύετε αρχεία PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: el
lastmod: 2026-08-22
og_description: Πώς να δημιουργήσετε barcode σε C# με το Aspose.BarCode. Αυτό το σεμινάριο
  σας δείχνει πώς να δημιουργήσετε εικόνα barcode σε C# χρησιμοποιώντας το DataBar
  Expanded, να ενεργοποιήσετε/απενεργοποιήσετε το 2‑Δ στοιχείο και να αποθηκεύσετε
  αρχεία PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Πώς να δημιουργήσετε γραμμωτό κώδικα σε C# – πλήρης οδηγός για τη δημιουργία
  εικόνας γραμμωτού κώδικα σε C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Πώς να δημιουργήσετε barcode σε C# – δημιουργήστε εικόνα barcode c# με DataBar
  Expanded
url: /el/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε barcode σε C# – δημιουργήστε εικόνα barcode c# με DataBar Expanded

Η δημιουργία barcode σε C# είναι μια συχνή απαίτηση όταν χρειάζεται να ενσωματώσετε δεδομένα αναγνώσιμα από μηχανή στις εφαρμογές σας. Αυτός ο οδηγός σας δείχνει πώς να δημιουργήσετε εικόνα barcode c# χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode, να απενεργοποιήσετε το 2‑D composite component και να αποθηκεύσετε το αποτέλεσμα ως αρχεία PNG.

Θα δείτε ένα πλήρες, εκτελέσιμο πρόγραμμα, μια εξήγηση κάθε επιλογής διαμόρφωσης και συμβουλές για την προσαρμογή της εξόδου. Δεν απαιτείται εξωτερική τεκμηρίωση — μόνο ο παρακάτω κώδικας και ένα περιβάλλον ανάπτυξης .NET.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει .NET)  
* Πακέτο NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  

Μπορείτε να προσθέσετε το πακέτο με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

Η βιβλιοθήκη παρέχει την κλάση `BarcodeGenerator` που χρησιμοποιείται σε όλο αυτόν τον οδηγό.

## Βήμα 1: Ρυθμίστε το έργο και εισάγετε τα namespaces

Δημιουργήστε μια νέα εφαρμογή κονσόλας και εισάγετε τα απαιτούμενα namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

## Βήμα 2: Αρχικοποιήστε τον δημιουργό barcode DataBar Expanded

Η πρώτη λειτουργική γραμμή δημιουργεί ένα `BarcodeGenerator` για τη συμβολική γραφή **DataBar Expanded** και παρέχει τη ακατέργαστη συμβολοσειρά δεδομένων. Η συμβολοσειρά δεδομένων ακολουθεί τη μορφή GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

## Βήμα 3: Ορίστε το πλάτος του μονάδας (X‑dimension)

Η X‑dimension ελέγχει το πλάτος του μικρότερου στοιχείου του barcode. Ορίζοντάς το σε pixel έχετε ακριβή έλεγχο του τελικού μεγέθους της εικόνας.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Μια τιμή `2` pixel λειτουργεί καλά για προβολή στην οθόνη· αυξήστε την για εκτυπώσεις υψηλότερης ανάλυσης.

## Βήμα 4: Απενεργοποιήστε το 2‑D composite component

Το DataBar Expanded μπορεί προαιρετικά να περιλαμβάνει ένα 2‑D component που μεταφέρει πρόσθετες πληροφορίες. Για να δημιουργήσετε ένα barcode **χωρίς** αυτό το component, ορίστε τη σημαία σε `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Η απενεργοποίηση του component μειώνει την οπτική πολυπλοκότητα και παράγει ένα μικρότερο αρχείο PNG.

## Βήμα 5: Αποθηκεύστε την εικόνα barcode χωρίς το 2‑D component

Επιλέξτε έναν φάκελο εξόδου και γράψτε την εικόνα στο δίσκο. Το enum `BarCodeImageFormat.Png` εξασφαλίζει ένα lossless αρχείο PNG.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Μετά από αυτήν την κλήση, το `Databar2DComponentDisabled.png` περιέχει ένα καθαρό barcode DataBar Expanded.

## Βήμα 6: Ενεργοποιήστε το 2‑D composite component

Αν χρειάζεστε το επιπλέον στρώμα δεδομένων, ενεργοποιήστε ξανά τη σημαία. Η ίδια παρουσία του δημιουργού μπορεί να επαναχρησιμοποιηθεί, αποφεύγοντας τη δημιουργία δεύτερου αντικειμένου.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Βήμα 7: Αποθηκεύστε την εικόνα barcode με ενεργοποιημένο το 2‑D component

Αποδώστε τη δεύτερη εικόνα χρησιμοποιώντας τις ίδιες ρυθμίσεις, εκτός από τη σημαία 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Τώρα το `Databar2DComponentEnabled.png` εμφανίζει το barcode με το πρόσθετο 2‑D pattern.

## Πλήρης κώδικας πηγής

Αντιγράψτε το πλήρες απόσπασμα παρακάτω στο `Program.cs` και εκτελέστε το έργο. Το πρόγραμμα δημιουργεί και τα δύο αρχεία PNG στον φάκελο που καθορίζετε.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Αναμενόμενη έξοδος

Running the program prints:

```
Barcode images generated successfully.
```

και δημιουργεί δύο αρχεία:

* `Databar2DComponentDisabled.png` – barcode χωρίς το 2‑D component  
* `Databar2DComponentEnabled.png` – barcode με το 2‑D component  

Ανοίξτε τα PNG σε οποιονδήποτε προβολέα εικόνων για να επαληθεύσετε τη διαφορά στην εμφάνιση.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

| Κατάσταση | Προσαρμογή |
|-----------|------------|
| **Διαφορετική συμβολική γραφή** | Αντικαταστήστε το `EncodeTypes.DatabarExpanded` με άλλη τιμή, π.χ., `EncodeTypes.Code128`. |
| **Υψηλότερη ανάλυση** | Αυξήστε το `XDimension.Pixels` σε 4 ή 5, ή ορίστε το `Resolution` στο `barcodeGenerator.Parameters.Image`. |
| **Άλλες μορφές εικόνας** | Χρησιμοποιήστε `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` ή `BarCodeImageFormat.Svg`. |
| **Εκτέλεση σε web εφαρμογή** | Μεταδώστε τα bytes της εικόνας απευθείας στην HTTP response αντί να τα αποθηκεύσετε στο δίσκο. |
| **Διαχείριση μνήμης** | Τυλίξτε τον δημιουργό σε ένα `using` block αν στοχεύετε στο .NET Framework για να εξασφαλίσετε την απελευθέρωση των μη διαχειριζόμενων πόρων. |

## Συμβουλές επαγγελματιών

* **Επαναχρησιμοποίηση του δημιουργού** – Η αλλαγή μόνο της σημαίας 2‑D αποφεύγει την επανεκκίνηση του αντικειμένου, εξοικονομώντας κύκλους CPU.  
* **Επικύρωση δεδομένων** – Τα δεδομένα GS1 πρέπει να ακολουθούν ακριβώς το μήκος και τους κανόνες ελέγχου αθροίσματος· μη έγκυρη είσοδος προκαλεί `ArgumentException`.  
* **Επεξεργασία σε παρτίδες** – Επανάληψη πάνω σε μια συλλογή συμβολοσειρών δεδομένων, εναλλαγή της σημαίας 2‑D όπως απαιτείται, και αποθήκευση κάθε εικόνας με μοναδικό όνομα αρχείου.  

## Συμπέρασμα

Τώρα γνωρίζετε πώς να δημιουργήσετε barcode σε C# και να δημιουργήσετε εικόνα barcode c# με πλήρη έλεγχο του 2‑D composite component. Το παράδειγμα δείχνει την αρχικοποίηση του δημιουργού, τη διαμόρφωση της X‑dimension, την εναλλαγή του component και την αποθήκευση αρχείων PNG. Από εδώ μπορείτε να εξερευνήσετε άλλες συμβολικές γραφές, να ενσωματώσετε τις εικόνες σε PDF ή να ενσωματώσετε τη δημιουργία barcode σε υπηρεσίες ASP.NET Core.

--- 

*Επόμενα βήματα*: δοκιμάστε τη δημιουργία QR codes, πειραματιστείτε με διαφορετικές αναλύσεις εικόνας ή ενσωματώστε τα παραγόμενα PNG σε PDF χρησιμοποιώντας το Aspose.PDF. Αυτές οι επεκτάσεις βασίζονται στο ίδιο API `BarcodeGenerator` και διατηρούν συνεπή τη ροή εργασίας σας.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε DataMatrix Barcodes χρησιμοποιώντας το Aspose.BarCode για .NET – Οδηγός βήμα‑βήμα](/barcode/english/net/datamatrix-barcode-configuration/)
- [Πώς να δημιουργήσετε και να προσαρμόσετε το ύψος Barcode για One-Dimensional Databar χρησιμοποιώντας το Aspose.BarCode για .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Πώς να δημιουργήσετε Aztec barcode με προσαρμοσμένη αναλογία διαστάσεων χρησιμοποιώντας το Aspose.BarCode για .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}