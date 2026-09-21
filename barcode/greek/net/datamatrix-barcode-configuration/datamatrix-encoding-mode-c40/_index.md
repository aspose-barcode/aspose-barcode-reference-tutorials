---
date: 2026-06-09
description: Μάθετε πώς να δημιουργείτε κωδικούς DataMatrix και να αποθηκεύετε PNG
  χρησιμοποιώντας κωδικοποίηση C40 με Aspose.BarCode – πλήρης οδηγός για τη δημιουργία
  barcode σε .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Λειτουργία κωδικοποίησης DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Πώς να δημιουργήσετε DataMatrix PNG με C40 χρησιμοποιώντας Aspose.BarCode
url: /el/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κύρια λειτουργία κωδικοποίησης DataMatrix (C40) με Aspose.BarCode για .NET

## Εισαγωγή

Σε αυτό το μάθημα θα μάθετε **how to generate datamatrix** barcode και πώς να τα αποθηκεύσετε ως αρχεία PNG χρησιμοποιώντας τη λειτουργία κωδικοποίησης C40 με Aspose.BarCode για .NET. Είτε δημιουργείτε σύστημα αποθεμάτων, γεννήτρια ετικετών αποστολής ή οποιαδήποτε λύση που απαιτεί συμπαγή, υψηλής πυκνότητας σύμβολα, η εξοικείωση με το C40 σας προσφέρει μικρότερα σύμβολα χωρίς να θυσιάζεται η αναγνωσιμότητα. Θα περάσουμε από κάθε βήμα — από τη ρύθμιση του περιβάλλοντος μέχρι την παραγωγή του τελικού PNG — ώστε να ενσωματώσετε τον κώδικα αμέσως στο έργο σας.

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “how to generate datamatrix”;** Δημιουργία εικόνας barcode DataMatrix προγραμματιστικά.  
- **Ποια λειτουργία κωδικοποίησης καλύπτεται;** DataMatrix C40, ένα αποδοτικό αλφαριθμητικό σχήμα.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να το τρέξω σε .NET Core;** Ναι, το Aspose.BarCode υποστηρίζει πλήρως .NET Core, .NET 5, .NET 6 και μεταγενέστερες εκδόσεις.  
- **Τι μορφή αρχείου παράγεται;** PNG – μορφή εικόνας χωρίς απώλειες, φιλική για το web.

## Πώς να δημιουργήσετε DataMatrix με κωδικοποίηση C40

Φορτώστε τα δεδομένα σας, διαμορφώστε τον δημιουργό και καλέστε `Save` – αυτή είναι η πλήρης ροή εργασίας σε τρία σύντομα βήματα. Η κλάση `BarcodeGenerator` διαχειρίζεται τη δημιουργία του συμβόλου, ενώ η παράμετρος `BarCodeImageFormat.Png` λέει στο Aspose.BarCode να γράψει το αποτέλεσμα ως αρχείο PNG. Η μέθοδος `Save` αποθηκεύει την παραγόμενη εικόνα barcode στη συγκεκριμένη διαδρομή αρχείου στη μορφή που επιλέχθηκε. Αυτή η παράγραφος με άμεση απάντηση σας δίνει τη λύση από άκρη σε άκρη πριν εμβαθύνουμε σε κάθε γραμμή κώδικα.

## Τι είναι η λειτουργία κωδικοποίησης DataMatrix (C40);

`DataMatrixEncodeMode` είναι μια απαρίθμηση που καθορίζει ποιο σχήμα κωδικοποίησης πρέπει να χρησιμοποιήσει το Aspose.BarCode για σύμβολα DataMatrix. Η επιλογή `DataMatrixEncodeMode.C40` επιλέγει την αλφαριθμητική κωδικοποίηση C40, η οποία συσσωρεύει γράμματα, ψηφία και ένα περιορισμένο σύνολο σημεία στίξης σε λιγότερα modules, μειώνοντας το συνολικό μέγεθος του συμβόλου ενώ διατηρεί την αναγνωσιμότητα για τυπικό κείμενο αποθεμάτων. Αυτό το αποδοτικό σχήμα είναι ιδανικό όταν χρειάζεται να κωδικοποιήσετε αλφαριθμητικά δεδομένα με συμπαγή μορφή.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για .NET;

Aspose.BarCode παρέχει **30+ παραμετρικές ρυθμίσεις** για διαστάσεις, επίπεδα διόρθωσης σφαλμάτων και λειτουργίες κωδικοποίησης, και υποστηρίζει **50+ μορφές εικόνας και barcode**. Η βιβλιοθήκη λειτουργεί σε **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, προσφέροντας δημιουργία χωρίς εξαρτήσεις που λειτουργεί σε διακομιστές, επιτραπέζιους υπολογιστές και κινητές συσκευές εξίσου.

## Προαπαιτούμενα

Πριν εμβαθύνουμε στον κώδικα, βεβαιωθείτε ότι διαθέτετε τα εξής:

1. **.NET Development Environment** – Visual Studio, Rider ή οποιοδήποτε IDE που υποστηρίζει C#.  
2. **Aspose.BarCode for .NET** – εγκατεστημένο μέσω NuGet ή του επίσημου εγκαταστάτη. Δείτε την [documentation](https://reference.aspose.com/barcode/net/) για λεπτομέρειες.  
3. **Basic C# knowledge** – πρέπει να είστε άνετοι με namespaces, κλάσεις και using statements.  
4. **Write‑access folder** – ένας φάκελος στο μηχάνημά σας όπου θα αποθηκευτεί το PNG.

## Εισαγωγή Απαραίτητων Ονομάτων Χώρου

Η κλάση `BarcodeGenerator` είναι το σημείο εισόδου για τη δημιουργία οποιουδήποτε barcode. Προσθέστε το απαιτούμενο namespace στην κορυφή του αρχείου C# ώστε να έχετε πρόσβαση στο API δημιουργίας:

```csharp
using Aspose.BarCode.Generation;
```

## Δημιουργία Barcode βήμα‑βήμα

Παρακάτω βρίσκεται ένας **step‑by‑step barcode** οδηγός. Κάθε βήμα εξηγείται με απλή γλώσσα, και οι αρχικοί placeholders διατηρούνται αμετάβλητοι για ευκολία αντιγραφής‑επικόλλησης.

### Βήμα 1: Ορισμός Διαδρομής Φακέλου
Ορίστε το φάκελο όπου θα αποθηκευτεί η εικόνα PNG. Αντικαταστήστε το placeholder με μια πραγματική διαδρομή στο μηχάνημά σας.

```csharp
string path = "Your Directory Path";
```

### Βήμα 2: Ρύθμιση Δημιουργίας Barcode
Δημιουργήστε μια παρουσία `BarcodeGenerator`, καθορίστε `EncodeTypes.DataMatrix` και παρέχετε τα δεδομένα που θέλετε να κωδικοποιήσετε.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Βήμα 3: Προσαρμογή Barcode
Διαμορφώστε τη διάσταση X (πλάτος pixel των modules) και αλλάξτε τη λειτουργία κωδικοποίησης σε C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Βήμα 4: Αποθήκευση Εικόνας Barcode
Τέλος, αποθηκεύστε το παραγόμενο barcode ως αρχείο PNG. Αυτή είναι η συγκεκριμένη απάντηση στο **how to save png** με Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Όταν εκτελέσετε το πρόγραμμα, θα βρείτε το `DataMatrixEncodeModeC40.png` στον φάκελο που καθορίσατε, έτοιμο για χρήση σε αναφορές, ετικέτες ή ιστοσελίδες.

## Συχνά Προβλήματα & Συμβουλές

- **Invalid Path** – Βεβαιωθείτε ότι ο φάκελος υπάρχει και έχετε δικαιώματα εγγραφής· διαφορετικά το `gen.Save` θα ρίξει εξαίρεση.  
- **Incorrect Encoding Mode** – Αν χρειάζεται να κωδικοποιήσετε χαρακτήρες εκτός του συνόλου C40, μεταβείτε σε `DataMatrixEncodeMode.Auto` ή άλλη κατάλληλη λειτουργία.  
- **Image Size** – Ρυθμίστε το `XDimension.Pixels` για να αυξήσετε ή να μειώσετε το συνολικό μέγεθος του barcode χωρίς να επηρεάσετε την αναγνωσιμότητα.

## Συχνές Ερωτήσεις

**Q: Τι είναι η λειτουργία κωδικοποίησης DataMatrix (C40);**  
A: Το C40 είναι ένα συμπαγές αλφαριθμητικό σχήμα κωδικοποίησης για σύμβολα DataMatrix, ιδανικό για κείμενο που περιλαμβάνει γράμματα, αριθμούς και περιορισμένο σύνολο ειδικών χαρακτήρων.

**Q: Πού μπορώ να βρω την τεκμηρίωση του Aspose.BarCode για .NET;**  
A: Μπορείτε να βρείτε την τεκμηρίωση [εδώ](https://reference.aspose.com/barcode/net/). Παρέχει λεπτομερείς οδηγίες για όλους τους τύπους barcode και τις επιλογές κωδικοποίησης.

**Q: Είναι το Aspose.BarCode για .NET συμβατό με όλες τις εκδόσεις του .NET;**  
A: Ναι, η βιβλιοθήκη υποστηρίζει ευρύ φάσμα εκδόσεων .NET, από .NET Framework 4.5+ έως .NET 6 και μεταγενέστερες.

**Q: Μπορώ να δοκιμάσω το Aspose.BarCode για .NET πριν το αγοράσω;**  
A: Ναι, μπορείτε να εξερευνήσετε μια δωρεάν δοκιμή του Aspose.BarCode για .NET επισκεπτόμενοι [this link](https://releases.aspose.com/). Σας επιτρέπει να δοκιμάσετε τις δυνατότητες και τις λειτουργίες της βιβλιοθήκης.

**Q: Πού μπορώ να λάβω υποστήριξη για το Aspose.BarCode για .NET;**  
A: Μπορείτε να βρείτε μια υποστηρικτική κοινότητα και πρόσβαση σε υποστήριξη για Aspose.BarCode για .NET στο [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Συμπέρασμα

Ακολουθώντας αυτόν τον **step‑by‑step barcode** οδηγό, γνωρίζετε πλέον ακριβώς **how to generate datamatrix** barcode και πώς να τα αποθηκεύσετε ως αρχεία PNG χρησιμοποιώντας τη λειτουργία κωδικοποίησης C40 με Aspose.BarCode για .NET. Αυτή η προσέγγιση σας δίνει πλήρη έλεγχο πάνω στην εμφάνιση, το μέγεθος και την αναπαράσταση των δεδομένων του barcode, καθιστώντας εύκολη την ενσωμάτωση υψηλής ποιότητας barcode σε οποιαδήποτε εφαρμογή .NET.

---

**Τελευταία ενημέρωση:** 2026-06-09  
**Δοκιμή με:** Aspose.BarCode 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Κωδικοποίηση DataMatrix σε Bytes με Aspose.BarCode για .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Κύρια κωδικοποίηση DataMatrix σε ASCII με Aspose.BarCode για .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Πώς να δημιουργήσετε DataMatrix Barcodes (ECC 200) με Aspose.BarCode για .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}