---
category: general
date: 2026-08-19
description: Δημιουργήστε αρχεία PNG τύπου databar σε C# με το Aspose.BarCode. Μάθετε
  πώς να δημιουργείτε εικόνες databar, να ρυθμίζετε τις παραμέτρους databar και να
  αποθηκεύετε την έξοδο PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: el
lastmod: 2026-08-19
og_description: Δημιουργήστε αρχεία PNG τύπου databar σε C# χρησιμοποιώντας το Aspose.BarCode.
  Αυτό το σεμινάριο σας καθοδηγεί στη δημιουργία εικόνων databar, στη ρύθμιση παραμέτρων
  databar όπως η διάσταση X και η αναλογία διαστάσεων, και στην αποθήκευση αρχείων
  PNG υψηλής ποιότητας για εκτύπωση ή χρήση στο web.
og_image_alt: create databar PNG example
og_title: Δημιουργία εικόνων databar PNG σε C# – οδηγός βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Πώς να δημιουργήσετε εικόνες PNG τύπου databar με C# και Aspose.BarCode
url: /el/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε εικόνες PNG τύπου databar με C# και Aspose.BarCode

Αν χρειάζεστε **να δημιουργήσετε αρχεία databar PNG** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς. Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που δημιουργεί στοίβαξη (stacked) omnidirectional DataBar κώδικες, ρυθμίζει βασικές παραμέτρους και αποθηκεύει δύο αρχεία PNG με διαφορετικές αναλογίες διαστάσεων.

Η δημιουργία μιας εικόνας DataBar δεν περιορίζεται μόνο στην κλήση μιας μεθόδου. Πρέπει επίσης να **ρυθμίσετε τις παραμέτρους databar** όπως η διάσταση X (πλάτος μονάδας) και η αναλογία διαστάσεων ώστε να πληρούν τις προδιαγραφές εκτύπωσης ή σάρωσης. Στο τέλος αυτού του tutorial θα κατανοήσετε **πώς να παράγετε γραφικά databar** που λειτουργούν αξιόπιστα σε πραγματικές συνθήκες.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
- Visual Studio 2022 ή οποιοδήποτε IDE συμβατό με C#
- Έγκυρη άδεια για **Aspose.BarCode for .NET** (η δωρεάν αξιολόγηση λειτουργεί για δοκιμές)
- Βασική εξοικείωση με τη σύνταξη της C#

> **Συμβουλή επαγγελματία:** Αν δεν έχετε ακόμη άδεια, μπορείτε να ζητήσετε ένα προσωρινό κλειδί αξιολόγησης από το portal της Aspose. Το API συμπεριφέρεται το ίδιο· μόνο το υδατογράφημα αλλάζει.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Ανοίξτε το έργο σας στο Visual Studio, κάντε δεξί‑κλικ στη λύση και επιλέξτε **Manage NuGet Packages**. Αναζητήστε `Aspose.BarCode` και εγκαταστήστε την πιο πρόσφατη σταθερή έκδοση.

```bash
dotnet add package Aspose.BarCode
```

Αυτή η εντολή προσθέτει το assembly `Aspose.BarCode` στο έργο σας και καθιστά διαθέσιμη την κλάση `BarcodeGenerator`.

## Βήμα 2: Αρχικοποίηση του δημιουργού barcode για στοίβαξη (stacked) omnidirectional DataBar

Ο κατασκευαστής `BarcodeGenerator` δέχεται δύο ορίσματα: τον τύπο του barcode και τη σειρά των ακατέργαστων δεδομένων. Για ένα stacked omnidirectional DataBar χρησιμοποιείτε `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Γιατί είναι σημαντικό:** Η σταθερά `EncodeTypes.DatabarStackedOmniDirectional` λέει στη βιβλιοθήκη να παράγει ένα barcode που μπορεί να διαβαστεί από οποιονδήποτε προσανατολισμό, κάτι ιδανικό για ετικέτες ραφιών λιανικής.

## Βήμα 3: Ρύθμιση της διάστασης X (πλάτος μονάδας) σε εικονοστοιχεία

Η διάσταση X ελέγχει το μέγεθος του μικρότερου στοιχείου μπάρας. Ορίζοντάς την σε εικονοστοιχεία έχετε ακριβή έλεγχο του τελικού μεγέθους της εικόνας.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Μια τιμή **2 εικονοστοιχεία** είναι καλή ισορροπία μεταξύ αναγνωσιμότητας και συμπαγούς μεγέθους για τις περισσότερες εκτυπωτές ετικετών. Προσαρμόστε αυτήν την τιμή αν χρειάζεστε μεγαλύτερες ή μικρότερες μονάδες.

## Βήμα 4: Ορισμός της πρώτης αναλογίας διαστάσεων και αποθήκευση του PNG

Η αναλογία διαστάσεων επηρεάζει το ύψος του stacked DataBar. Μια αναλογία **15** παράγει ένα σχετικά κοντό barcode, ενώ η **30** το κάνει πιο ψηλό.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Η μέθοδος `Save` γράφει το παραγόμενο barcode σε αρχείο PNG. Το PNG είναι lossless, διατηρώντας τις καθαρές άκρες που απαιτούνται για τους σαρωτές barcode.

## Βήμα 5: Αλλαγή της αναλογίας διαστάσεων και αποθήκευση δεύτερου PNG

Μπορείτε να επαναχρησιμοποιήσετε το ίδιο αντικείμενο `BarcodeGenerator` για να δημιουργήσετε παραλλαγές απλώς αλλάζοντας την αναλογία διαστάσεων.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Τώρα έχετε δύο αρχεία PNG—`DatabarAspectRatio15.png` και `DatabarAspectRatio30.png`—κάθε ένα με διαφορετική οπτική πυκνότητα.

## Βήμα 6: Επαλήθευση του αποτελέσματος

Ανοίξτε τα παραγόμενα αρχεία PNG σε οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε ένα καθαρό, υψηλής αντίθεσης DataBar barcode. Η σάρωση των εικόνων με έναν σαρωτή barcode σε smartphone επιβεβαιώνει ότι και οι δύο αναλογίες διαστάσεων αποκωδικοποιούν την αρχική τιμή GTIN `12345678901231`.

![create databar PNG example](databar_example.png)

*Η παραπάνω εικόνα δείχνει τα δύο αρχεία PNG δίπλα‑δίπλα. Η αριστερή εικόνα χρησιμοποιεί αναλογία 15, η δεξιά αναλογία 30.*

## Συνηθισμένες παραλλαγές και περιπτώσεις άκρων

| Σενάριο | Τι να αλλάξετε | Αιτία |
|----------|----------------|--------|
| **Διαφορετικά δεδομένα** | Αντικαταστήστε τη συμβολοσειρά `(01)12345678901231` με οποιονδήποτε έγκυρο Αναγνωριστικό Εφαρμογής GS1 και δεδομένα | Σας επιτρέπει να κωδικοποιήσετε αναγνωριστικά προϊόντων, σειριακούς αριθμούς κ.λπ. |
| **Υψηλότερη ανάλυση** | Αυξήστε το `XDimension.Pixels` σε 3 ή 4 | Απαιτείται όταν το barcode θα εκτυπωθεί σε μεγάλες διαστάσεις ή θα σαρωθεί από απόσταση. |
| **Άλλοι τύποι DataBar** | Χρησιμοποιήστε `EncodeTypes.DatabarStacked` ή `EncodeTypes.DatabarExpanded` | Επιλέξτε τον τύπο που ταιριάζει καλύτερα στη διάταξη της ετικέτας σας. |
| **Διαφανές φόντο** | Pass `BarCodeImageFormat.Png` with `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Χρήσιμο για επικάλυψη του barcode σε χρωματιστές ετικέτες. |

> **Προσοχή:** Ο ορισμός μιας διάστασης X που είναι πολύ μικρή (< 1 pixel) μπορεί να δημιουργήσει ένα barcode που φαίνεται θολό μετά από

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε και να προσαρμόσετε το ύψος του Barcode για One‑Dimensional Databar χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Δημιουργία One‑Dimensional Databar κωδικοποίησης GS1 με Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Δημιουργία Databar barcode με Aspose.BarCode χρησιμοποιώντας .NET API – Ρύθμιση γραμμής & στήλης](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}