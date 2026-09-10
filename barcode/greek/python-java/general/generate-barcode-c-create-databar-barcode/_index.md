---
category: general
date: 2026-07-21
description: Δημιουργήστε γρήγορα barcode C# με το Aspose.BarCode. Μάθετε πώς να δημιουργήσετε
  barcode DataBar, να προσαρμόσετε το μέγεθος του barcode και να εξάγετε την εικόνα
  του barcode σε λίγα μόνο βήματα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: el
lastmod: 2026-07-21
og_description: Δημιουργήστε barcode C# με χρήση του Aspose.BarCode. Δημιουργήστε
  barcode DataBar, προσαρμόστε το μέγεθός του και εξάγετε την εικόνα αμέσως.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Δημιουργία γραμμωτού κώδικα C# – Κατασκευή DataBar γραμμωτών κωδίκων με
  προσαρμοσμένο μέγεθος
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Δημιουργία γραμμωτού κώδικα C# – Δημιουργία DataBar γραμμωτού κώδικα
url: /el/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία barcode C# – Δημιουργία DataBar barcode

Ψάχνετε να **δημιουργήσετε barcode C#** χωρίς να σπαταλάτε χρόνο σε ατελείωτη τεκμηρίωση; Βρίσκεστε στο σωστό σημείο. Σε αυτόν τον οδηγό θα περάσουμε από τη δημιουργία ενός **DataBar barcode**, την προσαρμογή των διαστάσεών του και, τέλος, την **εξαγωγή της εικόνας του barcode**—όλα με λίγες γραμμές C#.

Φανταστείτε ότι χρειάζεστε μια συμπαγή ετικέτα προϊόντος που να χωράει σε μια μικρή ετικέτα ράφι. Η συμβολική DataBar Expanded Stacked κάνει τη δουλειά, και με το Aspose.BarCode μπορείτε να ελέγξετε ακριβώς πόσες στήλες ή σειρές χρησιμοποιεί. Έτοιμοι; Ας ξεκινήσουμε.

## Τι θα πετύχετε

- **Δημιουργία DataBar barcode** (η παραλλαγή “expanded stacked”) από την αρχή.  
- **Προσαρμογή μεγέθους barcode** ορίζοντας άμεσα στήλες ή σειρές.  
- **Αλλαγή διαστάσεων barcode** εν κινήσει χωρίς να ξαναδημιουργήσετε το γεννήτρια.  
- **Εξαγωγή εικόνας barcode** σε PNG (ή οποιαδήποτε μορφή υποστηρίζει το Aspose).  

Καμία εξωτερική υπηρεσία, καμία ακατάστατη ρύθμιση—απλός, εκτελέσιμος κώδικας C#.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης σε .NET Framework 4.7+).  
- Έγκυρη άδεια Aspose.BarCode for .NET (ή μπορείτε να τρέξετε σε λειτουργία δοκιμής).  
- Ένα IDE της επιλογής σας—Visual Studio, Rider ή VS Code αρκεί.  

Αν δεν έχετε εγκαταστήσει ακόμα το πακέτο NuGet, τρέξτε:

```bash
dotnet add package Aspose.BarCode
```

Αυτό είναι όλο—χωρίς άλλες εξαρτήσεις.

## Βήμα 1: Ρύθμιση του barcode generator (Πώς να **generate barcode C#**)

Πρώτα, χρειάζεται μια παρουσία `BarcodeGenerator` που να δείχνει στη συμβολική **DataBar Expanded Stacked**. Αυτό το αντικείμενο είναι η μηχανή που δημιουργεί την εικόνα αργότερα.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Γιατί είναι σημαντικό*: Η απαρίθμηση `EncodeTypes.DatabarExpandedStacked` λέει στο Aspose ότι θέλουμε την στοίβαξη, η οποία είναι ιδανική για στενούς χώρους. Το κείμενο που περνάμε γίνεται η κωδικοποιημένη τιμή· μπορείτε να το αντικαταστήσετε με οποιοδήποτε αριθμητικό string απαιτεί η εφαρμογή σας.

## Βήμα 2: **Προσαρμογή μεγέθους barcode** – ορισμός στηλών

Τα DataBar barcodes σας επιτρέπουν να επηρεάσετε την οπτική πυκνότητα ορίζοντας είτε τον αριθμό **στηλών** *είτε* **γραμμών**. Ας ξεκινήσουμε με τις στήλες. Ο αριθμός γραμμών θα υπολογιστεί αυτόματα ώστε το barcode να παραμένει έγκυρο.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Συμβουλή*: Οι στήλες επηρεάζουν το πλάτος του barcode. Περισσότερες στήλες → ευρύτερο barcode, κάτι που μπορεί να βελτιώσει την αξιοπιστία σάρωσης σε εκτυπωτές χαμηλής ανάλυσης.

## Βήμα 3: **Εξαγωγή εικόνας barcode** με τη ρύθμιση στηλών

Τώρα γράφουμε την εικόνα στο δίσκο. Μπορείτε να επιλέξετε PNG, JPEG, BMP ή ακόμη και SVG. Εδώ χρησιμοποιούμε PNG για καθαρή, χωρίς απώλειες έξοδο.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Αναμενόμενο αποτέλεσμα** – Ανοίξτε το `DatabarCols4.png` και θα δείτε ένα καλοσχεδιασμένο stacked DataBar με τέσσερις στήλες. Φαίνεται σαν πυκνή στοίβα κατακόρυφων γραμμών, ιδανική για μικρή ετικέτα.

## Βήμα 4: **Αλλαγή διαστάσεων barcode** – ορισμός γραμμών

Μερικές φορές χρειάζεστε ένα ψηλότερο barcode αντί για ένα πλατύτερο. Αλλάζουμε σε έλεγχο γραμμών· το Aspose θα επαναϋπολογίσει αυτόματα τις στήλες.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Γιατί η αλλαγή;* Οι γραμμές επηρεάζουν το ύψος του barcode. Περισσότερες γραμμές κάνουν το σύμβολο ψηλότερο, χρήσιμο όταν έχετε κατακόρυφο χώρο αλλά περιορισμένο πλάτος.

## Βήμα 5: **Εξαγωγή εικόνας barcode** με τη ρύθμιση γραμμών

Αποθηκεύστε τη δεύτερη παραλλαγή. Παρατηρήστε ότι το όνομα αρχείου αντανακλά την αλλαγή· μπορείτε επίσης να κρατήσετε και τις δύο εικόνες για σύγκριση.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Αποτέλεσμα** – Το `DatabarRows3.png` εμφανίζει τώρα μια πιο ψηλή έκδοση των ίδιων δεδομένων, εξακολουθώντας να είναι πλήρως αναγνώσιμο.

## Πλήρες λειτουργικό παράδειγμα

Συνδυάζοντας όλα τα παραπάνω, ακολουθεί μια αυτόνομη εφαρμογή κονσόλας που μπορείτε να αντιγράψετε‑επικολλήσετε και να τρέξετε αμέσως:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Τρέξτε το πρόγραμμα, μετά ανοίξτε τα δύο αρχεία PNG. Έχετε τώρα **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, και **export barcode image**—όλα σε λιγότερο από ένα λεπτό.

## Συχνές ερωτήσεις & ειδικές περιπτώσεις

- **Τι αν χρειάζομαι διαφορετική μορφή εικόνας;**  
  Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp`, `Gif` ή `Svg`. Το API διαχειρίζεται αυτόματα τη μετατροπή.

- **Μπορώ να αλλάξω ταυτόχρονα και γραμμές και στήλες;**  
  Τεχνικά μπορείτε να ορίσετε και τα δύο, αλλά το Aspose θα δώσει προτεραιότητα στην τελευταία ιδιότητα που τροποποιήσατε. Είναι πιο ασφαλές να ορίσετε *μία* διάσταση και να αφήσετε τη βιβλιοθήκη να υπολογίσει την άλλη για ένα έγκυρο DataBar.

- **Πώς εφαρμόζω χρώμα προσκηνίου/υπόβαθρου;**  
  Χρησιμοποιήστε `barcodeGen.Parameters.Barcode.ForegroundColor` και `BackgroundColor`. Παράδειγμα:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Υπάρχει όριο μεγέθους για τα κωδικοποιημένα δεδομένα;**  
  Το DataBar Expanded Stacked υποστηρίζει έως 74 αριθμητικούς χαρακτήρες (ή 30 αλφαριθμητικούς). Η υπέρβαση προκαλεί εξαίρεση.

## Επόμενα βήματα

Τώρα που έχετε κατακτήσει τα βασικά του **create databar barcode**, σκεφτείτε:

- Προσθήκη **σχολίων κειμένου** κάτω από το barcode (`barcodeGen.Parameters.CaptionAbove.Text`).
- Ενσωμάτωση του PNG απευθείας σε PDF χρησιμοποιώντας Aspose.PDF.
- Δημιουργία barcodes μαζικά μέσω βρόχου πάνω σε CSV με τα IDs προϊόντων.

Κάθε ένα από αυτά τα θέματα βασίζεται στο ίδιο αντικείμενο `BarcodeGenerator`, οπότε δεν θα χρειαστεί να ξεκινήσετε από την αρχή.

---

**Συμπέρασμα**: τώρα ξέρετε πώς να **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, και **export barcode image** με το Aspose.BarCode. Παίξτε με τις τιμές στήλης/γραμμής, αλλάξτε μορφές εικόνας, και ενσωματώστε τον κώδικα στο σύστημα αποθεμάτων ή POS σας. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας έργα.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}