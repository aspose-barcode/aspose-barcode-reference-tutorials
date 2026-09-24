---
category: general
date: 2026-08-09
description: Δημιουργήστε γρήγορα κωδικό PDF417 σε C#. Μάθετε πώς να δημιουργείτε
  PDF417 με συμπαγή λειτουργία, έλεγχο στηλών και έξοδο PNG χρησιμοποιώντας το API
  BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: el
lastmod: 2026-08-09
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# με ένα σύντομο παράδειγμα.
  Αυτός ο οδηγός σας δείχνει πώς να ρυθμίσετε τη συμπαγή λειτουργία, να ορίσετε στήλες
  και να αποθηκεύσετε το αποτέλεσμα ως εικόνα PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Δημιουργία γραμμωτού κώδικα PDF417 σε C# – πλήρης οδηγός
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Δημιουργία barcode PDF417 σε C# – οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία PDF417 barcode σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **δημιουργήσετε PDF417 barcode** σε μια εφαρμογή .NET, αυτό το tutorial σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε ένα πλήρες, εκτελέσιμο πρόγραμμα που δημιουργεί ένα compact PDF417 barcode, προσαρμόζει το μέγεθός του και αποθηκεύει την εικόνα ως αρχείο PNG.

Η δημιουργία ενός PDF417 barcode είναι συχνή απαίτηση για κινητά εισιτήρια, παρακολούθηση αποθεμάτων και ασφάλεια εγγράφων. Αυτός ο οδηγός καλύπτει τις βασικές επιλογές διαμόρφωσης, εξηγεί γιατί κάθε ρύθμιση είναι σημαντική και παρέχει πρακτικές συμβουλές για πραγματική χρήση.

## Προαπαιτούμενα

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Ένα IDE C# όπως το Visual Studio 2022 ή το Visual Studio Code  
* Το πακέτο **Aspose.BarCode for .NET** NuGet (έκδοση 23.10 ή νεότερη)  

Μπορείτε να εγκαταστήσετε το πακέτο με την ακόλουθη εντολή CLI:

```bash
dotnet add package Aspose.BarCode
```

Ο κώδικας παρακάτω υποθέτει ότι το πακέτο έχει αναφερθεί και ότι έχετε δικαίωμα εγγραφής στον φάκελο εξόδου.

## Βήμα 1: Ρύθμιση του έργου και εισαγωγή namespaces

Δημιουργήστε ένα νέο console project και προσθέστε τις απαιτούμενες οδηγίες `using`. Αυτά τα namespaces εκθέτουν την κλάση `BarcodeGenerator` και την απαρίθμηση μορφής εικόνας.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Γιατί είναι σημαντικό:** Η εισαγωγή των σωστών namespaces εξασφαλίζει ότι ο μεταγλωττιστής μπορεί να εντοπίσει τον τύπο `BarcodeGenerator` και το enum `BarCodeImageFormat`. Η έλλειψη ενός namespace προκαλεί σφάλμα μεταγλώττισης, το οποίο σταματά τη διαδικασία δημιουργίας barcode.

## Βήμα 2: Αρχικοποίηση του `BarcodeGenerator` με κωδικοποίηση PDF417

Ο κατασκευαστής `BarcodeGenerator` δέχεται δύο ορίσματα: τη συμβολική μορφή barcode (`EncodeTypes.Pdf417`) και το κείμενο που θέλετε να κωδικοποιήσετε. Το PDF417 υποστηρίζει ευρύ φάσμα χαρακτήρων, συμπεριλαμβανομένων των συμβόλων Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Εξήγηση:**  
* `EncodeTypes.Pdf417` λέει στη βιβλιοθήκη να χρησιμοποιήσει το πρότυπο PDF417.  
* Το δείγμα κειμένου περιέχει τόνους και ένα σύμβολο πνευματικών δικαιωμάτων για να δείξει τη διαχείριση Unicode.  

Αν χρειάζεστε κωδικοποίηση μόνο αριθμητικών δεδομένων, μπορείτε να περάσετε μια απλή συμβολοσειρά όπως `"1234567890"`.

## Βήμα 3: Ρύθμιση της διάστασης X για πιο λεπτή ανάλυση

Η διάσταση X ελέγχει το πλάτος ενός μονής μονάδας barcode (το μικρότερο μαύρο ή λευκό στοιχείο). Ορίζοντας μικρότερη τιμή pixel λαμβάνετε εικόνα υψηλότερης ανάλυσης.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Γιατί να το ρυθμίσετε;** Μια προεπιλεγμένη διάσταση X 3–4 pixel μπορεί να παράγει barcode που φαίνεται χονδροειδές σε οθόνες υψηλής DPI. Η μείωση σε **2 pixel** ισορροπεί την αναγνωσιμότητα με το μέγεθος του αρχείου, ειδικά όταν ενεργοποιήσετε το compact mode.

## Βήμα 4: Διαμόρφωση του αριθμού στηλών

Το PDF417 σας επιτρέπει να καθορίσετε πόσες στήλες θα περιέχει το barcode. Λιγότερες στήλες κάνουν το barcode πιο στενό αλλά ψηλότερο, ενώ περισσότερες στήλες δημιουργούν ένα πιο πλατύ, κοντύτερο barcode.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Πρακτική συμβουλή:** Για κινητά εισιτήρια που πρέπει να χωρέσουν σε στενή ετικέτα, ένας αριθμός στηλών **3–5** λειτουργεί καλά. Αυξήστε τον αριθμό αν έχετε πολλά δεδομένα και θέλετε ένα πιο κοντό barcode.

## Βήμα 5: Ενεργοποίηση compact mode για περικοπή κενών σειρών

Το compact mode αφαιρεί περιττές σειρές από το matrix του barcode, μειώνοντας το συνολικό μέγεθος της εικόνας χωρίς να χάνεται η κωδικοποιημένη πληροφορία.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Πότε να το χρησιμοποιήσετε:** Αν δημιουργείτε barcodes για αποθήκευση ή μετάδοση μέσω δικτύου, το compact mode μπορεί να μειώσει το αρχείο PNG έως και 30 %. Ωστόσο, ορισμένα παλιά scanners μπορεί να μην υποστηρίζουν το truncated PDF417· δοκιμάστε το με το υλικό σας.

## Βήμα 6: Αποθήκευση του barcode ως εικόνα PNG

Επιλέξτε διαδρομή εξόδου και καλέστε `Save`. Η απαρίθμηση `BarCodeImageFormat.Png` παράγει μια lossless εικόνα κατάλληλη για τις περισσότερες εφαρμογές.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Επαλήθευση αποτελέσματος:** Ανοίξτε το αρχείο PNG σε οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε ένα πυκνό, υψηλής αντίθεσης barcode που ταιριάζει με το δείγμα κειμένου. Η σάρωση της εικόνας με έναν PDF417 reader (π.χ., ZXing ή εφαρμογή smartphone) επιστρέφει την αρχική συμβολοσειρά `"Åspóse.Barcóde©"`.

![Δημιουργημένη εικόνα barcode PDF417 αποθηκευμένη ως PNG](compact-pdf417.png "Δημιουργημένο PDF417 barcode σε C#")

*Η παραπάνω εικόνα δείχνει το τελικό αποτέλεσμα του κώδικα του tutorial.*

## Πλήρες, εκτελέσιμο παράδειγμα

Συνδυάζοντας όλα τα κομμάτια, εδώ είναι ένα πλήρες console πρόγραμμα που μπορείτε να αντιγράψετε, επικολλήσετε και να τρέξετε.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Αναμενόμενη έξοδος

Η εκτέλεση του προγράμματος εκτυπώνει:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Το αρχείο `CompactPdf417.png` περιέχει ένα compact PDF417 barcode που κωδικοποιεί τη Unicode συμβολοσειρά που δόθηκε. Η σάρωση της εικόνας με έναν τυπικό PDF417 reader επιστρέφει το ακριβές κείμενο.

## Συνηθισμένες παραλλαγές και ακραίες περιπτώσεις

| Κατάσταση | Ρύθμιση | Αιτία |
|-----------|------------|--------|
| **Μεγαλύτερο φορτίο δεδομένων** (π.χ., > 150 χαρακτήρες) | Αυξήστε το `generator.Parameters.Barcode.Pdf417.Columns` σε 6‑8 | Περισσότερες στήλες αποτρέπουν το barcode να γίνει υπερβολικά ψηλό. |
| **Ανάγκη για διαφανές φόντο** | Χρησιμοποιήστε `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Το διαφανές PNG ενσωματώνεται καλύτερα σε επικάλυψη UI. |
| **Δημιουργία JPEG για web** | Αλλάξτε τη μορφή σε `BarCodeImageFormat.Jpeg` και προαιρετικά ορίστε `ImageQuality` | Το JPEG μειώνει το μέγεθος του αρχείου με κόστος την απώλεια ακριβούς πιστότητας. |
| **Διαχείριση null ή κενής εισόδου** | Προστατέψτε την είσοδο πριν δημιουργήσετε το generator: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Αποτρέπει εξαιρέσεις χρόνου εκτέλεσης και εξασφαλίζει ουσιαστικά barcodes. |

## Συμβουλές για παραγωγική χρήση

* **Exception handling:** Τυλίξτε τη λογική δημιουργίας σε ένα μπλοκ `try/catch` για να καταγράψετε σφάλματα όπως ανεπαρκής χώρος δίσκου ή μη έγκυρες παραμέτρους.  
* **Performance:** Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarcodeGenerator` όταν δημιουργείτε πολλά barcodes με τις ίδιες ρυθμίσεις· απλώς ενημερώστε την ιδιότητα `CodeText` μεταξύ των αποθηκεύσεων.  
* **Security:** Όταν το κωδικοποιημένο κείμενο περιέχει ευαίσθητες πληροφορίες, σκεφτείτε την κρυπτογράφηση πριν το περάσετε στο generator και την αποκρυπτογράφηση μετά τη σάρωση.  

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε PDF417 barcode** σε C# χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode, να ρυθμίσετε το compact mode, να ελέγξετε τον αριθμό στηλών και να εξάγετε το αποτέλεσμα ως εικόνα PNG. Αυτό το tutorial κάλυψε κάθε βήμα από τη ρύθμιση του έργου μέχρι τη διαχείριση ακραίων περιπτώσεων, παρέχοντάς σας μια έτοιμη λύση για εφαρμογές που βασίζονται σε barcode.

Στη συνέχεια, εξερευνήστε συναφή θέματα όπως **δημιουργία QR codes σε C#**, **batch barcode generation**, και **ενσωμάτωση σάρωσης barcode σε κινητές εφαρμογές**. Κάθε ένα από αυτά βασίζεται στα ίδια θεμέλια του `BarcodeGenerator` που μόλις μάθατε.

Καλή προγραμματιστική!

## Τι Θα Μάθετε Στη Σειρά;

Οι παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα επεξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να Δημιουργήσετε PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Πώς να Δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να δημιουργήσετε Aztec barcode με προσαρμοσμένη αναλογία διαστάσεων χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}