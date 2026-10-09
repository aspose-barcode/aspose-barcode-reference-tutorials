---
category: general
date: 2026-10-08
description: Μάθετε πώς να δημιουργήσετε εικόνα barcode σε C# και ανακαλύψτε πώς να
  ρυθμίσετε την αναλογία διαστάσεων για τα DataBar stacked omni‑directional barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: el
lastmod: 2026-10-08
og_description: Δημιουργήστε εικόνα barcode σε C# και μάθετε πώς να ρυθμίσετε την
  αναλογία διαστάσεων για τα DataBar stacked omni‑directional barcodes με ένα πλήρες
  παράδειγμα κώδικα.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Δημιουργία εικόνας barcode σε C# – βήμα‑βήμα οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να δημιουργήσετε εικόνα barcode και να προσαρμόσετε την αναλογία διαστάσεων
  σε C#
url: /el/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε εικόνα barcode και να προσαρμόσετε την αναλογία διαστάσεων σε C#

Αν χρειάζεστε να **δημιουργήσετε εικόνα barcode** προγραμματιστικά, αυτός ο οδηγός σας παρουσιάζει μια πλήρη, έτοιμη‑για‑εκτέλεση λύση. Θα δείτε ακριβώς **πώς να προσαρμόσετε την αναλογία διαστάσεων** για ένα DataBar stacked omni‑directional barcode, μια απαίτηση που εμφανίζεται συχνά σε εφαρμογές λιανικής και εφοδιαστικής.

Σε αυτό το tutorial θα μάθετε πώς να:
* Αρχικοποιήσετε ένα Aspose.BarCode `BarcodeGenerator` για τη συμβολική DataBar stacked omni‑directional.
* Ορίσετε τη διάσταση X (πλάτος μονάδας) σε pixel για να ελέγξετε το πάχος των γραμμών.
* Εφαρμόσετε δύο διαφορετικές αναλογίες διαστάσεων και αποθηκεύσετε κάθε αποτέλεσμα ως αρχείο PNG.
* Επαληθεύσετε το αποτέλεσμα και κατανοήσετε γιατί η αναλογία διαστάσεων είναι σημαντική.

Δεν απαιτούνται εξωτερικά εργαλεία—μόνο η βιβλιοθήκη Aspose.BarCode για .NET και ένα περιβάλλον ανάπτυξης .NET 6 (ή νεότερο).

## Πώς να δημιουργήσετε εικόνα barcode με το Aspose.BarCode

Το πρώτο βήμα είναι να δημιουργήσετε μια παρουσία του γεννήτριας με τη ζητούμενη συμβολική και τη συμβολοσειρά δεδομένων. Η enum `EncodeTypes.DatabarStackedOmniDirectional` ενημερώνει το Aspose.BarCode να παράγει ένα DataBar stacked omni‑directional barcode, το οποίο χρησιμοποιείται ευρέως για εφαρμογές GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Γιατί είναι σημαντικό:** Το αντικείμενο `BarcodeGenerator` είναι το σημείο εισόδου για όλες τις εργασίες δημιουργίας barcode. Καθορίζοντας τη συμβολική και τα ακατέργαστα δεδομένα εκ των προτέρων, εξασφαλίζετε ότι η παραγόμενη εικόνα συμμορφώνεται με το πρότυπο GS1.

## Ορισμός της διάστασης X (πλάτος μονάδας)

Η διάσταση X ορίζει το πλάτος της πιο στενής γραμμής (της μονάδας). Μια μεγαλύτερη διάσταση X παράγει ένα πιο παχύ barcode, το οποίο μπορεί να είναι χρήσιμο για εκτυπωτές χαμηλής ανάλυσης.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Γιατί είναι σημαντικό:** Η ρύθμιση της διάστασης X αποτελεί μέρος της διαδικασίας οπτικής βελτιστοποίησης. Δεν επηρεάζει τα κωδικοποιημένα δεδομένα, αλλά επηρεάζει την αξιοπιστία σάρωσης σε διαφορετικές συσκευές.

## Πώς να προσαρμόσετε την αναλογία διαστάσεων – πρώτη έκδοση (15)

Η αναλογία διαστάσεων ελέγχει τη σχέση ύψους‑πλάτους του DataBar barcode. Η ιδιότητα `DataBar.AspectRatio` δέχεται ακέραιες τιμές· μεγαλύτεροι αριθμοί παράγουν πιο ψηλές γραμμές.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Γιατί είναι σημαντικό:** Μια αναλογία διαστάσεων 15 είναι μια κοινή προεπιλογή για σαρωτές λιανικής. Το παραγόμενο PNG (`DatabarAspectRatio15.png`) θα έχει πιο ψηλή εμφάνιση, η οποία μπορεί να βελτιώσει την επιτυχία σάρωσης σε φορητές συσκευές.

## Πώς να προσαρμόσετε την αναλογία διαστάσεων – δεύτερη έκδοση (30)

Μπορεί να χρειαστείτε ένα πιο ψηλό barcode για συγκεκριμένες μορφές ετικετών. Η αλλαγή της αναλογίας διαστάσεων είναι τόσο απλή όσο η ανάθεση μιας νέας ακέραιας τιμής πριν καλέσετε ξανά το `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Γιατί είναι σημαντικό:** Δείχνοντας **πώς να προσαρμόσετε την αναλογία διαστάσεων**, μπορείτε να δημιουργήσετε πολλαπλές εικόνες barcode από την ίδια πηγή δεδομένων χωρίς να δημιουργείτε ξανά τον γεννήτρια. Αυτό μειώνει τη χρήση μνήμης και επιταχύνει την επεξεργασία παρτίδων.

### Αναμενόμενο αποτέλεσμα

Μετά την εκτέλεση του προγράμματος θα βρείτε δύο αρχεία PNG στον κατάλογο εκτέλεσης:

| Όνομα αρχείου                     | Αναλογία διαστάσεων | Περιγραφή εμφάνισης |
|-----------------------------------|---------------------|----------------------|
| `DatabarAspectRatio15.png`        | 15                  | Κανονικό ύψος, κατάλληλο για τους περισσότερους σαρωτές σημείου πώλησης. |
| `DatabarAspectRatio30.png`        | 30                  | Ψηλότερες γραμμές, χρήσιμο για μεγάλες ετικέτες ή εκτυπωτές χαμηλής ανάλυσης. |

Και οι δύο εικόνες περιέχουν το ίδιο κωδικοποιημένο GTIN `(01)12345678901231`, αλλά οι οπτικές αναλογίες διαφέρουν ανάλογα με την αναλογία διαστάσεων που ορίσατε.

## Συχνές ερωτήσεις και διαχείριση ειδικών περιπτώσεων

### Τι γίνεται αν χρειάζομαι διαφορετική διάσταση X;

Μπορείτε να αλλάξετε το `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` σε οποιονδήποτε ακέραιο μεγαλύτερο του μηδενός. Για εξόδους πολύ υψηλής ανάλυσης (π.χ., 300 dpi), μια τιμή 3‑4 pixel συχνά δίνει πιο καθαρά αποτελέσματα.

### Πώς να επιλέξω τη σωστή αναλογία διαστάσεων;

Η βέλτιστη αναλογία εξαρτάται από το περιβάλλον σάρωσης:

* **Ετικέτες χαμηλού προφίλ** – χρησιμοποιήστε μικρότερη αναλογία (π.χ., 10‑15) για να διατηρήσετε το barcode συμπαγές.
* **Μεγάλα εμπορευματικά κοντέινερ** – υψηλότερη αναλογία (π.χ., 25‑35) βελτιώνει την αναγνωσιμότητα από απόσταση.
* **Κανονιστικές απαιτήσεις** – ορισμένα πρότυπα απαιτούν ελάχιστο ύψος· συμβουλευτείτε την προδιαγραφή GS1 για ακριβείς αριθμούς.

### Μπορώ να δημιουργήσω άλλες μορφές barcode με τον ίδιο κώδικα;

Ναι. Αντικαταστήστε το `EncodeTypes.DatabarStackedOmniDirectional` με οποιαδήποτε άλλη τιμή `EncodeTypes` (π.χ., `EncodeTypes.Code128`). Το υπόλοιπο του κώδικα—διάσταση X, αναλογία διαστάσεων (αν υπάρχει), και αποθήκευση—παραμένει το ίδιο.

### Τι γίνεται αν χρειαστεί να δημιουργήσω την εικόνα σε διαφορετική μορφή;

`BarCodeImageFormat` υποστηρίζει PNG, JPEG, BMP, GIF και TIFF. Απλώς αλλάξτε το δεύτερο όρισμα του `Save`, για παράδειγμα:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Συμβουλή επαγγελματία: επαναχρησιμοποίηση του γεννήτρια για επεξεργασία παρτίδων

Όταν πρέπει να δημιουργήσετε δεκάδες barcodes με τις ίδιες οπτικές ρυθμίσεις, δημιουργήστε τον γεννήτρια μία φορά, ενημερώστε μόνο την ιδιότητα `CodeText` και καλέστε επανειλημμένα το `Save`. Αυτό αποφεύγει το κόστος επανειλημμένης κατανομής εσωτερικών buffers.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε εικόνα barcode** σε C# χρησιμοποιώντας το Aspose.BarCode και ακριβώς **πώς να προσαρμόσετε την αναλογία διαστάσεων** για σύμβολα DataBar stacked omni‑directional. Ελέγχοντας τη διάσταση X και την αναλογία διαστάσεων, μπορείτε να παράγετε barcodes που ικανοποιούν οποιαδήποτε απαίτηση σάρωσης ή διάταξης, διατηρώντας την υλοποίηση απλή και συντηρήσιμη.

### Επόμενα βήματα

* Εξερευνήστε άλλες συμβολικές όπως **Code128** ή **QR Code** αλλάζοντας την τιμή `EncodeTypes`.
* Συνδυάστε τη δημιουργία barcode με τη δημιουργία PDF (π.χ., χρησιμοποιώντας Aspose.PDF) για να ενσωματώσετε barcodes απευθείας σε τιμολόγια.
* Πειραματιστείτε με δυναμική επιλογή αναλογίας διαστάσεων βάσει του μεγέθους της ετικέτας—αυτό επεκτείνει το μοτίβο **πώς να προσαρμόσετε την αναλογία διαστάσεων** σε μια πλήρη μηχανή σχεδίασης ετικετών.

Νιώστε ελεύθεροι να προσαρμόσετε το παράδειγμα, να μοιραστείτε τα αποτελέσματά σας ή να θέσετε περαιτέρω ερωτήσεις στα σχόλια. Καλή προγραμματιστική!

## Τι Θα Πρέπει Να Μάθετε Στη Σύντομη Μελλοντική Περίοδο;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε databar stacked barcode σε C# με το Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Πώς να δημιουργήσετε εικόνα barcode με το Aspose.Barcode σε C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Πώς να προσαρμόσετε το μέγεθος του Barcode – Codablock F Aspect Ratio με το Aspose.BarCode για .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}