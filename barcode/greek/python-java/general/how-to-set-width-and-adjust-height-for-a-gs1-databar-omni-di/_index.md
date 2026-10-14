---
category: general
date: 2026-09-29
description: Πώς να ορίσετε το πλάτος ενός barcode GS1 DataBar Omni‑Directional και
  πώς να αλλάξετε το ύψος χρησιμοποιώντας C#. Ακολουθήστε έναν οδηγό βήμα‑προς‑βήμα
  με πλήρη κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: el
lastmod: 2026-09-29
og_description: Πώς να ορίσετε το πλάτος ενός barcode GS1 DataBar Omni‑Directional
  και πώς να αλλάξετε το ύψος του σε C#. Μάθετε τις ακριβείς κλήσεις API και δείτε
  ένα πλήρες εκτελέσιμο παράδειγμα.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Πώς να ορίσετε το πλάτος ενός barcode GS1 DataBar – Οδηγός C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Πώς να ορίσετε το πλάτος και να ρυθμίσετε το ύψος για έναν κωδικό GS1 DataBar
  Omni‑Directional σε C#
url: /el/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε το πλάτος και να προσαρμόσετε το ύψος για ένα GS1 DataBar Omni‑Directional barcode σε C#

Η ρύθμιση του πλάτους ενός GS1 DataBar Omni‑Directional barcode είναι μια συχνή εργασία όταν χρειάζεστε ακριβείς διαστάσεις για τον εξοπλισμό σάρωσης. Σε αυτό το σεμινάριο θα μάθετε επίσης **πώς να αλλάξετε το ύψος** ώστε το barcode να ταιριάζει τέλεια στη διάταξή σας. Ο οδηγός σας καθοδηγεί μέσα από τη διαδικασία, από την εγκατάσταση του έργου μέχρι ένα πλήρως εκτελέσιμο παράδειγμα κώδικα.

Θα καλύψουμε:

* Το απαιτούμενο πακέτο NuGet και την έκδοση .NET.
* Γιατί η X‑διάσταση (πλάτος μονάδας) είναι σημαντική για την αναγνωσιμότητα του barcode.
* Τις ακριβείς κλήσεις API για **πώς να ορίσετε το πλάτος** και **πώς να αλλάξετε το ύψος**.
* Διαχείριση edge‑case όπως ελάχιστο πλάτος μονάδας και απόδοση υψηλής ανάλυσης.
* Ένα πλήρες, αντιγραφή‑και‑επικόλληση παράδειγμα που παράγει δύο αρχεία PNG με διαφορετικά ύψη γραμμών.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

| Απαίτηση | Λόγος |
|------------|--------|
| .NET 6.0 SDK ή νεότερο | Το παράδειγμα χρησιμοποιεί σύγχρονα χαρακτηριστικά C# και εκτελείται σε Windows, Linux ή macOS. |
| Visual Studio 2022 (ή οποιοδήποτε IDE C#) | Παρέχει IntelliSense για το Aspose.Barcode API. |
| **Aspose.Barcode for .NET** πακέτο NuGet | Περιέχει `BarcodeGenerator`, `EncodeTypes` και υποστήριξη μορφών εικόνας. Εγκαταστήστε το με `dotnet add package Aspose.Barcode`. |
| Δικαίωμα εγγραφής σε φάκελο όπου θα αποθηκευτούν τα αρχεία PNG | Ο δημιουργός γράφει τις εικόνες εξόδου στο δίσκο. |

## Πώς να ορίσετε το πλάτος του barcode

Το βήμα **πώς να ορίσετε το πλάτος** εκτελείται ρυθμίζοντας την ιδιότητα `XDimension` των παραμέτρων του barcode. Η `XDimension` αντιπροσωπεύει το πλάτος μονάδας (το μικρότερο μπαρ ή κενό) σε pixels, points ή millimetres. Η σωστή ρύθμιση εξασφαλίζει ότι το barcode πληροί τις προδιαγραφές του scanner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Γιατί η X‑διάσταση είναι σημαντική

* **Ανοχή scanner** – Οι περισσότεροι scanners απαιτούν ελάχιστο πλάτος μονάδας· πολύ μικρή τιμή μπορεί να προκαλέσει σφάλματα ανάγνωσης.
* **Ανάλυση εκτύπωσης** – Σε εκτύπωση 300 dpi, μια μονάδα 2 px αντιστοιχεί σε ~0.17 mm, που βρίσκεται εντός του προτεινόμενου εύρους για GS1 DataBar.
* **Μέγεθος εικόνας** – Μεγαλύτερες τιμές X‑διάστασης αυξάνουν το συνολικό πλάτος του barcode, κάτι που μπορεί να επηρεάσει περιορισμούς διάταξης.

### Συμβουλές για αξιόπιστες ρυθμίσεις πλάτους

* **Ποτέ μην ορίζετε XDimension κάτω από 1 px** – η βιβλιοθήκη θα περιορίσει την τιμή, αλλά το barcode μπορεί να είναι μη αναγνώσιμο.
* **Ταιριάξτε το στόχο DPI** – αν αποδίδετε σε μορφή υψηλής ανάλυσης (π.χ., TIFF στα 600 dpi), αυξήστε την XDimension αναλογικά.
* **Δοκιμάστε με πραγματικό scanner** – μετά την αλλαγή του πλάτους, επικυρώστε το barcode στη συσκευή που θα το διαβάσει.

## Πώς να αλλάξετε το ύψος του barcode

Μόλις οριστεί το πλάτος, μπορείτε να ελέγξετε το κάθετο μέγεθος με την ιδιότητα `BarHeight`. Ο παρακάτω κώδικας δείχνει **πώς να αλλάξετε το ύψος** από 30 px σε 60 px και να αποθηκεύσετε δύο ξεχωριστές εικόνες.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Κατανόηση του ύψους μπαρ

* **Οπτική ισορροπία** – Ψηλότερα μπαρ βελτιώνουν την αναγνωσιμότητα σε φόντο χαμηλής αντίθεσης αλλά αυξάνουν το κάθετο αποτύπωμα της εικόνας.
* **Κανονιστικά όρια** – Ορισμένα πρότυπα (π.χ., ετικέτες λιανικής) ορίζουν μέγιστο ύψος μπαρ· προσαρμόστε ανάλογα.
* **Αναλογία διαστάσεων** – Η αλλαγή του ύψους δεν επηρεάζει το πλάτος μονάδας· μπορείτε να ρυθμίσετε και τα δύο ανεξάρτητα.

### Διαχείριση edge‑case για ρυθμίσεις ύψους

| Κατάσταση | Προτεινόμενη προσέγγιση |
|-----------|----------------------|
| Ύψος < 10 px | Αυξήστε τουλάχιστον στα 10 px· πολύ κοντά μπαρ μπορεί να αγνοηθούν από τους σαρωτές. |
| Πολύ ψηλά μπαρ (≥ 100 px) | Επαληθεύστε ότι το μέσο εξόδου (χαρτί, ετικέτα) μπορεί να φιλοξενήσει τον επιπλέον χώρο. |
| Απαιτείται ανάλογη κλιμάκωση | Υπολογίστε `BarHeight = XDimension * desiredRatio` για να διατηρήσετε την οπτική συνέπεια. |

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που συνδυάζει τα βήματα **πώς να ορίσετε το πλάτος** και **πώς να αλλάξετε το ύψος**. Αντιγράψτε τον κώδικα σε ένα νέο έργο console, επαναφέρετε το πακέτο NuGet Aspose.Barcode και εκτελέστε το. Δύο αρχεία PNG θα εμφανιστούν στο φάκελο `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Αναμενόμενο αποτέλεσμα**

Η εκτέλεση του προγράμματος παράγει δύο αρχεία PNG:

* `DatabarBarHeight30Pixels.png` – ένα barcode 30 px ύψος, μονάδες 2 px πλάτος.
* `DatabarBarHeight60Pixels.png` – το ίδιο barcode με διπλάσιο κάθετο μέγεθος.

Ανοίξτε οποιαδήποτε εικόνα σε οποιονδήποτε προβολέα· θα δείτε ένα καθαρό σύμβολο GS1 DataBar Omni‑Directional έτοιμο για σάρωση.

## Συχνές ερωτήσεις

| Ερώτηση | Απάντηση |
|----------|--------|
| *Μπορώ να χρησιμοποιήσω χιλιοστά αντί για pixels;* | Ναι. Ορίστε `generator.Parameters.Barcode.XDimension.Millimeters` και `BarHeight.Millimeters`. Η βιβλιοθήκη μετατρέπει σε pixels συσκευής βάσει του DPI της εικόνας. |
| *Τι γίνεται αν χρειάζομαι διαφορετικό τύπο barcode;* | Αντικαταστήστε το `EncodeTypes.DatabarOmniDirectional` με οποιαδήποτε άλλη τιμή `EncodeTypes` (π.χ., `EncodeTypes.QR`). Οι ιδιότητες πλάτους και ύψους λειτουργούν με τον ίδιο τρόπο. |
| *Υπάρχει τρόπος να δημιουργήσετε SVG αντί για PNG;* | Χρησιμοποιήστε `BarCodeImageFormat.Svg` στην κλήση `Save`. Οι ρυθμίσεις πλάτους/ύψους παραμένουν εφαρμόσιμες. |
| *Πρέπει να καλέσω `generator.Dispose()`;* | Το `BarcodeGenerator` υλοποιεί το `IDisposable`. Σε μια εφαρμογή κονσόλας μπορείτε να το τυλίξετε σε μπλοκ `using`, αλλά για σύντομα παραδείγματα είναι προαιρετικό. |

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να ορίσετε το πλάτος** ενός GS1 DataBar Omni‑Directional barcode και **πώς να αλλάξετε το ύψος** χρησιμοποιώντας το Aspose.Barcode API σε C#. Το πλήρες παράδειγμα δείχνει τη δημιουργία ενός generator, τη ρύθμιση των `XDimension` και `BarHeight`, και την αποθήκευση αρχείων PNG με διαφορετικά κάθετα μεγέθη.  

Από εδώ μπορείτε:

* Να πειραματιστείτε με άλλα `EncodeTypes` (π.χ., QR, Code128).
* Να αποδώσετε σε μορφές υψηλής ανάλυσης όπως TIFF για εκτύπωση.
* Να ενσωματώσετε τον generator σε ένα web API που επιστρέφει barcodes on‑the‑fly.

Καλή προγραμματιστική δουλειά και εύχομαι τα barcodes σας να σαρώνουν πάντα καθαρά!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να αλλάξετε το ύψος του barcode σε C# – Πλήρης οδηγός](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Παράδειγμα δημιουργού barcode σε C# – ορισμός πλάτους και ύψους](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Πώς να χρησιμοποιήσετε έναν δημιουργό barcode C# για τη δημιουργία DataBar Omni‑directional barcode](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}