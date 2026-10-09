---
category: general
date: 2026-09-29
description: Δημιουργήστε κωδικό planet barcode σε C# με γεμιστές και κενές γραμμές
  – βήμα‑βήμα οδηγός χρησιμοποιώντας το Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: el
lastmod: 2026-09-29
og_description: Δημιουργήστε γρήγορα barcode πλανήτη σε C#. Μάθετε πώς να αποδίδετε
  γεμιστές γραμμές, να εναλλάσσετε σε κενές γραμμές και να ρυθμίσετε τη διάσταση X
  με το Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Δημιουργήστε κώδικα γραμμωτού πλανήτη με γεμιστές και κενές γραμμές – οδηγός
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Πώς να δημιουργήσετε barcode πλανήτη με γεμιστές και κενές γραμμές
url: /el/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε κώδικα Planet με γεμιστές και κενές γραμμές

Αν χρειάζεστε **να δημιουργήσετε εικόνες κώδικα planet** σε C#, αυτός ο οδηγός σας δείχνει ακριβώς πώς να δημιουργήσετε τόσο τις εκδόσεις με γεμιστές γραμμές όσο και τις εκδόσεις με κενές γραμμές. Θα δείτε πώς να ορίσετε το πλάτος της γραμμής (X‑dimension), να εναλλάξετε την ιδιότητα `FilledBars` και να αποθηκεύσετε τα αποτελέσματα ως αρχεία PNG—όλα με τη βιβλιοθήκη Aspose.Barcode.

Η δημιουργία ταχυδρομικών barcode είναι συχνή απαίτηση για συστήματα αποστολών, εφαρμογές λιστών αλληλογραφίας και πίνακες ελέγχου λογιστικής. Στο τέλος αυτού του tutorial θα έχετε δύο έτοιμα αρχεία PNG που μπορείτε να ενσωματώσετε σε αναφορές, email ή εκτυπώσεις.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

| Απαίτηση | Γιατί είναι σημαντικό |
|-------------|----------------|
| .NET 6.0 ή νεότερο | Παρέχει το runtime για το παράδειγμα C#. |
| Visual Studio 2022 (ή οποιοδήποτε IDE C#) | Σας επιτρέπει να μεταγλωττίσετε και να εκτελέσετε τον κώδικα. |
| **Aspose.Barcode for .NET** πακέτο NuGet | Παρέχει την κλάση `BarcodeGenerator` και το `EncodeTypes.Planet`. Εγκαταστήστε το με `dotnet add package Aspose.Barcode`. |
| Δικαίωμα εγγραφής σε φάκελο στο δίσκο | Η μέθοδος `Save` γράφει αρχεία PNG στη διαδρομή που καθορίζετε. |

## Βήμα 1: Ρύθμιση του έργου και εισαγωγή namespaces

Δημιουργήστε ένα νέο console project (ή προσθέστε τον κώδικα σε υπάρχον) και αναφέρετε το namespace Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Αυτές οι οδηγίες `using` σας δίνουν πρόσβαση στην κλάση `BarcodeGenerator`, στα `EncodeTypes` και στα enums μορφής εικόνας που απαιτούνται για το tutorial.

## Βήμα 2: Δημιουργία Planet barcode με προεπιλεγμένες (γεμιστές) γραμμές

Το πρώτο barcode χρησιμοποιεί την προεπιλεγμένη απόδοση της βιβλιοθήκης, η οποία γεμίζει τις γραμμές.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Γιατί λειτουργεί:**  
`EncodeTypes.Planet` λέει στο Aspose.Barcode να χρησιμοποιήσει τη **συμβολική Planet**, η οποία είναι ένας ταχυδρομικός κώδικας που χρησιμοποιεί η United States Postal Service. Η ιδιότητα `XDimension` ελέγχει το πλάτος κάθε γραμμής· ορίζοντάς το σε 4 pixels παράγει ένα barcode που εκτυπώνεται καλά σε τυπικούς εκτυπωτές ετικετών. Από προεπιλογή, το `FilledBars` είναι `true`, οπότε οι γραμμές εμφανίζονται στερεές.

## Βήμα 3: Δημιουργία Planet barcode με κενές γραμμές

Για να δημιουργήσετε τα ίδια δεδομένα με *κενές* γραμμές, αρκεί να αλλάξετε τη σημαία `FilledBars` διατηρώντας τις υπόλοιπες ρυθμίσεις ίδιες.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Γιατί είναι σημαντικό:**  
Ορισμένα συστήματα αλληλογραφίας απαιτούν το στυλ **empty‑bars** για να βελτιώσουν την αναγνωσιμότητα όταν το barcode εκτυπώνεται σε σκούρο φόντο ή όταν χρησιμοποιείται αντίθετο χρωματικό σχήμα. Ορίζοντας `FilledBars = false`, ο δημιουργός σχεδιάζει μόνο τα περιγράμματα των γραμμών, αφήνοντας το εσωτερικό διαφανές.

## Αναμενόμενο αποτέλεσμα

Μετά την εκτέλεση του προγράμματος, ο φάκελος `C:\Barcodes` (ή η διαδρομή που επιλέξατε) περιέχει δύο αρχεία PNG:

| Αρχείο | Οπτική περιγραφή |
|------|---------------------|
| `PlanetFilledBars.png` | Οι γραμμές είναι στερεά μαύρα ορθογώνια σε λευκό φόντο. |
| `PlanetEmptyBars.png`  | Οι γραμμές είναι μαύρα περιγράμματα· το εσωτερικό κάθε γραμμής είναι διαφανές (εμφανίζει το φόντο). |

Και οι δύο εικόνες κωδικοποιούν το ίδιο αριθμητικό string `"123456"` και μοιράζονται πλάτος γραμμής 4 pixels, εξασφαλίζοντας ομοιομορφία εκτός από το στυλ γεμίσματος.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

### Αλλαγή του πλάτους της γραμμής

Αν ο εκτυπωτής ετικετών σας απαιτεί διαφορετικό πλάτος γραμμής, τροποποιήστε την τιμή `XDimension.Pixels`. Για εκτυπωτές υψηλής ανάλυσης, μια τιμή **2** ή **3** pixels μπορεί να είναι προτιμότερη· για εκτυπωτές χαμηλής ανάλυσης, **5** ή **6** pixels μπορούν να βελτιώσουν την αξιοπιστία σάρωσης.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Χρήση διαφορετικής μορφής εικόνας

Το Aspose.Barcode υποστηρίζει PNG, JPEG, BMP, GIF και TIFF. Αντικαταστήστε το `BarCodeImageFormat.Png` με άλλη τιμή enum για να ταιριάζει στη ροή εργασίας σας.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Δημιουργία πολλαπλών barcode σε βρόχο

Όταν χρειάζεστε μια παρτίδα Planet barcode (π.χ., για λίστα αλληλογραφίας), τυλίξτε τη λογική του δημιουργού σε βρόχο `foreach` και αλλάξτε το string δεδομένων σε κάθε επανάληψη.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Διαχείριση μη έγκυρης εισόδου

Η συμβολική Planet δέχεται μόνο αριθμητικά strings **5‑8** ψηφίων. Η παροχή μη έγκυρης τιμής προκαλεί `ArgumentException`. Προστατέψτε το με μια απλή μέθοδο επικύρωσης.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Pro tip: Επαλήθευση του barcode με εξομοιωτή σαρωτή

Το Aspose.Barcode περιλαμβάνει την κλάση `BarcodeReader` που μπορείτε να χρησιμοποιήσετε για να επιβεβαιώσετε ότι η παραγόμενη εικόνα αποκωδικοποιείται ξανά στα αρχικά δεδομένα.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Αν η έξοδος εμφανίζει `"123456"` και για τα δύο αρχεία, το barcode δημιουργήθηκε σωστά.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε εικόνες planet barcode** σε C# με στυλ γεμιστών και κενών γραμμών, να ελέγξετε το **Planet barcode XDimension** και να αποθηκεύσετε τα αποτελέσματα σε μορφή PNG χρησιμοποιώντας τη βιβλιοθήκη **Aspose.Barcode**. Ρυθμίστε το πλάτος της γραμμής, αλλάξτε τη μορφή εικόνας ή επαναλάβετε τη διαδικασία για μια συλλογή τιμών ώστε να ταιριάζει σε οποιοδήποτε workflow κωδικοποίησης ταχυδρομικών κωδίκων.

Επόμενα βήματα που μπορείτε να εξερευνήσετε:

* **Προσθήκη κειμένου αναγνώσιμου από άνθρωπο** κάτω από το barcode (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Ενσωμάτωση barcode σε έγγραφα PDF** με Aspose.PDF.
* **Δημιουργία άλλων ταχυδρομικών συμβολισμών** όπως **USPS POSTNET** ή **Intelligent Mail**.

Νιώστε ελεύθεροι να πειραματιστείτε με τις παραμέτρους και να ενσωματώσετε τον κώδικα στο σύστημα αποστολών ή αλληλογραφίας σας. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας projects.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}