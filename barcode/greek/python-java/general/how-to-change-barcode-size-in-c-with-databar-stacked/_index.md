---
category: general
date: 2026-08-22
description: Πώς να αλλάξετε το μέγεθος του barcode σε C# χρησιμοποιώντας τον δημιουργό
  DataBar Stacked Omni‑Directional. Μάθετε πώς να ορίσετε τη διάσταση X και την αναλογία
  διαστάσεων για την έξοδο PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: el
lastmod: 2026-08-22
og_description: Πώς να αλλάξετε το μέγεθος του barcode σε C# με τη γεννήτρια DataBar
  Stacked Omni‑Directional. Ακολουθήστε τον οδηγό βήμα‑προς‑βήμα για να ρυθμίσετε
  τη διάσταση X και την αναλογία διαστάσεων.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Πώς να αλλάξετε το μέγεθος του γραμμωτού κώδικα σε C# – πλήρης οδηγός
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Πώς να αλλάξετε το μέγεθος του barcode σε C# με DataBar Stacked
url: /el/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αλλάξετε το μέγεθος του barcode σε C# με DataBar Stacked

Αν χρειάζεστε **πώς να αλλάξετε το μέγεθος του barcode** σε μια εφαρμογή .NET, αυτός ο οδηγός δείχνει τα ακριβή βήματα χρησιμοποιώντας τον δημιουργό barcode DataBar Stacked Omni‑Directional. Θα δείτε πώς να ελέγξετε τη διάσταση X σε pixel, να προσαρμόσετε το λόγο διαστάσεων του barcode και να αποθηκεύσετε το αποτέλεσμα ως αρχείο PNG.

Η αλλαγή του μεγέθους του barcode είναι συχνά απαραίτητη όταν ο χώρος της εκτυπωμένης ετικέτας είναι περιορισμένος ή όταν απαιτείται εικόνα υψηλότερης ανάλυσης για ψηφιακά κανάλια. Αυτό το tutorial καλύπτει όλα όσα χρειάζεστε, από την αρχικοποίηση του δημιουργού μέχρι την παραγωγή δύο εικόνων με διαφορετικά μεγέθη.

## Προαπαιτήσεις

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Μια αναφορά στο πακέτο NuGet **Aspose.BarCode for .NET**  
* Βασική εξοικείωση με τη σύνταξη C#  

Δεν απαιτείται πρόσθετη διαμόρφωση· ο κώδικας εκτελείται σε Windows, Linux ή macOS.

## Πώς να αλλάξετε το μέγεθος του barcode σε C# – βήμα προς βήμα

Οι παρακάτω ενότητες χωρίζουν τη διαδικασία σε διακριτά, επαναχρησιμοποιήσιμα βήματα. Κάθε βήμα εξηγεί **γιατί** χρειάζεται ο κώδικας, όχι μόνο **τι** κάνει.

### Βήμα 1: Δημιουργία ενός δημιουργού barcode DataBar Stacked Omni‑Directional

Το αντικείμενο του δημιουργού περιέχει όλες τις ρυθμίσεις του barcode. Με τη μεταβίβαση του `EncodeTypes.DatabarStackedOmniDirectional` και δείγμα δεδομένων, δημιουργείτε ένα έγκυρο barcode έτοιμο για περαιτέρω προσαρμογή.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Γιατί είναι σημαντικό* – Η κλάση **C# barcode generator** περιλαμβάνει τον αλγόριθμο κωδικοποίησης. Ξεκινώντας με έναν έγκυρο δημιουργό εξασφαλίζει ότι οι επόμενες αλλαγές μεγέθους θα επηρεάσουν τον σωστό τύπο barcode.

### Βήμα 2: Ορισμός του βασικού μεγέθους μονάδας (διάσταση X) σε pixel

Η διάσταση X ορίζει το πλάτος μιας μοναδικής μονάδας barcode. Η προσαρμογή της αλλάζει το συνολικό πλάτος και ύψος αναλογικά.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Γιατί είναι σημαντικό* – Μια μεγαλύτερη διάσταση X παράγει μεγαλύτερο barcode, χρήσιμο για εκτυπωτές χαμηλής ανάλυσης. Αντίστροφα, μια μικρότερη τιμή δημιουργεί συμπαγές barcode κατάλληλο για μικρές ετικέτες.

### Βήμα 3: Αλλαγή του λόγου διαστάσεων του barcode σε 15 και αποθήκευση της εικόνας

Ο **barcode aspect ratio** ελέγχει τη σχέση ύψους προς πλάτος. Ένας λόγος 15 δίνει ένα σχετικά ψηλό barcode.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Γιατί είναι σημαντικό* – Διαφορετικές συσκευές σάρωσης έχουν βέλτιστες απαιτήσεις λόγου διαστάσεων. Ορίζοντας το λόγο σε 15 δείχνει πώς να **πώς να αλλάξετε το μέγεθος του barcode** τροποποιώντας το ύψος ενώ διατηρείται το πλάτος που ορίζεται από τη διάσταση X.

#### Αναμενόμενο αποτέλεσμα

Το αρχείο `DatabarAspectRatio15.png` εμφανίζει ένα DataBar Stacked Omni‑Directional barcode που είναι ψηλότερο από το προεπιλεγμένο. Το πλάτος του barcode αντανακλά τη διάσταση X των 2 pixel, και το ύψος ακολουθεί το λόγο 15.

### Βήμα 4: Αλλαγή του λόγου διαστάσεων του barcode σε 30 και αποθήκευση της νέας εικόνας

Η αύξηση του λόγου σε 30 κάνει το barcode ακόμη πιο ψηλό, δείχνοντας την ευελιξία των ρυθμίσεων μεγέθους.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Γιατί είναι σημαντικό* – Αντικαθιστώντας την τιμή του **barcode aspect ratio**, βλέπετε αμέσως πώς **πώς να αλλάξετε το μέγεθος του barcode** χωρίς να δημιουργήσετε ξανά τον δημιουργό. Αυτό εξοικονομεί χρόνο επεξεργασίας σε σενάρια batch.

#### Αναμενόμενο αποτέλεσμα

Το αρχείο `DatabarAspectRatio30.png` είναι εμφανώς ψηλότερο από την προηγούμενη εικόνα, επιβεβαιώνοντας ότι ο λόγος διαστάσεων επηρεάζει άμεσα το ύψος του barcode.

### Βήμα 5: Επαλήθευση των παραγόμενων εικόνων

Ανοίξτε τα αρχεία PNG σε οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε δύο barcodes με ίδιο πλάτος (ελεγχόμενο από τη διάσταση X) αλλά διαφορετικό ύψος (ελεγχόμενο από το λόγο διαστάσεων). Αν οι εικόνες φαίνονται θολές, αυξήστε τα pixel της διάστασης X· αν είναι πολύ ψηλές, μειώστε το λόγο διαστάσεων.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Γιατί είναι σημαντικό* – Η προγραμματιστική επαλήθευση διασφαλίζει ότι οι αλλαγές μεγέθους εφαρμόστηκαν σωστά, κάτι κρίσιμο για αυτοματοποιημένες αλυσίδες κατασκευής.

## Συνηθισμένες παραλλαγές και περιπτώσεις άκρων

| Κατάσταση | Ρύθμιση | Αιτία |
|-----------|------------|--------|
| **Πολύ μικρές ετικέτες** | Set `XDimension.Pixels = 1` and `AspectRatio = 10` | Μειώνει το συνολικό αποτύπωμα διατηρώντας την αναγνωσιμότητα |
| **Εκτύπωση υψηλής ανάλυσης** | Set `XDimension.Pixels = 4` and `AspectRatio = 20` | Αυξάνει την πυκνότητα pixel για καθαρό αποτέλεσμα |
| **Διαφορετική μορφή εικόνας** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` | Χρήσιμο όταν η υποστήριξη PNG είναι περιορισμένη |
| **Δυναμικά δεδομένα** | Pass a variable string to the `BarcodeGenerator` constructor | Δημιουργεί barcodes για κάθε προϊόν αυτόματα |

Όταν χρειάζεται να δημιουργήσετε πολλά barcodes με διαφορετικά μεγέθη, τυλίξτε τα βήματα σε μια μέθοδο:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Καλώντας `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` παράγει ένα barcode με προσαρμοσμένο μέγεθος σε μία μόνο γραμμή κώδικα.

## Συμβουλές για αξιόπιστες αλλαγές μεγέθους

* **Πάντα ορίστε τη διάσταση X πριν τον λόγο διαστάσεων.** Η αλλαγή του λόγου πρώτα μπορεί να οδηγήσει σε απρόσμενη κλιμάκωση εάν η διάσταση X έχει προεπιλεγμένη μη ιδανική τιμή.  
* **Χρησιμοποιήστε έναν συνεπή φάκελο εξόδου.** Η σκληρή κωδικοποίηση του `"YOUR_DIRECTORY"` λειτουργεί για demos, αλλά στην παραγωγή προτιμήστε `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Επικυρώστε το μέγεθος της παραγόμενης εικόνας.** Μικρές αλλαγές στη διάσταση X μπορεί να μην είναι ορατές στην οθόνη· ο έλεγχος των διαστάσεων pixel εγγυάται ότι η αλλαγή εφαρμόστηκε.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να αλλάξετε το μέγεθος του barcode** σε C# χρησιμοποιώντας τον δημιουργό DataBar Stacked Omni‑Directional barcode. Προσαρμόζοντας τα **pixel της διάστασης X** και το **barcode aspect ratio**, μπορείτε να παράγετε εικόνες PNG που ταιριάζουν σε οποιοδήποτε μέγεθος ετικέτας ή απαίτηση ανάλυσης. Το πλήρες, εκτελέσιμο παράδειγμα παραπάνω δείχνει τη συνολική ροή εργασίας από τη δημιουργία του δημιουργού μέχρι την επαλήθευση του μεγέθους.

### Τι να εξερευνήσετε στη συνέχεια

* **Προσαρμοσμένα χρώματα** – πειραματιστείτε με `barcodeGenerator.Parameters.Barcode.ForeColor` και `BackColor` για να ταιριάξετε με τις οδηγίες της μάρκας.  
* **Διαφορετικοί τύποι barcode** – αντικαταστήστε το `EncodeTypes.DatabarStackedOmniDirectional` με `EncodeTypes.QR` ή `EncodeTypes.Code128` για να δείτε πώς διαφέρουν οι παράμετροι μεγέθους μεταξύ των συμβολισμών.  
* **Επεξεργασία σε batch** – συνδυάστε τη μέθοδο `GenerateDatabar` με εισαγωγή CSV για να δημιουργήσετε χιλιάδες barcodes αυτόματα.

Αισθανθείτε ελεύθεροι να προσαρμόσετε τα αποσπάσματα κώδικα στην αρχιτεκτονική του έργου σας, και αφήστε τις προσαρμογές μεγέθους του barcode να βελτιώσουν την αξιοπιστία σάρωσης και το οπτικό σχεδιασμό. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να προσαρμόσετε το μέγεθος του barcode – Αναλογία διαστάσεων Codablock F με Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Πώς να δημιουργήσετε barcode Aztec με προσαρμοσμένη αναλογία διαστάσεων χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Πώς να δημιουργήσετε και να προσαρμόσετε το ύψος του barcode για One-Dimensional Databar χρησιμοποιώντας Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}