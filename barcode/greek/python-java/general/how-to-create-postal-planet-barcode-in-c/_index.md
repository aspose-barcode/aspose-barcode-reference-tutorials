---
category: general
date: 2026-11-23
description: Δημιουργήστε γραμμωτό κώδικα Postal Planet σε C# με το Aspose.BarCode.
  Μάθετε πώς να δημιουργείτε τον κώδικα Planet, να ορίζετε τη διάσταση X και να αποθηκεύετε
  γεμιστές ή κενές γραμμές.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: el
lastmod: 2026-11-23
og_description: Δημιουργήστε γραμμωτό κώδικα Planet Postal σε C# και μάθετε πώς να
  δημιουργείτε γραμμωτό κώδικα Planet με το Aspose.BarCode. Ακολουθήστε το πλήρες
  παράδειγμα για να παραγάγετε γεμάτες και κενές γραμμές.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Πώς να δημιουργήσετε γραμμωτό κώδικα Postal Planet σε C# – βήμα‑βήμα οδηγός
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Πώς να δημιουργήσετε γραμμωτό κώδικα Postal Planet σε C#
url: /el/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα Postal Planet σε C#

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα postal planet** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς **πώς να δημιουργήσετε planet barcode** χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Θα δείτε πώς να ρυθμίσετε τη διάσταση X, να εναλλάξετε μεταξύ γεμιστών και κενών γραμμών, και να αποθηκεύσετε τις εικόνες σε μορφή PNG.

Η δημιουργία ενός Planet barcode είναι συνηθισμένη για τις ταχυδρομικές υπηρεσίες που απαιτούν σύμβολα υψηλής πυκνότητας, αναγνώσιμα από μηχανές. Στο τέλος αυτού του σεμιναρίου θα έχετε δύο αρχεία PNG — ένα με συμπαγείς γραμμές και ένα με κενές γραμμές — έτοιμα για ενσωμάτωση σε οποιαδήποτε διαδικασία αποστολής αλληλογραφίας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερη έκδοση εγκατεστημένη.
* Visual Studio 2022 (ή οποιονδήποτε επεξεργαστή C#) ρυθμισμένο για ανάπτυξη .NET.
* Ενεργή άδεια NuGet για **Aspose.BarCode for .NET**. Εγκαταστήστε το πακέτο με:

```bash
dotnet add package Aspose.BarCode
```

Δεν απαιτούνται πρόσθετες εξωτερικές υπηρεσίες· η βιβλιοθήκη εκτελεί όλη την κωδικοποίηση τοπικά.

## Βήμα 1 – δημιουργία γραμμωτού κώδικα postal planet

Η πρώτη ενέργεια είναι η δημιουργία ενός `BarcodeGenerator` για τη συμβολική **Planet** και η παροχή των δεδομένων προς κωδικοποίηση. Η συμβολοσειρά δεδομένων πρέπει να είναι αριθμητική και έως 12 ψηφία σύμφωνα με την ταχυδρομική προδιαγραφή.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Η δημιουργία του γεννήτριας διανέμει όλες τις εσωτερικές δομές που απαιτούνται για την απόδοση. Η τιμή `EncodeTypes.Planet` του enum επιλέγει τον σωστό αλγόριθμο κωδικοποίησης για τη μορφή postal.

## Βήμα 2 – ορισμός της διάστασης X για καλύτερη ορατότητα

Η διάσταση X ορίζει το πλάτος ενός μοναδικού μονάδας (το μικρότερο στοιχείο γραμμής). Μια τιμή 4 pixel παρέχει καθαρή οπτική αναπαράσταση χωρίς να αυξάνει το συνολικό μέγεθος της εικόνας.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Η ρύθμιση της διάστασης X είναι απαραίτητη όταν το barcode θα εκτυπωθεί σε μέσο χαμηλής ανάλυσης. Η ίδια ρύθμιση θα επαναχρησιμοποιηθεί για την έκδοση με κενές γραμμές ώστε και οι δύο εικόνες να παραμείνουν συνεπείς.

## Βήμα 3 – αποθήκευση του barcode με γεμιστές γραμμές

Από προεπιλογή ο γεννήτορας αποδίδει **γεμιστές γραμμές** (συμπαγείς μαύρες μονάδες). Η αποθήκευση της εικόνας γίνεται με μία κλήση μεθόδου που γράφει το αρχείο PNG στο δίσκο.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Αντικαταστήστε το `YOUR_DIRECTORY` με την πραγματική διαδρομή όπου θέλετε να αποθηκευτούν τα αρχεία εξόδου. Η απαρίθμηση `BarCodeImageFormat.Png` εγγυάται συμπίεση χωρίς απώλειες, η οποία είναι ιδανική για επεξεργασία σε επόμενα βήματα.

## Βήμα 4 – δημιουργία δεύτερου γεννήτριας Planet barcode για κενές γραμμές

Για να παραχθεί μια έκδοση που χρησιμοποιεί **κενές γραμμές** (λευκές μονάδες πάνω σε μαύρο φόντο), χρειάζεστε ένα δεύτερο αντικείμενο `BarcodeGenerator`. Η επαναχρήση της ίδιας συμβολοσειράς δεδομένων διασφαλίζει ότι και οι δύο εικόνες αντιπροσωπεύουν τον ίδιο ταχυδρομικό κώδικα.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Η δημιουργία ξεχωριστού γεννήτριας απομονώνει την ιδιότητα `FilledBars`, επιτρέποντάς σας να αλλάξετε το οπτικό στυλ χωρίς να επηρεάσετε την πρώτη εικόνα.

## Βήμα 5 – ρύθμιση του γεννήτρια για απόδοση κενών γραμμών

Η σημαία `FilledBars` αλλάζει τη λειτουργία απόδοσης. Ορίζοντάς την σε `false` λέτε στη βιβλιοθήκη να σχεδιάσει τις γραμμές ως κενές (διαφανείς) διατηρώντας το φόντο συμπαγές.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Διατηρώντας την ίδια διάσταση X με τη γεμιστή έκδοση, εξασφαλίζετε ότι και τα δύο αρχεία PNG έχουν τις ίδιες διαστάσεις, κάτι που απλοποιεί τους υπολογισμούς διάταξης σε πρότυπα εκτύπωσης.

## Βήμα 6 – αποθήκευση του barcode που αποδίδει κενές γραμμές

Τέλος, γράψτε την εικόνα με κενές γραμμές στο δίσκο. Η ίδια μορφή PNG χρησιμοποιείται, αλλά μπορείτε να μεταβείτε σε JPEG ή BMP αλλάζοντας την τιμή του `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Σε αυτό το σημείο έχετε δύο αρχεία:

* `PostalPlanetFilledBars.png` – συμπαγείς μαύρες γραμμές.  
* `PostalPlanetEmptyBars.png` – κενές γραμμές πάνω σε μαύρο φόντο.

Και τα δύο ικανοποιούν την ταχυδρομική προδιαγραφή για τη συμβολική Planet.

## Πλήρης κώδικας

Συνδυάζοντας όλα τα βήματα δημιουργείται μια σύντομη εφαρμογή κονσόλας που μπορείτε να εκτελέσετε απευθείας.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Συμπιέστε και τρέξτε το πρόγραμμα:

```bash
dotnet run
```

Η κονσόλα εκτυπώνει *Barcodes generated successfully.* και τα δύο αρχεία PNG εμφανίζονται στον φάκελο του έργου.

## Αναμενόμενη έξοδος

Παρακάτω φαίνεται η οπτική αναπαράσταση της εικόνας με γεμιστές γραμμές. Η αντίστοιχη εικόνα με κενές γραμμές είναι παρόμοια, εκτός από το ότι οι γραμμές είναι διαφανείς.

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*Image alt text:* **Παράδειγμα δημιουργημένου γραμμωτού κώδικα postal planet με γεμιστές γραμμές** (περιέχει τη βασική λέξη‑κλειδί).

Και οι δύο εικόνες είναι προεπιλεγμένα 150 × 150 pixel, αλλά μπορείτε να ελέγξετε το συνολικό μέγεθος με τις παραμέτρους `ImageWidth` και `ImageHeight` εάν απαιτείται διαφορετική ανάλυση.

## Προαιρετικές παραλλαγές

### Αλλαγή μορφής εικόνας

Αν το σύστημα σας προτιμά JPEG, αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg`. Το JPEG εισάγει συμπιεστικά artefacts, οπότε χρησιμοποιήστε το μόνο όταν το μέγεθος αρχείου είναι κρίσιμο.

### Κλιμάκωση του barcode

Μπορείτε να μεγεθύνετε το barcode διατηρώντας το πλάτος της μονάδας, ρυθμίζοντας την ιδιότητα `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Οι υψηλότερες τιμές DPI βελτιώνουν την ποιότητα εκτύπωσης σε laser εκτυπωτές.

### Χρήση προσαρμοσμένου χρώματος φόντου

Το φόντο μπορεί να οριστεί με:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Αυτό είναι χρήσιμο για οπτικές δοκιμές, αλλά θα πρέπει να αποφεύγεται σε παραγωγικές ταχυδρομικές ετικέτες, οι οποίες απαιτούν λευκό φόντο.

## Συχνές ερωτήσεις

**Λειτουργεί αυτό με .NET Core;**  
Ναι. Η βιβλιοθήκη Aspose.BarCode στοχεύει στο .NET Standard 2.0, το οποίο είναι συμβατό με .NET 5, .NET 6 και .NET Core 3.1.

**Τι γίνεται αν η συμβολοσειρά δεδομένων περιέχει μη‑αριθμικούς χαρακτήρες;**  
Τα Planet barcodes δέχονται μόνο αριθμητική είσοδο. Η παροχή γραμμάτων ή συμβόλων προκαλεί `BarcodeException`. Επικυρώστε την είσοδο πριν δημιουργήσετε τον γεννήτορα.

**Μπορώ να δημιουργήσω barcode στη μνήμη χωρίς να το γράψω στο δίσκο;**  
Χρησιμοποιήστε τη μέθοδο `GenerateBarCodeImage` για να λάβετε ένα αντικείμενο `System.Drawing.Image`, το οποίο μπορείτε να μεταφέρετε απευθείας σε απόκριση ή βάση δεδομένων.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε γραμμωτό κώδικα postal planet** σε C# και κατανοείτε **πώς να δημιουργήσετε planet barcode** με στυλ γεμιστών και κενών γραμμών. Ο οδηγός κάλυψε ολόκληρη τη ροή εργασίας — από την αρχικοποίηση του γεννήτρια, τη ρύθμιση της διάστασης X, την εναλλαγή της σημαίας `FilledBars`, μέχρι την αποθήκευση των αρχείων PNG. Πειραματιστείτε με μορφές εικόνας, ρυθμίσεις DPI και χρώματα φόντου για να προσαρμόσετε το barcode στο συγκεκριμένο σύστημα αλληλογραφίας σας.

Για το επόμενο βήμα, εξερευνήστε άλλες ταχυδρομικές συμβολές όπως **POSTNET** ή **Intelligent Mail** χρησιμοποιώντας το ίδιο API της Aspose.BarCode. Η προσαρμογή παραμέτρων όπως `EncodeTypes.Postnet` ακολουθεί το ίδιο μοτίβο που παρουσιάστηκε εδώ, επιτρέποντάς σας να δημιουργήσετε μια ολοκληρωμένη σουίτα δημιουργίας barcode σε μια ενιαία βάση κώδικα.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω σεμινάρια καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}