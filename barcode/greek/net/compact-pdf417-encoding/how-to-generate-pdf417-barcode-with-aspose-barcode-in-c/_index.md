---
category: general
date: 2026-10-24
description: Μάθετε πώς να δημιουργείτε γραμμωτό κώδικα PDF417 χρησιμοποιώντας το
  Aspose.BarCode σε C# με συμπαγείς ρυθμίσεις και έλεγχο XDimension του κώδικα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: el
lastmod: 2026-10-24
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode. Ακολουθήστε
  αυτόν τον πλήρη οδηγό για να δημιουργήσετε συμπαγείς εικόνες PDF417, να ελέγξετε
  το XDimension και να ορίσετε στήλες.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Δημιουργία barcode PDF417 με το Aspose.BarCode – βήμα‑βήμα C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με το Aspose.BarCode σε C#
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε barcode PDF417 με Aspose.BarCode σε C#

Εάν χρειάζεστε **δημιουργία barcode PDF417** σε εφαρμογή .NET, αυτός ο οδηγός σας παρουσιάζει μια πλήρη, έτοιμη‑για‑εκτέλεση λύση. Θα δείτε πώς το Aspose.BarCode κάνει τη διαδικασία απλή, ενώ σας παρέχει λεπτομερή έλεγχο πάνω στο **compact PDF417**, **barcode XDimension** και **PDF417 columns**.

Η δημιουργία barcode είναι συχνή απαίτηση για συστήματα απογραφής, πλατφόρμες εισιτηρίων και ροές εργασίας εγγράφων. Στο τέλος αυτού του tutorial θα έχετε ένα αυτόνομο πρόγραμμα C# που παράγει μια καθαρή εικόνα PNG ενός barcode PDF417, έτοιμη να ενσωματωθεί σε οποιοδήποτε UI ή να εκτυπωθεί σε ετικέτα.

## Τι θα χρειαστείτε

- .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+)
- Visual Studio 2022 ή οποιονδήποτε επεξεργαστή C# προτιμάτε
- Έγκυρη άδεια Aspose.BarCode για .NET (η δωρεάν δοκιμή λειτουργεί για ανάπτυξη)
- Βασική εξοικείωση με τη σύνταξη C#

> **Pro tip:** Εάν αξιολογείτε το Aspose.BarCode, κατεβάστε τη δοκιμαστική έκδοση από τον επίσημο ιστότοπο και προσθέστε το πακέτο NuGet `Aspose.BarCode` στο έργο σας. Η δοκιμή προσθέτει ένα μικρό υδατογράφημα στην παραγόμενη εικόνα, το οποίο αφαιρείται μόλις εφαρμόσετε άδεια.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Ανοίξτε ένα τερματικό στο φάκελο της λύσης σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Η εντολή κατεβάζει την πιο πρόσφατη σταθερή έκδοση (από Οκτώβριο 2026, έκδοση 23.12). Η προσθήκη του πακέτου επαναφέρει το namespace `Aspose.BarCode.Generation` που θα χρησιμοποιήσετε για **δημιουργία εικόνων PDF417 barcode**.

## Βήμα 2: Δημιουργία βασικού έργου κονσόλας C#

Εάν δεν έχετε ήδη έργο, δημιουργήστε ένα:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Ανοίξτε το `Program.cs`. Το σκελετό περιέχει ήδη μια μέθοδο `Main` όπου θα τοποθετήσουμε τον κώδικα δημιουργίας barcode.

## Βήμα 3: Αρχικοποίηση του δημιουργού barcode

Πρώτα, εισάγετε το απαιτούμενο namespace:

```csharp
using Aspose.BarCode.Generation;
```

Στη συνέχεια, μέσα στο `Main`, δημιουργήστε ένα αντικείμενο `BarcodeGenerator` με τη συμβολική PDF417 και τα δεδομένα που θέλετε να κωδικοποιήσετε:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Η συμβολοσειρά περιλαμβάνει χαρακτήρες Unicode για να δείξει ότι το Aspose.BarCode διαχειρίζεται σωστά μη‑ASCII είσοδο. Εάν χρειάζεστε μόνο ASCII, αντικαταστήστε το κείμενο με οποιαδήποτε απλή συμβολοσειρά.

## Βήμα 4: Ρύθμιση του barcode XDimension (μέγεθος μονάδας)

Το **barcode XDimension** καθορίζει το πλάτος της μικρότερης γραμμής (της μονάδας). Ορίζοντάς το σε pixel έχετε ακριβή έλεγχο του τελικού μεγέθους εικόνας:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Μια τιμή `2` pixel παράγει μια συμπαγή εικόνα χωρίς να θυσιάζει την αξιοπιστία σάρωσης. Αυξήστε την τιμή για μεγαλύτερα barcodes ή μειώστε την για πολύ πυκνές διατάξεις.

## Βήμα 5: Διαμόρφωση επιλογών compact PDF417

Δύο ρυθμίσεις ειδικές για PDF417 επηρεάζουν σημαντικά το οπτικό αποτύπωμα:

| Ρύθμιση | Σημασία | Τυπική τιμή για συμπαγή έξοδο |
|---------|---------|-----------------------------------|
| `Columns` | Αριθμός στηλών δεδομένων | `3` |
| `Truncate` (compact mode) | Παραλείπει τη δεξιά ζώνη ησυχίας και μειώνει τον αριθμό των σειρών | `true` |

Εφαρμόστε τις ως εξής:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Η χρήση **PDF417 columns** με τιμή `3` μαζί με `Truncate = true` δημιουργεί ένα *compact PDF417* barcode που ταιριάζει όμορφα σε τυπική ετικέτα ενώ παραμένει αναγνώσιμο από τους περισσότερους σαρωτές.

## Βήμα 6: Αποθήκευση της εικόνας barcode

Τέλος, γράψτε το barcode στο δίσκο. Το παράδειγμα αποθηκεύει PNG, αλλά το Aspose.BarCode υποστηρίζει επίσης BMP, JPEG, GIF, TIFF και SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Η σταθερά `BarCodeImageFormat.Png` λέει στη βιβλιοθήκη να δημιουργήσει ένα lossless PNG, ιδανικό για περαιτέρω επεξεργασία ή εκτύπωση.

## Πλήρης, εκτελέσιμος κώδικας

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Η εκτέλεση του προγράμματος παράγει το `CompactPdf417.png` στο ριζικό φάκελο του έργου. Ανοίξτε το αρχείο με οποιονδήποτε προβολέα εικόνων· θα δείτε ένα πυκνά τοποθετημένο PDF417 barcode που κωδικοποιεί τη συμβολοσειρά *Åspóse.Barcóde©*.

![Screenshot of generated PDF417 barcode using Aspose.BarCode](placeholder-image.png "Generated PDF417 barcode")

*Image alt text: Screenshot of generated PDF417 barcode using Aspose.BarCode* – αυτό το alt text περιέχει τη βασική λέξη‑κλειδί για προσβασιμότητα και SEO.

## Επαλήθευση του αποτελέσματος

1. Ανοίξτε το αρχείο PNG. Το barcode πρέπει να αποτελείται από τρεις κάθετες στήλες δεδομένων με συμπαγή διάταξη (χωρίς επιπλέον ζώνες ησυχίας στη δεξιά πλευρά).
2. Σαρώστε την εικόνα με έναν σαρωτή barcode σε smartphone που υποστηρίζει PDF417. Το αποκωδικοποιημένο κείμενο πρέπει να ταιριάζει με την αρχική συμβολοσειρά.
3. Εάν ο σαρωτής αποτύχει, δοκιμάστε να αυξήσετε το `XDimension.Pixels` σε `3` ή `4`. Μεγαλύτερες μονάδες βελτιώνουν την αναγνωσιμότητα σε συσκευές χαμηλής ανάλυσης.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

### 1. Αλλαγή μορφής εικόνας

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Το SVG είναι βασισμένο σε διανυσματικά στοιχεία, διατηρεί το barcode καθαρό σε οποιοδήποτε επίπεδο ζουμ—χρήσιμο για ιστοσελίδες.

### 2. Κωδικοποίηση μεγάλου όγκου δεδομένων

Το PDF417 μπορεί να αποθηκεύσει έως ~1.1 KB κειμένου. Όταν το φορτίο υπερβαίνει τη χωρητικότητα τριών στηλών, η βιβλιοθήκη προσθέτει αυτόματα σειρές. Για να κρατήσετε το barcode συμπαγές, μπορείτε:

- Μειώστε το μήκος των δεδομένων (π.χ., χρησιμοποιήστε έναν αναγνωριστικό αντί για πλήρες μήνυμα)
- Αυξήστε τον αριθμό των **PDF417 columns** (π.χ., `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Χρήση άδειας για αφαίρεση του υδατογραφήματος δοκιμής

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Τοποθετήστε το αρχείο άδειας δίπλα στο εκτελέσιμο. Μετά την άδεια, η παραγόμενη εικόνα δεν περιέχει υδατογράφημα.

### 4. Διαχείριση εξαιρέσεων

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Τυπικές αποτυχίες περιλαμβάνουν ανεπαρκή δικαιώματα εγγραφής ή μη υποστηριζόμενη μορφή εικόνας.

## Γιατί είναι σημαντικές οι ρυθμίσεις

- **barcode XDimension** – Ελέγχει το οπτικό βάρος κάθε γραμμής. Πολύ μικρό καθιστά το barcode αδιάβαστο· πολύ μεγάλο σπαταλά χώρο.
- **PDF417 columns** – Λιγότερες στήλες παράγουν στενότερο barcode αλλά αυξάνουν τον αριθμό των σειρών.

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε PDF417 Barcode με Aspose – Πλήρης Οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Δημιουργία PDF417 barcode με compact ρυθμίσεις σε C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Πώς να αποθηκεύσετε barcode και να δημιουργήσετε PDF417 με Aspose σε C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}