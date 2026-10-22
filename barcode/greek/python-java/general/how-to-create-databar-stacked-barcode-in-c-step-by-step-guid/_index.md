---
category: general
date: 2026-10-21
description: Δημιουργήστε γρήγορα γραμμωτό κώδικα Databar stacked χρησιμοποιώντας
  C#. Μάθετε πώς να ορίζετε τη διάσταση X, να ρυθμίζετε την αναλογία διαστάσεων και
  να αποθηκεύετε εικόνες PNG σε αυτό το πλήρες σεμινάριο.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: el
lastmod: 2026-10-21
og_description: Δημιουργήστε γραμμωτό κώδικα databar stacked σε C# με το Aspose.BarCode.
  Ακολουθήστε αυτόν τον οδηγό για να ρυθμίσετε τη διάσταση X, να αλλάξετε την αναλογία
  διαστάσεων και να εξάγετε αρχεία PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Δημιουργήστε κωδικό γραμμής databar stacked σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Πώς να δημιουργήσετε στοίβα κωδικού databar σε C# – βήμα‑βήμα οδηγός
url: /el/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε κωδικογράφημα databar stacked σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **create databar stacked barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς. Θα δείτε πώς να ρυθμίσετε τη διάσταση X, να αλλάξετε την αναλογία διαστάσεων και να αποθηκεύσετε το κωδικογράφημα ως αρχεία PNG.

Η δημιουργία ενός DataBar stacked barcode δεν απαιτεί πολύπλοκο pipeline κατασκευής. Αυτό το tutorial καλύπτει όλα όσα χρειάζεστε: απαιτούμενα πακέτα, εξήγηση κώδικα‑βήμα‑βήμα και συμβουλές για κοινές παγίδες. Στο τέλος θα μπορείτε να παράγετε πολλαπλές εικόνες κωδικογράφησης με διαφορετικές αναλογίες διαστάσεων σε μία μόνο μέθοδο.

## Τι θα χρειαστείτε

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE που υποστηρίζει C#)  
* **Aspose.BarCode for .NET** πακέτο NuGet – η βιβλιοθήκη που παρέχει `BarcodeGenerator` και `EncodeTypes`  

Μπορείτε να προσθέσετε το πακέτο με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Ρυθμίστε το έργο και εισάγετε τα namespaces

Δημιουργήστε ένα νέο console project ή προσθέστε τον κώδικα σε ένα υπάρχον. Εισάγετε τα απαιτούμενα namespaces ώστε ο μεταγλωττιστής να αναγνωρίζει τις κλάσεις κωδικογράφησης.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Αυτές οι δηλώσεις `using` εκθέτουν τα `BarcodeGenerator`, `EncodeTypes` και `BarCodeImageFormat` που χρησιμοποιούνται αργότερα στο παράδειγμα.

## Βήμα 2: Ορίστε το φάκελο εξόδου

Επιλέξτε έναν φάκελο όπου θα γραφτούν τα παραγόμενα αρχεία PNG. Η χρήση απόλυτης ή σχετικής διαδρομής λειτουργεί με τον ίδιο τρόπο· το παράδειγμα χρησιμοποιεί έναν σχετικό φάκελο που ονομάζεται `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Η δημιουργία του φακέλου προγραμματιστικά αποτρέπει σφάλματα χρόνου εκτέλεσης όταν ο φάκελος λείπει.

## Βήμα 3: Αρχικοποιήστε το **create databar stacked barcode** generator

Δημιουργήστε μια παρουσία `BarcodeGenerator` με `EncodeTypes.DatabarStackedOmniDirectional`. Τα δείγμα δεδομένων `(01)12345678901231` ακολουθούν τη μορφή GS1‑128 που απαιτείται από το DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Το αντικείμενο του γεννήτριας περιέχει όλες τις παραμέτρους που επηρεάζουν την οπτική εμφάνιση του κωδικογράφηματος.

## Βήμα 4: Ορίστε τη διάσταση X (πλάτος pixel της μικρότερης γραμμής)

Η διάσταση X ελέγχει το συνολικό μέγεθος του κωδικογράφηματος χωρίς να αλλάζει τα κωδικοποιημένα δεδομένα. Μια τιμή `2` pixel παρέχει καθαρή, αναγνώσιμη εικόνα για τις περισσότερες αναλύσεις οθόνης.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ρυθμίστε αυτή την τιμή αν χρειάζεστε μεγαλύτερο ή μικρότερο κωδικογράφημα· διατηρήστε την αναλογία μεταξύ πλάτους και ύψους συνεπή.

## Βήμα 5: Διαμορφώστε την αναλογία διαστάσεων και αποθηκεύστε την πρώτη εικόνα

Η αναλογία διαστάσεων καθορίζει τη σχέση ύψους‑πλάτους ενός DataBar stacked barcode. Μια αναλογία `15` είναι η κοινή προεπιλογή που δίνει ένα συμπαγές αποτέλεσμα.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Η μέθοδος `Save` γράφει ένα αρχείο PNG στον φάκελο που ορίστηκε νωρίτερα. Το όνομα του αρχείου υποδεικνύει σαφώς την χρησιμοποιημένη αναλογία διαστάσεων.

### Αναμενόμενο αποτέλεσμα για αναλογία διαστάσεων 15

Η παραγόμενη εικόνα `DatabarAspectRatio15.png` φαίνεται παρόμοια με την παρακάτω εικονογράφηση.

![Εικόνα κωδικογράφηματος που δημιουργήθηκε με αναλογία διαστάσεων 15](https://example.com/images/databar-aspect15.png "Εικόνα κωδικογράφηματος που δημιουργήθηκε με αναλογία διαστάσεων 15")

*Κείμενο alt:* `create databar stacked barcode image saved with aspect ratio 15`

## Βήμα 6: Αλλάξτε την αναλογία διαστάσεων και αποθηκεύστε μια δεύτερη εικόνα

Μπορείτε να επαναχρησιμοποιήσετε την ίδια παρουσία `BarcodeGenerator` για να δημιουργήσετε παραλλαγές. Αλλάζοντας το `AspectRatio` σε `30` διπλασιάζει το ύψος κάθε στοίβας γραμμών, κάτι που μπορεί να απαιτείται για εκτύπωση υψηλής ανάλυσης.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Αναμενόμενο αποτέλεσμα για αναλογία διαστάσεων 30

Η εικόνα `DatabarAspectRatio30.png` είναι πιο ψηλή, διατηρώντας το ίδιο πλάτος ενώ αυξάνει την αναγνωσιμότητα για απομακρυσμένους σαρωτές.

![Εικόνα κωδικογράφηματος που δημιουργήθηκε με αναλογία διαστάσεων 30](https://example.com/images/databar-aspect30.png "Εικόνα κωδικογράφηματος που δημιουργήθηκε με αναλογία διαστάσεων 30")

*Κείμενο alt:* `create databar stacked barcode image saved with aspect ratio 30`

## Πλήρης κώδικας πηγής

Συνδυάζοντας όλα τα βήματα προκύπτει ένα αυτόνομο πρόγραμμα που μπορείτε να εκτελέσετε αμέσως.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Συγκεντρώστε και τρέξτε το πρόγραμμα. Μετά την εκτέλεση, ο φάκελος `Barcodes` περιέχει δύο αρχεία PNG, το καθένα αντιπροσωπεύει ένα **create databar stacked barcode** με διαφορετική αναλογία διαστάσεων.

## Συμβουλές επαγγελματιών και κοινές παγίδες

* **Συμβουλή επαγγελματία:** Κρατήστε τη διάσταση X μεταξύ 1 px και 4 px για τις περισσότερες περιπτώσεις χρήσης σε οθόνες. Μεγαλύτερες τιμές αυξάνουν το μέγεθος του αρχείου χωρίς να βελτιώνουν την αξιοπιστία σάρωσης.  
* **Παγίδα:** Η αλλαγή της τιμής `EncodeTypes` μετά τη δημιουργία του γεννήτρια δεν ενημερώνει την εσωτερική κωδικοποίηση. Πάντα καθορίζετε το σωστό `EncodeTypes` στον κατασκευαστή.  
* **Συμβουλή επαγγελματία:** Όταν χρειάζεστε περισσότερες από δύο αναλογίες διαστάσεων, κάντε επανάληψη πάνω σε έναν πίνακα ακέραιων τιμών και καλέστε το `Save` μέσα στη βρόχο. Αυτό μειώνει την επανάληψη κώδικα.  
* **Παγίδα:** Η αποθήκευση σε διαδρομή χωρίς δικαιώματα εγγραφής προκαλεί `UnauthorizedAccessException`. Βεβαιωθείτε ότι η εφαρμογή εκτελείται με τα κατάλληλα δικαιώματα συστήματος αρχείων.

## Συμπέρασμα

Τώρα ξέρετε πώς να **create databar stacked barcode** σε C# χρησιμοποιώντας το Aspose.BarCode. Ο οδηγός κάλυψε τη ρύθμιση του περιβάλλοντος, τη διαμόρφωση της διάστασης X, την προσαρμογή της αναλογίας διαστάσεων και την αποθήκευση αρχείων PNG. Με αυτή τη βάση μπορείτε να δημιουργήσετε επιπλέον παραλλαγές, να ενσωματώσετε τη δημιουργία κωδικογράφησης σε web APIs ή να ενσωματώσετε τις εικόνες σε PDF αναφορές.

Στη συνέχεια, εξερευνήστε σχετικά θέματα όπως οι βέλτιστες πρακτικές σάρωσης **DataBar Stacked Omnidirectional**, η ενσωμάτωση κωδικογραμμάτων σε απαντήσεις **ASP.NET Core**, ή η δημιουργία **QR codes** με την ίδια βιβλιοθήκη. Πειραματιστείτε με διαφορετικά `EncodeTypes` και μορφές εικόνας για να ταιριάξουν στις ανάγκες της εφαρμογής σας.

Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

- [Πώς να δημιουργήσετε εικόνες PNG databar με C# και Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Πώς να ορίσετε στήλες για ένα Databar Expanded Stacked barcode – πλήρης οδηγός C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode σε C# – Πλήρης Οδηγός](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}