---
category: general
date: 2026-11-14
description: Μάθετε πώς να δημιουργήσετε γρήγορα γραμμωτό κώδικα PDF417 σε C#. Αυτός
  ο οδηγός δείχνει επίσης πώς να δημιουργήσετε PDF417 και πώς να προσαρμόσετε τις
  ρυθμίσεις του PDF417 για ακριβή έλεγχο.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: el
lastmod: 2026-11-14
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με βήμα‑βήμα οδηγίες. Μάθετε
  πώς να δημιουργείτε PDF417 και πώς να προσαρμόζετε τις παραμέτρους του PDF417 για
  ακριβή αποτελέσματα.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Δημιουργία κωδικού PDF417 σε C# – πλήρης οδηγός με προσαρμοσμένη διάταξη
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με προσαρμοσμένη διάταξη σε C#
url: /el/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 με προσαρμοσμένη διάταξη σε C#

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα pdf417** για σύστημα έκδοσης εισιτηρίων, ετικέτα αποθέματος ή σάρωση από κινητή εφαρμογή, αυτό το tutorial δείχνει τη πλήρη διαδικασία. Θα δείτε πώς να δημιουργήσετε PDF417 γρήγορα και πώς να προσαρμόσετε τις ρυθμίσεις PDF417 όπως στήλες και γραμμές, ώστε ο κώδικας να ταιριάζει στους περιορισμούς του σχεδίου σας.

Η δημιουργία ενός γραμμωτού κώδικα δεν απαιτεί μια πολύπλοκη βιβλιοθήκη γραφικών — αρκεί το Aspose.BarCode for .NET (ή οποιοδήποτε συμβατό API). Στο τέλος αυτού του οδηγού θα έχετε ένα έτοιμο προς χρήση αρχείο PNG που μπορείτε να ενσωματώσετε σε PDFs, ιστοσελίδες ή να εκτυπώσετε απευθείας από την εφαρμογή σας.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
- Aspose.BarCode for .NET (πακέτο NuGet `Aspose.BarCode`)
- Βασική εξοικείωση με C# και Visual Studio (ή οποιοδήποτε IDE)

> **Συμβουλή επαγγελματία:** Αν χρησιμοποιείτε μια CI/CD pipeline, προσθέστε την αναφορά του πακέτου NuGet στο αρχείο του έργου σας ώστε οι κατασκευές να παραμένουν αναπαραγώγιμες.

## Βήμα 1: Εγκατάσταση της βιβλιοθήκης γραμμωτού κώδικα

Ανοίξτε το φάκελο του έργου σας σε ένα τερματικό και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Το πακέτο περιλαμβάνει την κλάση `BarcodeGenerator` που χρησιμοποιείται σε όλο το tutorial. Δεν απαιτούνται πρόσθετες εγγενείς εξαρτήσεις.

## Βήμα 2: Δημιουργία ενός βασικού γραμμωτού κώδικα PDF417

Ο πρώτος στόχος είναι να **δημιουργήσετε γραμμωτό κώδικα pdf417** με τις προεπιλεγμένες ρυθμίσεις. Το παρακάτω πρόγραμμα ρυθμίζει τον δημιουργό, κωδικοποιεί μια δείγματική συμβολοσειρά και αποθηκεύει το αποτέλεσμα ως εικόνα PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Γιατί λειτουργεί:**  
`EncodeTypes.Pdf417` λέει στη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική PDF417. Ο κατασκευαστής δημιουργεί αυτόματα ένα αντικείμενο `Barcode` με προεπιλεγμένες τιμές στήλης/γραμμής που εγγυώνται τη δυνατότητα σάρωσης για τις περισσότερες περιπτώσεις χρήσης.

Εκτελέστε το πρόγραμμα (`dotnet run`). Θα βρείτε το `Pdf417Default.png` στον φάκελο του έργου. Ανοίγοντας την εικόνα εμφανίζεται ένας τυπικός γραμμωτός κώδικας PDF417 έτοιμος για σάρωση.

![Δημιουργία παραδείγματος PDF417 barcode](https://example.com/images/pdf417-default.png){:alt="Δημιουργία παραδείγματος PDF417 barcode που δείχνει την προεπιλεγμένη διάταξη"}

## Βήμα 3: Πώς να δημιουργήσετε PDF417 με προσαρμοσμένες διαστάσεις

Μερικές φορές μια ετικέτα σταθερού μεγέθους ή ένα στοιχείο UI απαιτεί ένα συγκεκριμένο αποτύπωμα γραμμωτού κώδικα. Εκεί είναι που **πώς να δημιουργήσετε pdf417** με προσαρμοσμένες στήλες και γραμμές γίνεται απαραίτητο.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Γιατί μπορεί να το θέλετε:**  
- **Περιορισμένο πλάτος:** Η μείωση των στηλών και η αύξηση των γραμμών δημιουργεί έναν πιο πλατύ αλλά πιο σύντομο γραμμωτό κώδικα, ιδανικό για στενές ετικέτες.  
- **Περιορισμένο ύψος:** Η αύξηση των στηλών και η μείωση των γραμμών παράγει έναν πιο ψηλό, στενότερο γραμμωτό κώδικα, χρήσιμο όταν έχετε κατακόρυφο χώρο.

Τanto `Columns` όσο και `Rows` δέχονται μόνο τιμές εντός των τεκμηριωμένων ορίων (2‑30 για στήλες, 1‑90 για γραμμές). Η παροχή μιας τιμής εκτός εύρους προκαλεί `ArgumentOutOfRangeException`, επομένως πάντα να επικυρώνετε την είσοδο του χρήστη εάν εκθέτετε αυτές τις ρυθμίσεις σε UI.

## Βήμα 4: Πώς να προσαρμόσετε περαιτέρω το PDF417

Πέρα από στήλες και γραμμές, η συμβολική PDF417 προσφέρει πολλές προαιρετικές παραμέτρους:

| Ιδιότητα | Σκοπός | Τυπικές τιμές |
|----------|---------|----------------|
| `ErrorLevel` | Ελέγχει τη δυνατότητα διόρθωσης σφαλμάτων | 0‑8 (higher = more robust) |
| `MacroPdf417` | Ενεργοποιεί macro PDF417 για δεδομένα πολλαπλών τμημάτων | `true`/`false` |
| `CompactPdf417` | Παράγει πιο συμπαγή γραμμωτό κώδικα με κόστος μειωμένης διόρθωσης σφαλμάτων | `true`/`false` |
| `SecurityLevel` | Προσθέτει ψηφίο ελέγχου ασφαλείας | 0‑2 |

Ακολουθεί ένα γρήγορο παράδειγμα που επίσης ορίζει το επίπεδο σφάλματος στο μέγιστο (8) για ένα θορυβώδες περιβάλλον:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Γιατί είναι σημαντικό:**  
Η υψηλότερη διόρθωση σφαλμάτων επιτρέπει στους σαρωτές να ανακτούν δεδομένα ακόμη και αν μέρος του γραμμωτού κώδικα είναι κατεστραμμένο. Ωστόσο, αυξάνει επίσης το μέγεθος του γραμμωτού κώδικα, οπότε ισορροπήστε τη ρύθμιση με τους περιορισμούς του σχεδίου σας.

## Βήμα 5: Επαλήθευση λειτουργίας του γραμμωτού κώδικα

Μετά τη δημιουργία του PNG, δοκιμάστε το με οποιαδήποτε εφαρμογή σάρωσης γραμμωτού κώδικα (τα περισσότερα smartphones έχουν δωρεάν αναγνώστες PDF417). Αν ο σαρωτής επιστρέψει το αρχικό κείμενο (`Custom layout text`), ο γραμμωτός κώδικας είναι έγκυρος.

Αν αντιμετωπίσετε προβλήματα σάρωσης:

1. **Έλεγχος διαστάσεων:** Βεβαιωθείτε ότι οι στήλες/γραμμές παραμένουν εντός του επιτρεπτού εύρους.  
2. **Ρύθμιση επιπέδου σφάλματος:** Αυξήστε το `ErrorLevel` για κατεστραμμένα μέσα.  
3. **Ανασκόπηση ποιότητας εικόνας:** Αποθηκεύστε με υψηλότερο DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) εάν σκοπεύετε να εκτυπώσετε.

## Πλήρης κώδικας πηγής για έναν επαναχρησιμοποιήσιμο βοηθό

Παρακάτω υπάρχει μια συμπαγής, επαναχρησιμοποιήσιμη κλάση που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο .NET. Περιλαμβάνει **πώς να δημιουργήσετε pdf417** και **πώς να προσαρμόσετε pdf417** σε μια ενιαία μέθοδο.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Μπορείτε να καλέσετε αυτόν τον βοηθό ως εξής:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Η μέθοδος αφαιρεί τον επαναλαμβανόμενο boiler‑plate κώδικα, επιτρέποντάς σας να εστιάσετε στη λογική της επιχείρησης.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

- **Τιμές εκτός εύρους:** Πάντα να επικυρώνετε τις `columns` και `rows` πριν τις αναθέσετε.  
- **Λανθασμένη μορφή εικόνας:** Ορισμένοι παλιοί σαρωτές δέχονται μόνο BMP ή JPEG. Χρησιμοποιήστε `BarCodeImageFormat.Bmp` εάν χρειάζεται.  
- **Χαμηλό DPI για εκτύπωση:** Το προεπιλεγμένο DPI είναι 96. Για εκτυπώσεις υψηλής ποιότητας, ορίστε ρητά υψηλότερο DPI (π.χ., 300) όταν καλείτε το `Save`.  
- **Έλλειψη υποστήριξης γραμματοσειράς:** Το PDF417 κωδικοποιεί δυαδικά δεδομένα, οπότε γενικά δεν χρειάζεται να καθορίσετε γραμματοσειρά. Ωστόσο, εάν προσθέτετε κείμενο πάνω στην εικόνα, βεβαιωθείτε ότι η γραμματοσειρά είναι εγκατεστημένη στον προορισμό.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε pdf417 barcode** από την αρχή μέχρι το τέλος, πώς να **δημιουργήσετε pdf417** με προσαρμοσμένες ρυθμίσεις στήλης/γραμμής, και πώς να **προσαρμόσετε pdf417** για διόρθωση σφαλμάτων και συμπαγότητα. Ακολουθώντας το πρότυπο του επαναχρησιμοποιήσιμου βοηθού, μπορείτε να δημιουργείτε γραμμωτούς κώδικες κατόπιν ζήτησης, να τους προσαρμόζετε σε οποιονδήποτε περιορισμό σχεδίου, και να εγγυάστε αξιόπιστη σάρωση σε περιβάλλον παραγωγής.

**Επόμενα βήματα**

- Εξερευνήστε άλλες συμβολές όπως QR ή Code128 χρησιμοποιώντας την ίδια κλάση `BarcodeGenerator`.  
- Συνδυάστε την έξοδο PNG με μια βιβλιοθήκη δημιουργίας PDF (π.χ., iText7) για ενσωμάτωση γραμμωτών κωδίκων σε τιμολόγια.  
- Πειραματιστείτε με το `MacroPdf417` για μετάδοση δεδομένων πολλαπλών τμημάτων, μια λειτουργία χρήσιμη σε εφαρμογές logistics και μεταφορών.

Καλή προγραμματιστική, και εύχομαι οι γραμμωτοί κώδικές σας να σαρώνουν πάντα με την πρώτη προσπάθεια!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – οδηγός βήμα‑βήμα](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα και να προσαρμόσετε τον PDF417 γραμμωτό κώδικα σε C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 και να εξάγετε PNG σε C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}