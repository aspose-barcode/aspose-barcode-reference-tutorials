---
category: general
date: 2026-11-14
description: Δημιουργία μικρο‑PDF417 barcode σε C# με το Aspose.BarCode – βήμα‑βήμα
  οδηγός που καλύπτει τη ρύθμιση του δημιουργού, τη διάσταση X, τις στήλες και την
  εξαγωγή σε PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: el
lastmod: 2026-11-14
og_description: Δημιουργήστε μικρο‑κώδικα PDF417 σε C# χρησιμοποιώντας το Aspose.BarCode.
  Μάθετε πώς να ρυθμίσετε τον δημιουργό, να ορίσετε το XDimension, να επιλέξετε στήλες
  και να εξάγετε ως PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Δημιουργία μικρο‑PDF417 barcode σε C# – πλήρης οδηγός προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Πώς να δημιουργήσετε μικρο‑κώδικα PDF417 σε C#
url: /el/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε μικρο‑PDF417 barcode σε C#  

Αν χρειάζεστε να **δημιουργήσετε μικρο‑PDF417 barcode** γρήγορα, αυτός ο οδηγός σας δείχνει μια πλήρη, έτοιμη‑για‑εκτέλεση λύση. Θα δείτε πώς να δημιουργήσετε το γεννήτρια barcode, να ρυθμίσετε τη διάσταση X, να επιλέξετε τον αριθμό των στηλών και τελικά να αποθηκεύσετε το αποτέλεσμα ως εικόνα PNG—όλα χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode για .NET.

Η δημιουργία ενός μικρο‑PDF417 barcode δεν απαιτεί πολύπλοκο pipeline κατασκευής. Στο τέλος αυτού του tutorial θα έχετε ένα μόνο αρχείο C# που παράγει μια εικόνα barcode υψηλής ποιότητας που μπορείτε να ενσωματώσετε σε αναφορές, ετικέτες ή κινητές εφαρμογές.

## Προαπαιτούμενα  

* .NET 6.0 SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+).  
* Περιβάλλον ανάπτυξης όπως Visual Studio 2022, VS Code ή Rider.  
* Άδεια Aspose.BarCode για .NET (ή δωρεάν κλειδί αξιολόγησης). Μπορείτε να την αποκτήσετε από την [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Pro tip:** Αν χρησιμοποιείτε την έκδοση αξιολόγησης, το παραγόμενο PNG θα περιέχει ένα μικρό υδατογράφημα “Evaluation”. Μια αδειοδοτημένη έκδοση το αφαιρεί αυτόματα.

## Βήμα 1: Ρύθμιση του έργου  

Δημιουργήστε ένα νέο console project και προσθέστε το πακέτο NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Η εντολή `dotnet add package` κατεβάζει τις εξαρτήσεις του **Aspose.BarCode C# example**, ώστε να μην χρειάζεται να διαχειρίζεστε τα DLL χειροκίνητα.

## Βήμα 2: Γράψτε τον πλήρη κώδικα  

Αντικαταστήστε το αυτό‑δημιουργημένο `Program.cs` με τον παρακάτω κώδικα. Δείχνει πώς να **δημιουργήσετε μικρο‑pdf417 barcode** από την αρχή μέχρι το τέλος.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Γιατί κάθε γραμμή είναι σημαντική  

* **BarcodeGenerator constructor** – Δημιουργεί το **micro pdf417 barcode generator** με το κείμενο που θέλετε να κωδικοποιήσετε.  
* **XDimension.Pixels** – Ελέγχει το πλάτος του μονάδας· ορίζοντας το σε `2` pixels παράγει ένα πυκνό, υψηλής ανάλυσης barcode κατάλληλο για τους περισσότερους σαρωτές.  
* **Pdf417.Columns** – Το MicroPDF417 υποστηρίζει μόνο 1‑4 στήλες. Επιλέγοντας `4` μειώνει το ύψος του barcode, κάτι χρήσιμο όταν έχετε περιορισμένο κάθετο χώρο.  
* **Save method** – Αποθηκεύει το barcode σε αρχείο PNG. Το PNG είναι lossless, εξασφαλίζοντας ότι ο σαρωτής διαβάζει ακριβώς το μοτίβο που δημιουργήθηκε.

## Βήμα 3: Κατασκευή και εκτέλεση  

Συγκεντρώστε και εκτελέστε το πρόγραμμα:

```bash
dotnet run
```

Θα πρέπει να δείτε την έξοδο της κονσόλας:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Ένα αρχείο με όνομα **MicroPdf417.png** εμφανίζεται στον φάκελο του έργου. Ανοίξτε το με οποιονδήποτε προβολέα εικόνων· θα δείτε ένα καθαρό μικρο‑PDF417 barcode που κωδικοποιεί τη συμβολοσειρά `"Åspóse.Barcóde©"`.

![Δημιουργημένο παράδειγμα μικρο‑PDF417 barcode](MicroPdf417.png "Δημιουργημένο παράδειγμα μικρο‑PDF417 barcode"){.center-image width=400 alt="Δημιουργημένη εικόνα παραδείγματος μικρο‑PDF417 barcode"}

*Η παραπάνω εικόνα είναι το αποτέλεσμα του κώδικα που φαίνεται στο Βήμα 2.*

## Βήμα 4: Συνηθισμένες παραλλαγές και περιπτώσεις άκρων  

| Κατάσταση | Πώς να προσαρμόσετε τον κώδικα |
|-----------|------------------------------|
| **Διαφορετικό μήκος δεδομένων** | Το MicroPDF417 μπορεί να κωδικοποιήσει έως 1 200 χαρακτήρες. Απλώς αλλάξτε το δεύτερο όρισμα του `BarcodeGenerator`. |
| **Υψηλότερη ανάλυση** | Αυξήστε το `XDimension.Pixels` σε `3` ή `4`. Μεγαλύτερες μονάδες βελτιώνουν την αναγνωσιμότητα σε σαρωτές χαμηλής ανάλυσης, αλλά αυξάνουν το μέγεθος της εικόνας. |
| **Προσαρμοσμένα χρώματα** | Μετά τη δημιουργία του generator, ορίστε `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` και `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Αποθήκευση σε άλλες μορφές** | Αντικαταστήστε το `BarCodeImageFormat.Png` με `Jpeg`, `Bmp` ή `Gif` ανάλογα με τις απαιτήσεις σας. |
| **Ενσωμάτωση σε PDF** | Χρησιμοποιήστε `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` και στη συνέχεια συγχωνεύστε το PDF με άλλα έγγραφα χρησιμοποιώντας Aspose.PDF. |

> **Watch out for:** Ορίζοντας το `XDimension.Pixels` κάτω από `1` προκαλεί `ArgumentOutOfRangeException`. Διατηρείτε πάντα την τιμή του τουλάχιστον `1`.

## Βήμα 5: Επαλήθευση του barcode  

1. Ανοίξτε το PNG σε έναν προβολέα εικόνων.  
2. Χρησιμοποιήστε οποιαδήποτε εφαρμογή σάρωσης barcode σε smartphone που υποστηρίζει PDF417 (οι περισσότερες εφαρμογές “σάρωσης QR‑code” το περιλαμβάνουν).  
3. Σαρώστε την εικόνα· η εφαρμογή θα πρέπει να εμφανίσει το αρχικό κείμενο `"Åspóse.Barcóde©"`.

Αν η σάρωση αποτύχει, ελέγξτε ξανά τις ρυθμίσεις **X‑dimension** και **column** – ένα πολύ μικρό πλάτος μονάδας ή ένας μη υποστηριζόμενος αριθμός στηλών μπορεί να κάνουν το μοτίβο μη αναγνώσιμο.

## Συμπέρασμα  

Τώρα ξέρετε πώς να **δημιουργήσετε μικρο‑pdf417 barcode** σε C# χρησιμοποιώντας το Aspose.BarCode. Το tutorial κάλυψε:

* Δημιουργία ενός **micro pdf417 barcode generator**.  
* **Ορισμός XDimension pixels** για έλεγχο του πλάτους της μονάδας.  
* **Ορισμός στηλών barcode** για προσαρμογή του σχήματος.  
* **Αποθήκευση barcode ως PNG** για lossless έξοδο εικόνας.  

Από εδώ μπορείτε να εξερευνήσετε πρόσθετες δυνατότητες όπως προσαρμογή χρωμάτων, ενσωμάτωση του barcode σε PDF ή δημιουργία barcode σε πραγματικό χρόνο σε ASP.NET Core web APIs. Καλό coding!

## Τι πρέπει να μάθετε μετά;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία barcode PNG σε C# – πλήρης οδηγός για GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Πώς να δημιουργήσετε macro PDF417 barcode σε C# χρησιμοποιώντας Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Δημιουργία PDF417 barcode σε C# χρησιμοποιώντας Aspose.BarCode – βήμα‑βήμα οδηγός](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}