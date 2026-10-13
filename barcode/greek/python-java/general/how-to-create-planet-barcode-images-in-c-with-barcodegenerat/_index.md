---
category: general
date: 2026-09-26
description: Μάθετε πώς να δημιουργήσετε κωδικό Planet σε C# γρήγορα. Αυτός ο οδηγός
  καλύπτει γεμιστούς και άδειους κωδικούς Planet, ρυθμίσεις διάστασης X και εξαγωγή
  εικόνας.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: el
lastmod: 2026-09-26
og_description: Δημιουργήστε κώδικα γραμμωτού πλανήτη σε C# με πλήρες παράδειγμα κώδικα.
  Δημιουργήστε τόσο γεμιστά όσο και κενά γραμμωτά πλανήτη, ορίστε το πλάτος της γραμμής
  και αποθηκεύστε ως PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Δημιουργήστε εικόνες barcode πλανήτη σε C# – οδηγός βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να δημιουργήσετε εικόνες barcode πλανήτη σε C# με το BarcodeGenerator
url: /el/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε εικόνες κωδικού Planet σε C# με το BarcodeGenerator

Αν χρειάζεστε **να δημιουργήσετε κωδικούς Planet** σε εικόνες σε μια εφαρμογή .NET, αυτό το tutorial σας δείχνει τα ακριβή βήματα. Θα μάθετε πώς να δημιουργήσετε τόσο έναν γεμάτο όσο και έναν κενό κωδικό Planet, να ρυθμίσετε το πλάτος των γραμμών και να εξάγετε τα αποτελέσματα ως αρχεία PNG—όλα με τη βιβλιοθήκη Aspose.BarCode for .NET.

Η δημιουργία μιας **Planet barcode C#** λύσης είναι απλή μόλις κατανοήσετε τα κύρια **barcode generator parameters**. Στις ενότητες που ακολουθούν, θα περάσουμε από τον πλήρη, εκτελέσιμο κώδικα, θα εξηγήσουμε γιατί κάθε ρύθμιση είναι σημαντική και θα επισημάνουμε κοινά προβλήματα ώστε να τα αποφύγετε από την πρώτη προσπάθεια.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* SDK .NET 6.0 ή νεότερο εγκατεστημένο.
* Visual Studio 2022 (ή οποιοδήποτε IDE C# προτιμάτε).
* Το πακέτο NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) προστέθηκε στο έργο σας.

Μπορείτε να προσθέσετε το πακέτο μέσω του NuGet Package Manager Console:

```bash
dotnet add package Aspose.BarCode
```

## Βήμα 1: Ρύθμιση του BarcodeGenerator

Η κλάση `BarcodeGenerator` είναι το σημείο εισόδου για όλες τις εργασίες δημιουργίας κωδικών. Απαιτεί δύο ορίσματα: τον τύπο κωδικού (`EncodeTypes.Planet`) και τα δεδομένα που θα κωδικοποιηθούν.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Γιατί είναι σημαντικό:* Η δημιουργία του γεννήτρια με `EncodeTypes.Planet` λέει στη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική γραφή **Planet barcode**, η οποία χρησιμοποιείται συνήθως από τις ταχυδρομικές υπηρεσίες σε ορισμένες χώρες. Η συμβολοσειρά `"123456"` είναι το φορτίο που θα εμφανιστεί στον κωδικό.

## Βήμα 2: Διαμόρφωση της διάστασης X (πλάτος γραμμής)

Η διάσταση X ελέγχει το φυσικό πλάτος κάθε γραμμής. Μια τυπική τιμή για απόδοση στην οθόνη είναι 4 pixel, αλλά μπορείτε να την προσαρμόσετε ώστε να καλύπτει τις απαιτήσεις εκτύπωσης.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Γιατί είναι σημαντικό:* Ορίζοντας `XDimension.Pixels` διασφαλίζετε ότι ο παραγόμενος κωδικός δεν είναι ούτε πολύ λεπτός (προκαλώντας αποτυχίες σάρωσης) ούτε πολύ παχύς (σπαταλώντας χώρο). Η ίδια ρύθμιση θα επαναχρησιμοποιηθεί για τον κενό κωδικό.

## Βήμα 3: Αποθήκευση του γεμισμένου Planet barcode

Εξάγετε τον κωδικό σε αρχείο PNG χρησιμοποιώντας τη μέθοδο `Save`. Το enum `BarCodeImageFormat.Png` λέει στη βιβλιοθήκη να παράγει μια απώλεια‑απώλειας εικόνα κατάλληλη για περαιτέρω επεξεργασία.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Μετά την εκτέλεση του προγράμματος, θα βρείτε το `PostalPlanetFilledBars.png` στον φάκελο εξόδου. Ανοίξτε το για να επαληθεύσετε ότι οι γραμμές είναι συμπαγείς (γεμισμένες).

## Βήμα 4: Δημιουργία γεννήτριας για κενό Planet barcode

Ένας **κενός κωδικός Planet** εμφανίζει τα ίδια δεδομένα αλλά με μη γεμιστές (λευκές) γραμμές. Αυτό είναι χρήσιμο για οπτικά σχέδια που τοποθετούν τον κωδικό πάνω σε χρωματιστά φόντα.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Η κλήση του κατασκευαστή είναι πανομοιότυπη με την έκδοση γεμισμένης εικόνας· η διαφορά βρίσκεται στην παράμετρο που θα αλλάξουμε στη συνέχεια.

## Βήμα 5: Επαναχρησιμοποίηση της ίδιας διάστασης X

Για να διατηρηθεί το οπτικό μέγεθος συνεπές, εφαρμόστε το ίδιο πλάτος γραμμής στον κενό κωδικό.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Η επαναχρησιμοποίηση των **barcode generator parameters** εγγυάται ότι και οι δύο εικόνες ευθυγραμμίζονται τέλεια όταν τοποθετηθούν δίπλα‑δίπλα.

## Βήμα 6: Εναλλαγή σε μη γεμιστές γραμμές

Η σημαία `FilledBars` καθορίζει αν οι γραμμές αποδίδονται ως συμπαγές μαύρο (προεπιλογή) ή διαφανές λευκό.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Γιατί είναι σημαντικό:* Ορίζοντας `FilledBars = false` αλλάζει τη λειτουργία απόδοσης, που αποτελεί το κλειδί διάκρισης μεταξύ γεμισμένου και κενού Planet barcode.

## Βήμα 7: Αποθήκευση του κενού Planet barcode

Τέλος, εξάγετε την κενή έκδοση σε PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Όταν εκτελέσετε το πρόγραμμα, εμφανίζονται δύο αρχεία:

* `PostalPlanetFilledBars.png` – συμπαγείς μαύρες γραμμές.
* `PostalPlanetEmptyBars.png` – διαφανείς (μη γεμιστές) γραμμές.

Και οι δύο εικόνες περιέχουν τα ίδια δεδομένα (`123456`) και μοιράζονται την ίδια διάσταση X, καθιστώντας τες εναλλάξιμες στις περισσότερες περιπτώσεις UI.

## Πλήρες, εκτελέσιμο παράδειγμα

Συνδυάζοντας τα πάντα, εδώ είναι το πλήρες αρχείο πηγαίου κώδικα που μπορείτε να αντιγράψετε‑και‑επικολλήσετε σε ένα νέο έργο κονσόλας:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Αναμενόμενη έξοδος**

Η εκτέλεση του προγράμματος δημιουργεί δύο αρχεία PNG στον τρέχοντα φάκελο εργασίας του εκτελέσιμου. Ανοίξτε τα με οποιονδήποτε προβολέα εικόνων:

* **Γεμισμένη έκδοση** – σκοτεινές, συμπαγείς γραμμές που διαβάζονται εύκολα από τυπικούς σαρωτές.
* **Κενή έκδοση** – οι γραμμές εμφανίζονται ως λευκά κενά πάνω σε μαύρο φόντο, χρήσιμες για εφέ επικάλυψης.

## Συχνά προβλήματα και επαγγελματικές συμβουλές

| Πρόβλημα | Γιατί συμβαίνει | Πώς να το διορθώσετε |
|----------|----------------|----------------------|
| Οι γραμμές φαίνονται πολύ λεπτές | Η διάσταση X έμεινε στην προεπιλογή (1 pixel) | Ορίστε `XDimension.Pixels` σε 3‑5 pixels για χρήση στην οθόνη· αυξήστε για εκτυπώσεις υψηλής ανάλυσης. |
| Ο κενός κωδικός εμφανίζεται εντελώς μαύρος | `FilledBars` δεν έχει οριστεί σε `false` | Βεβαιωθείτε ότι η εντολή `emptyPlanet.Parameters.Barcode.FilledBars = false;` εκτελείται **μετά** τον ορισμό της διάστασης X. |
| Το αρχείο PNG λείπει | Η διαδρομή εξόδου είναι λανθασμένη ή ο φάκελος δεν υπάρχει | Παρέχετε πλήρη διαδρομή (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) ή δημιουργήστε τον φάκελο εκ των προτέρων με `Directory.CreateDirectory`. |
| Ο κωδικός δεν διαβάζεται | Η συμβολοσειρά δεδομένων περιέχει μη επιτρεπτούς χαρακτήρες για τη συμβολική γραφή Planet | Οι κωδικοί Planet δέχονται μόνο αριθμητικά φορτία· επικυρώστε την είσοδο με `int.TryParse`. |

**Επαγγελματική συμβουλή:** Αν χρειάζεται να ενσωματώσετε τον κωδικό σε PDF, μπορείτε να φορτώσετε το παραγόμενο PNG σε ένα `PdfDocument` χρησιμοποιώντας το Aspose.PDF, ή να προσθέσετε απευθείας τον κωδικό ως ροή εικόνας χωρίς εγγραφή στο δίσκο.

## Επόμενα βήματα

Τώρα που μπορείτε να **δημιουργήσετε κωδικούς Planet** σε εικόνες, εξετάστε τα παρακάτω συναφή θέματα:

* **Planet barcode C#** – προσαρμογή χρωμάτων, προσθήκη κειμένου αναγνώσιμου από άνθρωπο ή ενσωμάτωση του κωδικού σε PDF.
* **Barcode generator parameters** – ρύθμιση επιπέδου διόρθωσης σφαλμάτων, ζώνης ησυχίας ή περιστροφής.
* **Batch generation** – βρόχος πάνω σε λίστα ταχυδρομικών κωδικών για δημιουργία αρχείου zip με PNG.
* **Alternative formats** – εξαγωγή σε SVG ή JPEG για φιλική στο web διανομή.

Πειραματιστείτε με διαφορετικές τιμές `XDimension` και τη σημαία `FilledBars` για να δείτε πώς επηρεάζουν την αξιοπιστία σάρωσης και το οπτικό στυλ. Όταν είστε έτοιμοι, ενσωματώστε τον κώδικα δημιουργίας στην web API ή στην επιφάνεια εργασίας σας για αυτοματοποιημένη δημιουργία ταχυδρομικών κωδικών εν κινήσει.

---


## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία κωδικού Planet σε C# – Πλήρης Οδηγός Βήμα‑βήμα](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Γεννήτρια κωδικού C# – δημιουργία κωδικού Planet και παράδειγμα RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Δημιουργία Ταχυδρομικού Κωδικού σε C# – Πλήρης Οδηγός με κωδικό Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}