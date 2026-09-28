---
date: 2026-09-28
description: Μάθετε πώς να δημιουργήσετε 2d matrix barcode με Aspose.BarCode for .NET
  – ένας οδηγός βήμα‑βήμα για τη δημιουργία κωδικών DotCode με εκτεταμένο κείμενο
  κώδικα.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Διαμόρφωση Εκτεταμένου Κειμένου Κώδικα DotCode
og_description: Μάθετε να δημιουργείτε 2d matrix barcode χρησιμοποιώντας Aspose.BarCode
  for .NET. Αυτός ο οδηγός δείχνει βήμα‑βήμα πώς να δημιουργήσετε κωδικούς DotCode
  με εκτεταμένο κείμενο κώδικα.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Δημιουργία 2d matrix barcode με Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Πώς να δημιουργήσετε 2d matrix barcode με Aspose.BarCode for .NET
url: /el/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε 2d matrix barcode μέσω Aspose.BarCode για .NET

## Εισαγωγή

Στον χώρο της δημιουργίας και διαχείρισης barcode, το Aspose.BarCode για .NET ξεχωρίζει ως μια ευέλικτη λύση που υποστηρίζει **50+ μορφές εισόδου και εξόδου** και μπορεί να επεξεργαστεί έγγραφα με εκατοντάδες σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Είτε χρειάζεστε barcode για παρακολούθηση προϊόντων, έλεγχο αποθεμάτων ή εφαρμογές πλούσιες σε δεδομένα, η δημιουργία ενός **2d matrix barcode** όπως το DotCode με εκτεταμένο κείμενο κώδικα σας επιτρέπει να ενσωματώσετε τόσο κειμενικά όσο και δυαδικά δεδομένα σε ένα συμπαγές τετράγωνο σύμβολο. Αυτός ο οδηγός σας καθοδηγεί στη δημιουργία του εκτεταμένου κειμένου κώδικα βήμα‑βήμα και στην απόδοση της τελικής εικόνας.

## Σύντομες απαντήσεις
- **Τι σημαίνει “create dotcode extended codetext”**; Σημαίνει τη δημιουργία ενός DotCode barcode που περιλαμβάνει FNC1, ECICodetext, απλό κείμενο και διαχωριστές συμβόλων σε ένα ενιαίο εκτεταμένο payload.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.BarCode for .NET.  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Πόσο χρόνο διαρκεί η υλοποίηση;** Περίπου 10‑15 λεπτά για ένα βασικό παράδειγμα.

## Πώς να δημιουργήσετε dotcode extended codetext

Φορτώστε το έργο σας, ορίστε τον φάκελο, δημιουργήστε το εκτεταμένο κείμενο κώδικα και δημιουργήστε την εικόνα – όλα σε λιγότερο από δώδεκα γραμμές κώδικα. Η παρακάτω άμεση απάντηση συνοψίζει όλη τη διαδικασία:

Φορτώστε το `BarcodeGenerator` με `EncodeTypes.DotCode`, δημιουργήστε το εκτεταμένο κείμενο κώδικα χρησιμοποιώντας το `DotCodeExtendedCodetextBuilder` (προσθέτοντας FNC1, ECICodetext, απλό κείμενο και διαχωριστές FNC3), στη συνέχεια καλέστε το `Save` για να γράψετε ένα αρχείο PNG. Αυτή η ακολουθία δημιουργεί ένα πλήρως συμβατό 2d matrix barcode με μία κλήση.

## Τι είναι το dotcode extended codetext;

Το **dotcode extended codetext** είναι μια σύνθετη συμβολοσειρά που συνδυάζει πολλαπλά τμήματα δεδομένων—όπως αναγνωριστικά FNC1, ECICodetext, απλό κείμενο και διαχωριστές FNC3—σε ένα payload που μπορεί να αποκωδικοποιήσει το DotCode. Επιτρέπει την κωδικοποίηση πολυγλωσσικού κειμένου, δυαδικών δεδομένων και δομημένων δεδομένων μέσα σε ένα ενιαίο 2d matrix barcode, καθιστώντας το ιδανικό για αλυσίδες εφοδιασμού, υγειονομική περίθαλψη και σενάρια IoT.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για αυτήν την εργασία;

Το Aspose.BarCode επεξεργάζεται **έως 500 σελίδες ανά δευτερόλεπτο** σε τυπικό εξοπλισμό διακομιστή και υποστηρίζει **πάνω από 30 συμβολισμούς barcode**, συμπεριλαμβανομένου του DotCode. Το API `GetExtendedCodetext` εγγυάται τη σωστή τοποθέτηση των χαρακτήρων ελέγχου, εξαλείφοντας τα σφάλματα χειροκίνητης συνένωσης συμβολοσειρών και διασφαλίζοντας τη συμμόρφωση με το ISO/IEC 24724. Επιπλέον, προσφέρει ενσωματωμένη διόρθωση σφαλμάτων και αυτόματη διαχείριση της ζώνης ησυχίας, μειώνοντας την ανάγκη χειροκίνητης ρύθμισης.

## Προαπαιτούμενα

- **Aspose.BarCode for .NET** – κατεβάστε από την [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- Ένα περιβάλλον ανάπτυξης .NET (συνιστάται Visual Studio 2022 ή νεότερο).  
- Προαιρετικά: ένα προσωρινό αρχείο άδειας για αξιολόγηση.

## Εισαγωγή ονομάτων χώρων

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Αυτοί οι χώροι ονομάτων εκθέτουν την κλάση `BarcodeGenerator` και το βοηθητικό `DotCodeExtendedCodetextBuilder` που χρειάζεται για το παράδειγμα.

```csharp
using Aspose.BarCode.Generation;
```

Τώρα που καλύψαμε τα προαπαιτούμενα, ας αναλύσουμε τη διαδικασία δημιουργίας του DotCode Extended Code Text σε έναν οδηγό βήμα‑βήμα.

## Βήμα 1: ορίστε τη διαδρομή του φακέλου

Καθορίστε πού θα αποθηκευτεί το παραγόμενο PNG. Χρησιμοποιήστε απόλυτη ή σχετική διαδρομή που η εφαρμογή σας μπορεί να γράψει.

```csharp
string path = "Your Directory Path";
```

Αντικαταστήστε το `"Your Directory Path"` με την πραγματική διαδρομή στο σύστημά σας.

## Βήμα 2: δημιουργήστε dotcode extended codetext

Η κλάση `DotCodeExtendedCodetextBuilder` συναρμολογεί τα διάφορα τμήματα σε μια ενιαία συμβολοσειρά εκτεταμένου κώδικα.

Για να δημιουργήσετε το DotCode Extended Code Text, ακολουθήστε τα παρακάτω υπο‑βήματα:

### 2.1 προσθήκη αναγνωριστικού μορφής fnc1

Το αναγνωριστικό μορφής FNC1 σηματοδοτεί την έναρξη ενός νέου πεδίου δεδομένων. Απαιτείται για σύμβολα DotCode συμβατά με GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 προσθήκη ecicodetext

Το ECICodetext κωδικοποιεί ειδικούς χαρακτήρες και διεθνές κείμενο. Σε αυτό το παράδειγμα κωδικοποιούμε το `"犬Right狗"` χρησιμοποιώντας UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 προσθήκη plain codetext

Μπορείτε επίσης να προσθέσετε απλό κείμενο στο DotCode Extended Code Text. Εδώ, προσθέτουμε το `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 προσθήκη διαχωριστή συμβόλου fnc3

Ο διαχωριστής συμβόλου FNC3 διαχωρίζει διαφορετικές ενότητες του κώδικα, βελτιώνοντας την αναγνωσιμότητα για τους σαρωτές.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 προσθήκη αρχικοποίησης αναγνώστη fnc3

Αυτό το βήμα προσθέτει τις πληροφορίες Αρχικοποίησης Αναγνώστη FNC3, που ενημερώνουν τον σαρωτή πώς να ερμηνεύσει τα επόμενα δεδομένα.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 δημιουργία codetext

Τώρα δημιουργήστε το DotCode Extended Codetext καλώντας τη μέθοδο `GetExtendedCodetext` στο αντικείμενο `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Βήμα 3: δημιουργήστε την εικόνα dotcode

Αποδώστε την εικόνα barcode από το εκτεταμένο κείμενο κώδικα.

#### 3.1 αρχικοποίηση δημιουργού barcode

Η κλάση `BarcodeGenerator` είναι το βασικό αντικείμενο του Aspose.BarCode για τη δημιουργία οποιουδήποτε barcode. Την δημιουργείτε με την επιθυμητή συμβολή (`EncodeTypes.DotCode`) και το εκτεταμένο κείμενο κώδικα που μόλις κατασκευάσατε.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Τέλος, καλέστε το `Save` για να γράψετε το αρχείο PNG στο δίσκο. Η εικόνα είναι έτοιμη για ενσωμάτωση σε αναφορές, κινητές εφαρμογές ή εκτυπωμένες ετικέτες.

## Συχνά προβλήματα και λύσεις

- **Λανθασμένη κωδικοποίηση** – Βεβαιωθείτε ότι χρησιμοποιείτε `ECIEncodings.UTF8` όταν προσθέτετε πολυγλωσσικό κείμενο· διαφορετικά οι χαρακτήρες μπορεί να εμφανιστούν παραμορφωμένοι.  
- **Σφάλματα πρόσβασης αρχείου** – Επαληθεύστε ότι η εφαρμογή έχει δικαιώματα εγγραφής στον προορισμό.  
- **Λείπει η ζώνη ησυχίας** – Ορίστε `gen.Parameters.Barcode.Margin` εάν οι σαρωτές απαιτούν επιπλέον λευκό χώρο γύρω από το σύμβολο.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το παραγόμενο barcode σε κινητή εφαρμογή;**  
A: Ναι. Η εικόνα PNG που παράγεται από το γεννήτρια μπορεί να ενσωματωθεί σε iOS, Android ή οποιαδήποτε πλατφόρμα κινητής εφαρμογής.

**Q: Τι αν χρειαστεί να κωδικοποιήσω δυαδικά δεδομένα αντί για κείμενο;**  
A: Χρησιμοποιήστε τη μέθοδο `AddECICodetext` με το κατάλληλο `ECIEncodings` (π.χ., `ECIEncodings.Base64`) για να ενσωματώσετε δυαδικά payloads.

**Q: Πώς μπορώ να αλλάξω το μέγεθος του barcode χωρίς να επηρεάσω την αναγνωσιμότητα;**  
A: Ρυθμίστε την ιδιότητα `XDimension.Pixels`; υψηλότερες τιμές αυξάνουν το μέγεθος του μονάδας, ενώ χαμηλότερες τιμές κάνουν το barcode πιο συμπαγές.

**Q: Υπάρχει τρόπος να προσθέσω ζώνη ησυχίας γύρω από το barcode;**  
A: Ναι. Ορίστε `gen.Parameters.Barcode.Margin` για να ορίσετε την επιθυμητή ζώνη ησυχίας σε pixel.

**Q: Υποστηρίζει η βιβλιοθήκη .NET 8;**  
A: Οι τελευταίες εκδόσεις του Aspose.BarCode είναι συμβατές με .NET 8· απλώς αναφερθείτε στην κατάλληλη έκδοση του πακέτου NuGet.

Αν χρειάζεστε περαιτέρω καθοδήγηση ή έχετε ερωτήσεις, μη διστάσετε να επισκεφθείτε την [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) ή να συμμετάσχετε στην κοινότητα στο [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

---

**Τελευταία ενημέρωση:** 2026-09-28  
**Δοκιμή με:** Aspose.BarCode 24.12 for .NET  
**Συγγραφέας:** Aspose

## Σχετικοί Οδηγοί

- [Δημιουργία DotCode Barcode .NET (Auto Mode) με Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Πώς να δημιουργήσετε DataMatrix Barcodes χρησιμοποιώντας Aspose.BarCode για .NET – Οδηγός βήμα‑βήμα](/barcode/net/datamatrix-barcode-configuration/)
- [Πώς να δημιουργήσετε Aztec barcode με Aspose.BarCode για .NET](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}