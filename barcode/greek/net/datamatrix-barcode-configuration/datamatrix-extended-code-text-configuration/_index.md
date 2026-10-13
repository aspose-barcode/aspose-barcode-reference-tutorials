---
date: 2026-09-23
description: Μάθετε πώς να χρησιμοποιήσετε Aspose.BarCode για τη δημιουργία ενός DataMatrix
  barcode με εκτεταμένο code text σε .NET, ιδανικό για εφαρμογές αποθεμάτων και εφοδιαστικής.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Διαμόρφωση Εκτεταμένου Code Text για DataMatrix
og_description: Πώς να χρησιμοποιήσετε Aspose.BarCode για τη δημιουργία ενός DataMatrix
  barcode με εκτεταμένο code text σε .NET. Ακολουθήστε έναν γρήγορο οδηγό βήμα‑βήμα
  για λύσεις αποθεμάτων και εφοδιαστικής.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Πώς να χρησιμοποιήσετε Aspose.BarCode για τη δημιουργία κειμένου κώδικα
  DataMatrix σε .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Πώς να χρησιμοποιήσετε Aspose.BarCode για τη δημιουργία κειμένου κώδικα DataMatrix
  σε .NET
url: /el/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το Aspose.BarCode για δημιουργία κειμένου κώδικα DataMatrix σε .NET

Η ενσωμάτωση των barcode σε σύγχρονες εφαρμογές .NET δεν αποτελεί πλέον μια εξειδικευμένη εργασία — είναι μια βασική απαίτηση για αποθέματα, εφοδιαστική αλυσίδα και λύσεις κινητής σάρωσης. Σε αυτόν τον οδηγό θα **μάθετε πώς να χρησιμοποιείτε το Aspose.BarCode** για να διαμορφώσετε ένα barcode DataMatrix με εκτεταμένο κείμενο κώδικα, να δημιουργήσετε την εικόνα και να την επαληθεύσετε προγραμματιστικά. Θα δείτε γιατί αυτή η προσέγγιση είναι ιδανική για τη δημιουργία barcode για αποθέματα και πώς εντάσσεται σε έργα .NET Core ή .NET 6.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη χρειάζεται;** Aspose.BarCode for .NET  
- **Ποιος τύπος barcode;** DataMatrix with extended code text  
- **Μπορώ να χρησιμοποιήσω .NET Core / .NET 6;** Yes, the API is cross‑platform  
- **Χρειάζομαι άδεια για δοκιμές;** A free trial works for development; a license is required for production  
- **Πόσο διαρκεί η υλοποίηση;** About 10‑15 minutes for a basic example  

## Τι είναι το Aspose.BarCode για .NET;
Το Aspose.BarCode για .NET είναι μια εμπορική βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν και να αναγνωρίζουν περισσότερα από 30 σύμβολα barcode, συμπεριλαμβανομένων των DataMatrix, QR και Code 128, και να παράγουν εικόνες έως 10.000 × 10.000 pixel χωρίς εξωτερικές εξαρτήσεις. Υποστηρίζει .NET Framework 4.5+, .NET Core 3.1+ και .NET 5/6/7.

## Γιατί να χρησιμοποιήσετε εκτεταμένο κείμενο κώδικα DataMatrix;
Το εκτεταμένο κείμενο κώδικα DataMatrix σας επιτρέπει να ενσωματώσετε πολλαπλά σχήματα κωδικοποίησης — UTF‑8, C40, Text, X12 — σε ένα μόνο σύμβολο, επιτρέποντας έως **3116 codewords** (περίπου 155 KB δεδομένων) σε ένα συμπαγές τετράγωνο. Αυτή η δυνατότητα είναι ιδανική για πολυγλωσσική σήμανση προϊόντων, παρακολούθηση ιατρικών συσκευών και έξυπνη συσκευασία όπου χρειάζεται να συνδυάσετε αλφαριθμητικά IDs με δυαδικά payloads.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Aspose.BarCode for .NET** – κατεβάστε το από την επίσημη ιστοσελίδα **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Περιβάλλον ανάπτυξης .NET** – Visual Studio, Rider ή VS Code με το .NET SDK.  
3. **Βασικές γνώσεις C#** – θα πρέπει να είστε άνετοι με κλάσεις, namespaces και την οδηγία `using`.

## Εισαγωγή namespaces

Προσθέστε τα απαιτούμενα namespaces στην αρχή του αρχείου C# ώστε ο μεταγλωττιστής να γνωρίζει πού βρίσκονται οι κλάσεις barcode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Αυτά τα namespaces σας δίνουν πρόσβαση τόσο στη δημιουργία όσο και στην αναγνώριση barcode.

## Πώς να διαμορφώσετε εκτεταμένο κείμενο κώδικα DataMatrix;

Φορτώστε τον builder, προσθέστε τα επιθυμητά τμήματα και αφήστε το Aspose.BarCode να διαχειριστεί αυτόματα τα σήματα ECI. Αυτή η παράγραφος απάντησης σας καθοδηγεί στα ακριβή βήματα: δημιουργήστε ένα `DataMatrixExtCodetextBuilder`, προσθέστε τμήματα Unicode, C40, απλό κείμενο και Text mode, και στη συνέχεια ανακτήστε το συνδυασμένο string για τον δημιουργό.

### Βήμα 1: Ορισμός φακέλου εξόδου

Καθορίστε πού θα αποθηκευτεί η παραγόμενη εικόνα barcode. Αντικαταστήστε το placeholder με ένα έγκυρο μονοπάτι στο σύστημά σας.

```csharp
string path = "Your Directory Path";
```

### Βήμα 2: Δημιουργία εκτεταμένου κειμένου κώδικα

`DataMatrixExtCodetextBuilder` είναι μια βοηθητική κλάση που συναρμολογεί το εκτεταμένο κείμενο κώδικα σύμφωνα με την προδιαγραφή DataMatrix. Εισάγει αυτόματα τα απαιτούμενα σήματα ECI (Extended Channel Interpretation).

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Αυτό το παράδειγμα δείχνει πώς μπορείτε να συνδυάσετε χαρακτήρες Unicode, κωδικοποίηση C40, απλό κείμενο και Text mode σε ένα μόνο σύμβολο DataMatrix.

### Βήμα 3: Δημιουργία του τελικού string κώδικα

Αφού διαμορφώσετε όλα τα μέρη, ανακτήστε το συνδυασμένο string που το Aspose.BarCode θα ενσωματώσει στο barcode.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Βήμα 4: Δημιουργία του barcode DataMatrix

`BarcodeGenerator` είναι η κεντρική κλάση που παράγει εικόνες barcode. Δημιουργήστε την με `EncodeTypes.DataMatrix` και το εκτεταμένο κείμενο κώδικα, στη συνέχεια ορίστε παραμέτρους εμφάνισης όπως η διάσταση X, η μορφή εικόνας και το προαιρετικό κείμενο που διαβάζεται από άνθρωπο.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Ο παραπάνω κώδικας **δημιουργεί barcode aspose .net** με το επιθυμητό εκτεταμένο κείμενο κώδικα και το αποθηκεύει ως αρχείο PNG.

### Βήμα 5: Επαλήθευση του barcode διαβάζοντάς το ξανά

`BarCodeReader` επαληθεύει ότι το παραγόμενο σύμβολο μπορεί να αποκωδικοποιηθεί σωστά, κάτι που είναι απαραίτητο για αυτοματοποιημένες δοκιμές και διασφάλιση ποιότητας.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Αν όλα έχουν ρυθμιστεί σωστά, η κονσόλα θα εμφανίσει το ακριβές εκτεταμένο κείμενο κώδικα που δημιουργήσατε νωρίτερα.

## Συνηθισμένα προβλήματα και αντιμετώπιση

| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| Το barcode δεν διαβάζεται | Η διάσταση X είναι πολύ μικρή | Αυξήστε το `XDimension.Pixels` (π.χ., 4 → 6) |
| Παραμορφωμένοι χαρακτήρες | Λάθος κωδικοποίηση ECI | Βεβαιωθείτε ότι το `ECIEncodings.UTF8` ταιριάζει με το σύνολο χαρακτήρων |
| Το αρχείο δεν αποθηκεύτηκε | Μη έγκυρο μονοπάτι | Χρησιμοποιήστε απόλυτο μονοπάτι ή βεβαιωθείτε ότι ο φάκελος υπάρχει |
| Απόκλιση άδειας | Η δοκιμαστική έκδοση έληξε | Εφαρμόστε προσωρινή ή πλήρη άδεια (δείτε Συχνές Ερωτήσεις) |

## Συχνές ερωτήσεις

### Ε1: Τι είναι το Aspose.BarCode για .NET;
A1: Το Aspose.BarCode για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν και να αναγνωρίζουν μια μεγάλη ποικιλία συμβόλων barcode, συμπεριλαμβανομένων των DataMatrix, QR, Code128 και άλλων.

### Ε2: Πού μπορώ να βρω την τεκμηρίωση για το Aspose.BarCode για .NET;
A2: Μπορείτε να έχετε πρόσβαση στην πλήρη αναφορά API **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Ε3: Υπάρχει δωρεάν δοκιμαστική έκδοση για το Aspose.BarCode για .NET;
A3: Ναι, μια δωρεάν δοκιμαστική έκδοση μπορεί να ληφθεί από **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Ε4: Πώς μπορώ να αποκτήσω προσωρινή άδεια για δοκιμές;
A4: Παρέχονται προσωρινές άδειες για σκοπούς αξιολόγησης και μπορούν να ζητηθούν από τη **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Ε5: Πού μπορώ να λάβω υποστήριξη ή να θέσω ερωτήσεις σχετικά με το Aspose.BarCode για .NET;
A5: Το επίσημο φόρουμ Aspose.BarCode είναι το καλύτερο μέρος για βοήθεια: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Τελευταία ενημέρωση:** 2026-09-23  
**Δοκιμή με:** Aspose.BarCode 24.11 for .NET  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}