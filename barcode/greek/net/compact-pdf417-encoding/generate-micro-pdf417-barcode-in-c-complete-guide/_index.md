---
category: general
date: 2026-07-18
description: Δημιουργία μικρο‑pdf417 barcode με το Aspose.BarCode για .NET – βήμα‑βήμα
  οδηγός που καλύπτει στήλες, γραμμές και έξοδο PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: el
lastmod: 2026-07-18
og_description: Δημιουργήστε άμεσα μικρο‑pdf417 barcode με το Aspose.BarCode για .NET.
  Μάθετε πώς να ελέγχετε στήλες, γραμμές και να αποθηκεύετε ως PNG σε λίγα λεπτά.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Δημιουργία μικρού barcode PDF417 – Πλήρες σεμινάριο C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Δημιουργία μικρού γραμμωτού κώδικα PDF417 σε C# – Πλήρης οδηγός
url: /el/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία μικρού κωδικού Micro PDF417 σε C# – Πλήρης Οδηγός

Έχετε αναρωτηθεί ποτέ πώς να **δημιουργήσετε μικρό κωδικό pdf417** απευθείας από την εφαρμογή σας C#; Δεν είστε οι μόνοι. Είτε ετικετοποιείτε αποθέματα, κωδικοποιείτε σύντομες διευθύνσεις URL, είτε δημιουργείτε μια προσαρμοσμένη λύση σάρωσης, η εξοικείωση με αυτόν τον μικρό αλλά ισχυρό 2‑Δ κώδικα μπορεί να σας εξοικονομήσει πολύ κόπο.

Σε αυτό το tutorial θα περάσουμε από ένα πραγματικό παράδειγμα χρησιμοποιώντας **Aspose.BarCode for .NET**, δείχνοντας πώς να ρυθμίσετε στήλες, σειρές και μέγεθος μονάδας, και στη συνέχεια να αποθηκεύσετε το αποτέλεσμα σε αρχείο PNG. Στο τέλος θα έχετε μια έτοιμη κονσόλα που παράγει τρεις διαφορετικές εικόνες κωδικών—χωρίς μυστικά.

## Τι Θα Χρειαστείτε

- .NET 6 ή νεότερο (ο κώδικας λειτουργεί επίσης σε .NET Framework 4.7+)
- Visual Studio 2022 (ή οποιοδήποτε IDE C# προτιμάτε)
- Το πακέτο NuGet **Aspose.BarCode** (`Aspose.BarCode`)
- Ένας φάκελος με δικαιώματα εγγραφής για τα PNG εξόδου

Αν έχετε ήδη όλα αυτά, υπέροχα—ας ξεκινήσουμε.

## Βήμα 1: Δημιουργία Έργου και Εγκατάσταση Aspose.BarCode

Πρώτα, δημιουργήστε ένα νέο έργο κονσόλας:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** Εκτελέστε `dotnet restore` μετά την προσθήκη του πακέτου για να βεβαιωθείτε ότι όλες οι εξαρτήσεις έχουν λυθεί.

Τώρα ανοίξτε το `Program.cs`. Θα ξεκινήσουμε εισάγοντας τους απαραίτητους χώρους ονομάτων:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Αυτές οι δύο δηλώσεις `using` μας δίνουν πρόσβαση στο `BarcodeGenerator`, `EncodeTypes` και στο enum μορφής εικόνας που θα χρειαστούμε αργότερα.

## Βήμα 2: Αρχικοποίηση του Γεννήτριας MicroPdf417

Η καρδιά της λειτουργίας είναι το αντικείμενο `BarcodeGenerator`. Του δίνουμε τον τύπο κωδικοποίησης **MicroPdf417** και το κείμενο που θέλουμε να κωδικοποιήσουμε—στην περίπτωσή μας τη λέξη “ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Γιατί `MicroPdf417`; Σε σύγκριση με το πλήρες PDF417, η μικρή έκδοση συμπιέζει περισσότερα δεδομένα σε μικρότερο χώρο, ιδανική για ετικέτες με περιορισμένο χώρο.

## Βήμα 3: Ρύθμιση του Μεγέθους Μονάδας (Διάσταση X)

Το μέγεθος μονάδας καθορίζει πόσα pixel καταλαμβάνει κάθε μικρό τετράγωνο του κωδικού. Μια τιμή **2 pixel** προσφέρει καθαρή, ευανάγνωστη εικόνα χωρίς να αυξάνει υπερβολικά το μέγεθος του αρχείου.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Σημείωση:** Αν χρειάζεστε μεγαλύτερο κωδικό για σάρωση από απόσταση, αυξήστε αυτήν την τιμή σε 3 ή 4.

## Βήμα 4: Δημιουργία Κωδικών με Διαφορετικές Ρυθμίσεις Στήλης/Σειράς

### 4.1 Δύο Στήλες, Αυτόματη Υπολογιζόμενη Σειρά

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Έξι Σειρές, Αυτόματη Υπολογιζόμενη Στήλη

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Τέσσερις Στήλες × Οκτώ Σειρές (Πλήρης Προσδιορισμός)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Κάθε κλήση `Save` γράφει ένα αρχείο PNG στον τρέχοντα φάκελο του έργου. Μπορείτε να αλλάξετε τη διαδρομή (`"YOUR_DIRECTORY/..."`) σε κάτι όπως `Path.Combine(Environment.CurrentDirectory, "output")` αν προτιμάτε έναν αφιερωμένο φάκελο.

## Βήμα 5: Πλήρες Παράδειγμα Λειτουργίας

Συνδυάζοντας όλα τα παραπάνω, ορίστε το πλήρες πρόγραμμα έτοιμο για αντιγραφή‑και‑επικόλληση:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Αναμενόμενο Αποτέλεσμα

Η εκτέλεση του προγράμματος δημιουργεί τρία αρχεία PNG:

| Όνομα αρχείου | Προσεγγ. διαστάσεις (px) | Οπτική ένδειξη |
|---------------|--------------------------|----------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Στενός, πιο ψηλός κωδικός |
| `MicroPdf417Rows6.png` | 120 × 180 | Πλατύς, πιο κοντός κωδικός |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Σχεδόν τετράγωνος, ισορροπημένη διάταξη |

Ανοίξτε οποιοδήποτε από αυτά σε προβολή εικόνας—θα δείτε έναν καθαρό **Micro PDF417** κωδικό έτοιμο για σάρωση.

## Συχνές Ερωτήσεις & Ακραίες Περιπτώσεις

- **Τι γίνεται αν ο φάκελος εξόδου δεν υπάρχει;**  
  Καλέστε `Directory.CreateDirectory(path)` πριν από το πρώτο `Save` για να αποφύγετε `DirectoryNotFoundException`.

- **Μπορώ να αλλάξω τη μορφή εικόνας;**  
  Φυσικά. Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Gif` ανάλογα με τις ανάγκες.

- **Υπάρχει όριο στο μήκος του κειμένου;**  
  Το MicroPdf417 μπορεί να κωδικοποιήσει έως 1 KB δεδομένων, αλλά τα πρακτικά όρια εξαρτώνται από τις επιλεγμένες σειρές/στήλες. Αν προκύψει σφάλμα, αυξήστε τις σειρές ή τις στήλες.

- **Πώς ενσωματώνω τον κωδικό σε PDF;**  
  Χρησιμοποιήστε το Aspose.Pdf για να εισάγετε το παραγόμενο PNG, ή αλλάξτε σε `BarCodeImageFormat.Pdf` για άμεση έξοδο PDF.

## Pro Tips για Δημιουργία Κωδικών σε C#

1. **Κρατήστε τον γεννήτρια στη μνήμη** όταν χρειάζεστε πολλούς κωδικούς με τις ίδιες ρυθμίσεις—απλώς αλλάζετε το κείμενο, εξοικονομώντας CPU.  
2. **Ρυθμίστε την διόρθωση σφαλμάτων** μέσω `generator.Parameters.Barcode.Pdf417.ErrorLevel` αν το περιβάλλον σάρωσης είναι θορυβώδες.  
3. **Δοκιμάστε με πραγματικούς σαρωτές** νωρίς. Ορισμένες φορητές συσκευές δυσκολεύονται με πολύ πυκνούς μικρούς κωδικούς· η προσαρμογή του `XDimension` μπορεί να κάνει μεγάλη διαφορά.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε μικρό κωδικό pdf417** χρησιμοποιώντας **Aspose.BarCode for .NET**, να χειριστείτε **στήλες MicroPdf417** και **σειρές MicroPdf417**, και να αποθηκεύσετε το αποτέλεσμα ως PNG—όλα από μια μόνο, κομψή εφαρμογή κονσόλας C#. Πειραματιστείτε με διαφορετικά μεγέθη μονάδας, επίπεδα σφάλματος ή ακόμη και χρωματική έξοδο για να ταιριάξετε στις ανάγκες του έργου σας.

Στη συνέχεια, μπορείτε να εξερευνήσετε **δημιουργία κωδικών C#** για άλλες συμβολές όπως QR, Code128 ή DataMatrix, ή να ενσωματώσετε τις εικόνες απευθείας σε PDF με Aspose.Pdf. Ο ουρανός είναι το όριο όταν έχετε τα βασικά.

Καλή προγραμματιστική και να είναι πάντα οι σάρωσές σας χωρίς σφάλματα!

## Τι Θα Μάθετε Στη Σύντομη Μελλοντική Σας

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας έργα.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}