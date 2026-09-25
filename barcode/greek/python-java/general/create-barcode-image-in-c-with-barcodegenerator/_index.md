---
category: general
date: 2026-08-12
description: Δημιουργήστε εικόνα barcode σε C# χρησιμοποιώντας το BarCodeGenerator.
  Μάθετε πώς να δημιουργείτε DataBar, να ελέγχετε το μέγεθος της εικόνας barcode και
  να δημιουργείτε πολλαπλά barcode αποδοτικά.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: el
lastmod: 2026-08-12
og_description: Δημιουργήστε εικόνα barcode σε C# με το BarCodeGenerator. Αυτό το
  σεμινάριο δείχνει βήμα‑βήμα πώς να δημιουργήσετε κώδικες DataBar, να προσαρμόσετε
  το μέγεθος της εικόνας barcode και να παράγετε πολλαπλά barcodes.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Δημιουργία εικόνας barcode σε C# – πλήρης οδηγός BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Δημιουργία εικόνας barcode σε C# με BarCodeGenerator
url: /el/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εικόνας barcode σε C# με BarCodeGenerator

Αν χρειάζεστε **να δημιουργήσετε εικόνα barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε με την κλάση `BarCodeGenerator`. Είτε δημιουργείτε ένα σύστημα POS λιανικής είτε ένα εργαλείο παρακολούθησης αποθεμάτων, θα μάθετε να δημιουργείτε σύμβολα DataBar, να ελέγχετε το μέγεθος της εικόνας barcode και να παράγετε πολλαπλά barcodes σε μία εκτέλεση.

Θα ανακαλύψετε επίσης πώς το API **barcode generator c#** σας επιτρέπει να ρυθμίζετε διαστάσεις, να αλλάζετε μορφές εξόδου και να αντιμετωπίζετε ειδικές περιπτώσεις όπως μη έγκυρες συμβολοσειρές δεδομένων. Στο τέλος του οδηγού μπορείτε με σιγουριά **να δημιουργήσετε πολλαπλά barcodes** χωρίς να γράφετε επαναλαμβανόμενο κώδικα.

## Προαπαιτούμενα

- .NET 6.0 ή νεότερο εγκατεστημένο  
- Περιβάλλον ανάπτυξης (Visual Studio, Rider ή VS Code)  
- Το πακέτο NuGet Aspose.BarCode for .NET (ή οποιαδήποτε συμβατή βιβλιοθήκη που παρέχει `BarCodeGenerator`)  

Μπορείτε να προσθέσετε το πακέτο με:

```bash
dotnet add package Aspose.BarCode
```

## Τι καλύπτει αυτός ο οδηγός

1. Ρύθμιση μιας **barcode generator c#** εμφάνισης για κωδικοποίηση DataBar Omni‑directional.  
2. Προσαρμογή **μεγέθους εικόνας barcode** με αλλαγή του X‑dimension και του ύψους των γραμμών.  
3. Χρήση βρόχου για **δημιουργία πολλαπλών barcode** με διαφορετικά ύψη.  
4. Αποθήκευση των εικόνων ως αρχεία PNG και επαλήθευση του αποτελέσματος.  

Όλα τα αποσπάσματα κώδικα είναι πλήρη και έτοιμα για αντιγραφή‑επικόλληση σε ένα νέο έργο console.

![Παράδειγμα δημιουργίας εικόνας barcode](barcode-example.png){alt="Παράδειγμα δημιουργίας εικόνας barcode"}

## Βήμα 1: Αρχικοποίηση του γεννήτρια – βασικά δημιουργίας εικόνας barcode

Το πρώτο βήμα είναι η δημιουργία ενός αντικειμένου `BarCodeGenerator` με τη ζητούμενη συμβολική. Για ένα σύμβολο DataBar Omni‑directional χρησιμοποιείτε το `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Γιατί είναι σημαντικό:** Η δημιουργία του γεννήτρια ορίζει τους κανόνες κωδικοποίησης και το φορτίο δεδομένων. Αν παραλείψετε τη σωστή τιμή `EncodeTypes`, η βιβλιοθήκη θα παράγει ένα μη υποστηριζόμενο barcode ή θα ρίξει εξαίρεση.

## Βήμα 2: Διαμόρφωση X‑dimension και ύψους γραμμής – έλεγχος μεγέθους εικόνας barcode

Το οπτικό μέγεθος ενός barcode καθορίζεται από δύο παραμέτρους:

| Παράμετρος | Τι ελέγχει | Τυπικό εύρος |
|------------|------------|--------------|
| `x_dimension.pixels` | Πλάτος της μικρότερης μονάδας (το “σημείο”) | 1 – 4 px |
| `bar_height.pixels`  | Ύψος των κάθετων γραμμών                | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Συμβουλή:** Μικρότερο X‑dimension δίνει εικόνα υψηλότερης ανάλυσης αλλά μπορεί να είναι πιο δύσκολο να σαρωθεί με εκτυπωτές χαμηλής ποιότητας. Ρυθμίστε την τιμή ανάλογα με τον εξοπλισμό σάρωσης που στοχεύετε.

## Βήμα 3: Αποθήκευση του πρώτου barcode – δημιουργία εικόνας barcode για ύψος 30 px

Τώρα μπορείτε να δημιουργήσετε την εικόνα και να την γράψετε στο δίσκο. Η μέθοδος `Save` δέχεται διαδρομή αρχείου και έναν enum μορφής εικόνας.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Αναμενόμενο αποτέλεσμα:** Ένα αρχείο PNG με όνομα `Databar30.png` εμφανίζεται στο `C:\Barcodes`. Το άνοιγμα του αρχείου δείχνει ένα σύμβολο DataBar Omni‑directional με καθαρό, υψηλής αντίθεσης μοτίβο.

## Βήμα 4: Αλλαγή του ύψους και δημιουργία επιπλέον εικόνων – δημιουργία πολλαπλών barcode

Για **να δημιουργήσετε πολλαπλά barcode** με διαφορετικές διαστάσεις, χρειάζεται μόνο να τροποποιήσετε την ιδιότητα `BarHeight` και να καλέσετε ξανά το `Save`. Αυτό αποφεύγει την επανεκκίνηση του γεννήτρια, εξοικονομώντας μνήμη και χρόνο CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Γιατί λειτουργεί:** Το αντικείμενο `BarCodeGenerator` διατηρεί όλη την κατάσταση διαμόρφωσης. Η αλλαγή μιας μόνο ιδιότητας ενημερώνει τη μηχανή απόδοσης για την επόμενη κλήση `Save`, επιτρέποντάς σας να **δημιουργήσετε πολλαπλά barcode** αποδοτικά.

## Βήμα 5: Προχωρημένα – πώς να δημιουργήσετε DataBar με προσαρμοσμένα δεδομένα

Το παραπάνω παράδειγμα χρησιμοποιεί ένα στατικό φορτίο GS1. Σε πραγματικές συνθήκες συχνά χρειάζεται να ενσωματώσετε μεταβλητούς αναγνωριστικούς προϊόντων. Η βιβλιοθήκη δέχεται οποιαδήποτε συμβολοσειρά που ταιριάζει με την προδιαγραφή DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Κύριο σημείο:** Η ρύθμιση του `generator.CodeText` ενημερώνει τα κωδικοποιημένα δεδομένα χωρίς επαναδημιουργία του αντικειμένου. Αυτό είναι το προτεινόμενο **πώς να δημιουργήσετε databar** όταν διαχειρίζεστε μεγάλα σύνολα δεδομένων.

## Βήμα 6: Επαλήθευση και αντιμετώπιση προβλημάτων – διασφάλιση σωστού μεγέθους εικόνας barcode

Μετά τη δημιουργία των εικόνων, μπορεί να θέλετε προγραμματιστικά να επιβεβαιώσετε ότι οι διαστάσεις ταιριάζουν με τις προσδοκίες σας. Η κλάση `Image` από το `System.Drawing` μπορεί να διαβάσει το αρχείο και να αναφέρει το μέγεθός του.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Αν το ύψος δεν αντανακλά την τιμή που ορίσατε, ελέγξτε:

- **X‑dimension**: Μια πολύ μικρή τιμή μπορεί να κάνει τον renderer να στρογγυλοποιήσει το ύψος.  
- **Image format**: Ορισμένες μορφές (π.χ., JPEG) εφαρμόζουν συμπίεση που μπορεί να αλλάξει τις διαστάσεις των pixel κατά την αποθήκευση. Το PNG διατηρεί ακριβείς διαστάσεις.

## Βήμα 7: Καλές πρακτικές για το μέγεθος εικόνας barcode και απόδοση

| Σύσταση | Αιτία |
|---------|-------|
| Διατηρήστε το `x_dimension.pixels` μεταξύ 2 – 3 px για τους περισσότερους σαρωτές. | Ισορροπεί την αναγνωσιμότητα και το μέγεθος του αρχείου. |
| Χρησιμοποιήστε PNG για απώλεια‑απώλειας έξοδο όταν η εικόνα θα εκτυπωθεί. | Εγγυάται ακριβείς διαστάσεις και καθαρά άκρα. |
| Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarCodeGenerator` όταν δημιουργείτε πολλά barcode. | Μειώνει το κόστος κατανομής αντικειμένων. |
| Επικυρώστε τη συμβολοσειρά εισόδου έναντι του προτύπου GS1 πριν την αναθέσετε στο `CodeText`. | Αποτρέπει εξαιρέσεις χρόνου εκτέλεσης και μη έγκυρες σάρωσες. |
| Αποθηκεύστε τις παραγόμενες εικόνες σε αφιερωμένο φάκελο με σαφή σύστημα ονοματοδοσίας (π.χ., `Databar_{GTIN}.png`). | Απλοποιεί την επεξεργασία downstream και τα αρχεία ελέγχου. |

## Πλήρες λειτουργικό παράδειγμα

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που ενσωματώνει όλα τα βήματα από την αρχικοποίηση μέχρι την επαλήθευση. Αντιγράψτε τον κώδικα σε ένα νέο έργο console και εκτελέστε το.



## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία εικόνας barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Δημιουργία εικόνας barcode DotCode – γραμμές & στήλες (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Πώς να δημιουργήσετε ζώνη σιωπής Barcode για ITF-14 χρησιμοποιώντας Aspose.BarCode για .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}