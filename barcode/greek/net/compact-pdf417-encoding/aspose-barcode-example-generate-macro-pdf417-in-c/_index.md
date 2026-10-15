---
category: general
date: 2026-10-09
description: Μάθετε πώς να δημιουργήσετε PDF417 barcode σε C# χρησιμοποιώντας το Aspose.BarCode
  – δημιουργήστε ένα Macro PDF417 με πλήρη υποστήριξη metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Μάθετε πώς να δημιουργήσετε PDF417 barcode σε C# χρησιμοποιώντας το
  Aspose.BarCode – δημιουργήστε ένα Macro PDF417 με πλήρη υποστήριξη metadata, συμπεριλαμβανομένων
  του file ID, segment data, timestamp και άλλα.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Πώς να δημιουργήσετε PDF417 barcode σε C# με Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Πώς να δημιουργήσετε PDF417 barcode σε C# με Aspose.BarCode
url: /el/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με το Aspose.BarCode

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί γραμμωτούς κώδικες PDF417;** Aspose.BarCode for .NET.  
- **Ποια μορφή εξάγει το παράδειγμα;** Μια απώλεια‑απλή PNG εικόνα.  
- **Χρειάζομαι άδεια;** Η δωρεάν δοκιμή λειτουργεί για το δείγμα· απαιτείται εμπορική άδεια για παραγωγή.  
- **Ποια έκδοση .NET υποστηρίζεται;** .NET 6.0 ή νεότερη.  
- **Μπορώ να προσθέσω μεταδεδομένα στον κώδικα;** Ναι – το Macro PDF417 υποστηρίζει file ID, segment count, timestamps και άλλα.

## Τι είναι ένας γραμμωτός κώδικας PDF417;
Ένας γραμμωτός κώδικας PDF417 είναι μια στοιβαγμένη γραμμική συμβολική που μπορεί να κωδικοποιήσει έως περίπου 1 KB δεδομένων ανά σύμβολο και υποστηρίζει προαιρετικά macro μεταδεδομένα για αρχεία πολλαπλών τμημάτων. Αποτελείται από πολλαπλές σειρές στοιβαγμένων γραμμικών προτύπων, επιτρέποντας υψηλή χωρητικότητα δεδομένων ενώ παραμένει αναγνώσιμος από τυπικούς 2‑D σαρωτές. Η μορφή περιλαμβάνει επίσης επίπεδα διόρθωσης σφαλμάτων για βελτιωμένη αξιοπιστία, και η προαιρετική λειτουργία macro επιτρέπει το διαχωρισμό μεγάλων αρχείων σε αρκετούς κώδικες με μεταδεδομένα που βοηθούν στην επανασυναρμολόγησή τους.

## Γιατί να χρησιμοποιήσετε το Aspose.BarCode για PDF417;
Το Aspose.BarCode υποστηρίζει **πάνω από 50 συμβολές γραμμωτών κωδίκων** και μπορεί να δημιουργήσει Macro PDF417 κώδικες με έως **2 000 στήλες**, διαχειριζόμενο αρχεία μεγαλύτερα από **10 MB** χωρίς να φορτώνει ολόκληρο το φορτίο στη μνήμη. Αυτή η ποσοτικοποιημένη δυνατότητα εξασφαλίζει ομαλή λειτουργία σε σενάρια υψηλής απόδοσης σε επιχειρηματικό επίπεδο και παρέχει εκτενείς επιλογές προσαρμογής.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- .NET 6.0 (ή νεότερη) εγκατεστημένη  
- Visual Studio 2022 ή οποιοδήποτε IDE συμβατό με C#  
- Ένα έγκυρο κλειδί άδειας για **Aspose.BarCode for .NET** (η δωρεάν δοκιμή λειτουργεί για αυτό το παράδειγμα)  

Προσθέστε το πακέτο NuGet Aspose.BarCode στο έργο σας:

```bash
dotnet add package Aspose.BarCode
```

## Πώς να δημιουργήσετε έναν PDF417 γραμμωτό κώδικα σε C#;

`BarcodeGenerator` είναι η κύρια κλάση για τη δημιουργία εικόνων γραμμωτών κωδίκων.  
`EncodeTypes.MacroPdf417` επιλέγει τη συμβολή Macro PDF417 για τη δημιουργία του κώδικα.  
`Save` γράφει τον παραγόμενο κώδικα σε αρχείο εικόνας.

Φορτώστε το `BarcodeGenerator` με την τιμή enum `EncodeTypes.MacroPdf417` και το κείμενο-στόχο, στη συνέχεια καλέστε `Save` – αυτή είναι η πλήρης ροή δημιουργίας σε τρεις γραμμές. Ο δημιουργός διαχειρίζεται αυτόματα Unicode, και η δήλωση `using` εγγυάται ότι οι μη διαχειριζόμενοι πόροι απελευθερώνονται μετά την αποθήκευση της εικόνας.

### Βήμα 1: δημιουργήστε το αντικείμενο BarcodeGenerator σε C# instance

Η κλάση `BarcodeGenerator` δημιουργεί και ρυθμίζει εικόνες γραμμωτών κωδίκων.  

Δημιουργήστε ένα αντικείμενο `BarcodeGenerator` με την τιμή enum `EncodeTypes.MacroPdf417` και το κείμενο που θέλετε να κωδικοποιήσετε. Το κείμενο μπορεί να περιέχει χαρακτήρες Unicode, τους οποίους η βιβλιοθήκη διαχειρίζεται αυτόματα.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Γιατί είναι σημαντικό*: `EncodeTypes.MacroPdf417` λέει στη μηχανή να παραγάγει σύμβολο Macro PDF417, το οποίο υποστηρίζει τμηματικά δεδομένα και πρόσθετα μεταδεδομένα σε επίπεδο αρχείου. Η δήλωση `using` εγγυάται ότι οι μη διαχειριζόμενοι πόροι απελευθερώνονται μετά την αποθήκευση της εικόνας.

### Βήμα 2: ορίστε την βασική εμφάνιση του γραμμωτού κώδικα

`XDimension.Pixels` ορίζει το μέγεθος κάθε μονάδας του κώδικα σε εικονοστοιχεία.

Ένας Macro PDF417 κώδικας αποτελείται από τετράγωνες μονάδες. Ο έλεγχος του μεγέθους των μονάδων και του αριθμού στηλών επηρεάζει τόσο την αναγνωσιμότητα όσο και το μέγεθος του αρχείου.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Γιατί είναι σημαντικό*: `XDimension.Pixels` καθορίζει την οπτική πυκνότητα· μια τιμή 2 pixels λειτουργεί καλά για προβολή σε οθόνη ενώ διατηρεί την εικόνα μικρή. Προσαρμόστε τον αριθμό στηλών ώστε να ταιριάζει με τους περιορισμούς του σχεδίου σας—περισσότερες στήλες δημιουργούν έναν πιο πλατύ, κοντύτερο κώδικα.

### Βήμα 3: ορίστε συγκεκριμένα μεταδεδομένα Macro PDF417

`MacroPdf417FileID` προσδιορίζει το αρχείο στο οποίο ανήκουν όλα τα τμήματα του κώδικα.

Το Macro PDF417 επεκτείνει το τυπικό φορμά PDF417 με πεδία που επιτρέπουν την ανασύνθεση μεγάλων αρχείων από πολλαπλά τμήματα κώδικα. Κάθε πεδίο είναι προαιρετικό, αλλά η ρύθμισή τους δείχνει τις πλήρεις δυνατότητες του API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Γιατί είναι σημαντικό*:  
- `MacroPdf417FileID` συνδέει όλα τα τμήματα που ανήκουν στο ίδιο λογικό αρχείο.  
- `MacroPdf417SegmentID` και `MacroPdf417SegmentsCount` επιτρέπουν στον αποκωδικοποιητή να αναδιατάξει τα τμήματα σωστά.  
- `MacroPdf417Checksum` παρέχει γρήγορο έλεγχο ακεραιότητας χωρίς αποκωδικοποίηση ολόκληρου του φορτίου.  
- `MacroPdf417FileSize` και `MacroPdf417TimeStamp` επιτρέπουν στα επόμενα συστήματα να επαληθεύσουν ότι το ανασυντεθειμένο αρχείο ταιριάζει με το αρχικό.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` είναι χρήσιμα σε σενάρια λογιστικής ή ανταλλαγής εγγράφων.  
- Ο ορισμός του `MacroPdf417Terminator` σε `Set` σηματοδοτεί αυτόν τον κώδικα ως το τελικό τμήμα, κάτι που απλοποιεί τον αλγόριθμο ανασύνθεσης.

### Βήμα 4: αποθηκεύστε την παραγόμενη εικόνα του γραμμωτού κώδικα

`Save` γράφει την εικόνα του κώδικα στο καθορισμένο μονοπάτι αρχείου.

Τέλος, γράψτε τον κώδικα σε αρχείο PNG. Μπορείτε να επιλέξετε οποιαδήποτε υποστηριζόμενη μορφή (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Γιατί είναι σημαντικό*: Το PNG διατηρεί τα pixel δεδομένα χωρίς απώλειες, εξασφαλίζοντας ότι οι σαρωτές διαβάζουν ακριβώς το μοτίβο μονάδων που διαμορφώσατε. Η αλλαγή μορφής μπορεί να επηρεάσει την οπτική ποιότητα και το μέγεθος του αρχείου.

#### Αναμενόμενο αποτέλεσμα

Η εκτέλεση του πλήρους προγράμματος δημιουργεί ένα αρχείο με όνομα **ExtPDF417Meta.png**. Το άνοιγμα της εικόνας εμφανίζει έναν ορθογώνιο Macro PDF417 κώδικα με το κείμενο “Åspóse.Barcóde©” κωδικοποιημένο, και η οπτική πυκνότητα ταιριάζει με τη διάσταση X 2 pixels που ορίσατε. Η σάρωση της εικόνας με έναν αναγνώστη συμβατό με PDF417 επιστρέφει όλα τα πεδία μεταδεδομένων που ορίστηκαν στο Βήμα 3.

## Πλήρες λειτουργικό παράδειγμα

Αντιγράψτε τον κώδικα παρακάτω σε ένα νέο έργο κονσόλας (`dotnet new console`) και αντικαταστήστε το `YOUR_DIRECTORY` με μια απόλυτη ή σχετική διαδρομή που υπάρχει στον υπολογιστή σας.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Εκτελέστε το πρόγραμμα (`dotnet run`). Μετά την εκτέλεση, ελέγξτε ότι το αρχείο PNG εμφανίζεται στην τοποθεσία που καθορίσατε. Χρησιμοποιήστε οποιαδήποτε εφαρμογή ανάγνωσης γραμμωτών κωδίκων που υποστηρίζει Macro PDF417 για να επιβεβαιώσετε ότι τα μεταδεδομένα έχουν ενσωματωθεί σωστά.

## Συνηθισμένες παραλλαγές και περιπτώσεις άκρων

- **Διαφορετικές μορφές εικόνας**: Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Tiff` εάν το επόμενο σύστημα προτιμά άλλη μορφή.  
- **Αλλαγή μεγέθους μονάδας**: Μεγαλύτερες τιμές `XDimension.Pixels` βελτιώνουν την αξιοπιστία σάρωσης σε σαρωτές χαμηλής ανάλυσης αλλά αυξάνουν το μέγεθος της εικόνας.  
- **Πολλαπλά τμήματα**: Για να παράγετε ένα αρχείο πολλαπλών τμημάτων, δημιουργήστε μια σειρά γραμμωτών κωδίκων, αυξήστε το `MacroPdf417SegmentID` για κάθε έναν, και διατηρήστε το `MacroPdf417FileID` σταθερό. Μόνο το τελευταίο τμήμα πρέπει να έχει ορισμένο `MacroPdf417Terminator`.  
- **Υποστήριξη Unicode**: Ο δημιουργός κωδικοποιεί αυτόματα χαρακτήρες Unicode· βεβαιωθείτε ότι η πηγή σας χρησιμοποιεί κωδικοποίηση UTF-8 εάν την διαβάζετε από εξωτερικό αρχείο.  
- **Διαχείριση σφαλμάτων**: Τυλίξτε το μπλοκ `using` σε try‑catch για να πιάσετε `BarCodeException` για μη έγκυρες παραμέτρους (π.χ., αριθμός στηλών εκτός ορίου).

## Επαγγελματικές συμβουλές

- **Απόδοση**: Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarcodeGenerator` όταν δημιουργείτε πολλούς κώδικες με τις ίδιες ρυθμίσεις· αλλάξτε μόνο την ιδιότητα `CodeText` μεταξύ των αποθηκεύσεων.  
- **Εκτίμηση μεγέθους αρχείου**: Το πεδίο `MacroPdf417FileSize` πρέπει να ταιριάζει με τον αριθμό byte του αρχικού φορτίου· οι ασυμφωνίες μπορεί να προκαλέσουν αποτυχίες επικύρωσης στα επόμενα συστήματα.  
- **Δοκιμή**: Επικυρώστε τους παραγόμενους κώδικες τόσο με τον ενσωματωμένο αποκωδικοποιητή της Aspose (`BarCodeReader`) όσο και με έναν εξωτερικό σαρωτή για να εξασφαλίσετε διαλειτουργικότητα.

## Συμπέρασμα

Αυτό το παράδειγμα **Aspose.BarCode** σας δείχνει πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417 σε C#** με πλήρη υποστήριξη Macro μεταδεδομένων, παρέχοντάς σας μια σταθερή βάση για την κατασκευή αξιόπιστων αγωγών ανταλλαγής δεδομένων βασισμένων σε γραμμωτούς κώδικες.

## Τι πρέπει να μάθετε στη συνέχεια;

Οι παρακάτω οδηγίες καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε γραμμωτό κώδικα – Compact PDF417 με το Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να δημιουργήσετε ήσυχη ζώνη γραμμωτού κώδικα για Code 16K χρησιμοποιώντας το Aspose.BarCode για .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Πώς να δημιουργήσετε ήσυχη ζώνη γραμμωτού κώδικα για ITF-14 χρησιμοποιώντας το Aspose.BarCode για .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Τελευταία ενημέρωση:** 2026-10-09  
**Δοκιμή με:** Aspose.BarCode 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε εικόνα γραμμωτού κώδικα Pdf417 σε C με το Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα – Compact PDF417 με το Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Μάθημα δημιουργίας γραμμωτού κώδικα – Πώς να δημιουργήσετε γραμμωτό κώδικα Pdf417](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}