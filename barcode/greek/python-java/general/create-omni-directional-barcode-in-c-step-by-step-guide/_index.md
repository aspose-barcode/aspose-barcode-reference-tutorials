---
category: general
date: 2026-07-15
description: Δημιουργήστε πολυκατευθυντικό barcode σε C# γρήγορα με το Aspose.BarCode
  – μάθετε πώς να δημιουργείτε barcode σε C# με ρυθμιζόμενο ύψος γραμμής και διάσταση
  X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: el
lastmod: 2026-07-15
og_description: Δημιουργήστε πολυκατευθυντικό barcode σε C# με το Aspose.BarCode.
  Μάθετε πώς να παράγετε barcode σε C# ρυθμίζοντας το XDimension και το BarHeight
  για τέλεια αποτελέσματα.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Δημιουργία πολυκατευθυντικού γραμμωτού κώδικα σε C# – Πλήρης Οδηγός Προγραμματισμού
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Δημιουργία πολυκατευθυντικού γραμμωτού κώδικα σε C# – Οδηγός βήμα‑βήμα
url: /el/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# δημιουργία omni-directional barcode σε C# – Οδηγός βήμα‑βήμα

Έχετε αναρωτηθεί ποτέ πώς να δημιουργήσετε ένα barcode C# που συμμορφώνεται με τη συμβολική GS1 DataBar Omni‑Directional; Δεν είστε μόνοι. Σε αυτό το tutorial θα **δημιουργήσουμε omni-directional barcode** από το μηδέν, θα ρυθμίσουμε τη διάσταση X και θα παίξουμε με το ύψος των γραμμών — όλα χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode.

Θα περάσουμε από ένα πραγματικό σενάριο: χρειάζεστε ένα συμπαγές, υψηλής πυκνότητας barcode για ετικέτα λιανικής, και θέλετε πλήρη έλεγχο του οπτικού μεγέθους του. Στο τέλος θα έχετε δύο αρχεία PNG — ένα με ύψος γραμμής 30 px και ένα με 60 px — έτοιμα να ενσωματωθούν σε οποιαδήποτε ροή εκτύπωσης.

## Απαιτήσεις

- .NET 6 (ή οποιοδήποτε πρόσφατο .NET runtime) εγκατεστημένο στον υπολογιστή σας.  
- Visual Studio 2022 ή VS Code — το αγαπημένο σας IDE αρκεί.  
- Ένα δωρεάν πακέτο NuGet Aspose.BarCode for .NET (`Aspose.BarCode`).

Δεν απαιτούνται άλλες εξαρτήσεις. Αν δεν έχετε χρησιμοποιήσει ποτέ το NuGet, απλώς ανοίξτε το Package Manager Console και εκτελέστε:

```powershell
Install-Package Aspose.BarCode
```

## δημιουργία omni-directional barcode – Κατανόηση των Βασικών

Η **GS1 DataBar Omni‑Directional** συμβολική είναι σχεδιασμένη για σάρωση σε οποιαδήποτε προσανατολισμό, καθιστώντας την ιδανική για ετικέτες άκρων ραφιών. Όταν καλείτε `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, η βιβλιοθήκη κάνει το σκληρό έργο: κωδικοποιεί τα δεδομένα, εφαρμόζει τους κανόνες της συμβολικής και προετοιμάζει μια raster εικόνα.

> **Pro tip:** Πάντα τυλίξτε τα ακατέργαστα δεδομένα στη σωστή μορφή Application Identifier (AI), π.χ. `"(01)12345678901231"` για ένα GTIN‑14. Αυτό ενημερώνει το σαρωτή τι αντιπροσωπεύουν τα ψηφία.

## Βήμα 1 – Ρύθμιση του Barcode Generator (how to generate barcode c#)

Πρώτα δημιουργούμε το αντικείμενο generator. Αυτό είναι το θεμέλιο του **how to generate barcode c#** με Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Η τιμή enum `EncodeTypes.DatabarOmniDirectional` λέει στη μηχανή ποια συμβολική να χρησιμοποιήσει. Το δεύτερο όρισμα είναι η ακατέργαστη συμβολοσειρά δεδομένων, ήδη τυλιγμένη στο GTIN AI.

## Βήμα 2 – Ρύθμιση της Διάστασης X (barcode XDimension)

Η **barcode XDimension** ελέγχει το πλάτος της μικρότερης γραμμής. Μια τιμή 2 px είναι καλή ισορροπία μεταξύ αναγνωσιμότητας και συμπαγούς μεγέθους για τις περισσότερες εκτυπωτές ετικετών.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Αν χρειάζεστε πιο λεπτό ή πιο χοντρό αποτέλεσμα, απλώς αλλάξτε τον αριθμό. Θυμηθείτε: η διάσταση X είναι η βασική μονάδα· όλα τα άλλα πλάτη γραμμών είναι πολλαπλάσια αυτής της τιμής.

## Βήμα 3 – Δημιουργία της Πρώτης Εικόνας με Ύψος Γραμμής 30 px (barcode BarHeight)

Τώρα ορίζουμε το **barcode BarHeight** στα 30 px και αποθηκεύουμε την εικόνα. Αυτό παράγει ένα μέτριο barcode που ταιριάζει άνετα σε μια τυπική ετικέτα.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Η μέθοδος `Save` γράφει ένα αρχείο PNG στο δίσκο. Μπορείτε να αλλάξετε σε `BarCodeImageFormat.Jpeg` αν προτιμάτε έξοδο JPEG.

## Βήμα 4 – Αύξηση του Ύψους Γραμμής σε 60 px για Μεγαλύτερες Ετικέτες (barcode BarHeight)

Μερικές φορές απαιτείται μεγαλύτερο barcode — ίσως για ετικέτα ραφιού που βρίσκεται πιο μακριά από το σαρωτή. Ας διπλασιάσουμε το ύψος.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Παρατηρήστε ότι **δεν** χρειάζεται να δημιουργήσουμε ξανά το generator· απλώς τροποποιούμε την παράμετρο και ξαναχρησιμοποιούμε το ίδιο αντικείμενο. Αυτό εξοικονομεί μνήμη και διατηρεί τον κώδικα καθαρό.

## Βήμα 5 – Αποθήκευση της Δεύτερης Εικόνας (how to generate barcode c#)

Τέλος, αποθηκεύουμε το δεύτερο PNG. Τώρα έχετε δύο αρχεία που διαφέρουν μόνο στο ύψος της γραμμής.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Αναμενόμενο αποτέλεσμα

- `DatabarBarHeight30Pixels.png` – ένα omni‑directional barcode ύψους 30 px.  
- `DatabarBarHeight60Pixels.png` – τα ίδια δεδομένα, αλλά με barcode ύψους 60 px.

Ανοίξτε τα αρχεία σε οποιονδήποτε προβολέα εικόνων· θα δείτε καθαρές, σαρώσιμες γραμμές που τηρούν την προδιαγραφή GS1 DataBar Omni‑Directional.

## Συχνές Ερωτήσεις & Ακραίες Περιπτώσεις

### Τι γίνεται αν χρειαστώ διαφορετική Διάσταση X;

Απλώς ορίστε μια νέα τιμή πριν καλέσετε `Save`. Για εκτύπωση ultra‑high‑density μπορείτε να κατεβάσετε σε 1 px, αλλά δοκιμάστε πρώτα με το σαρωτή σας — ορισμένες συσκευές δυσκολεύονται με γραμμές κάτω από 2 px.

### Μπορώ να προσθέσω κείμενο αναγνώσιμο από άνθρωπο κάτω από το barcode;

Ναι. Ορίστε `barcodeGenerator.Parameters.Barcode.CodeText` σε μια συμβολοσειρά και προαιρετικά ρυθμίστε `barcodeGenerator.Parameters.Barcode.CodeLocation` σε `BarCodeTextLocation.Below`. Αυτό είναι χρήσιμο σε λιανικές περιβάλλοντες όπου πρέπει να φαίνεται ο αριθμητικός GTIN.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Είναι το PNG η καλύτερη μορφή για εκτύπωση;

Το PNG είναι lossless, διατηρώντας τις αιχμηρές άκρες που χρειάζονται οι σαρωτές barcode. Αν το επόμενο σύστημα σας απαιτεί διαφορετική μορφή (TIFF, BMP), απλώς αλλάξτε το enum `BarCodeImageFormat`.

## Πλήρες Παράδειγμα Εφαρμογής (create omni-directional barcode)

Παρακάτω βρίσκεται το πλήρες, έτοιμο‑για‑εκτέλεση πρόγραμμα. Αντιγράψτε‑και‑επικολλήστε το σε ένα νέο κονσολικό project και πατήστε **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Τρέξτε το πρόγραμμα, ελέγξτε το φάκελο εξόδου, και θα δείτε τα δύο αρχεία PNG ακριβώς όπως περιγράφηκαν.

## Περίληψη

Δείξαμε **πώς να δημιουργήσετε barcode C#** κώδικα που δημιουργεί ένα **create omni-directional barcode** χρησιμοποιώντας το Aspose.BarCode. Με την προσαρμογή του **barcode XDimension** και του **barcode BarHeight**, αποκτάτε ακριβή έλεγχο του οπτικού μεγέθους χωρίς να θυσιάζετε την αξιοπιστία σάρωσης.

## Τι Ακολουθεί;

- Πειραματιστείτε με άλλες ρυθμίσεις **GS1 DataBar Omni-Directional** όπως `Color` ή `Margin`.  
- Συνδυάστε πολλαπλά barcodes σε ένα μόνο καμβά χρησιμοποιώντας `Graphics` για σύνθετα σχέδια ετικετών.  
- Ενσωματώστε το generator σε ένα web API ώστε η πλατφόρμα e‑commerce σας να εκδίδει barcodes κατ’ ανάγκη.

Έχετε κάποια ιδέα που θέλετε να μοιραστείτε; Αφήστε ένα σχόλιο και ας συνεχίσουμε τη συζήτηση. Καλό coding!

## Τι Θα Μάθετε Στη Σειρά;

Οι παρακάτω οδηγίες καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [Πώς να Δημιουργήσετε Barcode – Ρύθμιση Code 39 με Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Πώς να Δημιουργήσετε Quiet Zone για Barcode ITF-14 Χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Πώς να δημιουργήσετε quiet zone για Barcode Code 16K χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}