---
category: general
date: 2026-09-22
description: Μάθετε πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C#, να ορίσετε
  το μέγεθός του και να παράγετε αρχεία εικόνας γραμμωτού κώδικα με σαφή παραδείγματα
  κώδικα βήμα‑βήμα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: el
lastmod: 2026-09-22
og_description: Δημιουργήστε γρήγορα γραμμωτό κώδικα PDF417 σε C#. Αυτό το σεμινάριο
  δείχνει πώς να ορίσετε το μέγεθος του κώδικα, να ενεργοποιήσετε τη συμπαγή λειτουργία
  και να εξάγετε εικόνες PNG για οποιοδήποτε έργο .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Δημιουργία γραμμωτού κώδικα PDF417 σε C# – οδηγός βήμα προς βήμα
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 και να ορίσετε το μέγεθός του σε
  C#
url: /el/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 και να ορίσετε το μέγεθός του σε C#

Αν χρειάζεστε **δημιουργία γραμμωτού κώδικα PDF417** σε C#, αυτός ο οδηγός σας δείχνει πώς να δημιουργήσετε τον κώδικα, να ελέγξετε τις διαστάσεις του και να αποθηκεύσετε το αποτέλεσμα ως αρχείο εικόνας. Είτε χτίζετε σύστημα έκδοσης εισιτηρίων, ετικέτα λογιστικής ή ασφαλή διαπίστευση, η εξοικείωση με τη μορφή PDF417 σας επιτρέπει να κωδικοποιήσετε μεγάλες ποσότητες δεδομένων σε μια συμπαγή οπτική μορφή.

Σε αυτό το tutorial θα μάθετε να:

* **Δημιουργείτε γραμμωτό κώδικα PDF417** με τη βιβλιοθήκη Aspose.BarCode (ή οποιαδήποτε συμβατή).  
* **Ορίζετε το μέγεθος του κώδικα** ρυθμίζοντας τη διάσταση X και τον αριθμό στηλών.  
* Δημιουργείτε **εικόνα γραμμωτού κώδικα σε C#** για έξοδο PNG, JPEG ή BMP.  

Το παράδειγμα χρησιμοποιεί την δωρεάν έκδοση community της Aspose.BarCode για .NET, αλλά οι ίδιες έννοιες ισχύουν και για άλλες βιβλιοθήκες που εκθέτουν παρόμοιες ιδιότητες.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερη έκδοση εγκατεστημένη.  
* Ένα IDE για C# (Visual Studio, Visual Studio Code, Rider κ.λπ.).  
* Το πακέτο NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Δεν απαιτείται πρόσθετη ρύθμιση· η βιβλιοθήκη λειτουργεί σε Windows, Linux και macOS.

## Βήμα 1: Δημιουργία βασικού PDF417 barcode και ορισμός του μεγέθους

Το πρώτο βήμα είναι να δημιουργήσετε ένα αντικείμενο `BarcodeGenerator` με το enum `EncodeTypes.Pdf417` και να περάσετε το κείμενο που θέλετε να κωδικοποιήσετε. Στη συνέχεια ρυθμίστε τη **διάσταση X** (πλάτος μονάδας) και τον αριθμό **στηλών** για να ελέγξετε το συνολικό μέγεθος.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Γιατί είναι σημαντικές αυτές οι ρυθμίσεις**

* `XDimension.Pixels` καθορίζει το πιο στενό πλάτος γραμμής. Μικρότερες τιμές παράγουν πιο πυκνό κώδικα, ενώ μεγαλύτερες αυξάνουν την αναγνωσιμότητα σε σαρωτές χαμηλής ανάλυσης.  
* `Pdf417.Columns` επηρεάζει την αναλογία διαστάσεων του κώδικα. Λιγότερες στήλες κάνουν τον κώδικα πιο ψηλό· περισσότερες στήλες τον «απλώνουν». Η ρύθμιση των στηλών είναι ο κύριος τρόπος **ορισμού μεγέθους barcode** χωρίς να αλλάζει το κωδικοποιημένο δεδομένο.

Μετά την εκτέλεση του κώδικα, θα βρείτε το αρχείο `Pdf417Basic.png` στον καθορισμένο φάκελο. Η εικόνα μοιάζει με το στιγμιότυπο παρακάτω:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Βήμα 2: Δημιουργία συμπαγούς PDF417 barcode (truncate mode) με το ίδιο μέγεθος

Μερικές φορές χρειάζεται ένας πιο σύντομος κώδικας λόγω περιορισμένου χώρου. Το PDF417 προσφέρει *truncate* (συμπαγή) λειτουργία που αφαιρεί το μοτίβο τερματισμού και μειώνει το συνολικό ύψος. Η ιδιότητα `Truncate` ενεργοποιεί αυτή τη συμπεριφορά.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Τι αλλάζει με `Truncate = true`;**

* Ο κώδικας γίνεται περίπου 15‑20 % πιο σύντομος κατακόρυφα, κάτι που είναι χρήσιμο για μικρές ετικέτες ή οθόνες κινητών.  
* Τα δεδομένα παραμένουν πλήρως ανακτήσιμα· οι περισσότεροι σύγχρονοι σαρωτές καταλαβαίνουν αυτόματα τη λειτουργία truncate.

Το παραγόμενο `CompactPdf417.png` εμφανίζεται ως μια πιο λεπτή έκδοση του βασικού κώδικα.

## Βήμα 3: Δημιουργία Micro PDF417 barcode, ρύθμιση στηλών και αποθήκευση

Το Micro PDF417 είναι μια νεότερη, υψηλής πυκνότητας παραλλαγή σχεδιασμένη για πολύ μικρούς χώρους (π.χ. κάρτες ταυτότητας). Υποστηρίζει μόνο 1‑4 στήλες, και η βιβλιοθήκη εκθέτει την ίδια ιδιότητα `XDimension` για έλεγχο μεγέθους.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Βασικά σημεία για το Micro PDF417**

* Το enum `EncodeTypes.MicroPdf417` επιλέγει αυτόματα τη μικρο‑παραλλαγή.  
* Επειδή το σύμβολο είναι πιο πυκνό, μπορεί να χρειαστεί εκτυπωτής υψηλότερης ανάλυσης (300 dpi ή περισσότερο) για να παραμείνει αναγνώσιμο.  
* Η ρύθμιση του αριθμού στηλών είναι ο μοναδικός «knob» μεγέθους· η βιβλιοθήκη εξακολουθεί να σέβεται το `XDimension`.

## Πώς να ορίσετε το μέγεθος barcode για διαφορετικές μορφές εξόδου

Τα παραδείγματα παραπάνω χρησιμοποιούν PNG, αλλά η ίδια μέθοδος `Save` λειτουργεί και με JPEG, BMP ή TIFF. Αν χρειάζεστε συγκεκριμένες διαστάσεις εικόνας (π.χ. 300 × 150 px), συνδυάστε το `XDimension` με τα `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Η αύξηση του `ImageResolution` ενώ κλιμακώνετε το `XDimension` διατηρεί την οπτική ποιότητα σε εκτυπώσεις υψηλής ανάλυσης.

## Συνηθισμένα προβλήματα και επαγγελματικές συμβουλές

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Ο κώδικας εμφανίζεται θολός στην οθόνη | Χαμηλό DPI σε συνδυασμό με μικρό `XDimension` | Αυξήστε το `ImageResolution` και/ή το `XDimension.Pixels` |
| Ο σαρωτής δεν διαβάζει τη λειτουργία truncate | Παλαιότερο firmware σαρωτή δεν υποστηρίζει | Χρησιμοποιήστε τη μη‑συμπαγή (full) λειτουργία για παλαιό εξοπλισμό |
| Το Micro PDF417 δεν διαβάζεται | Εκτύπωση < 300 dpi ή ανεπαρκής αντίθεση | Εκτυπώστε σε ματ χαρτί στα 300 dpi ή περισσότερο, εξασφαλίστε σκούρο φόντο |
| Το αρχείο εξόδου είναι κατεστραμμένο | Έλλειψη δικαιώματος εγγραφής στον προορισμό | Επαληθεύστε ότι το `YOUR_DIRECTORY` υπάρχει και είναι εγγράψιμο |

**Επαγγελματική συμβουλή:** Πάντα δημιουργείτε τον κώδικα ως PNG όταν χρειάζεστε απώλεια‑από‑ποιότητα ποιότητα για περαιτέρω επεξεργασία (π.χ. ενσωμάτωση σε PDF). Το PNG διατηρεί ακριβείς τιμές pixel, ενώ το JPEG εισάγει συμπίεση που μπορεί να επηρεάσει την αναγνωσιμότητα του κώδικα.

## Πλήρες, εκτελέσιμο παράδειγμα

Παρακάτω βρίσκεται μια πλήρης εφαρμογή κονσόλας που δείχνει και τους τρεις τύπους κώδικα σε μία εκτέλεση. Αντιγράψτε τον κώδικα σε νέο .NET console project και τρέξτε το.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Αναμενόμενο αποτέλεσμα**

Η εκτέλεση του προγράμματος δημιουργεί τρία αρχεία PNG μέσα σε φάκελο `Barcodes`:

* `Pdf417Basic.png` – τυπικός PDF417 κώδικας με τρεις στήλες.  
* `CompactPdf417.png` – τα ίδια δεδομένα σε truncate (συμπαγή) λειτουργία, ελαφρώς πιο σύντομο.  
* `MicroPdf417.png` – υψηλής πυκνότητας Micro PDF417 παραλλαγή με τέσσερις στήλες.

Ανοίξτε οποιαδήποτε εικόνα με προβολέα· θα δείτε το χαρακτηριστικό «στοίβαγμα» του κώδικα.

## Τι πρέπει να μάθετε στη συνέχεια;

Οι παρακάτω οδηγίες καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας έργα.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}