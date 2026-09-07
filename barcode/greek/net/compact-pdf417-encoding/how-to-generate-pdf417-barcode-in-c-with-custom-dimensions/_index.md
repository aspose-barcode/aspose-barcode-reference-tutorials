---
category: general
date: 2026-09-07
description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# και μάθετε πώς να ορίσετε τις
  διαστάσεις του κώδικα για ακριβή έλεγχο. Ακολουθήστε αυτόν τον οδηγό βήμα‑προς‑βήμα
  για να δημιουργήσετε μια εικόνα PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: el
lastmod: 2026-09-07
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# και μάθετε πώς να ορίσετε
  τις διαστάσεις του κώδικα. Αυτό το σεμινάριο παρουσιάζει ένα πλήρες, εκτελέσιμο
  παράδειγμα.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Δημιουργία κώδικα PDF417 σε C# – πλήρης οδηγός με διαστάσεις
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με προσαρμοσμένες διαστάσεις
url: /el/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με προσαρμοσμένες διαστάσεις

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα που δημιουργεί μια εικόνα PNG ενώ σας επιτρέπει να ελέγχετε τις διαστάσεις του κώδικα.

Η δημιουργία γραμμωτού κώδικα PDF417 είναι συχνή απαίτηση για συστήματα αποθεμάτων, κάρτες επιβίβασης και ασφαλή έγγραφα. Σε αυτό το tutorial θα μάθετε επίσης **πώς να ορίσετε τις διαστάσεις του κώδικα** ώστε το αποτέλεσμα να ταιριάζει με τις ανάγκες του layout σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- .NET 6.0 SDK ή νεότερη έκδοση εγκατεστημένη  
- Visual Studio 2022 (ή οποιοδήποτε IDE συμβατό με C#)  
- Το **Aspose.BarCode for .NET** πακέτο NuGet (ή οποιαδήποτε συμβατή βιβλιοθήκη που υποστηρίζει PDF417)  

Μπορείτε να προσθέσετε το πακέτο με την ακόλουθη εντολή:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Δημιουργία γεννήτριας γραμμωτού κώδικα PDF417

Το πρώτο βήμα είναι να δημιουργήσετε ένα αντικείμενο `BarcodeGenerator` με τύπο `EncodeTypes.Pdf417` και το κείμενο που θέλετε να κωδικοποιήσετε. Το αντικείμενο της γεννήτριας περιέχει όλες τις ρυθμίσεις για τον κώδικα.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Γιατί είναι σημαντικό:** Η παράμετρος `EncodeTypes.Pdf417` λέει στη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική μορφή PDF417, η οποία υποστηρίζει μεγάλα δεδομένα και διόρθωση σφαλμάτων. Η συμβολοσειρά κειμένου μπορεί να περιέχει χαρακτήρες Unicode, ώστε να κωδικοποιείτε διεθνή σύμβολα χωρίς επιπλέον εργασία.

## Βήμα 2: Πώς να ορίσετε τις διαστάσεις του κώδικα

Ο έλεγχος του μεγέθους κάθε μονάδας (το μικρότερο μαύρο/λευκό τετράγωνο) καθορίζει τη συνολική ανάλυση της εικόνας. Η ιδιότητα `XDimension.Pixels` ορίζει το πλάτος σε pixel μιας μονάδας.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Γιατί είναι σημαντικό:** Μια μεγαλύτερη τιμή `XDimension` παράγει εικόνα υψηλότερης ανάλυσης, χρήσιμη για εκτύπωση ή σάρωση από απόσταση. Αντίστροφα, μια μικρότερη τιμή μειώνει το μέγεθος του αρχείου για χρήση στο web.

## Βήμα 3: Ορισμός διάταξης PDF417 (στήλες και γραμμές)

Το PDF417 σας επιτρέπει να επηρεάσετε το σχήμα του πλέγματος καθορίζοντας τον αριθμό των στηλών και των γραμμών. Αυτό μπορεί να επηρεάσει την αναγνωσιμότητα και το φυσικό μέγεθος του κώδικα.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Γιατί είναι σημαντικό:** Η ρύθμιση στηλών και γραμμών σας επιτρέπει να προσαρμόσετε τον κώδικα σε συγκεκριμένο χώρο ή να πληροί τις απαιτήσεις αναλογίας του σαρωτή. Η βιβλιοθήκη προσθέτει αυτόματα padding εάν τα δεδομένα δεν γεμίζουν πλήρως το πλέγμα.

## Βήμα 4: Αποθήκευση του κώδικα ως εικόνα PNG

Τέλος, γράψτε τον παραγόμενο κώδικα σε αρχείο. Το PNG διατηρεί την απώλεια‑από‑ποιότητα ποιότητα, καθιστώντας το ιδανικό για περαιτέρω επεξεργασία.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Όταν εκτελέσετε το πρόγραμμα, το `Pdf417Layout.png` εμφανίζεται στο φάκελο εξόδου του έργου. Η εικόνα φαίνεται ως εξής:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Κείμενο εναλλακτικής περιγραφής εικόνας: Παραγόμενη εικόνα γραμμωτού κώδικα PDF417 με προσαρμοσμένες διαστάσεις*  

**Γιατί είναι σημαντικό:** Η αποθήκευση ως PNG εξασφαλίζει ότι οι ακριβείς διαστάσεις των μονάδων που ορίσατε διατηρούνται, κάτι κρίσιμο για εφαρμογές σάρωσης.

## Πλήρες παράδειγμα σε ένα μπλοκ

Παρακάτω βρίσκεται ολόκληρο το πρόγραμμα που μπορείτε να αντιγράψετε, επικολλήσετε και να τρέξετε χωρίς τροποποιήσεις (εκτός από το μονοπάτι εξόδου, αν το επιθυμείτε).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Αναμενόμενο αποτέλεσμα

- **Αρχείο:** `Pdf417Layout.png` (PNG, χωρίς απώλειες)  
- **Διαστάσεις:** Προσδιορίζονται από το `XDimension` (2 px) × (στήλες × γραμμές) πλέγμα  
- **Περιεχόμενο:** Ένας σκανάρισιμος γραμμωτός κώδικας PDF417 που κωδικοποιεί τη συμβολοσειρά Unicode `Åspóse.Barcóde©`

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

### Τι κάνω αν χρειάζομαι μεγαλύτερη εικόνα για εκτύπωση;

Αυξήστε το `XDimension.Pixels` σε 4 ή 5. Μεγαλύτερες τιμές παράγουν κώδικα υψηλότερης ανάλυσης, αλλά αυξάνουν και το μέγεθος του αρχείου.

### Μπορώ να κωδικοποιήσω περισσότερα δεδομένα από τη συμβολοσειρά του παραδείγματος;

Ναι. Το PDF417 μπορεί να περιέχει έως 1 850 χαρακτήρες. Απλώς αντικαταστήστε το όρισμα κειμένου στον κατασκευαστή `BarcodeGenerator`. Εάν τα δεδομένα υπερβαίνουν τη χωρητικότητα του πλέγματος, η βιβλιοθήκη προσθέτει αυτόματα επιπλέον γραμμές.

### Πώς λειτουργεί η διόρθωση σφαλμάτων;

Το PDF417 περιλαμβάνει ενσωματωμένη διόρθωση σφαλμάτων. Μπορείτε να ρυθμίσετε το επίπεδό της μέσω:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Τα υψηλότερα επίπεδα αυξάνουν την ανθεκτικότητα με κόστος μεγαλύτερων κωδίκων.

### Τι κάνω αν ο κώδικας φαίνεται θολός στην οθόνη;

Βεβαιωθείτε ότι το DPI της εξαγόμενης εικόνας ταιριάζει με το περιβάλλον εμφάνισης. Μπορείτε να ορίσετε DPI κατά την αποθήκευση:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Pro tips

- **Pro tip:** Δοκιμάζετε πάντα τον παραγόμενο κώδικα με τον πραγματικό σαρωτή που σκοπεύετε να χρησιμοποιήσετε. Διαφορετικές συσκευές έχουν διαφορετική ανοχή στο μέγεθος των μονάδων και στις ζώνες ησυχίας.  
- **Watch out for:** Πολύ μικρές τιμές `XDimension` (< 1 px) μπορεί να εμφανιστούν ως αόρατες γραμμές σε οθόνες υψηλής ανάλυσης.  
- **Tip for web apps:** Σερβίρετε το PNG με `Cache-Control: public, max-age=86400` για να μειώσετε το κόστος επαναλαμβανόμενης δημιουργίας.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# και να **ορίσετε ακριβώς τις διαστάσεις του κώδικα** ώστε να ταιριάζει σε οποιαδήποτε απαίτηση. Το πλήρες, εκτελέσιμο παράδειγμα δείχνει τη δημιουργία εικόνας PNG με προσαρμοσμένη διάταξη στηλών/γραμμών και μέγεθος μονάδας, έτοιμη για εκτύπωση ή ψηφιακή διανομή.

### Επόμενα βήματα

- Εξερευνήστε **πώς να δημιουργήσετε γραμμωτό κώδικα PDF417** με διαφορετικές μορφές εικόνας (JPEG, BMP).  
- Μάθετε **πώς να ορίσετε διαστάσεις κώδικα** δυναμικά βάσει εισόδου χρήστη ή DPI συσκευής.  
- Ενσωματώστε τη δημιουργία κώδικα σε ένα ASP.NET Core API για να παρέχετε κώδικες κατόπιν αιτήματος.

Μη διστάσετε να πειραματιστείτε με άλλες ρυθμίσεις PDF417 όπως διόρθωση σφαλμάτων, περιθώρια και χρώμα. Καλή προγραμματιστική διασκέδαση!

## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κυριαρχήσετε σε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}