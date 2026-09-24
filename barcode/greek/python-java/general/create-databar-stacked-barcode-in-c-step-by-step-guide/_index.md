---
category: general
date: 2026-08-06
description: Δημιουργήστε γρήγορα στοίβαγμα DataBar barcode σε C#. Μάθετε πώς να ορίζετε
  τη διάσταση X, να ρυθμίζετε την αναλογία διαστάσεων και να εξάγετε αρχεία PNG χρησιμοποιώντας
  τη γεννήτρια DataBar Stacked Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: el
lastmod: 2026-08-06
og_description: Δημιουργήστε στοιβαγμένο barcode τύπου databar σε C# με το Aspose.BarCode.
  Αυτό το σεμινάριο δείχνει πώς να ρυθμίσετε τη διάσταση X, να αλλάξετε την αναλογία
  διαστάσεων και να αποθηκεύσετε εικόνες PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Δημιουργία στοιβαγμένου barcode databar σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Δημιουργία στοίβακτου barcode Databar σε C# – βήμα‑βήμα οδηγός
url: /el/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία databar stacked barcode σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **create databar stacked barcode** εικόνες σε C#, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Θα μάθετε να ορίζετε τη διάσταση X, να αλλάζετε την αναλογία διαστάσεων του barcode και να αποθηκεύετε το αποτέλεσμα ως αρχεία PNG — όλα σε λίγα σύντομα βήματα.

Η δημιουργία DataBar Stacked barcode είναι συνηθισμένη όταν πρέπει να κωδικοποιήσετε δεδομένα GS1‑128 για σάρωση λιανικής ή παρακολούθηση logistics. Στις επόμενες ενότητες καλύπτουμε τα πάντα, από τη ρύθμιση του έργου μέχρι την επαλήθευση του αποτελέσματος, ώστε να μπορείτε να ενσωματώσετε τη λύση σε οποιαδήποτε εφαρμογή .NET χωρίς να χάσετε λεπτομέρεια.

## Προαπαιτούμενα

* **.NET 6.0** (ή νεότερο) εγκατεστημένο – ο κώδικας στοχεύει στο σύγχρονο SDK.
* Μια **licensed** αντίγραφο του **Aspose.BarCode for .NET**. Η δωρεάν αξιολόγηση λειτουργεί για δοκιμές αλλά προσθέτει υδατογράφημα.
* Ένα IDE όπως το **Visual Studio 2022** ή το **VS Code** με την επέκταση C#.
* Βασική εξοικείωση με τη σύνταξη **C#** και την έννοια των GS1 Application Identifiers.

> **Pro tip:** Αν χρησιμοποιείτε το NuGet package manager, η εντολή `dotnet add package Aspose.BarCode` επιλύει αυτόματα όλες τις εξαρτήσεις.

## Βήμα 1: Δημιουργία νέου έργου console

Ανοίξτε ένα τερματικό ή το Package Manager Console και εκτελέστε:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Η εντολή `dotnet new console` δημιουργεί ένα ελάχιστο αρχείο **Program.cs**. Η προσθήκη του πακέτου **Aspose.BarCode** καθιστά διαθέσιμη την κλάση `BarcodeGenerator`.

## Βήμα 2: Αρχικοποίηση του γεννήτριας DataBar Stacked Omnidirectional

Ανοίξτε το **Program.cs** και αντικαταστήστε το προεπιλεγμένο περιεχόμενο με τον παρακάτω κώδικα. Η πρώτη γραμμή δημιουργεί ένα **BarcodeGenerator** ρυθμισμένο για τη συμβολολογία **DataBar Stacked Omnidirectional** και παρέχει ένα φορτίο GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Γιατί είναι σημαντικό:** Η τιμή enum `EncodeTypes.DatabarStackedOmniDirectional` ενημερώνει τη βιβλιοθήκη να παράγει ένα **databar stacked barcode**, που είναι η στοίβαξη παραλλαγή της omnidirectional οικογένειας DataBar. Αυτή η συμβολολογία μπορεί να περιέχει έως 14 αριθμητικούς χαρακτήρες, καθιστώντας την ιδανική για κωδικούς GTIN‑14.

## Βήμα 3: Ορισμός της διάστασης X (πλάτος μονάδας)

Η διάσταση X ελέγχει το πλάτος της μικρότερης γραμμής (του μονάδας). Μια τιμή που είναι πολύ μικρή μπορεί να αποτυπώνεται κακά σε εκτυπωτές χαμηλής ανάλυσης, ενώ μια τιμή που είναι πολύ μεγάλη μπορεί να υπερβαίνει το χώρο της ετικέτας.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** Η ιδιότητα `Pixels` είναι βολική για δοκιμές σε οθόνη. Για σενάρια που εστιάζουν στην εκτύπωση, χρησιμοποιήστε το `generator.Parameters.Barcode.XDimension.Millimeters`.

## Βήμα 4: Προσαρμογή της αναλογίας διαστάσεων και αποθήκευση της πρώτης εικόνας

Η **aspect ratio** επηρεάζει τη σχέση ύψος‑πλάτος του stacked barcode. Ο τύπος DataBar Stacked Omnidirectional υποστηρίζει αναλογίες από 10 έως 30. Θα δημιουργήσουμε δύο εικόνες για να δείξουμε την οπτική επίδραση.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Η κλήση στο `generator.Save` γράφει ένα αρχείο **PNG** στον τρέχοντα φάκελο εργασίας. Το enum `BarCodeImageFormat.Png` εξασφαλίζει συμπίεση χωρίς απώλειες, ιδανική για περαιτέρω επεξεργασία ή ενσωμάτωση σε PDF.

## Βήμα 5: Αλλαγή της αναλογίας διαστάσεων σε 30 και αποθήκευση της δεύτερης εικόνας

Τώρα αυξάνουμε το ύψος των στοίβακων γραμμών αλλάζοντας την αναλογία διαστάσεων σε **30**. Αυτό κάνει το barcode ψηλότερο χωρίς να αλλάζει τη διάσταση X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Η εκτέλεση του προγράμματος τώρα παράγει δύο αρχεία PNG:

* **DatabarAspectRatio15.png** – ένα συμπαγές barcode κατάλληλο για μικρές ετικέτες.
* **DatabarAspectRatio30.png** – ένα ψηλότερο barcode που βελτιώνει την αξιοπιστία σάρωσης σε επιφάνειες χαμηλής αντίθεσης.

Μπορείτε να ανοίξετε τις εικόνες σε οποιονδήποτε προβολέα για να επαληθεύσετε ότι οι γραμμές είναι σωστά στοίβαγμένες και ότι τα κωδικοποιημένα δεδομένα ταιριάζουν με το αρχικό GS1 string.

## Βήμα 6: Επαλήθευση της κωδικοποιημένης τιμής (προαιρετικό)

Αν χρειάζεστε επιβεβαίωση ότι το barcode πραγματικά αντιπροσωπεύει το εισαγόμενο string, μπορείτε να το αποκωδικοποιήσετε με την ίδια βιβλιοθήκη:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Ο αποκωδικοποιητής θα πρέπει να εμφανίσει `(01)12345678901231`, αποδεικνύοντας ότι η διαδικασία **create databar stacked barcode** διατήρησε τα δεδομένα.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Το barcode εμφανίζεται θολό | Η διάσταση X ορίστηκε πολύ χαμηλή για την ανάλυση εξόδου | Αυξήστε το `XDimension.Pixels` ή χρησιμοποιήστε `Millimeters` για εκτύπωση |
| Ο scanner αναφέρει “symbol not found” | Η αναλογία διαστάσεων εκτός του υποστηριζόμενου εύρους 10‑30 | Κρατήστε την αναλογία μεταξύ 10 και 30· 15 και 30 είναι ασφαλείς προεπιλογές |
| Το PNG περιέχει υδατογράφημα | Χρήση της δωρεάν άδειας αξιολόγησης του Aspose.BarCode | Αγοράστε πλήρη άδεια ή χρησιμοποιήστε τη δοκιμαστική έκδοση μόνο για δοκιμές |
| Η αποκωδικοποίηση αποτυγχάνει στη δεύτερη εικόνα | Ο αποκωδικοποιητής ρυθμίστηκε για λανθασμένη συμβολολογία | Χρησιμοποιήστε το `DecodeType.DatabarStackedOmniDirectional` όταν διαβάζετε stacked barcodes |

## Επόμενα βήματα

Τώρα που μπορείτε να **create databar stacked barcode** εικόνες, ίσως θέλετε να:

* **Ενσωμάτωση των PNG σε PDF τιμολόγια** χρησιμοποιώντας μια βιβλιοθήκη PDF όπως το **Aspose.PDF**.
* **Δημιουργία barcode σε πραγματικό χρόνο σε web API** – επιστρέψτε τα bytes PNG απευθείας από έναν ελεγκτή ASP.NET Core.
* **Πειραματισμός με άλλες παραλλαγές DataBar** (π.χ., `DatabarExpanded`, `DatabarLimited`) αλλάζοντας το enum `EncodeTypes`.
* **Ρύθμιση χρωμάτων** ορίζοντας `generator.Parameters.Barcode.ForeColor` και `BackColor` για σχεδιασμούς ειδικούς για το brand.

Κάθε ένα από αυτά τα θέματα βασίζεται στις ίδιες βασικές έννοιες που καλύφθηκαν εδώ: η αρχικοποίηση του `BarcodeGenerator`, η ρύθμιση των οπτικών παραμέτρων και η αποθήκευση του αποτελέσματος με `BarCodeImageFormat`.

---

### Συμπέρασμα

Αυτό το tutorial έδειξε πώς να **create databar stacked barcode** εικόνες σε C# χρησιμοποιώντας το Aspose.BarCode. Μάθατε να ορίζετε τη **διάσταση X**, να τροποποιείτε την **αναλογία διαστάσεων του barcode** και να εξάγετε το αποτέλεσμα ως αρχεία **PNG** με το `BarcodeGenerator`. Με το προαιρετικό βήμα αποκωδικοποίησης, μπορείτε επίσης να επαληθεύσετε ότι τα κωδικοποιημένα δεδομένα GS1 είναι ακριβή. Εφαρμόστε αυτά τα μοτίβα στη δική σας απογραφή, αποστολή ή εφαρμογές σημείου πώλησης, και εξερευνήστε τις πολλές επιλογές προσαρμογής που προσφέρει η βιβλιοθήκη. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Ρύθμιση ύψους One-Dimensional Databar Barcode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Δημιουργία εικόνας barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}