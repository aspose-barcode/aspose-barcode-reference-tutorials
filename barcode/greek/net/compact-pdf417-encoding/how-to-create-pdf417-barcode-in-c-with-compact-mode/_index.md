---
category: general
date: 2026-09-10
description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# γρήγορα. Μάθετε πώς να ενεργοποιήσετε
  τη συμπαγή λειτουργία, να ορίσετε στήλες και να δημιουργήσετε PNG με το BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: el
lastmod: 2026-09-10
og_description: Δημιουργήστε γραμμωτό κώδικα PDF417 σε C# ενεργοποιώντας τη συμπαγή
  λειτουργία, ορίζοντας στήλες και αποθηκεύοντας ως PNG. Ακολουθήστε τον πλήρη οδηγό
  βήμα‑προς‑βήμα.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Δημιουργία κωδικού PDF417 σε C# – οδηγός για τη συμπαγή λειτουργία
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με συμπαγή λειτουργία
url: /el/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα PDF417 σε C# με συμπαγή λειτουργία

Αν χρειάζεστε **να δημιουργήσετε γραμμωτό κώδικα PDF417** σε μια εφαρμογή .NET, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε. Θα δείτε πώς να **ενεργοποιήσετε τη συμπαγή λειτουργία**, να ορίσετε τον αριθμό των στηλών και να αποθηκεύσετε το αποτέλεσμα ως εικόνα PNG χρησιμοποιώντας τη βιβλιοθήκη BarcodeGenerator C#.

Η δημιουργία γραμμωτού κώδικα είναι μια συνηθισμένη απαίτηση για παρακολούθηση αποθεμάτων, συστήματα εισιτηρίων και εφαρμογές κινητής σάρωσης. Στο τέλος αυτού του οδηγού θα έχετε ένα αυτόνομο, εκτελέσιμο παράδειγμα που παράγει έναν συμπαγή γραμμωτό κώδικα PDF417 έτοιμο για παραγωγική χρήση.

## Προαπαιτούμενα

* .NET 6.0 ή νεότερη έκδοση εγκατεστημένη (ο κώδικας λειτουργεί επίσης με .NET Framework 4.7+)
* Μια πρόσφατη έκδοση της βιβλιοθήκης **BarcodeGenerator** (π.χ., Aspose.BarCode for .NET)
* Ένα IDE ή επεξεργαστή όπως το Visual Studio 2022 ή το VS Code
* Δικαίωμα εγγραφής σε φάκελο όπου θα αποθηκευτεί το PNG

Δεν απαιτούνται πρόσθετα πακέτα NuGet πέρα από τη βιβλιοθήκη γραμμωτού κώδικα.

## Βήμα 1: Δημιουργία γεννήτριας γραμμωτού κώδικα PDF417

Το πρώτο βήμα είναι να δημιουργήσετε ένα αντικείμενο `BarcodeGenerator` με την παράμετρο enum `EncodeTypes.Pdf417` και το κείμενο που θέλετε να κωδικοποιήσετε. Αυτό το αντικείμενο καθοδηγεί όλη τη διαδικασία δημιουργίας.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Γιατί είναι σημαντικό*: Η τιμή `EncodeTypes.Pdf417` ενημερώνει τη βιβλιοθήκη να χρησιμοποιήσει τη συμβολική PDF417, ενώ το δεύτερο όρισμα παρέχει το φορτίο. Μπορείτε να αντικαταστήσετε το `"Compact mode"` με οποιοδήποτε αλφαριθμητικό κείμενο που χρειάζεται να κωδικοποιήσετε.

## Βήμα 2: Ορισμός διάστασης X (πλάτος μονάδας)

Η διάσταση X ελέγχει το πλάτος κάθε μικρού τετραγώνου (μονάδας) στον γραμμωτό κώδικα. Μικρότερες τιμές παράγουν πιο πυκνή εικόνα, κάτι που είναι χρήσιμο όταν ο χώρος είναι περιορισμένος.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Μια τιμή των `2` εικονοστοιχείων είναι μια καλή ισορροπία μεταξύ αναγνωσιμότητας και συμπαγούς μεγέθους για τους περισσότερους σαρωτές που βασίζονται σε οθόνη.

## Βήμα 3: Ορισμός αριθμού στηλών

Το PDF417 μπορεί να οργανώσει τα δεδομένα σε ένα πλέγμα γραμμών και στηλών. Η ρύθμιση του αριθμού των στηλών αλλάζει την αναλογία διαστάσεων του γραμμωτού κώδικα.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Ορίζοντας **πώς να ορίσετε στήλες** σε `3` παράγει έναν σύντομο, πλατύ γραμμωτό κώδικα που ταιριάζει καλά σε μια ετικέτα. Μπορείτε να πειραματιστείτε με τιμές από `1` έως `30` ανάλογα με την ποσότητα των δεδομένων και τον στόχο σαρωτή.

## Βήμα 4: Ενεργοποίηση συμπαγούς λειτουργίας

Η συμπαγής λειτουργία αφαιρεί περιττές σειρές γεμίσματος, καθιστώντας τον γραμμωτό κώδικα μικρότερο χωρίς να χάσει την ακεραιότητα των δεδομένων. Αυτό είναι το βασικό βήμα για έναν **συμπαγή PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Όταν το `Truncate` είναι `true`, η βιβλιοθήκη υπολογίζει αυτόματα τον ελάχιστο αριθμό σειρών που απαιτούνται για την αποθήκευση των δεδομένων, γι' αυτό η τελική εικόνα φαίνεται “συμπαγής”.

## Βήμα 5: Αποθήκευση του παραγόμενου γραμμωτού κώδικα ως εικόνα PNG

Τέλος, γράψτε τον γραμμωτό κώδικα σε αρχείο. Το PNG διατηρεί τις καθαρές άκρες που χρειάζονται για αξιόπιστη σάρωση.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Αντικαταστήστε το `YOUR_DIRECTORY` με μια απόλυτη ή σχετική διαδρομή στην οποία η εφαρμογή σας μπορεί να γράψει. Μετά την εκτέλεση, θα βρείτε ένα αρχείο `CompactPdf417.png` που περιέχει τον γραμμωτό κώδικα.

### Πλήρης κώδικας πηγής

Συνδυάζοντας όλα τα βήματα μαζί λαμβάνετε ένα ενιαίο, έτοιμο‑για‑εκτέλεση πρόγραμμα:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Η εκτέλεση αυτού του προγράμματος παράγει το `CompactPdf417.png` στον ίδιο φάκελο με το εκτελέσιμο. Ανοίξτε την εικόνα με οποιονδήποτε προβολέα· θα πρέπει να δείτε έναν πυκνό, υψηλής αντίθεσης γραμμωτό κώδικα PDF417 έτοιμο για σάρωση.

## Πώς να ενεργοποιήσετε τη συμπαγή λειτουργία σε άλλες περιπτώσεις

* **Batch generation** – Όταν δημιουργείτε πολλούς γραμμωτούς κώδικες, ορίστε το `Truncate` μία φορά στη γεννήτρια και επαναχρησιμοποιήστε το για κάθε νέο φορτίο.
* **Different image formats** – Η ίδια μέθοδος `Save` λειτουργεί με `BarCodeImageFormat.Jpeg` ή `BarCodeImageFormat.Bmp` εάν χρειάζεστε διαφορετικό τύπο αρχείου.
* **Dynamic column count** – Εάν το μήκος της κωδικοποιημένης συμβολοσειράς διαφέρει, υπολογίστε έναν βέλτιστο αριθμό στηλών βάσει του μήκους της συμβολοσειράς και της ανάλυσης του σαρωτή.

## Πώς να ορίσετε στήλες για συγκεκριμένες περιπτώσεις χρήσης

* **Label printing** – Χρησιμοποιήστε μικρό αριθμό στηλών (π.χ., `2`‑`5`) ώστε ο γραμμωτός κώδικας να είναι αρκετά σύντομος για να χωράει σε στενές ετικέτες.
* **Mobile scanning** – Μεγαλύτερος αριθμός στηλών (`10`‑`15`) παράγει ψηλότερους γραμμωτούς κώδικες που είναι πιο εύκολο να εστιάσει η κάμερα του τηλεφώνου.
* **Error‑correction trade‑off** – Περισσότερες στήλες μειώνουν τον αριθμό των σειρών, κάτι που μπορεί να επηρεάσει την ενσωματωμένη διόρθωση σφαλμάτων του γραμμωτού κώδικα. Δοκιμάστε με τον στόχο σαρωτή σας για να βρείτε το βέλτιστο σημείο.

## Συνηθισμένα προβλήματα και επαγγελματικές συμβουλές

| Πρόβλημα | Γιατί συμβαίνει | Διόρθωση |
|----------|------------------|----------|
| Ο γραμμωτός κώδικας είναι μη αναγνώσιμος | Η διάσταση X είναι πολύ χαμηλή (π.χ., `1` εικονοστοιχείο) | Αυξήστε το `XDimension.Pixels` τουλάχιστον σε `2` |
| Η εικόνα είναι πολύ μεγάλη | Οι στήλες έχουν οριστεί πολύ υψηλά για ένα σύντομο φορτίο | Μειώστε το `Pdf417.Columns` ή ενεργοποιήστε το `Truncate` |
| Το αρχείο PNG είναι κενό | Ο φάκελος εξόδου δεν υπάρχει ή δεν έχει δικαίωμα εγγραφής | Βεβαιωθείτε ότι ο φάκελος υπάρχει και ότι η διαδικασία έχει δικαιώματα εγγραφής |
| Ο σαρωτής αναφέρει “κατεστραμμένα δεδομένα” | Το Truncate είναι απενεργοποιημένο ενώ χρησιμοποιούνται πολλές στήλες | Ενεργοποιήστε το `Truncate` ή μειώστε τον αριθμό των στηλών |

## Επαλήθευση του αποτελέσματος

Μπορείτε να επαληθεύσετε τον γραμμωτό κώδικα με οποιαδήποτε εφαρμογή σαρωτή PDF417 (υπάρχουν πολλές δωρεάν εφαρμογές για Android/iOS). Ανοίξτε το `CompactPdf417.png` στην εφαρμογή και επιβεβαιώστε ότι το κωδικοποιημένο κείμενο ταιριάζει με το αρχικό φορτίο (“Compact mode”). Εάν το κείμενο διαφέρει, ελέγξτε ξανά τη σημαία `Truncate` και τις ρυθμίσεις στηλών.

## Επόμενα βήματα

* **Integrate with ASP.NET Core** – Επιστρέψτε το PNG απευθείας από μια ενέργεια ελεγκτή αντί να το αποθηκεύετε σε δίσκο.
* **Add human‑readable text** – Χρησιμοποιήστε το `barcodeGenerator.Parameters.Barcode.CodeTextParameters` για να εμφανίσετε τη κωδικοποιημένη συμβολοσειρά κάτω από τον γραμμωτό κώδικα.
* **Explore other symbologies** – Η ίδια κλάση `BarcodeGenerator` υποστηρίζει QR, Code128, DataMatrix και άλλα. Αλλάξτε το `EncodeTypes` για να τα δοκιμάσετε.

---

### Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε γραμμωτό κώδικα PDF417** σε C# ενώ **ενεργοποιείτε τη συμπαγή λειτουργία**, ελέγχοντας **πώς να ορίσετε στήλες**, και χρησιμοποιώντας το API **barcode generator C#** για **να δημιουργήσετε έναν γραμμωτό κώδικα** που πληροί τις πραγματικές απαιτήσεις μεγέθους. Εφαρμόστε αυτά τα βήματα σε οποιοδήποτε έργο .NET που χρειάζεται συμπαγείς, υψηλής πυκνότητας γραμμωτούς κώδικες, και επεκτείνετε το μοτίβο σε άλλες μορφές γραμμωτών κωδίκων όπως απαιτείται. Καλή προγραμματιστική!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε σε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία γραμμωτού κώδικα PDF417 σε C# – Πλήρης Οδηγός Βήμα‑βήμα](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Πώς να ορίσετε το επίπεδο σφάλματος σε γραμμωτό κώδικα PDF417 – Πλήρης Οδηγός](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Πώς να αποθηκεύσετε γραμμωτό κώδικα σε C# – Δημιουργία γραμμωτών κωδίκων PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}