---
category: general
date: 2026-07-18
description: Μάθετε πώς να δημιουργείτε εικόνες barcode με έναν .net γεννήτρια barcode
  και να αλλάζετε εύκολα το ύψος του barcode για σύμβολα GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: el
lastmod: 2026-07-18
og_description: Το .net barcode generator σας επιτρέπει να δημιουργείτε γρήγορα εικόνες
  barcode. Αυτός ο οδηγός δείχνει πώς να δημιουργήσετε barcode, να ρυθμίσετε το ύψος
  των γραμμών και να αποθηκεύσετε αρχεία PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Αλλάξτε το ύψος του barcode με τον .NET δημιουργό barcode
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET δημιουργός barcode – αλλαγή ύψους barcode
url: /el/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – αλλαγή ύψους barcode

Έχετε αναρωτηθεί ποτέ **πώς να δημιουργήσετε εικόνες barcode** χωρίς να χειρίζεστε μια δεκάδα εξωτερικών εργαλείων; Στον κόσμο του .NET υπάρχει ένας εκπληκτικά απλός τρόπος για να το κάνετε, και το κλειδί είναι το **.net barcode generator**. Με λίγες μόνο γραμμές C# μπορείτε να δημιουργήσετε ένα σύμβολο GS1‑Databar Omni‑Directional, να ρυθμίσετε το ύψος των γραμμών και να αποθηκεύσετε το αποτέλεσμα σε αρχείο PNG.

Αν δημιουργείτε σύστημα αποθεμάτων, εκτυπωτή ετικετών αποστολής ή οποιαδήποτε εφαρμογή που χρειάζεται έναν κώδικα που μπορεί να σαρωθεί, αυτό το tutorial θα σας μεταφέρει από το μηδέν σε ένα λειτουργικό barcode σε λίγα λεπτά. Θα περάσουμε από τον πλήρη κώδικα, θα εξηγήσουμε γιατί κάθε ρύθμιση είναι σημαντική και θα σας δείξουμε πώς να **αλλάξετε το ύψος του barcode** χωρίς να παραβιάσετε τις προδιαγραφές.

## Τι θα χρειαστείτε

- .NET 6.0 ή νεότερο (το API λειτουργεί το ίδιο και σε .NET Framework 4.7+)
- Αναφορά στη βιβλιοθήκη barcode (π.χ., Aspose.BarCode for .NET – οι ίδιες κλάσεις χρησιμοποιούνται από πολλά εμπορικά κιτ)
- Περιβάλλον ανάπτυξης (Visual Studio, Rider ή VS Code με την επέκταση C#)
- Φάκελος όπου έχετε δικαίωμα εγγραφής – το tutorial θα αποθηκεύει αρχεία PNG εκεί

Αυτό είναι όλο. Δεν χρειάζονται επιπλέον πακέτα NuGet εκτός από τη βιβλιοθήκη barcode.

## Χρήση του .net barcode generator για αλλαγή ύψους barcode

Παρακάτω υπάρχει ένα **πλήρες, εκτελέσιμο πρόγραμμα console**. Επικολλήστε το σε ένα νέο έργο C#, προσαρμόστε το φάκελο εξόδου και πατήστε F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Γιατί κάθε γραμμή είναι σημαντική

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Δημιουργεί ένα στιγμιότυπο του **.net barcode generator** με την επιθυμητή συμβολική αναπαράσταση και τα δεδομένα. Η απαρίθμηση `EncodeTypes.DatabarOmniDirectional` ενημερώνει τη βιβλιοθήκη να χρησιμοποιήσει τη μορφή GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | Η X‑διάσταση είναι το πλάτος της πιο λεπτής γραμμής. Ορίζοντάς την σε *2 pixels* παρέχει καθαρή εικόνα στα περισσότερα μοντέρνα οθόνες ενώ διατηρεί το μέγεθος του αρχείου μικρό. |
| `BarHeight.Pixels = 30;` | Αυτό είναι το βήμα **αλλαγής ύψους barcode** που καθορίζει το ύψος κάθε γραμμής. Ύψος 30 pixel είναι μια καλή προεπιλογή για μικρές ετικέτες. |
| `generator.Save(...);` | Αποθηκεύει το barcode σε αρχείο PNG. Το PNG είναι loss‑less, πράγμα που σημαίνει ότι οι σαρωτές βλέπουν το ακριβές μοτίβο που δημιουργήθηκε. |
| `BarHeight.Pixels = 60;` | Εδώ **αλλάζουμε το ύψος του barcode** ξανά—αυτή τη φορά σε 60 pixels. Η βιβλιοθήκη επανασχεδιάζει αυτόματα το σύμβολο με τη νέα διάσταση όταν καλέσετε το `Save` για δεύτερη φορά. |
| `Console.WriteLine(...);` | Σας παρέχει γρήγορη ανατροφοδότηση ότι η διαδικασία ολοκληρώθηκε χωρίς εξαίρεση. |

> **Συμβουλή επαγγελματία:** Αν χρειάζεστε έξοδο υψηλότερης ανάλυσης για εκτύπωση, αλλάξτε το `BarCodeImageFormat.Png` σε `BarCodeImageFormat.Tiff` και αυξήστε την ιδιότητα `Resolution` (π.χ., `generator.Parameters.ImageResolution = 300;`). Το ύψος των γραμμών θα παραμείνει σεβαστό, απλώς θα αποδοθεί σε πιο λεπτή DPI.

## Πώς να δημιουργήσετε εικόνες barcode με διαφορετικές ρυθμίσεις

Το παραπάνω απόσπασμα καλύπτει τα βασικά, αλλά σε πραγματικές περιπτώσεις συχνά απαιτούνται πρόσθετες ρυθμίσεις:

### Προσαρμογή της X‑διάστασης για μεγαλύτερες εκτυπώσεις
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Η αύξηση της X‑διάστασης κάνει ολόκληρο το barcode μεγαλύτερο χωρίς να αλλάζει τα κωδικοποιημένα δεδομένα. Αυτό είναι χρήσιμο όταν εκτυπώνετε σε μεγάλες ετικέτες.

### Αλλαγή μορφής εξόδου
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
Το SVG κλιμακώνεται άπειρα, κάτι που είναι τέλειο για σαρωτές στο web που χρειάζονται καθαρά διανυσματικά γραφικά.

### Προσθήκη κειμένου αναγνώσιμου από άνθρωπο
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Η ενεργοποίηση του `CodeTextVisible` προσθέτει τα ακατέργαστα δεδομένα κάτω από το barcode, χρήσιμο για επαλήθευση κατά τη δοκιμή.

## Συνηθισμένα λάθη όταν **αλλάζετε το ύψος του barcode**

1. **Ύψος πολύ μικρό** – Κάποιοι σαρωτές απαιτούν ελάχιστο ύψος γραμμής (συχνά 10 mm σε φυσικές μονάδες). Αν ορίσετε το `BarHeight.Pixels` πολύ χαμηλά, η παραγόμενη εικόνα μπορεί να είναι αδιάβαστη από πραγματικό σαρωτή. Πάντα δοκιμάζετε με το στοχευόμενο υλικό.
2. **Ασυμφωνία X‑διάστασης και ύψους** – Ένα τεράστιο ύψος γραμμής σε συνδυασμό με πολύ μικρή X‑διάσταση μπορεί να φαίνεται τεντωμένο και να προκαλέσει σφάλματα αποκωδικοποίησης. Στοχεύστε σε ισορροπημένη αναλογία (περίπου 3:1 έως 5:1) εκτός αν οι προδιαγραφές ορίζουν διαφορετικά.
3. **Ξεχάνοντας να επαναφέρετε τις παραμέτρους** – Ο generator διατηρεί την κατάσταση μεταξύ των αποθηκεύσεων. Αν αλλάξετε το `BarHeight` για μία εικόνα και στη συνέχεια χρησιμοποιήσετε την ίδια παρουσία για άλλο barcode, το προηγούμενο ύψος θα παραμείνει. Επαναφέρετε την ιδιότητα ή δημιουργήστε νέο `BarcodeGenerator` για κάθε διαφορετικό barcode.

## Πλήρες παράδειγμα από την αρχή μέχρι το τέλος (συμπεριλαμβανομένης της εγκατάστασης NuGet)

Αν ξεκινάτε από το μηδέν, ακολουθήστε αυτά τα βήματα για να εκτελέσετε το έργο:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Αντικαταστήστε το αυτόματα δημιουργημένο `Program.cs` με το μπλοκ κώδικα που εμφανίστηκε παραπάνω, **θυμηθείτε να αντικαταστήσετε το `YOUR_DIRECTORY`** με κάτι όπως `Path.Combine(Environment.CurrentDirectory, "output")`. Στη συνέχεια:

```bash
dotnet run
```

Θα πρέπει να δείτε δύο αρχεία PNG στον φάκελο `output`:

- `DatabarBarHeight30Pixels.png` – ένα συμπαγές barcode ύψους 30 pixel.
- `DatabarBarHeight60Pixels.png` – μια πιο ψηλή έκδοση 60 pixel.

Και οι δύο εικόνες θα φαίνονται παρόμοιες, αλλά η δεύτερη θα έχει αισθητά μεγαλύτερα bars, κάνοντάς το πιο εύκολο για σαρωτές χαμηλής ανάλυσης να το διαβάσουν.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output που δείχνει διαφορετικά ύψη γραμμών"}

## Σύνοψη & επόμενα βήματα

Καλύψαμε πώς να **δημιουργήσετε εικόνες barcode** χρησιμοποιώντας ένα **.net barcode generator**, να ρυθμίσουμε τη **αλλαγή ύψους barcode** και να αποθηκεύσουμε τα αποτελέσματα σε μορφή PNG. Τα κύρια σημεία είναι:

- Δημιουργήστε το στιγμιότυπο του generator με το σωστό `EncodeTypes`.
- Ελέγξτε το οπτικό μέγεθος μέσω `XDimension` και `BarHeight`.
- Καλέστε το `Save` μετά από κάθε αλλαγή για να αποθηκεύσετε μια νέα εικόνα.
- Ρυθμίστε την ανάλυση, τη μορφή,

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε barcode Aztec με προσαρμοσμένη αναλογία διαστάσεων χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Πώς να δημιουργήσετε dotcode με εκτεταμένο κείμενο κώδικα χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Πώς να δημιουργήσετε DataMatrix Barcodes (ECC 200) με Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}