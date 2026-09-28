---
category: general
date: 2026-08-22
description: Δημιουργήστε γραμμωτό κώδικα FCC 11 σε C# χρησιμοποιώντας το Aspose.BarCode.
  Μάθετε βήμα‑βήμα τον κώδικα, ρυθμίστε τις διαστάσεις και δημιουργήστε εικόνες PNG
  για την Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: el
lastmod: 2026-08-22
og_description: Δημιουργήστε κωδικό γραμμής FCC 11 σε C# με το Aspose.BarCode. Ακολουθήστε
  αυτό το σύντομο οδηγό για να δημιουργήσετε κωδικούς γραμμής PNG για το Australia Post,
  συμπεριλαμβανομένων των παραλλαγών FCC 59 και FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Δημιουργία barcode FCC 11 σε C# – πλήρης οδηγός Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Πώς να δημιουργήσετε γραμμωτό κώδικα FCC 11 σε C# με το Aspose.BarCode
url: /el/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε το barcode FCC 11 σε C# με Aspose.BarCode

Αν χρειάζεστε **να δημιουργήσετε το barcode FCC 11** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει τον ακριβή κώδικα που απαιτείται. Θα δείτε πώς να διαμορφώσετε τις διαστάσεις του barcode, να επιλέξετε τον κατάλληλο πίνακα κωδικοποίησης και να αποθηκεύσετε το αποτέλεσμα ως αρχείο PNG.

Η δημιουργία barcode Australia Post είναι μια κοινή απαίτηση για τη λογιστική, τα συστήματα αλληλογραφίας και την παρακολούθηση αποθεμάτων. Αυτό το tutorial καλύπτει τη μορφή FCC 11 και επίσης δείχνει πώς να παράγετε barcode FCC 59 και FCC 62 με διαφορετικούς πίνακες κωδικοποίησης, ώστε να μπορείτε να επαναχρησιμοποιήσετε το ίδιο μοτίβο για άλλες ταχυδρομικές υπηρεσίες.

## Τι θα χρειαστείτε

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Visual Studio 2022 (ή οποιοδήποτε IDE συμβατό με C#)  
* Ένα έγκυρο άδεια για **Aspose.BarCode for .NET** – η έκδοση community λειτουργεί για αξιολόγηση  
* Δικαίωμα εγγραφής σε φάκελο όπου θα αποθηκευτούν τα αρχεία PNG  

Αυτές οι προαπαιτήσεις εγγυώνται ότι ο κώδικας θα μεταγλωττιστεί και θα εκτελεστεί χωρίς πρόσθετη διαμόρφωση.

## Βήμα 1: Εγκατάσταση του πακέτου NuGet Aspose.BarCode

Ανοίξτε ένα τερματικό στον φάκελο του έργου και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Η εντολή προσθέτει την πιο πρόσφατη σταθερή έκδοση της βιβλιοθήκης στο αρχείο του έργου σας. Το πακέτο περιέχει την κλάση `BarcodeGenerator` που χρησιμοποιείται σε όλο το tutorial.

## Βήμα 2: Ορισμός του φακέλου εξόδου

Δημιουργήστε ένα φάκελο όπου θα αποθηκευτούν οι παραγόμενες εικόνες. Η διαδρομή μπορεί να είναι απόλυτη ή σχετική με το εκτελέσιμο.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` εξασφαλίζει ότι ο φάκελος υπάρχει, αποτρέποντας σφάλματα χρόνου εκτέλεσης όταν η μέθοδος `Save` γράφει το αρχείο.

## Βήμα 3: Δημιουργία του barcode FCC 11

Η μορφή FCC 11 είναι η προεπιλεγμένη κωδικοποίηση για τα barcode της Australia Post. Ο παρακάτω κώδικας δημιουργεί ένα barcode που κωδικοποιεί τη αριθμητική συμβολοσειρά `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Γιατί λειτουργεί αυτό:**  
* `EncodeTypes.AustraliaPost` λέει στη βιβλιοθήκη να εφαρμόσει τους κανόνες κωδικοποίησης της Australia Post.  
* Η συμβολοσειρά δεδομένων `1101234567` ακολουθεί την προδιαγραφή FCC 11: τα πρώτα δύο ψηφία (`11`) προσδιορίζουν τη μορφή, ακολουθούμενα από έναν 7‑ψήφιο αναφορά πελάτη.  
* `XDimension` και `BarHeight` ελέγχουν το μέγεθος του εκτυπωμένου barcode, το οποίο είναι σημαντικό για την αναγνωσιμότητα από το scanner.  

Μετά την εκτέλεση του προγράμματος, θα βρείτε το `PostalAustraliaPostFCC11.png` στον φάκελο `Barcodes`. Η εικόνα φαίνεται ως εξής:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Βήμα 4: Δημιουργία πρόσθετων barcode Australia Post (προαιρετικό)

Ενώ ο κύριος στόχος είναι να **δημιουργήσετε το barcode FCC 11**, συχνά χρειάζεστε barcode FCC 59 ή FCC 62 για διαφορετικές κλάσεις αλληλογραφίας. Ο παρακάτω κώδικας επαναχρησιμοποιεί το ίδιο αντικείμενο `BarcodeGenerator`, αλλάζοντας μόνο τη συμβολοσειρά δεδομένων και τον προαιρετικό πίνακα κωδικοποίησης.

### 4.1 FCC 59 με κωδικοποίηση N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 με κωδικοποίηση N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 με κωδικοποίηση C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 με άλλη κωδικοποίηση

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Οι τέσσερις εικόνες αποθηκεύονται δίπλα-δίπλα στον ίδιο φάκελο, καθιστώντας εύκολη τη σύγκριση των οπτικών διαφορών.

## Βήμα 5: Κατανόηση των πινάκων κωδικοποίησης

Η Australia Post ορίζει τρεις πίνακες κωδικοποίησης:

* **N‑Table** – ερμηνεύει αριθμητικές πληροφορίες πελάτη. Χρησιμοποιήστε το όταν το payload περιέχει μόνο ψηφία.  
* **C‑Table** – υποστηρίζει αλφαριθμητικούς χαρακτήρες, χρήσιμο για αριθμούς αναφοράς που περιλαμβάνουν γράμματα.  
* **Other** – εναλλακτική επιλογή για προσαρμοσμένες ή επεκταμένες μορφές δεδομένων.  

Η επιλογή του σωστού πίνακα εξασφαλίζει ότι ο scanner barcode θα αποκωδικοποιήσει τις πληροφορίες ακριβώς όπως προορίζεται. Εάν παραλείψετε την ιδιότητα `AustralianPostEncodingTable`, η βιβλιοθήκη προεπιλέγει τον N‑Table, ο οποίος μπορεί να περικόψει μη‑αριθμητικούς χαρακτήρες.

## Συμβουλές, ειδικές περιπτώσεις και κοινά προβλήματα

| Κατάσταση | Συνιστώμενη προσέγγιση |
|-----------|----------------------|
| Το μήκος της συμβολοσειράς δεδομένων είναι μικρότερο από το απαιτούμενο | Συμπληρώστε το αριθμητικό μέρος με αρχικά μηδενικά ώστε να πληροί την προδιαγραφή FCC. |
| Το barcode εμφανίζεται θολό όταν εκτυπώνεται | Αυξήστε το `XDimension` σε 5 ή 6 pixel και ελέγξτε τις ρυθμίσεις DPI του εκτυπωτή. |
| Ο scanner επιστρέφει “invalid format” | Επαληθεύστε ότι ο σωστός πίνακας κωδικοποίησης (N‑Table, C‑Table, Other) ταιριάζει με το payload των δεδομένων. |
| Εκτέλεση σε Linux χωρίς GUI | Βεβαιωθείτε ότι το πακέτο `System.Drawing.Common` είναι αναφερθέν, ή χρησιμοποιήστε τη μέθοδο `Save` με `BarCodeImageFormat.Png` που δεν απαιτεί περιβάλλον εμφάνισης. |
| Απαιτείται διαφορετική μορφή εικόνας | Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg` ή `BarCodeImageFormat.Tiff` όπως απαιτείται. |

## Πλήρες εκτελέσιμο παράδειγμα

Παρακάτω υπάρχει ένα αυτόνομο πρόγραμμα που μπορείτε να αντιγράψετε σε ένα νέο έργο κονσόλας (`dotnet new console`) και να το εκτελέσετε χωρίς τροποποιήσεις.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputPath);

        // -------------------------------------------------
        // Create FCC 11 barcode – primary goal
        // -------------------------------------------------
        var fcc11 = new BarcodeGenerator(EncodeTypes.AustraliaPost, "1101234567");
        fcc11.Parameters.Barcode.XDimension.Pixels = 4;
        fcc11.Parameters.Barcode.BarHeight.Pixels = 50;
        fcc11


## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε barcode java – Barcode Australia Post με Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Δημιουργία One-Dimensional Databar κωδικοποίησης GS1 με Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Πώς να δημιουργήσετε quiet zone barcode .NET για Code 16K χρησιμοποιώντας Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}