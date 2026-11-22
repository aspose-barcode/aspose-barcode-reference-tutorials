---
category: general
date: 2026-11-20
description: Δημιουργήστε γρήγορα εικόνα ταχυδρομικού barcode σε C#. Μάθετε πώς να
  δημιουργείτε barcode τύπου planet και RM4SCC με προσαρμόσιμα στυλ γραμμών.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: el
lastmod: 2026-11-20
og_description: Δημιουργήστε εικόνα ταχυδρομικού barcode σε C# με το Aspose.BarCode.
  Αυτό το σεμινάριο δείχνει πώς να δημιουργήσετε κώδικα planet, να προσαρμόσετε τα
  στυλ των γραμμών και να παράγετε εικόνες RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Δημιουργία εικόνας ταχυδρομικού barcode σε C# – οδηγός βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Δημιουργήστε εικόνα ταχυδρομικού barcode και δημιουργήστε barcode πλανήτη
url: /el/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία εικόνας ταχυδρομικού barcode και δημιουργία planet barcode

Δημιουργήστε εικόνα ταχυδρομικού barcode σε C# χρησιμοποιώντας τη βιβλιοθήκη Aspose.BarCode. Εάν χρειάζεστε να δημιουργήσετε planet barcode ή barcodes RM4SCC για εφαρμογές αποστολής αλληλογραφίας, αυτό το tutorial παρέχει μια πλήρη, έτοιμη προς εκτέλεση λύση.

Η δημιουργία barcode για τις ταχυδρομικές υπηρεσίες συχνά απαιτεί ακριβείς διαστάσεις και τη δυνατότητα εναλλαγής μεταξύ γεμιστών και κενών στυλ ράβδων. Αυτός ο οδηγός σας καθοδηγεί στη ρύθμιση του φακέλου εξόδου, στη δημιουργία τόσο γεμιστών όσο και κενών Planet barcode, και στην παραγωγή ενός barcode RM4SCC με τις ίδιες οπτικές ρυθμίσεις. Στο τέλος θα έχετε τέσσερα αρχεία PNG που μπορείτε να χρησιμοποιήσετε απευθείας στη ροή εργασίας αποστολής.

## Prerequisites

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 ή νεότερη έκδοση εγκατεστημένη  
* Visual Studio 2022 (ή οποιοδήποτε IDE C# προτιμάτε)  
* Το πακέτο **Aspose.BarCode** NuGet (`Install-Package Aspose.BarCode`)  

Δεν απαιτείται πρόσθετη διαμόρφωση· ο κώδικας χρησιμοποιεί μόνο την προεπιλεγμένη γραμματοσειρά και τον κωδικοποιητή PNG.

## Create postal barcode image – overview

Ο πυρήνας της διαδικασίας είναι η κλάση `BarcodeGenerator`. Δέχεται μια τιμή `EncodeTypes` που καθορίζει τη συμβολική μορφή του barcode (για παράδειγμα, `EncodeTypes.Planet` για ένα Planet barcode). Μετά τη διαμόρφωση του γεννήτρια, καλείτε το `Save` για να γράψετε το αρχείο εικόνας.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Παράδειγμα δημιουργίας εικόνας ταχυδρομικού barcode που δείχνει γεμιστές και κενές ράβδους.*

## Step 1: Set up the output folder

Πρώτα ορίστε έναν φάκελο όπου θα αποθηκευτούν τα αρχεία PNG. Η χρήση απόλυτης ή σχετικής διαδρομής λειτουργεί το ίδιο· απλώς βεβαιωθείτε ότι ο φάκελος υπάρχει ή αφήστε τον κώδικα να τον δημιουργήσει.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Η δημιουργία του φακέλου προγραμματιστικά αποτρέπει το `DirectoryNotFoundException` όταν το tutorial εκτελείται σε νέο μηχάνημα.

## Step 2: Generate planet barcode with filled bars

Ένα Planet barcode με γεμιστές ράβδους είναι το προεπιλεγμένο οπτικό στυλ. Ο παρακάτω κώδικας δημιουργεί το barcode, ορίζει τη διάσταση X σε 4 pixel (συνηθισμένο μέγεθος για ταχυδρομικές εφαρμογές) και αποθηκεύει την εικόνα.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Why this works:**  
* `EncodeTypes.Planet` λέει στη γεννήτρια να χρησιμοποιήσει τη συμβολική μορφή Planet, η οποία απαιτείται από πολλές ταχυδρομικές υπηρεσίες.  
* `XDimension.Pixels` ελέγχει το πλάτος κάθε ράβδου· 4 px προσφέρει καθαρή, αναγνώσιμη εικόνα χωρίς υπερβολικό μέγεθος αρχείου.  
* Η μέθοδος `Save` επιλέγει αυτόματα τον κωδικοποιητή PNG βάσει του enum `BarCodeImageFormat`.

## Step 3: Generate planet barcode with empty bars

Κάποιες ταχυδρομικές προδιαγραφές προτιμούν κενές (λευκές) ράβδους σε σκούρο φόντο. Μπορείτε να το πετύχετε ορίζοντας `FilledBars` σε `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** Όταν το `FilledBars` είναι `false`, η γεννήτρια ζωγραφίζει τις ράβδους στο χρώμα φόντου (λευκό εξ ορισμού) και τα κενά στο χρώμα προσώπου (μαύρο). Εάν χρειάζεστε διαφορετικό συνδυασμό χρωμάτων, προσαρμόστε τα `Parameters.Barcode.ForeColor` και `BackColor`.

## Step 4: Generate RM4SCC barcode with filled bars

Το RM4SCC είναι άλλη ταχυδρομική συμβολική μορφή που χρησιμοποιείται στο Ηνωμένο Βασίλειο. Τα βήματα δημιουργίας αντικατοπτρίζουν το παράδειγμα Planet· μόνο η τιμή `EncodeTypes` αλλάζει.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**What to expect:** Το παραγόμενο PNG εμφανίζει ένα συμπαγές barcode RM4SCC που συμμορφώνεται με τις οδηγίες του βρετανικού ταχυδρομείου. Το μέγεθος της εικόνας θα είναι παρόμοιο με τα Planet barcode επειδή η διάσταση X είναι η ίδια.

## Step 5: Verify the generated images

Μετά την εκτέλεση του προγράμματος, ανοίξτε τα τέσσερα αρχεία στον φάκελο `Barcodes`. Θα πρέπει να δείτε:

* `PostalPlanetFilledBars.png` – σκούρες ράβδοι σε ανοιχτό φόντο  
* `PostalPlanetEmptyBars.png` – ανοιχτές ράβδοι σε σκούρο φόντο (αντίστροφο)  
* `PostalRM4SCCFilledBars.png` – τυπικό μοτίβο RM4SCC  

Εάν κάποια εικόνα φαίνεται παραμορφωμένη, ελέγξτε τα εξής:

* **Διάσταση X** – πολύ μικρή (< 2 px) μπορεί να προκαλέσει θολότητα· πολύ μεγάλη (> 10 px) μπορεί να υπερβεί τα όρια μεγέθους ετικέτας.  
* **Συμβολοσειρά δεδομένων** – η τιμή `"123456"` πρέπει να πληροί τις απαιτήσεις μήκους της επιλεγμένης συμβολικής μορφής (Planet απαιτεί 6 ψηφία, RM4SCC επίσης 6 ψηφία).  
* **Δικαιώματα φακέλου** – βεβαιωθείτε ότι η εφαρμογή έχει δικαίωμα εγγραφής στον φάκελο εξόδου.

## Common variations and edge cases

| Σενάριο | Προσαρμογή |
|----------|------------|
| **Διαφορετικά δεδομένα barcode** | Αντικαταστήστε το `"123456"` με οποιαδήποτε έγκυρη αριθμητική συμβολοσειρά. Για Planet, το μήκος πρέπει να είναι ακριβώς 6 ψηφία· το RM4SCC επίσης απαιτεί 6 ψηφία. |
| **Προσαρμοσμένα χρώματα** | Ορίστε `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` και `BackColor = System.Drawing.Color.LightYellow;`. |
| **Υψηλότερη ανάλυση** | Αυξήστε το `XDimension.Pixels` σε 6 ή 8 για μεγαλύτερες εκτυπώσεις. |
| **Άλλες μορφές εικόνας** | Χρησιμοποιήστε `BarCodeImageFormat.Jpeg` ή `BarCodeImageFormat.Bmp` στην κλήση `Save`. |
| **Δημιουργία παρτίδας** | Επαναλάβετε έναν βρόχο πάνω σε μια συλλογή συμβολοσειρών και καλέστε την ίδια λογική γεννήτριας μέσα στο βρόχο, επαναχρησιμοποιώντας τη διαδρομή `outputFolder`. |

## Full, runnable example

Αντιγράψτε τον κώδικα παρακάτω σε ένα νέο έργο κονσόλας C#. Συγκεντρώνεται με .NET 6.0 και παράγει αυτόματα όλες τις τέσσερις εικόνες barcode.



## Τι θα πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}