---
category: general
date: 2026-10-02
description: Δημιουργήστε γρήγορα barcode stacked databars σε C#. Μάθετε να ορίζετε
  το XDimension, να ρυθμίζετε την αναλογία διαστάσεων και να εξάγετε εικόνες PNG με
  έναν δημιουργό barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: el
lastmod: 2026-10-02
og_description: Δημιουργήστε barcode με στοίβαξη databars σε C# με πλήρες παράδειγμα
  κώδικα. Ρυθμίστε το XDimension, αλλάξτε την αναλογία διαστάσεων και αποθηκεύστε
  αρχεία PNG με λίγες μόνο γραμμές.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Δημιουργία στοίβαξης barcode τύπου databars σε C# – γρήγορος οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Δημιουργία barcode με στοιβαγμένες γραμμές δεδομένων σε C# – βήμα‑βήμα οδηγός
url: /el/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία stacked databars barcode σε C# – βήμα‑βήμα οδηγός

Αν χρειάζεστε **create stacked databars barcode** σε ένα .NET έργο, αυτό το tutorial σας δείχνει ακριβώς πώς. Θα δείτε πώς να ρυθμίσετε τη διάσταση X, να αλλάξετε τις αναλογίες διαστάσεων και να αποθηκεύσετε το αποτέλεσμα ως αρχεία PNG—όλα με τη βιβλιοθήκη Aspose.BarCode.

Η δημιουργία ενός stacked DataBar barcode δεν απαιτεί πολύπλοκο pipeline γραφικών. Στο τέλος αυτού του οδηγού θα έχετε δύο έτοιμες PNG εικόνες που απεικονίζουν διαφορετικές αναλογίες διαστάσεων, και θα καταλάβετε γιατί αυτές οι παράμετροι είναι σημαντικές για την αξιοπιστία σάρωσης.

## Τι θα χρειαστείτε

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+)
- Visual Studio 2022 ή οποιοδήποτε IDE για C#
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Δικαίωμα εγγραφής σε φάκελο όπου θα αποθηκευτούν τα αρχεία PNG

## Βήμα 1: Ρύθμιση του έργου και εισαγωγή namespaces

Δημιουργήστε μια νέα εφαρμογή console (ή προσθέστε τον κώδικα σε υπάρχον έργο) και εισάγετε τα απαιτούμενα namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Γιατί είναι σημαντικό:** `Aspose.BarCode.Generation` παρέχει την κλάση `BarcodeGenerator`, ενώ το `Aspose.BarCode` περιέχει την απαρίθμηση `BarCodeImageFormat` που χρησιμοποιείται για την αποθήκευση εικόνων.

## Βήμα 2: Αρχικοποίηση του γεννήτρια για stacked omnidirectional DataBar

Η τιμή `EncodeTypes.DatabarStackedOmniDirectional` επιλέγει τη συμβολική αναπαράσταση stacked DataBar. Η συμβολοσειρά δεδομένων πρέπει να ακολουθεί τη μορφή GS1 Application Identifier (AI); εδώ χρησιμοποιούμε μια ψεύτικη τιμή GTIN‑14.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Γιατί είναι σημαντικό:** Ο επιλεγμένος τύπος κωδικοποίησης λέει στη βιβλιοθήκη να αποδώσει ένα *stacked* barcode, το οποίο είναι απαραίτητο για ετικέτες υψηλής πυκνότητας όπου ο κάθετος χώρος είναι περιορισμένος.

## Βήμα 3: Ορισμός του μεγέθους του module (διάσταση X) σε pixel

Η διάσταση X ελέγχει το πλάτος της μικρότερης γραμμής (το “module”). Μια τιμή 2 pixel λειτουργεί καλά για τις περισσότερες εξόδους ανάλυσης οθόνης.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Γιατί είναι σημαντικό:** Οι σαρωτές ερμηνεύουν το πλάτος του module ως τη βασική μονάδα μέτρησης. Πολύ μικρή τιμή μπορεί να προκαλέσει θολές εκτυπώσεις· πολύ μεγάλη σπαταλά χώρο.

## Βήμα 4: Αποθήκευση της πρώτης εικόνας με αναλογία διαστάσεων 15

Η ιδιότητα `AspectRatio` επηρεάζει τη σχέση ύψους προς πλάτος κάθε stacked τμήματος. Μια αναλογία 15 είναι η κοινή προεπιλογή για λιανικές εφαρμογές.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Γιατί είναι σημαντικό:** Μια χαμηλότερη αναλογία δημιουργεί ένα πιο επίπεδο barcode, το οποίο μπορεί να είναι πιο εύκολο στη σάρωση σε ορισμένα υλικά ετικετών. Η μορφή PNG διατηρεί την απώλεια ποιότητας για δοκιμές.

## Βήμα 5: Αλλαγή της αναλογίας σε 30 και αποθήκευση της δεύτερης εικόνας

Η αύξηση της αναλογίας κάνει κάθε stacked τμήμα ψηλότερο, κάτι που μπορεί να βελτιώσει την αξιοπιστία σάρωσης σε φόντο χαμηλής αντίθεσης.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Γιατί είναι σημαντικό:** Διαφορετικοί λιανοπωλητές ή εταίροι logistics μπορεί να απαιτούν συγκεκριμένες διαστάσεις barcode. Η παροχή και των δύο εκδόσεων σας επιτρέπει να συγκρίνετε γρήγορα την απόδοση σάρωσης.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω είναι το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑επικολλήσετε στο `Program.cs`. Συγκεντρώνεται και εκτελείται χωρίς τροποποίηση μετά την εγκατάσταση του πακέτου NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Αναμενόμενο αποτέλεσμα

Η εκτέλεση του προγράμματος δημιουργεί δύο αρχεία στο φάκελο εκτέλεσης:

| Όνομα αρχείου                 | Αναλογία διαστάσεων | Περιγραφή |
|-------------------------------|----------------------|------------|
| `DatabarAspectRatio15.png`    | 15                   | Σύντομο, πιο επίπεδο stacked barcode |
| `DatabarAspectRatio30.png`    | 30                   | Ψηλότερο, πιο παρατεταμένο stacked barcode |

Μπορείτε να ανοίξετε τα αρχεία PNG με οποιονδήποτε προβολέα εικόνων για να επαληθεύσετε ότι το barcode αποδίδεται σωστά.

![Δημιουργία stacked databars barcode παράδειγμα](placeholder-image.png){alt="Δημιουργία stacked databars barcode παράδειγμα"}

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

| Ερώτηση | Απάντηση |
|----------|--------|
| **Μπορώ να χρησιμοποιήσω διαφορετική διάσταση X;** | Ναι. Τυπικές τιμές κυμαίνονται από 1 ως 4 pixel. Μεγαλύτερες τιμές αυξάνουν το μέγεθος του barcode αλλά μπορεί να βελτιώσουν την αναγνωσιμότητα σε εκτυπωτές χαμηλής ανάλυσης. |
| **Τι αν χρειάζομαι διαφορετική συμβολική αναπαράσταση;** | Αντικαταστήστε το `EncodeTypes.DatabarStackedOmniDirectional` με άλλη τιμή `EncodeTypes`, όπως `DatabarStacked` (μη‑omnidirectional) ή `DatabarLimited`. |
| **Πώς αλλάζω τη μορφή εξόδου;** | Χρησιμοποιήστε `BarCodeImageFormat.Jpeg`, `Gif`, ή `Bmp` στην κλήση `Save`. |
| **Είναι υποχρεωτική η μορφή GTIN‑14;** | Η συμβολική αναπαράσταση DataBar απαιτεί μια αριθμητική συμβολοσειρά με κατάλληλο AI (π.χ., `(01)` για GTIN‑14). Προσαρμόστε τα δεδομένα ανάλογα με την περίπτωση χρήσης σας. |
| **Τι γίνεται με τις ρυθμίσεις DPI;** | Ο γεννήτορας σέβεται την ιδιότητα `Resolution`. Για εκτυπώσεις υψηλής ανάλυσης, ορίστε `barcodeGen.Parameters.ImageResolution.DpiX` και `DpiY` αναλόγως. |

## Συμβουλές επαγγελματιών

- **Batch generation:** Τυλίξτε τη λογική αποθήκευσης σε βρόχο και δώστε του μια λίστα GTIN για να παράγετε χιλιάδες barcodes αυτόματα.
- **Validation:** Χρησιμοποιήστε `barcodeGen.Validate()` πριν την αποθήκευση για να εντοπίσετε κακοδιαμορφωμένα δεδομένα νωρίς.
- **Performance:** Η επαναχρησιμοποίηση του ίδιου αντικειμένου `BarcodeGenerator` (αλλάζοντας μόνο τις παραμέτρους) είναι πιο γρήγορη από τη δημιουργία νέου αντικειμένου για κάθε εικόνα.

## Επόμενα βήματα

Τώρα που μπορείτε να **create stacked databars barcode** με προσαρμοσμένες αναλογίες, σκεφτείτε να εξερευνήσετε:

- Προσθήκη κειμένου αναγνώσιμου από άνθρωπο κάτω από το barcode (`barcodeGen.Parameters.Barcode.CodeText`).
- Εξαγωγή σε **PDF** για εκτυπώσιμα φύλλα ετικετών (`BarCodeImageFormat.Pdf`).
- Ενσωμάτωση του γεννήτρια σε web API για παροχή barcodes κατ' απαίτηση.
- Πειραματισμός με άλλες **δευτερεύουσες λέξεις‑κλειδιά** όπως *C# barcode generator* και *barcode aspect ratio* για να βελτιώσετε την υλοποίησή σας για συγκεκριμένο υλικό.

Καλό κώδικα, και απολαύστε την ευελιξία που προσφέρει η Aspose.BarCode στα C# barcode έργα σας!

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικά θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία stacked databar barcode σε C# – βήμα‑βήμα οδηγός](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [stacked omnidirectional databar barcode σε C# – Πλήρης Οδηγός](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Πώς να δημιουργήσετε εικόνες databar PNG με C# και Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}