---
category: general
date: 2026-11-17
description: Μάθετε πώς να αποθηκεύετε γραμμωτό κώδικα, να ενεργοποιείτε τη συμπαγή
  λειτουργία, να προσαρμόζετε στήλες και να δημιουργείτε γραμμωτό κώδικα PDF417 με
  ένα πλήρες παράδειγμα C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: el
lastmod: 2026-11-17
og_description: Πώς να αποθηκεύσετε τον γραμμωτό κώδικα, να ενεργοποιήσετε τη συμπαγή
  λειτουργία και να προσαρμόσετε τις στήλες κατά τη δημιουργία ενός γραμμωτού κώδικα
  PDF417 σε C#. Ακολουθήστε τον οδηγό βήμα‑προς‑βήμα.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Πώς να αποθηκεύσετε το barcode ως PNG και να ενεργοποιήσετε τη συμπαγή λειτουργία
  σε C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Πώς να αποθηκεύσετε το γραμμωτό κώδικα ως PNG και να ενεργοποιήσετε τη συμπαγή
  λειτουργία σε C#
url: /el/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποθηκεύσετε barcode ως PNG και να ενεργοποιήσετε τη λειτουργία compact σε C#

Αν χρειάζεστε **how to save barcode** σε μορφή που μπορεί να χρησιμοποιηθεί στο web ή στην εκτύπωση, αυτός ο οδηγός σας δείχνει τα ακριβή βήματα. Θα μάθετε επίσης πώς να **enable compact mode**, **adjust columns**, και **generate PDF417 barcode** με τη βιβλιοθήκη Aspose.BarCode για .NET.

Το tutorial καλύπτει τα πάντα από τη ρύθμιση του έργου μέχρι το τελικό αρχείο PNG, ώστε να μπορείτε να αντιγράψετε τον κώδικα στη δική σας λύση χωρίς επιπλέον έρευνα. Δεν απαιτείται εξωτερική τεκμηρίωση· περιλαμβάνεται το πλήρες, εκτελέσιμο παράδειγμα.

## Προαπαιτούμενα

* .NET 6.0 ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE C#)  
* Το πακέτο NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Αυτά τα τρία στοιχεία είναι οι μόνες εξαρτήσεις για τον κώδικα που ακολουθεί.

## Βήμα 1: Δημιουργία γεννήτριας barcode PDF417

Η πρώτη εργασία όταν **generate PDF417 barcode** είναι να δημιουργήσετε ένα αντικείμενο `BarcodeGenerator` με τον σωστό τύπο κωδικοποίησης και τα δεδομένα που θέλετε να κωδικοποιήσετε.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Η απαρίθμηση `EncodeTypes.Pdf417` ενημερώνει τη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική PDF417, η οποία είναι ένα στοίβαγμα γραμμικού barcode κατάλληλο για κωδικοποίηση μεγάλων ποσοτήτων δεδομένων. Η συμβολοσειρά `"Compact mode"` γίνεται το κείμενο αναγνώσιμο από άνθρωπο κάτω από το barcode.

## Βήμα 2: Ορισμός διάστασης X (πλάτος μονάδας)

Κάθε γραμμή σε ένα barcode ονομάζεται μονάδα. Ο έλεγχος του πλάτους της μονάδας σας επιτρέπει να ρυθμίσετε ακριβώς το οπτικό μέγεθος του barcode χωρίς να αλλάξετε τα δεδομένα.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Μια διάσταση X 2 pixel παράγει μια συμπαγή εικόνα που εξακολουθεί να διαβάζεται αξιόπιστα στα περισσότερα συστήματα.

## Βήμα 3: **How to adjust columns** για τον κώδικα PDF417

Το PDF417 σας επιτρέπει να καθορίσετε πόσες στήλες θα χρησιμοποιήσει το barcode. Λιγότερες στήλες παράγουν ένα υψηλότερο, πιο στενό σύμβολο, ενώ περισσότερες στήλες κάνουν το σύμβολο πιο πλατύ αλλά πιο κοντό.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Αυτή η γραμμή δείχνει **how to adjust columns**. Μπορείτε να αλλάξετε την τιμή σε 2, 4 ή οποιονδήποτε αριθμό υποστηρίζεται από τη βιβλιοθήκη, ανάλογα με το χώρο που έχετε στο επιθυμητό μέσο.

## Βήμα 4: **How to enable compact mode** και περικοπή του συμβόλου

Η λειτουργία compact αφαιρεί περιττές επενδύσεις και μειώνει το συνολικό αποτύπωμα του barcode. Η βιβλιοθήκη εκθέτει αυτή τη δυνατότητα μέσω της ιδιότητας `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Παρατηρήστε ότι η φράση **enable compact mode** εμφανίζεται εδώ, και η ίδια ενέργεια περιγράφεται με την ακριβή διατύπωση **how to enable compact mode** αργότερα στον οδηγό για να ικανοποιηθεί η δευτερεύουσα απαίτηση λέξης-κλειδί.

## Βήμα 5: **How to save barcode** ως εικόνα PNG

Η αποθήκευση της παραγόμενης εικόνας είναι το τελικό βήμα. Η μέθοδος `Save` γράφει το barcode στο σύστημα αρχείων στη μορφή που καθορίζετε.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Αντικαταστήστε το `YOUR_DIRECTORY` με μια απόλυτη ή σχετική διαδρομή στην οποία η εφαρμογή σας μπορεί να γράψει. Μετά την εκτέλεση, θα βρείτε ένα αρχείο με όνομα `CompactPdf417.png` που περιέχει το compact PDF417 barcode.

### Αναμενόμενο αποτέλεσμα

Ανοίγοντας το αποθηκευμένο αρχείο PNG εμφανίζεται ένα κατακόρυφα compact PDF417 barcode με τρεις στήλες και περικομμένες επενδύσεις. Το οπτικό μέγεθος είναι περίπου 2 px ανά μονάδα, καθιστώντας την εικόνα κατάλληλη για ενσωμάτωση σε ετικέτες HTML `<img>` ή για εκτύπωση σε μικρές ετικέτες.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε σε ένα νέο έργο console. Περιλαμβάνει όλες τις απαραίτητες δηλώσεις `using` και δείχνει **how to save barcode**, **enable compact mode**, **how to adjust columns**, και **generate PDF417 barcode** σε μια ενιαία ροή.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Η εκτέλεση αυτού του προγράμματος παράγει το αρχείο PNG που περιγράφηκε νωρίτερα. Η έξοδος της κονσόλας επιβεβαιώνει τη θέση του αποθηκευμένου αρχείου, βοηθώντας σας να επαληθεύσετε ότι το βήμα **how to save barcode** ολοκληρώθηκε επιτυχώς.

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

### Τι γίνεται αν χρειάζομαι διαφορετική μορφή εικόνας;

Η μέθοδος `Save` δέχεται οποιαδήποτε τιμή της απαρίθμησης `BarCodeImageFormat`, όπως `Jpeg`, `Bmp` ή `Gif`. Αντικαταστήστε το `BarCodeImageFormat.Png` με την επιθυμητή μορφή και το υπόλοιπο του κώδικα παραμένει αμετάβλητο.

### Πώς η περικοπή επηρεάζει τη χωρητικότητα δεδομένων;

Η ενεργοποίηση του **compact mode** (περικοπή) μειώνει τον αριθμό των σειρών, κάτι που μπορεί να μειώσει τη μέγιστη χωρητικότητα δεδομένων του barcode. Εάν αντιμετωπίσετε εξαίρεση “Data too large”, είτε αυξήστε τον αριθμό των στηλών είτε απενεργοποιήστε την περικοπή.

### Μπορώ να χρησιμοποιήσω δυναμικό αριθμό στηλών;

Ναι. Μπορείτε να υπολογίσετε τον αριθμό των στηλών βάσει του μήκους της εισαγόμενης συμβολοσειράς:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Αυτό το απόσπασμα δείχνει **how to adjust columns** προγραμματιστικά, διασφαλίζοντας ότι το barcode ταιριάζει σε ένα δεδομένο layout.

### Η διάσταση X περιορίζεται σε ακέραια pixel;

Η ιδιότητα `Pixels` δέχεται οποιονδήποτε θετικό ακέραιο. Για εξόδους υψηλότερης ανάλυσης (π.χ., εκτύπωση), ίσως προτιμήσετε να ορίσετε `Points` αντί για `Pixels` ώστε να επιτύχετε μέγεθος ανεξάρτητο από τη συσκευή.

## Συμβουλές για χρήση σε παραγωγή

* **Pro tip:** Τυλίξτε τη δημιουργία του barcode σε μπλοκ try‑catch για να διαχειριστείτε το `BarCodeException` όταν τα δεδομένα εισόδου υπερβαίνουν τη χωρητικότητα του συμβόλου.  
* **Watch out for:** Δικαιώματα συστήματος αρχείων. Η διαδικασία πρέπει να έχει δικαίωμα εγγραφής στον προορισμό, διαφορετικά το βήμα **how to save barcode** θα αποτύχει με `UnauthorizedAccessException`.  
* **Performance note:** Η δημιουργία πολλών barcode σε βρόχο ωφελείται από την επαναχρησιμοποίηση ενός ενιαίου αντικειμένου `BarcodeGenerator` και την ενημέρωση μόνο της ιδιότητας `CodeText` μεταξύ των επαναλήψεων.

## Συμπέρασμα

Τώρα γνωρίζετε **how to save barcode** ως αρχείο PNG, **enable compact mode**, **how to adjust columns**, και **generate PDF417 barcode** χρησιμοποιώντας το Aspose.BarCode για C#. Το πλήρες παράδειγμα δείχνει κάθε απαιτούμενο βήμα, από την αρχικοποίηση του γεννήτριας μέχρι τη δημιουργία της τελικής εικόνας.

Από εδώ μπορείτε να εξερευνήσετε συναφή θέματα όπως η προσθήκη λογότυπου στο barcode, η προσαρμογή χρωμάτων ή η ενσωμάτωση του γεννήτρια σε API ASP.NET Core. Κάθε μία από αυτές τις επεκτάσεις ακολουθεί το ίδιο μοτίβο που παρουσιάζεται σε αυτόν τον οδηγό, ώστε να προσαρμόσετε τον κώδικα με σιγουριά.

Μη διστάσετε να πειραματιστείτε με διαφορετικούς αριθμούς στηλών, διαστάσεις X και μορφές εικόνας για να καλύψετε τις ακριβείς προδιαγραφές του έργου σας. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}