---
category: general
date: 2026-10-14
description: Μάθετε πώς να δημιουργήσετε pdf417 με Aspose.BarCode, προσθέστε προσαρμοσμένο
  κείμενο, μεταδεδομένα macro και εξάγετε το αποτέλεσμα ως PNG σε έναν βήμα‑βήμα οδηγό
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Μάθετε πώς να δημιουργήσετε pdf417 με Aspose.BarCode. Αυτός ο οδηγός
  δείχνει βήμα‑βήμα πώς να προσθέσετε προσαρμοσμένο κείμενο, μεταδεδομένα macro και
  να αποθηκεύσετε τον barcode ως εικόνα PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Πώς να δημιουργήσετε pdf417 – πλήρης οδηγός C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Πώς να δημιουργήσετε pdf417 – πλήρης οδηγός C#
url: /el/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε pdf417 – πλήρης οδηγός C#

Αν χρειάζεστε **generate pdf417** για ένα σύμβολο MacroPdf417, αυτό το tutorial σας καθοδηγεί μέσα από όλη τη διαδικασία. Θα δείτε πώς να ρυθμίσετε τις επιλογές που αφορούν το macro, να ενσωματώσετε προσαρμοσμένο κείμενο Unicode και να αποθηκεύσετε τον barcode ως εικόνα PNG. Στο τέλος του οδηγού θα έχετε ένα έτοιμο σε χρήση απόσπασμα C# που μπορεί να ενσωματωθεί σε οποιοδήποτε έργο .NET, είτε πρόκειται για εφαρμογή κονσόλας, υπηρεσία Windows ή μικρο‑υπηρεσία βασισμένη στο cloud.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.BarCode for .NET (supports 70+ symbologies).  
- **Μπορώ να προσθέσω χαρακτήρες Unicode;** Yes – the API fully supports UTF‑8 strings like `"Åspóse.Barcóde©"`.  
- **Χρειάζομαι άδεια για παραγωγή;** A valid Aspose.BarCode license is required for unlimited use; a free evaluation works for testing.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET 6+, .NET 5, .NET Core 3.1, and .NET Framework 4.7+.  
- **Είναι το PNG η καλύτερη μορφή για εκτύπωση;** PNG preserves lossless quality and is ideal for high‑resolution barcode printing.

## Τι είναι το pdf417;
`PDF417` είναι ένας στοίβακτος γραμμικός barcode που μπορεί να κωδικοποιήσει έως περίπου 1 700 χαρακτήρες ανά σύμβολο. Χρησιμοποιείται ευρέως για εισιτήρια μεταφοράς, ταυτότητες και παρακολούθηση αποθεμάτων επειδή μπορεί να αποθηκεύσει μεγάλες ποσότητες δεδομένων σε μια συμπαγή, μηχανικά αναγνώσιμη μορφή.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για τη δημιουργία pdf417;
Aspose.BarCode supports **70+ barcode symbologies**, processes files up to **2 GB** without loading the entire document into memory, and guarantees **100 % compliance with ISO/IEC 15438**. In benchmark tests the library creates a full‑size MacroPdf417 barcode in under **150 ms** on a typical development laptop, making it fast enough for high‑throughput server scenarios.

## Προαπαιτούμενα

* **.NET 6.0 ή νεότερο** (ο κώδικας λειτουργεί επίσης σε .NET Framework 4.7+).  
* Μια **έγκυρη άδεια Aspose.BarCode για .NET** (η δωρεάν δοκιμή λειτουργεί για ανάπτυξη).  
* **Visual Studio 2022** ή οποιοδήποτε άλλο IDE C# προτιμάτε.  
* Βασική εξοικείωση με τη σύνταξη C# και τις αντικειμενοστραφείς έννοιες.  

Δεν απαιτούνται πρόσθετα πακέτα NuGet πέρα από το **Aspose.BarCode**.

## Πώς να δημιουργήσετε pdf417 με επιλογές macro;

Φορτώστε το `BarcodeGenerator` με το enum `EncodeTypes.MacroPdf417`, ορίστε το μέγεθος μονάδας, διαμορφώστε τα πεδία macro και τέλος αποθηκεύστε την εικόνα. Τα παρακάτω βήματα δείχνουν τη σωστή σειρά για να αποφύγετε κοινά προβλήματα.

### Βήμα 1: εγκαταστήστε το πακέτο NuGet Aspose.BarCode

Ανοίξτε το έργο σας στο Visual Studio, στη συνέχεια εκτελέστε την παρακάτω εντολή στο Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Το πακέτο προσθέτει το namespace `Aspose.BarCode`, το οποίο περιέχει την κλάση `BarcodeGenerator` που χρησιμοποιείται σε όλο το tutorial.

### Βήμα 2: δημιουργήστε έναν δημιουργό barcode για MacroPdf417

`BarcodeGenerator` είναι η βασική κλάση που χρησιμοποιείται για τη δημιουργία barcode στο Aspose.BarCode.  
Η πρώτη γραμμή δημιουργεί μια παρουσία `BarcodeGenerator` που στοχεύει τη συμβολολογία **MacroPdf417** και ενσωματώνει το προσαρμοσμένο κείμενο που θέλετε να κωδικοποιήσετε.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` είναι η βασική κλάση του Aspose.BarCode για τη δημιουργία οποιουδήποτε barcode· περιέχει όλες τις επιλογές κωδικοποίησης και τις ρυθμίσεις απόδοσης.

### Βήμα 3: ορίστε το βασικό μέγεθος μονάδας

`XDimension` ορίζει το πλάτος μιας μονάδας (pixel) στο barcode.  
Το μέγεθος μονάδας ελέγχει την οπτική πυκνότητα του barcode. Μια τιμή pixel `2` παράγει μια καθαρή εικόνα που εκτυπώνεται καλά σε τυπικούς εκτυπωτές ετικετών.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Η αύξηση της τιμής κάνει το barcode μεγαλύτερο, ενώ η μείωση μπορεί να προκαλέσει προβλήματα σάρωσης σε συσκευές χαμηλής ανάλυσης.

### Βήμα 4: διαμορφώστε τις ρυθμίσεις διάταξης ειδικές για PDF417 macro

`Columns` καθορίζει τον αριθμό των στηλών δεδομένων στο barcode PDF417.  
MacroPdf417 απαιτεί αρκετές επιπλέον παραμέτρους. Αυτές οι ρυθμίσεις σας επιτρέπουν να χωρίσετε τα δεδομένα σε πολλαπλά αρχεία, να ταυτοποιήσετε κάθε τμήμα και να επαληθεύσετε την ακεραιότητα.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Η ιδιότητα `Columns` επηρεάζει το πλάτος του barcode, ενώ τα πεδία macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) επιτρέπουν στα downstream συστήματα να επανασυνθέσουν σωστά τα αρχικά δεδομένα.

### Βήμα 5: προσθέστε πρόσθετα μεταδεδομένα macro

`MacroPdf417Terminator` υποδεικνύει αν το τρέχον τμήμα είναι το τελευταίο σε μια σειρά macro.  
Aspose.BarCode σας επιτρέπει να ενσωματώσετε προαιρετικά πεδία macro όπως checksum, μέγεθος αρχείου, χρονική σήμανση και πληροφορίες αποστολέα/παραλήπτη. Αυτά τα πεδία είναι χρήσιμα για ιχνηλασία και ανίχνευση σφαλμάτων.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

Το checksum προστατεύει από σφάλματα μετάδοσης, ενώ η χρονική σήμανση και τα πεδία αποστολέα παρέχουν συμφραζόμενα για downstream επεξεργασία. Ορίζοντας `MacroPdf417Terminator` σε `Set` σηματοδοτεί ότι αυτό είναι το τελικό τμήμα της σειράς macro.

### Βήμα 6: αποθηκεύστε το barcode ως εικόνα PNG

`Save` γράφει την παραγόμενη εικόνα barcode σε αρχείο με τη συγκεκριμένη μορφή.  
Τέλος, γράψτε το παραγόμενο barcode στο δίσκο. Το PNG διατηρεί την απώλεια ποιότητας, κάτι ιδανικό για σάρωση.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Όταν ολοκληρωθεί ο κώδικας, το αρχείο `ExtPDF417Meta.png` περιέχει ένα υψηλής ανάλυσης MacroPdf417 barcode που κωδικοποιεί το προσαρμοσμένο κείμενο και όλα τα μεταδεδομένα macro.

#### Αναμενόμενο αποτέλεσμα

Ανοίγοντας το `ExtPDF417Meta.png` εμφανίζεται ένα κάθετα προσανατολισμένο barcode με σαφώς ορισμένες σειρές και στήλες. Η σάρωση της εικόνας με οποιονδήποτε αναγνώστη PDF417 επιστρέφει το αρχικό string **Åspóse.Barcóde©** και τα macro πεδία που διαμορφώσατε (file ID, segment ID, checksum, κλ.).

## Πώς να δημιουργήσετε pdf417 χωρίς επιλογές macro;

Για να δημιουργήσετε ένα τυπικό PDF417 barcode, χρειάζεται μόνο να ορίσετε τη συμβολολογία σε `EncodeTypes.Pdf417`, να παρέχετε το κείμενο προς κωδικοποίηση, προαιρετικά να προσαρμόσετε παραμέτρους μεγέθους όπως `XDimension` και `Columns`, και στη συνέχεια να καλέσετε το `Save`. Αυτή η προσέγγιση παραλείπει όλες τις ιδιότητες ειδικές για macro, παράγοντας ένα μονό‑τμημα barcode κατάλληλο για τις περισσότερες εφαρμογές.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Αυτό το απόσπασμα δείχνει **how to generate pdf417** γρήγορα όταν δεν απαιτείται λειτουργικότητα macro. Η άμεση απάντηση: δημιουργήστε ένα `BarcodeGenerator` με `EncodeTypes.Pdf417`, ορίστε το `CodeText`, προαιρετικά προσαρμόστε `XDimension` και `Columns`, και στη συνέχεια καλέστε `Save` με τη μορφή εικόνας που επιθυμείτε.

## Συνηθισμένα προβλήματα και επαγγελματικές συμβουλές

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| Το barcode είναι πολύ μικρό για σάρωση | Η X‑dimension ορίστηκε σε 1 pixel ή οι στήλες είναι πολύ πολλές | Χρησιμοποιήστε τουλάχιστον `2` pixels για `XDimension` και διατηρήστε τις στήλες μεταξύ `3` και `9` για τυπικά μεγέθη ετικετών |
| Οι χαρακτήρες Unicode εμφανίζονται ως � | Ασυμφωνία κωδικοποίησης στο αρχείο έργου | Βεβαιωθείτε ότι το αρχείο έργου είναι αποθηκευμένο ως UTF‑8 και το πηγαίο αρχείο περιέχει το σωστό BOM |
| Τα πεδία macro αγνοούνται από το σαρωτή | `MacroPdf417Terminator` δεν έχει οριστεί για το τελευταίο τμήμα | Ορίστε `MacroPdf417Terminator = Pdf417MacroTerminator.Set` στο τελικό τμήμα |
| Το αρχείο εικόνας είναι κατεστραμμένο | Η ροή εξόδου δεν κλείνει σωστά | Χρησιμοποιήστε τη δήλωση `using` (όπως φαίνεται) για να εγγυηθείτε την απελευθέρωση του δημιουργού |

## Πλήρες, εκτελέσιμο παράδειγμα

`BarcodeGenerator` είναι η κλάση που δημιουργεί την εικόνα barcode.  
Αντιγράψτε τον παρακάτω κώδικα σε μια νέα εφαρμογή κονσόλας και τρέξτε το. Το πρόγραμμα δημιουργεί το barcode, το αποθηκεύει και εκτυπώνει τη διαδρομή εξόδου στην κονσόλα.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Η εκτέλεση του προγράμματος εκτυπώνει μια γραμμή παρόμοια με:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Ανοίξτε το αρχείο για να επαληθεύσετε την οπτική έξοδο.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα σε ένα ASP.NET Core web API;**  
A: Ναι. Η ίδια κλάση `BarcodeGenerator` λειτουργεί σε οποιοδήποτε .NET runtime, συμπεριλαμβανομένου του ASP.NET Core, εφόσον η συναρμολόγηση `Aspose.BarCode` είναι αναφορά.

**Q: Υποστηρίζει το Aspose.BarCode άλλες μορφές εικόνας;**  
A: Απόλυτα. Μπορείτε να αποθηκεύσετε σε PNG, JPEG, BMP, TIFF, ακόμη και SVG περνώντας την αντίστοιχη τιμή enum `BarCodeImageFormat` στη μέθοδο `Save`.

**Q: Πόσο μεγάλα μπορούν να είναι τα κωδικοποιημένα δεδομένα;**  
A: Ένα μοναδικό σύμβολο PDF417 μπορεί να περιέχει έως 1 700 χαρακτήρες· με MacroPdf417 μπορείτε να χωρίσετε τα δεδομένα σε πολλαπλά τμήματα, υποστηρίζοντας πρακτικά απεριόριστο μήκος.

**Q: Υπάρχει τρόπος να προσθέσω χρώμα στο barcode;**  
A: Ναι. Ορίστε τις ιδιότητες `ForeColor` και `BackColor` του `BarcodeGenerator` πριν καλέσετε το `Save` για να παραγάγετε χρωματιστά barcodes.

**Q: Τι γίνεται αν χρειαστεί να ενσωματώσω το barcode απευθείας σε PDF;**  
A: Χρησιμοποιήστε το Aspose.PDF για να εισάγετε την παραγόμενη εικόνα PNG ή SVG σε μια σελίδα PDF, ή χρησιμοποιήστε τη ενσωματωμένη δυνατότητα εξαγωγής PDF του Aspose.BarCode.

## Συμπέρασμα

Τώρα γνωρίζετε **how to generate pdf417** για τη συμβολολογία MacroPdf417, να ενσωματώνετε προσαρμοσμένο κείμενο Unicode, να διαμορφώνετε μεταδεδομένα macro και να εξάγετε το αποτέλεσμα ως εικόνα PNG. Το ίδιο μοτίβο σας επιτρέπει να δημιουργήσετε ένα απλό PDF417 barcode όταν δεν απαιτούνται επιλογές macro, και μπορείτε να προσαρμόσετε τον κώδικα σε άλλες μορφές barcode που υποστηρίζει το Aspose.BarCode. Πειραματιστείτε με διαφορετικές τιμές `XDimension`, αριθμούς στηλών και συνδυασμούς πεδίων macro για να βελτιστοποιήσετε το barcode για τον συγκεκριμένο εκτυπωτή ή σαρωτή σας.

Στη συνέχεια, εξερευνήστε συναφή θέματα όπως **create barcode custom text** για QR codes, προσθήκη φίλτρων χρώματος με παραμέτρους `Color`, ή ενσωμάτωση barcodes απευθείας σε έγγραφα PDF χρησιμοποιώντας το Aspose.PDF. Η ευελιξία του Aspose.BarCode σημαίνει ότι μπορείτε να διαχειριστείτε τα πάντα, από απλά one‑line barcodes μέχρι πολύπλοκα multi‑segment macro barcodes, με λίγες μόνο γραμμές C#.

Καλή προγραμματιστική δουλειά και απολαύστε την αξιοπιστία που φέρνει το Aspose.BarCode στις .NET barcode λύσεις σας!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να δημιουργήσετε DataMatrix barcode με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Create Macro Pdf417 Barcode With Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Adjust Barcode Size C Guide To Generate Pdf417 Barcodes](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Read Barcode From Image C Complete Guide With Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}