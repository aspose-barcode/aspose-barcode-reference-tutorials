---
category: general
date: 2026-09-16
description: Μάθετε πώς να ορίζετε στήλες barcode σε C# χρησιμοποιώντας το BarcodeGenerator
  και επίσης να ορίζετε γραμμές barcode για τα DataBar Expanded Stacked barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: el
lastmod: 2026-09-16
og_description: Ορίστε στήλες barcode σε C# γρήγορα. Αυτός ο οδηγός σας δείχνει πώς
  να ρυθμίσετε στήλες, σειρές και μορφή εικόνας με το BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Ορισμός στηλών και γραμμών barcode σε C# – πλήρης οδηγός BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να ορίσετε στήλες και σειρές barcode με το C# BarcodeGenerator
url: /el/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε στήλες και σειρές barcode με C# BarcodeGenerator

Εάν χρειάζεστε να ορίσετε στήλες barcode σε μια εφαρμογή C#, αυτό το tutorial δείχνει τα ακριβή βήματα που απαιτούνται. Θα δείτε πώς να διαμορφώσετε τόσο τις στήλες όσο και τις σειρές για ένα DataBar Expanded Stacked barcode, και στη συνέχεια να αποθηκεύσετε το αποτέλεσμα ως εικόνα PNG.

Η δημιουργία barcode προγραμματιστικά σας εξοικονομεί την ανάγκη για χειροκίνητο σχεδιασμό και εγγυάται συνέπεια σε αναφορές, τιμολόγια και ετικέτες προϊόντων. Το παρακάτω παράδειγμα καλύπτει ολόκληρη τη ροή εργασίας, από την εγκατάσταση της βιβλιοθήκης μέχρι την παραγωγή δύο εικόνων — μία με προσαρμοσμένο αριθμό στηλών και μία με προσαρμοσμένο αριθμό σειρών.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 ή νεότερη έκδοση εγκατεστημένη.
* Αναφορά στο πακέτο **Aspose.BarCode for .NET** μέσω NuGet. Εγκαταστήστε το με:

```bash
dotnet add package Aspose.BarCode
```

* Πρόσβαση εγγραφής σε φάκελο όπου θα αποθηκευτούν τα παραγόμενα αρχεία PNG.

Αυτές οι απαιτήσεις διασφαλίζουν ότι ο κώδικας θα μεταγλωττιστεί και θα εκτελεστεί χωρίς πρόσθετη διαμόρφωση.

## Πώς να ορίσετε στήλες barcode σε C#

Το πρώτο σημαντικό βήμα είναι η δημιουργία μιας στιγμής `BarcodeGenerator` για τη συμβολή **DataBar Expanded Stacked** και η ανάθεση του επιθυμητού αριθμού στηλών.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Γιατί λειτουργεί:**  
`EncodeTypes.DatabarExpandedStacked` ενημερώνει τη βιβλιοθήκη ποια συμβολή πρέπει να αποδοθεί. Η ρύθμιση του `Parameters.Barcode.DataBar.Columns` αλλάζει τη διαρρύθμιση των εσωτερικών μονάδων, επηρεάζοντας άμεσα το οπτικό πλάτος του barcode. Η μέθοδος `Save` γράφει την εικόνα στο δίσκο με τη ζητούμενη μορφή `BarCodeImageFormat`.

### Αναμενόμενο αποτέλεσμα
Ανοίξτε το `C:\Barcodes\DatabarCols4.png` σε οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε ένα DataBar Expanded Stacked barcode που είναι πιο φαρδύ από το προεπιλεγμένο, επειδή χρησιμοποιεί τέσσερις στήλες.

## Πώς να ορίσετε σειρές barcode σε C#

Αφού αποθηκεύσετε την εικόνα με τις στήλες, μπορεί να θέλετε ένα barcode που διαφέρει σε ύψος προσαρμόζοντας τις σειρές. Η διαδικασία είναι παρόμοια με τη ρύθμιση των στηλών, αλλά χρησιμοποιεί την ιδιότητα `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Γιατί λειτουργεί:**  
Η επανεκκίνηση του generator εξασφαλίζει ότι η προηγούμενη ρύθμιση στηλών δεν επηρεάζει τη διαμόρφωση των σειρών. Η αλλαγή του `Parameters.Barcode.DataBar.Rows` τροποποιεί το ύψος του barcode, παράγοντας μια πιο ψηλή εικόνα όταν ο αριθμός σειρών υπερβαίνει το προεπιλεγμένο.

### Αναμενόμενο αποτέλεσμα
Ανοίξτε το `C:\Barcodes\DatabarRows3.png`. Το barcode θα εμφανιστεί πιο ψηλό, αντανακλώντας τη διαμόρφωση τριών σειρών.

## Πλήρες παράδειγμα από άκρο σε άκρο

Παρακάτω υπάρχει ένα ενιαίο πρόγραμμα που δημιουργεί και τις δύο εικόνες σε μία εκτέλεση. Η διατήρηση του κώδικα σε ένα αρχείο δείχνει πώς μπορείτε να εναλλάσσετε μεταξύ ρυθμίσεων στηλών και σειρών χωρίς επανεκκίνηση της εφαρμογής.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Η εκτέλεση του προγράμματος παράγει δύο αρχεία PNG:

* **DatabarCols4.png** – barcode με τέσσερις στήλες.  
* **DatabarRows3.png** – barcode με τρεις σειρές.

Και τα δύο αρχεία χρησιμοποιούν τη **μορφή εικόνας barcode** PNG, η οποία διατηρεί τις αιχμηρές άκρες και υποστηρίζει συμπίεση χωρίς απώλειες — ιδανική για εκτύπωση και ψηφιακή προβολή.

## Συχνές ερωτήσεις και συμβουλές

| Ερώτηση | Απάντηση |
|----------|--------|
| *Μπορώ να χρησιμοποιήσω JPEG αντί για PNG;* | Ναι. Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg`. Το JPEG είναι μικρότερο αλλά εισάγει συμπιεστικά artefacts, που μπορεί να επηρεάσουν την αξιοπιστία του scanner. |
| *Ποιος είναι ο μέγιστος αριθμός στηλών ή σειρών;* | Η βιβλιοθήκη επικυρώνει τις τιμές βάσει του προτύπου DataBar. Τιμές εκτός του επιτρεπτού εύρους προκαλούν `ArgumentException`. Ελέγξτε την τεκμηρίωση του Aspose.BarCode για τα ακριβή όρια. |
| *Πρέπει να κάνω dispose το `BarcodeGenerator`;* | Η κλάση υλοποιεί το `IDisposable`. Τυλίξτε τον generator σε ένα `using` block αν δημιουργείτε πολλές στιγμές σε βρόχο, ώστε να ελευθερώνονται άμεσα οι μη διαχειριζόμενοι πόροι. |
| *Πώς να αλλάξω το μέγεθος του barcode χωρίς να τροποποιήσω στήλες/σειρές;* | Χρησιμοποιήστε `barcodeGenerator.Parameters.Image.Width` και `Height` για να κλιμακώσετε την έξοδο εικόνας, διατηρώντας αμετάβλητη τη διάταξη των μονάδων. |

**Pro tip:** Όταν δημιουργείτε barcode για εκτύπωση υψηλής ανάλυσης, αυξήστε τις διαστάσεις της εξόδου εικόνας (`Width`/`Height`) αντί για τον αριθμό στηλών ή σειρών. Αυτή η προσέγγιση διατηρεί το τυπικό μέγεθος μονάδας που ορίζεται από τη συμβολή, ενώ σας παρέχει πιο καθαρή εικόνα.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να ορίσετε στήλες και σειρές barcode σε C# χρησιμοποιώντας την κλάση **BarcodeGenerator**. Ο οδηγός κάλυψε την αρχικοποίηση του generator, τη διαμόρφωση των αριθμών στηλών και σειρών, την αποθήκευση του barcode σε μορφή PNG, και την αντιμετώπιση κοινών παραλλαγών όπως η αλλαγή μορφής εικόνας και η διαχείριση πόρων.

Στη συνέχεια, εξερευνήστε συναφή θέματα όπως **προσαρμογή χρωμάτων barcode**, **προσθήκη κειμένου αναγνώσιμου από άνθρωπο**, και **ενσωμάτωση barcode σε έγγραφα PDF**. Όλες αυτές οι επεκτάσεις βασίζονται στο ίδιο πρότυπο διαμόρφωσης που παρουσιάστηκε εδώ, επιτρέποντάς σας να δημιουργήσετε πλήρως εξοπλισμένες λύσεις barcode για οποιαδήποτε εφαρμογή .NET.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}