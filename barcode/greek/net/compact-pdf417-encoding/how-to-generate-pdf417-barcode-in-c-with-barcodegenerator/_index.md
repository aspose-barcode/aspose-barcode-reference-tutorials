---
category: general
date: 2026-11-20
description: Μάθετε πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# χρησιμοποιώντας
  το BarcodeGenerator. Αυτός ο οδηγός βήμα‑βήμα καλύπτει τη διάσταση X, τις ρυθμίσεις
  στήλης και την εξαγωγή PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: el
lastmod: 2026-11-20
og_description: Δημιουργήστε γρήγορα barcode PDF417 σε C#. Ακολουθήστε αυτόν τον οδηγό
  για να ορίσετε διαστάσεις, στήλες και να εξάγετε το barcode ως εικόνα PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Δημιουργία κώδικα PDF417 σε C# – πλήρης οδηγός βήμα προς βήμα
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με το BarcodeGenerator
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με το BarcodeGenerator

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που ορίζει το X‑Dimension, επιλέγει τον αριθμό των στηλών και αποθηκεύει το αποτέλεσμα ως εικόνα PNG.

Η δημιουργία γραμμωτού κώδικα PDF417 είναι συνηθισμένη όταν πρέπει να κωδικοποιήσετε πολλά δεδομένα—όπως άδεια οδήγησης, κάρτα επιβίβασης ή αρχείο αποθέματος—σε μια συμπαγή, μηχανικά αναγνώσιμη εικόνα. Σε αυτό το σεμινάριο χρησιμοποιούμε την κλάση **BarcodeGenerator** από τη βιβλιοθήκη Aspose.BarCode, αλλά οι έννοιες ισχύουν για οποιαδήποτε βιβλιοθήκη που υποστηρίζει PDF417.

Με το τέλος αυτού του άρθρου θα μπορείτε να:

* Αρχικοποιήσετε ένα `BarcodeGenerator` για κωδικοποίηση PDF417.  
* Ρυθμίσετε το μέγεθος του μονάδας με **set XDimension pixels**.  
* Ελέγξετε τη διάταξη χρησιμοποιώντας **configure PDF417 columns**.  
* **Αποθηκεύσετε τον γραμμωτό κώδικα ως PNG** για χρήση σε ιστοσελίδες, κινητές εφαρμογές ή έντυπο υλικό.  

> **Προαπαιτούμενα**  
> * .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+).  
> * Μια αναφορά στο πακέτο NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Βασική εξοικείωση με C# και Visual Studio (ή οποιοδήποτε IDE προτιμάτε).

---

## Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C#

Ο πυρήνας της λύσης είναι μια σύντομη διαδικασία τεσσάρων βημάτων. Κάθε βήμα είναι ενσωματωμένο σε μια αφιερωμένη μέθοδο ώστε να μπορείτε να επαναχρησιμοποιήσετε τη λογική σε μεγαλύτερα έργα.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Γιατί αυτά τα τέσσερα βήματα έχουν σημασία

1. **Initialize the generator** – Το `BarcodeGenerator` συνδέει την επιλεγμένη συμβολογία (`EncodeTypes.Pdf417`) με τα δεδομένα που θέλετε να κωδικοποιήσετε. Χωρίς αυτό το αντικείμενο δεν μπορείτε να έχετε πρόσβαση σε περαιτέρω ρυθμίσεις.  
2. **Set X‑Dimension** – Το PDF417 αποτελείται από μικροσκοπικές ορθογώνιες μονάδες. Η αλλαγή του `XDimension.Pixels` σας επιτρέπει να ελέγξετε την οπτική πυκνότητα του γραμμωτού κώδικα, κάτι που είναι κρίσιμο για την αναγνωσιμότητα σε οθόνες ή εκτυπωτές χαμηλής ανάλυσης.  
3. **Configure columns** – Το PDF417 μπορεί να οργανώσει τις λέξεις κώδικα του σε μεταβλητό αριθμό στηλών. Λιγότερες στήλες παράγουν έναν πιο ψηλό γραμμωτό κώδικα, ενώ περισσότερες στήλες τον κάνουν πιο πλατύ. Ρυθμίστε το ώστε να ταιριάζει στον χώρο όπου θα τοποθετηθεί η εικόνα.  
4. **Save as PNG** – Το PNG είναι μορφή χωρίς απώλειες, διατηρώντας τις αιχμηρές άκρες που απαιτούνται για ακριβή σάρωση. Μπορείτε επίσης να επιλέξετε JPEG ή BMP, αλλά το PNG είναι η πιο ασφαλής προεπιλογή.

---

## Διαμόρφωση διαστάσεων γραμμωτού κώδικα (X‑Dimension)

Το βήμα **set XDimension pixels** επηρεάζει άμεσα το πώς οι σαρωτές ερμηνεύουν τον γραμμωτό κώδικα. Αν η μονάδα είναι πολύ μικρή, οι κάμερες χαμηλής ποιότητας μπορεί να χάσουν μεμονωμένες γραμμές· αν είναι πολύ μεγάλη, ο γραμμωτός κώδικας μπορεί να γίνει άσκοπα μεγάλος.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Καλύτερη πρακτική:** Δοκιμάστε την παραγόμενη εικόνα στο προοριζόμενο μέγεθος εκτύπωσης. Για εκτύπωση υψηλής πυκνότητας (300 dpi ή περισσότερο), μια τιμή `1` ή `2` λειτουργεί καλά. Για προβολή στην οθόνη στα 96 dpi, `2`–`3` προσφέρει καθαρό οπτικό αποτέλεσμα.

---

## Ορισμός στηλών PDF417

Το βήμα **configure PDF417 columns** σας επιτρέπει να αποφασίσετε το σχήμα του γραμμωτού κώδικα.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Πότε να αλλάξετε τον αριθμό στηλών

| Στήλες | Προκύπτον σχήμα | Τυπική χρήση |
|---------|----------------|------------------|
| 1–3     | Ψηλό, στενό   | Ετικέτες με περιορισμένο πλάτος |
| 4–9     | Ισορροπημένο  | Γενική σάρωση |
| 10+     | Πλατύ, κοντό   | Μεγάλη σήμανση ή γραφικά ιστοσελίδας |

Αν το φορτίο δεδομένων σας υπερβαίνει την προεπιλεγμένη χωρητικότητα, η βιβλιοθήκη προσθέτει αυτόματα επιπλέον γραμμές, αλλά μπορείτε ακόμη να επηρεάσετε την αναλογία διαστάσεων τροποποιώντας τον αριθμό των στηλών.

---

## Εξαγωγή γραμμωτού κώδικα σε PNG

Η αποθήκευση του γραμμωτού κώδικα ως εικόνα PNG είναι απλή:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Γιατί PNG;**  
* Η συμπίεση χωρίς απώλειες διατηρεί τις αιχμηρές άκρες που χρειάζονται οι αναγνώστες γραμμωτών κωδίκων.  
* Το PNG υποστηρίζει διαφάνεια, κάτι που μπορεί να είναι χρήσιμο αν τοποθετήσετε τον γραμμωτό κώδικα πάνω σε χρωματικό φόντο αργότερα.

Αν χρειάζεστε διαφορετική μορφή, αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Svg`—το API διαχειρίζεται τη μετατροπή αυτόματα.

---

## Συνηθισμένα προβλήματα και αντιμετώπιση

| Πρόβλημα | Πιθανή αιτία | Διόρθωση |
|----------|--------------|----------|
| Ο γραμμωτός κώδικας εμφανίζεται θολός | Το X‑Dimension είναι πολύ μικρό για την ανάλυση εξόδου | Αυξήστε το `XDimension.Pixels` σε 3 ή 4. |
| Ο σαρωτής δεν μπορεί να διαβάσει τον κώδικα | Οι χαρακτήρες Unicode δεν υποστηρίζονται από την επιλεγμένη γραμματοσειρά | Βεβαιωθείτε ότι η γραμματοσειρά της βιβλιοθήκης υποστηρίζει τους χαρακτήρες, ή αντικαταστήστε τους με ισοδύναμα ASCII. |
| Το αρχείο εξόδου δεν δημιουργήθηκε | Μη έγκυρη διαδρομή ή έλλειψη δικαιωμάτων εγγραφής | Χρησιμοποιήστε απόλυτη διαδρομή και επαληθεύστε την πρόσβαση εγγραφής στο φάκελο. |
| Πάρα πολλές γραμμές, ο γραμμωτός κώδικας γίνεται ψηλός | Ο αριθμός στηλών είναι πολύ χαμηλός για το μήκος των δεδομένων | Αυξήστε το `Pdf417.Columns` σε μεγαλύτερο αριθμό (π.χ., 6). |

---

## Συνοπτική πλήρης λειτουργική παράδειγμα

Παρακάτω βρίσκεται το **πλήρες πρόγραμμα** που μπορείτε να αντιγράψετε‑επικολλήσετε σε ένα νέο έργο κονσόλας. Δεν απαιτείται επιπλέον κώδικας εκτός από τις δηλώσεις `using` και το πακέτο Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Αναμενόμενο αποτέλεσμα:** Ένα αρχείο με όνομα `Pdf417Basic.png` που περιέχει έναν καθαρό γραμμωτό κώδικα PDF417 που κωδικοποιεί τη συμβολοσειρά `Åspóse.Barcóde©`. Όταν ανοίξει, η εικόνα θα πρέπει να δείχνει μια σειρά από στοίβαξη ορθογώνιων γραμμών με πιο πυκνή αριστερή πλευρά (λόγω της διάταξης τριών στηλών).

---

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# χρησιμοποιώντας την κλάση `BarcodeGenerator`. Το σεμινάριο κάλυψε την αρχικοποίηση του γεννήτρια, **set XDimension pixels**, **configure PDF417 columns**, και **save barcode as PNG**—τα ουσιώδη βήματα για οποιαδήποτε παραγωγική ροή εργασίας γραμμωτών κωδίκων.

Από εδώ μπορείτε να:

* Δοκιμάσετε διαφορετικούς `EncodeTypes` (π.χ., QR, Code128).  
* Προσθέσετε επίπεδα διόρθωσης σφαλμάτων μέσω `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Αποδώσετε τον γραμμωτό κώδικα απευθείας σε `MemoryStream` για web API.  

Νιώστε ελεύθεροι να προσαρμόσετε τον κώδικα στο δικό σας έργο και να μοιραστείτε τα αποτελέσματά σας στα σχόλια ή στο Stack Overflow χρησιμοποιώντας την ετικέτα `#pdf417`. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετικότατα θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον λειτουργίες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία γραμμωτού κώδικα PDF417 ως PNG σε C# – οδηγός βήμα‑βήμα](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# – οδηγός βήμα‑βήμα](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με προσαρμοσμένες διαστάσεις](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}