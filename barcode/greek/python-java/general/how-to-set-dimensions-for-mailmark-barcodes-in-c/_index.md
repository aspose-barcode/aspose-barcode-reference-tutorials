---
category: general
date: 2026-08-22
description: Μάθετε πώς να ορίζετε διαστάσεις για τους κώδικες γραμμής Mailmark σε
  C# και να τους αποθηκεύετε ως εικόνες PNG. Περιλαμβάνει πλήρες κώδικα, εξηγήσεις
  και συμβουλές.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: el
lastmod: 2026-08-22
og_description: Πώς να ορίσετε διαστάσεις για τους κωδικούς Mailmark σε C# και να
  τους εξάγετε ως αρχεία PNG. Ακολουθήστε το πλήρες παράδειγμα και αποφύγετε τα κοινά
  λάθη.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Πώς να ορίσετε διαστάσεις για τους κωδικούς γραμμής Mailmark σε C# – βήμα‑βήμα
  οδηγός
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Πώς να ορίσετε διαστάσεις για τους κωδικούς γραμμής Mailmark σε C#
url: /el/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να ορίσετε διαστάσεις για κωδικούς Mailmark σε C#

Αν χρειάζεστε **πώς να ορίσετε διαστάσεις** για έναν κωδικό Mailmark σε C#, αυτός ο οδηγός δείχνει τα ακριβή βήματα. Θα δείτε πώς να ρυθμίσετε τη διάσταση X και το ύψος των γραμμών, και στη συνέχεια να αποθηκεύσετε τον κωδικό ως εικόνα PNG χωρίς επιπλέον εργαλεία.

Η δημιουργία ταχυδρομικών κωδικών είναι μια συνηθισμένη εργασία όταν αναπτύσσετε λογισμικό ετικετών αλληλογραφίας, αλλά το προεπιλεγμένο μέγεθος συχνά δεν ταιριάζει με τις απαιτήσεις του εκτυπωτή ή της διάταξης. Στο τέλος αυτού του σεμιναρίου θα μπορείτε να ελέγχετε ακριβώς το μέγεθος του κωδικού και να παράγετε δύο έγκυρους τύπους Mailmark (τύπου C και τύπου L) έτοιμους για εκτύπωση.

**Τι θα μάθετε**

* Πώς να ορίσετε τη διάσταση X (πλάτος μονάδας) και το ύψος των γραμμών για ένα `BarcodeGenerator`.
* Πώς να αποθηκεύσετε τον παραγόμενο κωδικό ως αρχείο PNG χρησιμοποιώντας το `BarCodeImageFormat`.
* Συνηθισμένα προβλήματα όπως μη έγκυρες διαδρομές φακέλων ή μη υποστηριζόμενες τιμές διαστάσεων.
* Συμβουλές για την επαναχρησιμοποίηση της ίδιας διαμόρφωσης σε πολλούς κωδικούς.

## Προαπαιτούμενα

* .NET 6.0 ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+).
* Το πακέτο NuGet **Aspose.BarCode for .NET** (ή οποιαδήποτε συμβατή βιβλιοθήκη που παρέχει `BarcodeGenerator`, `EncodeTypes` και `BarCodeImageFormat`).
* Βασική εξοικείωση με τη σύνταξη C# και τη διαχείριση αρχείων.

> **Pro tip:** Εγκαταστήστε το πακέτο με την εντολή CLI  
> `dotnet add package Aspose.BarCode` για να διατηρήσετε το έργο σας οργανωμένο.

## Βήμα 1: Ορίστε τον φάκελο εξόδου

Πριν δημιουργήσετε οποιονδήποτε κωδικό, πρέπει να αποφασίσετε πού θα γραφτούν τα αρχεία PNG. Η χρήση απόλυτης διαδρομής αποφεύγει εκπλήξεις σε διαφορετικούς υπολογιστές.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Γιατί είναι σημαντικό*: Αν ο φάκελος δεν υπάρχει, η μέθοδος `Save` ρίχνει `IOException`. Η κλήση `Directory.CreateDirectory` είναι ιδεοπολιτική — δεν κάνει τίποτα αν ο φάκελος υπάρχει ήδη.

## Βήμα 2: Δημιουργήστε έναν κωδικό Mailmark τύπου C και **ορίστε διαστάσεις**

Ο Mailmark τύπου C κωδικοποιεί μια αλφαριθμητική συμβολοσειρά 20 χαρακτήρων. Αφού αρχικοποιήσετε το γεννήτρια, μπορείτε να **ορίσετε διαστάσεις** μέσω του αντικειμένου `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Γιατί επιλέγονται αυτές οι τιμές;

* **Διάσταση X** ελέγχει το πλάτος της μικρότερης γραμμής (μια “μονάδα”). Μια τιμή `4` εικονοστοιχεία (pixels) παράγει έναν κωδικό που διαβάζεται εύκολα από τις περισσότερες λέιζερ εκτυπώσεις, ενώ το μέγεθος του αρχείου παραμένει μέτριο.
* **BarHeight** καθορίζει το κάθετο μέγεθος των γραμμών. `50` εικονοστοιχεία είναι ένα κοινό ύψος για τυπικές ετικέτες αλληλογραφίας, αλλά μπορείτε να το αυξήσετε για μεγαλύτερες μορφές.

> **Edge case:** Ορισμένοι εκτυπωτές απαιτούν ελάχιστο ύψος γραμμής 30 px. Ορίζοντας ύψος μικρότερο από αυτό που υποστηρίζει ο εκτυπωτής μπορεί να δημιουργήσει αδιάβαστους κωδικούς.

## Βήμα 3: Δημιουργήστε έναν κωδικό Mailmark τύπου L και **ορίστε διαστάσεις**

Ο τύπος L χρησιμοποιεί μεγαλύτερη συμβολοσειρά δεδομένων (μέχρι 30 χαρακτήρες). Η ίδια προσέγγιση ορισμού διαστάσεων ισχύει.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Επαναχρησιμοποίηση διαμόρφωσης

Αν παράγετε πολλούς κωδικούς με τα ίδια διαστάσεις, σκεφτείτε να εξάγετε τη διαμόρφωση σε μια βοηθητική μέθοδο:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Καλώντας `ApplyStandardDimensions(mailmarkC)` και `ApplyStandardDimensions(mailmarkL)` μειώνετε την επανάληψη κώδικα και κάνετε τις μελλοντικές αλλαγές (π.χ. αλλαγή σε μονάδες 5 pixel) μια εντολή.

## Βήμα 4: Επαληθεύστε τα παραγόμενα αρχεία PNG

Αφού τρέξετε το πρόγραμμα, ανοίξτε τα δύο αρχεία PNG σε οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε δύο διαφορετικούς κωδικούς Mailmark, καθένας με 4 px ανά μονάδα και ύψος 50 px.

*Αναμενόμενο αποτέλεσμα*

| Όνομα αρχείου                 | Προσεγγ. διαστάσεις (px) |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × μονάδα × N μονάδες |
| `PostalMailmarkLType.png`     | 4 px × μονάδα × N μονάδες |

Το ακριβές πλάτος εξαρτάται από το μήκος των κωδικοποιημένων δεδομένων, αλλά το ύψος θα είναι πάντα **50 px** επειδή ορίσαμε `BarHeight.Pixels`.

## Συνηθισμένα προβλήματα και πώς να τα αποφύγετε

| Πρόβλημα                              | Συμπτωμα                                            | Διόρθωση |
|---------------------------------------|-----------------------------------------------------|----------|
| Μη έγκυρη διαδρομή φακέλου             | `IOException: Could not find a part of the path`   | Χρησιμοποιήστε `Path.Combine` με `Environment.SpecialFolder` ή ελέγξτε τη συμβολοσειρά διαδρομής. |
| Διάσταση X ορισμένη σε 0 ή αρνητική   | Ο κωδικός εμφανίζεται ως στερεό μπλοκ               | Βεβαιωθείτε ότι `XDimension.Pixels` είναι θετικός ακέραιος (ελάχιστο 1). |
| Μη υποστηριζόμενο `EncodeTypes.Mailmark` | `ArgumentException` κατά τη δημιουργία του γεννήτρια | Επιβεβαιώστε ότι έχετε πρόσφατη έκδοση της βιβλιοθήκης Aspose.BarCode που περιλαμβάνει υποστήριξη Mailmark. |
| Αποθήκευση με λάθος μορφή εικόνας      | Κατεστραμμένο αρχείο PNG                             | Χρησιμοποιήστε `BarCodeImageFormat.Png` (ή `Jpeg` αν χρειάζεστε διαφορετική μορφή). |

## Επέκταση του παραδείγματος

* **Διαφορετικά μεγέθη** – Αλλάξτε `XDimension.Pixels` σε 3 για πιο συμπαγή κωδικό, ή αυξήστε `BarHeight.Pixels` σε 70 για μεγαλύτερες ετικέτες.
* **Παραγωγή σε παρτίδες** – Επαναλάβετε μέσω μιας συλλογής συμβολοσειρών δεδομένων, εφαρμόζοντας τις ίδιες ρυθμίσεις διαστάσεων σε κάθε επανάληψη.
* **Άλλες μορφές εικόνας** – Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg` ή `BarCodeImageFormat.Bmp` αν η ροή εργασίας σας το απαιτεί.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να ορίσετε διαστάσεις** για κωδικούς Mailmark σε C# και να τους εξάγετε ως αρχεία PNG. Με τη ρύθμιση των `XDimension.Pixels` και `BarHeight.Pixels` ελέγχετε το οπτικό μέγεθος τόσο των κωδικών τύπου C όσο και τύπου L, εξασφαλίζοντας ότι πληρούν τις προδιαγραφές του εκτυπωτή και τις απαιτήσεις διάταξης.  

Από εδώ μπορείτε να πειραματιστείτε με διαφορετικές τιμές διαστάσεων, να ενσωματώσετε τον κώδικα σε ένα μεγαλύτερο σύστημα ετικετών αλληλογραφίας, ή να δημιουργήσετε παρτίδες κωδικών για μαζικές αποστολές.

---

*Επόμενα βήματα*: εξερευνήστε τις **διαστάσεις BarcodeGenerator** για QR codes, ή διαβάστε την τεκμηρίωση Aspose.BarCode σχετικά με το **ρύθμιση DPI** για εκτυπώσεις υψηλής ανάλυσης. Αν χρειάζεστε ενσωμάτωση του κωδικού σε PDF, συνδυάστε αυτήν την προσέγγιση με τη βιβλιοθήκη **Aspose.PDF** για μια πλήρη ολοκληρωμένη λύση.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας έργα.

- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)
- [How to Configure Patch Code Barcodes with Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}