---
category: general
date: 2026-10-14
description: Δημιουργήστε ένα console barcode scanner σε C# που διαβάζει barcode PDF417,
  υποστηρίζει macro PDF417 και αποκωδικοποιεί πολλαπλά barcode από μία εικόνα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Δημιουργήστε ένα console barcode scanner σε C# για γρήγορη ανάγνωση
  barcode PDF417 και macro PDF417 από εικόνες. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς
  να αποκωδικοποιήσετε πολλαπλά barcode σε μία εικόνα.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Δημιουργία console barcode scanner σε C# – πλήρης οδηγός
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Δημιουργία console barcode scanner σε C# – παράδειγμα ανάγνωσης barcode PDF417
url: /el/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία σάρωσης barcode σε κονσόλα με C# – παράδειγμα ανάγνωσης barcode PDF417

`BarCodeReader` είναι η βασική κλάση του Aspose.BarCode που αποκωδικοποιεί barcode από εικόνες και επιστρέφει λεπτομερή μεταδεδομένα. Αν χρειάζεστε να διαβάσετε δεδομένα barcode PDF417 από μια εικόνα, αυτός ο οδηγός σας δείχνει πώς να το κάνετε με την κλάση **BarCodeReader** σε C#. Θα μάθετε ένα παράδειγμα **δημιουργίας σάρωσης barcode σε κονσόλα** που επίσης διαχειρίζεται macro PDF417 και μπορεί να διαβάσει πολλαπλά barcode σε μία εικόνα.

Η εργασία με barcode συχνά σημαίνει αντιμετώπιση διαφορετικών πηγών εικόνας, μεταβαλλόμενων συνθηκών φωτισμού και μερικές φορές σύνθετων δεδομένων όπως τμήματα macro PDF417. Αυτό το tutorial καλύπτει όλα όσα χρειάζεστε για να αποκωδικοποιήσετε ένα barcode PDF417, να εξάγετε τα εκτεταμένα πεδία του και να επεξεργαστείτε πολλά barcode από την ίδια εικόνα. Στο τέλος θα έχετε ένα εκτελέσιμο πρόγραμμα κονσόλας που διαβάζει barcode από αρχείο εικόνας και εκτυπώνει λεπτομερείς πληροφορίες στην κονσόλα.

## Σύντομες απαντήσεις
- **What does the example do?** Δημιουργεί μια σάρωση barcode σε κονσόλα που διαβάζει barcode PDF417 και macro PDF417 από μια εικόνα και εκτυπώνει όλα τα αποκωδικοποιημένα πεδία.  
- **Which library is required?** Aspose.BarCode for .NET (NuGet).  
- **Can it read multiple barcodes at once?** Ναι – ο αναγνώστης επαναλαμβάνει κάθε barcode που βρέθηκε στην εικόνα.  
- **Do I need an internet connection?** Όχι, η βιβλιοθήκη λειτουργεί πλήρως offline.  
- **What .NET version is supported?** .NET 6.0 ή νεότερη.

## Τι θα χρειαστείτε

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* .NET 6.0 SDK ή νεότερο εγκατεστημένο  
* Μια πρόσφατη έκδοση του **Aspose.BarCode for .NET** πακέτου NuGet (ή οποιαδήποτε συμβατή βιβλιοθήκη που παρέχει `BarCodeReader` και `DecodeType.MacroPdf417`)  
* Ένα αρχείο εικόνας που περιέχει barcode PDF417 ή macro PDF417 (το δείγμα χρησιμοποιεί `ExtPDF417Meta.png`)  
* Έναν επεξεργαστή κώδικα ή IDE όπως το Visual Studio 2022  

Δεν απαιτούνται πρόσθετες υπηρεσίες ή εξωτερικά API.

## Ρύθμιση του έργου για ανάγνωση barcode

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Τοποθετήστε το `ExtPDF417Meta.png` (ή οποιαδήποτε εικόνα που περιέχει barcode PDF417) στο φάκελο του έργου.  
   Για αυτό το tutorial υποθέτουμε ότι το αρχείο βρίσκεται στο `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Το έργο είναι τώρα έτοιμο να μεταγλωττιστεί και να εκτελεστεί το παράδειγμα του αναγνώστη barcode.

## Πώς να δημιουργήσετε μια σάρωση barcode σε κονσόλα με C#;

`BarCodeReader` είναι μια κλάση που παρέχεται από το Aspose.BarCode και διαβάζει barcode από εικόνες και επιστρέφει τα αποκωδικοποιημένα δεδομένα τους.  
Φορτώστε την εικόνα με `BarCodeReader`, ορίστε τον τύπο αποκωδικοποίησης σε `MacroPdf417` και επαναλάβετε τα αποτελέσματα – αυτό είναι ό,τι χρειάζεστε για να δημιουργήσετε μια σάρωση barcode σε κονσόλα. Ο αναγνώστης απελευθερώνει αυτόματα τους εγγενείς πόρους χάρη στη δήλωση `using`, οπότε δεν χρειάζεται να διαχειρίζεστε τη μνήμη χειροκίνητα. Αυτή η προσέγγιση λειτουργεί για οποιαδήποτε μορφή εικόνας υποστηρίζεται από το .NET, όπως PNG, JPEG ή BMP.

### Αναλυτική περιγραφή βήμα προς βήμα

Ο πυρήνας της λύσης είναι ένα μπλοκ `using` που δημιουργεί μια παρουσία `BarCodeReader`, καθορίζει `DecodeType.MacroPdf417` και επαναλαμβάνει κάθε εντοπισμένο barcode. Ο παρακάτω κώδικας είναι ένα πλήρες, αυτόνομο πρόγραμμα που μπορείτε να επικολλήσετε στο `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Why this works**:  

* `DecodeType.MacroPdf417` λέει στον αναγνώστη να ψάξει για την επέκταση macro του PDF417, η οποία μεταφέρει επιπλέον μεταδεδομένα όπως το ID αρχείου, τον αριθμό τμημάτων και χρονικές σφραγίδες.  
* Η δήλωση `using` εγγυάται ότι οι μη διαχειριζόμενοι πόροι (χειριστές αρχείων, εγγενείς buffers αποκωδικοποίησης) απελευθερώνονται άμεσα.  
* Ο βρόχος `foreach` επεξεργάζεται αυτόματα **όλα** τα barcode που περιέχει η εικόνα, ικανοποιώντας την απαίτηση *read multiple barcodes*.

Όταν εκτελέσετε το πρόγραμμα (`dotnet run`), θα πρέπει να δείτε έξοδο παρόμοια με την ακόλουθη:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Αν η εικόνα περιέχει περισσότερα από ένα barcode PDF417, ο βρόχος εκτυπώνει ξεχωριστό μπλοκ για κάθε barcode, δείχνοντας έτσι πώς να **read multiple barcodes** από μία εικόνα.

## Πώς μπορώ να διαβάσω πολλαπλά barcode από μια εικόνα;

Χρησιμοποιήστε μία μόνο παρουσία `BarCodeReader` και ορίστε τη σημαία `DecodeType` ώστε να περιλαμβάνει όλες τις μορφές που θέλετε να εντοπίσετε. Συνδυάζοντας σημαίες με τον τελεστή bitwise OR, μπορείτε να πείτε στη βιβλιοθήκη να ψάξει για PDF417, QR, Code‑128 και πολλές άλλες συμβολές σε μία διαδρομή. Αυτό εξαλείφει την ανάγκη για ξεχωριστούς αναγνώστες και μειώνει το χρόνο επεξεργασίας.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* είναι ένα bitmask, έτσι μπορείτε να συνδυάσετε οποιονδήποτε αριθμό υποστηριζόμενων μορφών. Το Aspose.BarCode υποστηρίζει **30+ barcode symbologies**, συμπεριλαμβανομένων QR, DataMatrix, Code‑128 και UPC‑A, επιτρέποντας σε έναν σάρωνα να χειριστεί διάφορες περιπτώσεις χρήσης όπως σήμανση προϊόντων, επαλήθευση εισιτηρίων και επαλήθευση ταυτότητας.

## Τι είναι το macro PDF417 και πώς να προσπελάσετε τα πεδία του με ασφάλεια;

Macro PDF417 είναι μια επέκταση της συμβολής PDF417 που επιτρέπει σε ένα μεγάλο σύνολο δεδομένων να χωριστεί σε πολλαπλά σύμβολα barcode.  
Macro PDF417 προσθέτει ένα πλούσιο σύνολο εκτεταμένων ιδιοτήτων. Ωστόσο, δεν περιλαμβάνει κάθε barcode όλα τα πεδία. Η πρόσβαση σε μια ιδιότητα που λείπει μπορεί να προκαλέσει `NullReferenceException`. Η πιο ασφαλής προσέγγιση είναι να επαληθεύετε κάθε ιδιότητα πριν την εκτύπωση, εξασφαλίζοντας ότι η εφαρμογή σας παραμένει σταθερή ακόμη και όταν λείπουν τα macro δεδομένα.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Why this matters*: Σε πραγματικές εγκαταστάσεις μπορεί να λάβετε απλά barcode PDF417 που δεν έχουν macro δεδομένα. Ο έλεγχος άμυνας εξασφαλίζει ότι η εφαρμογή σας συνεχίζει να λειτουργεί χωρίς κατάρρευση.

## Συνηθισμένα προβλήματα και βέλτιστες πρακτικές

| Πρόβλημα | Γιατί συμβαίνει | Προτεινόμενη διόρθωση |
|----------|----------------|-----------------------|
| Η διαδρομή της εικόνας είναι λανθασμένη | `BarCodeReader` ρίχνει εξαίρεση αρχείου που δεν βρέθηκε πριν γίνει οποιαδήποτε αποκωδικοποίηση | Χρησιμοποιήστε `Path.Combine` και επαληθεύστε ότι το αρχείο υπάρχει με `File.Exists` |
| Εικόνα χαμηλής ανάλυσης | Ο αποκωδικοποιητής δεν μπορεί να εντοπίσει τις άκρες του barcode, με αποτέλεσμα μηδενικές ανιχνεύσεις | Παρέχετε ελάχιστη ανάλυση 300 dpi για αξιόπιστα αποτελέσματα |
| Barcode περιστραμμένο > 45° | Πολλές βιβλιοθήκες υποθέτουν κάθετη προσανατολισμό | Ενεργοποιήστε `reader.RecognitionOptions.RotateImage = true` εάν η εικόνα μπορεί να είναι περιστραμμένη |
| Λείπουν πεδία macro | Προσπάθεια ανάγνωσης ιδιότητας null προκαλεί κατάρρευση | Πάντα ελέγξτε για `null` πριν προσπελάσετε τις ιδιότητες macro |
| Επεξεργασία μεγάλου batch | Η επαναδημιουργία του reader για κάθε αρχείο προσθέτει επιπλέον φόρτο | Επαναχρησιμοποιήστε μία μόνο παρουσία `BarCodeReader` με διαφορετικά streams όταν επεξεργάζεστε πολλές εικόνες |

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για σάρωση barcode σε κονσόλα;

Aspose.BarCode μπορεί να αποκωδικοποιήσει **30+ τύπους barcode** και επεξεργάζεται εικόνες έως **200 MP** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, επιτυγχάνοντας ρυθμό **150 καρέ ανά δευτερόλεπτο** σε τυπική CPU 3.2 GHz. Αυτές οι μετρήσιμες δυνατότητες το καθιστούν αξιόπιστη επιλογή για λύσεις υψηλού όγκου, on‑premises σάρωσης όπου η καθυστέρηση και η ακρίβεια είναι κρίσιμες.

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να διαβάσετε DataMatrix Barcodes με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Διαβάστε DataMatrix barcode C# – Δημιουργία DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Διαβάστε Barcode από Εικόνα – Κατακτώντας την Εξαγωγή Περιοχής Barcode σε Java με Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Συχνές ερωτήσεις

**Q: Can I use this scanner in a production environment?**  
A: Ναι. Αγοράστε εμπορική άδεια Aspose.BarCode για να αφαιρέσετε το υδατογράφημα αξιολόγησης και να αποκτήσετε πλήρη υποστήριξη.

**Q: Does the library work on Linux and macOS?**  
A: Απόλυτα. Το Aspose.BarCode for .NET είναι cross‑platform και λειτουργεί σε .NET 6+ σε Windows, Linux και macOS.

**Q: How do I handle very large images without exhausting memory?**  
A: Χρησιμοποιήστε τον κατασκευαστή `LoadOptions` για να ενεργοποιήσετε τη λειτουργία streaming, η οποία επεξεργάζεται την εικόνα σε τμήματα αντί να τη φορτώνει ολόκληρη στη RAM.

**Q: Is it possible to decode encrypted or password‑protected images?**  
A: Ο αναγνώστης μπορεί να διαχειριστεί εικόνες κρυπτογραφημένες με τυπικά σχήματα κωδικού PNG/JPEG· απλώς παρέχετε τον κωδικό μέσω `reader.ImagePassword`.

**Q: What if my barcode is partially damaged?**  
A: Ενεργοποιήστε επιλογές διόρθωσης σφαλμάτων όπως `reader.RecognitionOptions.CorrectErrors = true` για να βελτιώσετε την ανθεκτικότητα σε ζημίες ή θόρυβο.

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Σχετικές οδηγίες

- [Πώς να διαβάσετε Pdf417 σε C πλήρες παράδειγμα Barcode Reader](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Διαβάστε πολλαπλά Barcodes C πλήρης οδηγός με Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Αποκωδικοποίηση Barcode από Εικόνα με Παράδειγμα C Barcode Reader](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}