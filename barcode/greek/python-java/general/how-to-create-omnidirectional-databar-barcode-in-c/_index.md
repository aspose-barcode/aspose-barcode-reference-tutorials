---
category: general
date: 2026-09-29
description: Μάθετε πώς να δημιουργήσετε πολυκατευθυντικό barcode Databar σε C# με
  το Aspose.BarCode. Ρυθμίστε τη διάσταση X, ορίστε την αναλογία διαστάσεων και αποθηκεύστε
  εικόνες PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: el
lastmod: 2026-09-29
og_description: Δημιουργήστε πολυκατευθυντικό barcode Databar σε C# χρησιμοποιώντας
  το Aspose.BarCode. Μάθετε πώς να ορίζετε τη διάσταση X, να ρυθμίζετε την αναλογία
  διαστάσεων και να εξάγετε αρχεία PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Δημιουργήστε πολυκατευθυντικό barcode Databar σε C# – οδηγός βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Πώς να δημιουργήσετε πολυκατευθυντικό Databar barcode σε C#
url: /el/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε πολυκατευθυντικό Databar barcode σε C#

Αν χρειάζεστε **να δημιουργήσετε πολυκατευθυντικό Databar barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει τα ακριβή βήματα. Θα δείτε πώς να αρχικοποιήσετε ένα DataBar stacked πολυκατευθυντικό barcode, να ρυθμίσετε τη διάσταση X, να αλλάξετε την αναλογία διαστάσεων και να δημιουργήσετε εικόνες PNG με το Aspose.BarCode.

Η δημιουργία ενός **DataBar stacked πολυκατευθυντικού barcode** είναι συνηθισμένη όταν πρέπει να κωδικοποιήσετε αναγνωριστικά προϊόντων για σαρωτές λιανικής. Σε αυτό το tutorial θα μάθετε να **ορίζετε την αναλογία διαστάσεων του barcode**, να ελέγχετε το μέγεθος του μονάδας και να εξάγετε το αποτέλεσμα χωρίς να αφήσετε το IDE.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερη έκδοση εγκατεστημένη
- Visual Studio 2022 (ή οποιοδήποτε IDE συμβατό με C#)
- Το πακέτο NuGet **Aspose.BarCode for .NET** (έκδοση 23.12 ή νεότερη)

Μπορείτε να προσθέσετε το πακέτο μέσω του NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Αρχικοποίηση του πολυκατευθυντικού Databar barcode

Το πρώτο βήμα είναι να δημιουργήσετε μια παρουσία `BarcodeGenerator` που στοχεύει στη συμβολολογία **DataBar stacked πολυκατευθυντικό**. Ο κατασκευαστής λαμβάνει τον τύπο κωδικοποίησης και τη συμβολοσειρά δεδομένων.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Γιατί είναι σημαντικό:** Η τιμή `EncodeTypes.DatabarStackedOmniDirectional` ενημερώνει το Aspose.BarCode να αποδώσει τη συγκεκριμένη μορφή πολυκατευθυντικού Databar, η οποία απαιτείται για σάρωση και στις δύο κατευθύνσεις.

## Βήμα 2: Ορισμός της διάστασης X (μέγεθος μονάδας)

Η διάσταση X ελέγχει το πλάτος μιας μονάδας barcode σε εικονοστοιχεία (pixels). Μια τιμή `2` pixels λειτουργεί καλά για απόδοση στην οθόνη και στους περισσότερους εκτυπωτές.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Γιατί είναι σημαντικό:** Μια συνεπής διάσταση X εξασφαλίζει ότι το barcode πληροί τις ελάχιστες προδιαγραφές μεγέθους για σαρωτές λιανικής, ενώ διατηρεί το μέγεθος του αρχείου εικόνας διαχειρίσιμο.

## Βήμα 3: Ορισμός της πρώτης αναλογίας διαστάσεων και αποθήκευση της εικόνας

Η **αναλογία διαστάσεων** καθορίζει τη σχέση ύψους προς πλάτος του DataBar. Μια αναλογία `15` παράγει ένα συμπαγές, ψηλό barcode ιδανικό για στενούς χώρους ετικετών.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Γιατί είναι σημαντικό:** Η ρύθμιση της αναλογίας διαστάσεων σας επιτρέπει να προσαρμόσετε το barcode σε διαφορετικές διατάξεις ετικετών χωρίς να θυσιάζετε την αναγνωσιμότητα. Το αποθηκευμένο PNG μπορεί να ελεγχθεί σε οποιονδήποτε προβολέα εικόνων.

## Βήμα 4: Αλλαγή της αναλογίας διαστάσεων και δημιουργία δεύτερης εικόνας

Μερικές φορές απαιτείται ένα πιο πλατύ barcode—π.χ., όταν η ετικέτα διαθέτει περισσότερο οριζόντιο χώρο. Η αλλαγή της αναλογίας σε `30` δημιουργεί μια πιο επίπεδη εμφάνιση.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Γιατί είναι σημαντικό:** Με την έκθεση της ιδιότητας **set barcode aspect ratio**, μπορείτε να παράγετε πολλαπλές παραλλαγές barcode από μία βάση κώδικα, απλοποιώντας τις αυτοματοποιημένες διαδικασίες δημιουργίας ετικετών.

## Αναμενόμενο αποτέλεσμα

| Όνομα αρχείου                | Αναλογία διαστάσεων | Οπτική περιγραφή |
|------------------------------|---------------------|-------------------|
| `DatabarAspectRatio15.png`   | 15                  | Ψηλό, στενό barcode κατάλληλο για στενές ετικέτες |
| `DatabarAspectRatio30.png`   | 30                  | Πλατύτερο barcode που γεμίζει περισσότερο οριζόντιο χώρο |

![Παράδειγμα δημιουργίας πολυκατευθυντικού Databar barcode](databar-example.png "Create omnidirectional Databar barcode example")

*Το στιγμιότυπο δείχνει τα δύο παραγόμενα αρχεία PNG δίπλα-δίπλα.*

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

### Τι γίνεται αν χρειάζομαι διαφορετική διάσταση X;

Μπορείτε να ορίσετε οποιαδήποτε ακέραια τιμή στο `XDimension.Pixels`. Τιμές κάτω από `1` αγνοούνται, και τιμές πάνω από `10` μπορεί να δημιουργήσουν υπερμεγέθη μονάδες που υπερβαίνουν τα περιθώρια του εκτυπωτή. Δοκιμάστε το οπτικό αποτέλεσμα μετά από κάθε αλλαγή.

### Πώς κωδικοποιώ άλλα δεδομένα AI (π.χ., UPC, EAN);

Αντικαταστήστε τη συμβολοσειρά δεδομένων στον κατασκευαστή `BarcodeGenerator` με το κατάλληλο Αναγνωριστικό Εφαρμογής (AI). Για κωδικό UPC‑A, χρησιμοποιήστε `"012345678905"` χωρίς πρόθεμα AI.

### Μπορώ να εξάγω σε μορφές εκτός του PNG;

Ναι. Η μέθοδος `Save` δέχεται `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` και `BarCodeImageFormat.Bmp`. Επιλέξτε τη μορφή που ταιριάζει στη συνέχεια της ροής εργασίας σας.

## Συμβουλή επαγγελματία: επαναχρησιμοποίηση του γεννήτριας για επεξεργασία παρτίδας

Αν χρειάζεται να δημιουργήσετε δεκάδες barcodes με διαφορετικές αναλογίες διαστάσεων, διατηρήστε τη στιγμή `BarcodeGenerator` ενεργή και τροποποιήστε μόνο το `DataBar.AspectRatio` πριν από κάθε `Save`. Αυτό αποφεύγει το κόστος επανεκκίνησης του γεννήτριας για κάθε εικόνα.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε πολυκατευθυντικό Databar barcode** σε C# χρησιμοποιώντας το Aspose.BarCode. Αρχικοποιώντας ένα `BarcodeGenerator`, ορίζοντας τη διάσταση X, ρυθμίζοντας την **set barcode aspect ratio** και αποθηκεύοντας αρχεία PNG, μπορείτε να παράγετε εικόνες barcode που καλύπτουν διάφορες απαιτήσεις ετικετών.  

Στη συνέχεια, εξερευνήστε συναφή θέματα όπως **generate barcode image** για QR codes, **DataBar stacked omnidirectional barcode** validation, ή την ενσωμάτωση των παραγόμενων PNG σε τιμολόγια PDF με το Aspose.PDF. Πειραματιστείτε με διαφορετικές αναλογίες διαστάσεων και μεγέθη μονάδων για να βρείτε τη βέλτιστη διαμόρφωση για το συγκεκριμένο υλικό εκτύπωσης σας.

---

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικά θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to generate barcode in C# – create barcode image c# with DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}