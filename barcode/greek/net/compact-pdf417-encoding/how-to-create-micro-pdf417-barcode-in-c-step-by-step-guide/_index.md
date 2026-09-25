---
category: general
date: 2026-08-22
description: Μάθετε πώς να δημιουργήσετε μικρο‑κώδικα PDF417 σε C# και να δημιουργήσετε
  μια εικόνα PNG του κώδικα. Περιλαμβάνει τον καθορισμό διαστάσεων του κώδικα και
  την αποθήκευση του αρχείου.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: el
lastmod: 2026-08-22
og_description: Δημιουργήστε μικρο‑PDF417 barcode σε C# και εξάγετέ το ως PNG. Ακολουθήστε
  αυτόν τον οδηγό για να ορίσετε τις διαστάσεις του barcode και να δημιουργήσετε γρήγορα
  μια εικόνα barcode.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Δημιουργήστε μικρό γραμμωτό κώδικα PDF417 σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Πώς να δημιουργήσετε μικρό κωδικό PDF417 σε C# – οδηγός βήμα‑βήμα
url: /el/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε μικρό PDF417 barcode σε C# – οδηγός βήμα‑βήμα

Αν χρειάζεστε **να δημιουργήσετε μικρό PDF417 barcode** για σύστημα έκδοσης εισιτηρίων, ετικέτα αποθέματος ή κινητή σάρωση, αυτό το tutorial σας δείχνει ακριβώς πώς. Θα δείτε το πλήρες πρόγραμμα C# που δημιουργεί ένα barcode PNG, θα μάθετε πώς να ορίζετε τις διαστάσεις του barcode και θα κατανοήσετε κάθε επιλογή διαμόρφωσης.

Στο τέλος αυτού του οδηγού θα μπορείτε να δημιουργήσετε μια εικόνα barcode υψηλής ανάλυσης, να προσαρμόσετε τη διάσταση X, να επιλέξετε τον αριθμό στηλών και να αποθηκεύσετε το αποτέλεσμα ως αρχείο PNG — όλα με λίγες γραμμές κώδικα.

## Τι θα χρειαστείτε

- .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί με .NET Core και .NET Framework)
- Visual Studio 2022 ή οποιοδήποτε IDE συμβατό με C#
- Το πακέτο NuGet **Aspose.BarCode for .NET** (ή οποιαδήποτε βιβλιοθήκη που υποστηρίζει `EncodeTypes.MicroPdf417`)
- Βασική εξοικείωση με τη σύνταξη C#

> **Συμβουλή επαγγελματία:** Η δωρεάν έκδοση community του Aspose.BarCode είναι επαρκής για ανάπτυξη και δοκιμές. Για παραγωγή, αποκτήστε άδεια για να αφαιρέσετε τα υδατογράμματα αξιολόγησης.

## Βήμα 1: Εγκατάσταση της βιβλιοθήκης barcode

Ανοίξτε ένα τερματικό στο φάκελο του έργου σας και εκτελέστε:

```bash
dotnet add package Aspose.BarCode
```

Αυτό προσθέτει το assembly `Aspose.BarCode`, το οποίο παρέχει την κλάση `BarcodeGenerator` που χρησιμοποιείται για **δημιουργία εικόνας barcode C#** εφαρμογών.

## Βήμα 2: Αρχικοποίηση του δημιουργού – δημιουργία μικρού PDF417 barcode

Η πρώτη ενέργεια δημιουργεί ένα στιγμιότυπο `BarcodeGenerator` διαμορφωμένο για τη συμβολική Micro PDF417 και παρέχει τα δεδομένα που θέλετε να κωδικοποιήσετε.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Γιατί είναι σημαντικό*: Η απαρίθμηση `EncodeTypes.MicroPdf417` ενημερώνει τη βιβλιοθήκη να χρησιμοποιήσει τη συμπαγή έκδοση του PDF417, η οποία είναι ιδανική για μικρές ετικέτες και κινητές οθόνες.

## Βήμα 3: Πώς να ορίσετε τις διαστάσεις του barcode σε C#

Η λεπτομερής ρύθμιση του πλάτους του μονάδας (διάσταση X) ελέγχει την οπτική πυκνότητα του barcode. Μια μικρότερη τιμή παράγει πιο καθαρή εικόνα, ενώ μια μεγαλύτερη τιμή καθιστά το barcode πιο εύκολο στην σάρωση από απόσταση.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Γιατί πρέπει να ορίσετε διαστάσεις**: Χωρίς να προσαρμόσετε τη διάσταση X, η προεπιλεγμένη τιμή μπορεί να παράγει ένα barcode που φαίνεται θολό όταν αποδίδεται σε υψηλό DPI. Ορίζοντάς το σε 2 pixel είναι μια καλή ισορροπία για τις περισσότερες σάρωσεις μέσω οθόνης.

## Βήμα 4: Επιλογή αριθμού στηλών – έλεγχος του πλάτους του barcode

Το Micro PDF417 επιτρέπει από 1 έως 4 στήλες. Περισσότερες στήλες συμπιέζουν τα δεδομένα οριζόντια, μειώνοντας το συνολικό πλάτος της εικόνας.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Ακραία περίπτωση*: Εάν ζητήσετε 5 στήλες, η βιβλιοθήκη ρίχνει `ArgumentOutOfRangeException`. Πάντα παραμείνετε εντός του τεκμηριωμένου εύρους.

## Βήμα 5: Πώς να δημιουργήσετε PNG barcode – αποθήκευση της εικόνας

Τώρα μπορείτε να εξάγετε το δημιουργημένο barcode σε αρχείο PNG. Το PNG διατηρεί την απώλεια ποιότητας, κάτι που είναι απαραίτητο για αξιόπιστη σάρωση.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Όταν εκτελέσετε το πρόγραμμα, θα δείτε ένα μήνυμα κονσόλας που επιβεβαιώνει τη θέση του αρχείου. Το αποτέλεσμα `MicroPdf417.png` φαίνεται ως εξής:

![Στιγμιότυπο οθόνης που δείχνει ένα δημιουργημένο micro PDF417 barcode με C#](micro-pdf417-example.png "Δημιουργημένο micro PDF417 barcode")

*Κείμενο alt εικόνας*: **micro PDF417 barcode που δημιουργήθηκε σε C#** – δείχνει το τελικό αποτέλεσμα μετά την εφαρμογή των διαστάσεων και των ρυθμίσεων στήλης.

## Βήμα 6: Εκτέλεση και επαλήθευση του αποτελέσματος

1. Δομήστε το έργο: `dotnet build`.
2. Εκτελέστε: `dotnet run`.
3. Ανοίξτε το `MicroPdf417.png` στην επιφάνεια εργασίας σας και σαρώστε το με μια εφαρμογή σάρωσης barcode για κινητά.

Θα πρέπει να δείτε το κείμενο **“Sample text”** να αποκωδικοποιείται. Εάν ο σαρωτής αναφέρει σφάλμα, ελέγξτε ξανά τη διάσταση X και τον αριθμό στηλών — ακραίες τιμές μπορούν να κάνουν το barcode πολύ πυκνό για ορισμένες συσκευές.

## Συχνές παραλλαγές και αντιμετώπιση προβλημάτων

| Situation | Adjustment |
|-----------|------------|
| **Απαιτείται μεγαλύτερο barcode για εκτυπωτές χαμηλής ανάλυσης** | Αυξήστε το `XDimension.Pixels` σε 3 ή 4. |
| **Θέλετε ψηλότερο barcode χωρίς αλλαγή του πλάτους** | Ορίστε το `generator.Parameters.Barcode.Pdf417.Rows` (εύρος γραμμών 3‑90). |
| **Δημιουργία πολλαπλών barcode σε βρόχο** | Ξαναχρησιμοποιήστε το ίδιο στιγμιότυπο `BarcodeGenerator` και αλλάξτε μόνο το `CodeText` πριν από κάθε `Save`. |
| **Αποθήκευση ως JPEG αντί για PNG** | Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg`. |
| **Εκτέλεση σε .NET Framework 4.7** | Ο ίδιος κώδικας λειτουργεί· απλώς αναφέρετε το κατάλληλο `Aspose.BarCode.dll`. |

## Πλήρης λίστα πηγαίου κώδικα (εκτελέσιμος)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Αναμενόμενο αποτέλεσμα** – ένα αρχείο PNG 200 × 100 pixel που περιέχει ένα καθαρό Micro PDF417 barcode που αποκωδικοποιείται σε “Sample text”.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε μικρό PDF417 barcode** σε C#, **ορίσετε τις διαστάσεις του barcode**, και **δημιουργήσετε μια εικόνα barcode PNG**. Το πλήρες παράδειγμα δείχνει κάθε απαιτούμενο βήμα — από την εγκατάσταση της βιβλιοθήκης μέχρι την αποθήκευση του τελικού αρχείου — ώστε να μπορείτε να ενσωματώσετε τη δημιουργία barcode απευθείας στις δικές σας εφαρμογές.

Στη συνέχεια, εξερευνήστε συναφή θέματα όπως **δημιουργία QR codes με Aspose.BarCode**, **προσαρμογή χρωμάτων**, ή **ενσωμάτωση barcode σε έγγραφα PDF**. Κάθε ένα από αυτά βασίζεται στις ίδιες θεμελιώδεις αρχές `BarcodeGenerator` που καλύφθηκαν εδώ.

Μη διστάσετε να πειραματιστείτε με διαφορετικές συμβολοσειρές δεδομένων, αριθμούς στηλών και τιμές X‑dimension ώστε να ταιριάζουν στο συγκεκριμένο περιβάλλον σάρωσής σας. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να δημιουργήσετε PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Πώς να δημιουργήσετε Aztec barcode με Aspose.BarCode για .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}