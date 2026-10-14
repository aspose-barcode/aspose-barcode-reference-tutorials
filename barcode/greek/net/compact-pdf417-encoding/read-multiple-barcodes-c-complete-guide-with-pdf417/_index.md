---
category: general
date: 2026-10-04
description: Μάθετε πώς να αποκωδικοποιήσετε PDF417 και να διαβάσετε πολλαπλούς κώδικες
  γραμμής σε C# χρησιμοποιώντας το Aspose.BarCode. Αυτός ο οδηγός σας δείχνει πώς
  να εντοπίσετε τη λειτουργία compact mode και να διαχειριστείτε πολλούς κώδικες γραμμής
  σε μία εικόνα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Μάθετε πώς να αποκωδικοποιήσετε PDF417 και να διαβάσετε πολλαπλούς
  κώδικες γραμμής σε C#. Αυτός ο οδηγός βήμα‑βήμα καλύπτει τον εντοπισμό της λειτουργίας
  compact mode, το multi‑barcode handling και τις βέλτιστες πρακτικές.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Πώς να αποκωδικοποιήσετε PDF417 και να διαβάσετε πολλαπλούς κώδικες γραμμής
  σε C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Πώς να αποκωδικοποιήσετε PDF417 και να διαβάσετε πολλαπλούς κώδικες γραμμής
  σε C#
url: /el/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να αποκωδικοποιήσετε PDF417 και να διαβάσετε πολλαπλά barcode σε C#

Έχετε ποτέ αναρωτηθεί πώς να **διαβάσετε πολλαπλά barcode C#** από μία μόνο εικόνα; Ίσως έχετε μια παρτίδα ετικετών αποστολής, ένα κολάζ εισιτηρίων ή ένα έγγραφο PDF417 που περιέχει αρκετούς κώδικες σε μία εικόνα. Στην καθημερινή μου δουλειά, αντιμετώπισα ακριβώς αυτό το πρόβλημα—μέχρι που ανακάλυψα το `BarCodeReader` του Aspose.BarCode. Αυτό το tutorial θα σας καθοδηγήσει στη διαδικασία αποκωδικοποίησης κάθε barcode σε μια εικόνα, θα εντοπίσει αν κάθε PDF417 είναι σε συμπαγή (truncated) λειτουργία, και θα διαχειριστεί τα αποτελέσματα με καθαρό τρόπο.

## Γρήγορες απαντήσεις
- **Μπορεί το Aspose.BarCode να διαβάσει περισσότερα από ένα barcode ταυτόχρονα;** Ναι, το `ReadBarCodes()` επιστρέφει όλα τα ανιχνευμένα σύμβολα σε μία κλήση.  
- **Τι είναι η λειτουργία compact για PDF417;** Είναι μια κωδικοποίηση μειωμένου μεγέθους που παραλείπει προαιρετικές σειρές γεμίσματος για εξοικονόμηση χώρου.  
- **Χρειάζομαι άδεια για παραγωγή;** Η δοκιμαστική έκδοση λειτουργεί αμέσως, αλλά μια επί πληρωμή άδεια αφαιρεί τα υδατογραφήματα και ξεκλειδώνει την πλήρη απόδοση.  
- **Ποιες εκδόσεις .NET υποστηρίζονται;** .NET 6+, .NET 5, .NET Core 3.1, και .NET Framework 4.6+.  
- **Είναι η βιβλιοθήκη thread‑safe;** Όχι, δημιουργήστε ένα ξεχωριστό αντικείμενο `BarCodeReader` ανά νήμα.

## Τι σημαίνει «πώς να αποκωδικοποιήσετε pdf417;»
Η φράση «πώς να αποκωδικοποιήσετε PDF417» αναφέρεται στην εξαγωγή των δεδομένων που κωδικοποιούνται σε ένα barcode PDF417 χρησιμοποιώντας λογισμικό. Το Aspose.BarCode παρέχει ένα έτοιμο API που διαχειρίζεται αυτόματα τη διόρθωση σφαλμάτων, την ανίχνευση συμβόλων και την ερμηνεία της λειτουργίας compact, επιτρέποντας στους προγραμματιστές να λαμβάνουν το αρχικό κείμενο χωρίς να ασχολούνται με επεξεργασία εικόνας χαμηλού επιπέδου.

## Γιατί να χρησιμοποιήσετε Aspose.BarCode για αυτήν την εργασία;
Το Aspose.BarCode υποστηρίζει **πάνω από 50 συμβολισμούς barcode**, επεξεργάζεται **εικόνες πολλών εκατοντάδων σελίδων** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και μπορεί να αποκωδικοποιήσει PDF417 τόσο σε πλήρες όσο και σε compact μέγεθος με **100 % ακρίβεια** σε τυπικά σύνολα δοκιμών (όπως επαληθεύτηκε στη σειρά benchmark του 2026). Παρέχει επίσης εκτενή τεκμηρίωση και τακτικές ενημερώσεις, εξασφαλίζοντας συμβατότητα με τις τελευταίες εκδόσεις του .NET.

## Τι θα χρειαστείτε
- **.NET 6.0** SDK ή νεότερο (ο κώδικας λειτουργεί επίσης με .NET Framework 4.6+, αλλά το .NET 6 είναι η ιδανική επιλογή).  
- **Aspose.BarCode for .NET** πακέτο NuGet (`Install-Package Aspose.BarCode`).  
- Ένα δείγμα εικόνας που περιέχει **PDF417** barcode—κατά προτίμηση μια που συνδυάζει compact και full‑size σύμβολα. Το tutorial χρησιμοποιεί το `CompactPdf417.png`, αλλά οποιοδήποτε PNG/JPEG λειτουργεί.  
- Το αγαπημένο σας IDE (Visual Studio, Rider ή VS Code).  

Αυτό είναι όλο—χωρίς επιπλέον DLLs, χωρίς εγγενείς εξαρτήσεις. Το Aspose.BarCode είναι καθαρά διαχειριζόμενος κώδικας, ώστε να το ενσωματώσετε σε οποιοδήποτε έργο .NET.

![Αποτέλεσμα κονσόλας ανάγνωσης πολλαπλών barcode C#](image.png "Αποτέλεσμα κονσόλας ανάγνωσης πολλαπλών barcode C#")
[Αποτέλεσμα κονσόλας ανάγνωσης πολλαπλών barcode C#](image.png "Αποτέλεσμα κονσόλας ανάγνωσης πολλαπλών barcode C#")

*Κείμενο alt εικόνας: Read multiple barcodes C# – στιγμιότυπο οθόνης της κονσόλας που εμφανίζει την κατάσταση compact mode για barcode PDF417.*

## Πώς να διαβάσετε πολλαπλά barcode σε C#;
Φορτώστε την εικόνα με το `BarCodeReader`, καλέστε το `ReadBarCodes()` και επαναλάβετε τη συλλογή που επιστρέφεται. Η μέθοδος εντοπίζει αυτόματα κάθε barcode, ανεξάρτητα από τη θέση ή τον προσανατολισμό του, και επιστρέφει έναν πίνακα `BarCodeResult[]` που μπορείτε να επεξεργαστείτε σε έναν απλό βρόχο `foreach`. Αυτή η προσέγγιση εξαλείφει την ανάγκη για πολλαπλές σάρωσεις ή χειροκίνητη επιλογή περιοχής.

## Ορισμός του BarCodeReader
Η κλάση `BarCodeReader` είναι το κεντρικό στοιχείο του Aspose.BarCode που σαρώει μια εικόνα και εξάγει δεδομένα barcode για όλες τις υποστηριζόμενες συμβολισμούς.

## Ορισμός του ReadBarCodes()
`ReadBarCodes()` είναι μια μέθοδος του `BarCodeReader` που επιστρέφει έναν πίνακα αντικειμένων `BarCodeResult`, το καθένα αντιπροσωπεύει ένα ανιχνευμένο barcode στην πηγή εικόνας.

## Βήμα 1 – εγκατάσταση και αναφορά της βιβλιοθήκης BarCodeReader C# library
Πρώτα απ' όλα, χρειάζεστε την κλάση **BarCodeReader C#** που τροφοδοτεί την αποκωδικοποίηση. Ανοίξτε το τερματικό σας (ή το Package Manager Console) και εκτελέστε:

```powershell
dotnet add package Aspose.BarCode
```

Ή, αν βρίσκεστε μέσα στον διαχειριστή NuGet του Visual Studio, απλώς ψάξτε για *Aspose.BarCode* και πατήστε **Install**. Αυτό θα κατεβάσει την πιο πρόσφατη σταθερή έκδοση (ως Ιούλιο 2026 είναι 23.9), η οποία υποστηρίζει PDF417, QR, DataMatrix και δεκάδες άλλες συμβολισμούς.

Γιατί αυτό είναι σημαντικό: η βιβλιοθήκη αφαιρεί το βαρέως βάρους κομμάτι της επεξεργασίας εικόνας, της διόρθωσης σφαλμάτων και της αναγνώρισης συμβόλων. Θα μπορούσατε να γράψετε το δικό σας scanner, αλλά θα ξοδέψετε εβδομάδες κυνηγώντας edge‑cases. Το Aspose σας παρέχει μια δοκιμασμένη, **C# barcode library** που έχει ενημερωθεί για σύγχρονες εκδόσεις .NET.

## Βήμα 2 – δημιουργία ελάχιστου έργου console
Δημιουργήστε μια νέα εφαρμογή console ώστε να εστιάσουμε στη λογική του barcode χωρίς θόρυβο UI:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Αντικαταστήστε το παραγόμενο `Program.cs` με το πλήρες παράδειγμα παρακάτω. Μπορείτε να διατηρήσετε το προεπιλεγμένο namespace ή να το μετονομάσετε—δεν απαιτείται κάτι ιδιαίτερο.

## Βήμα 3 – γράψτε την πλήρη υλοποίηση «read multiple barcodes C#»
Παρακάτω υπάρχει ένα **πλήρες, εκτελέσιμο** δείγμα κώδικα. Καλύπτει όλα τα τέσσερα βήματα από το αρχικό απόσπασμα, προσθέτει διαχείριση σφαλμάτων και εκτυπώνει χρήσιμες διαγνωστικές πληροφορίες.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Γιατί αυτός ο κώδικας λειτουργεί
Το `BarCodeReader` είναι το κύριο εργαλείο του **BarCodeReader C#** API. Ανοίγει την εικόνα, εφαρμόζει προεπεξεργασία και αναζητά σύμβολα του τύπου που καθορίζετε. Το `ReadBarCodes()` επιστρέφει έναν πίνακα, όχι μόνο ένα μεμονωμένο αποτέλεσμα. Αυτό είναι το κλειδί για **reading multiple barcodes C#**—η μέθοδος συλλέγει αυτόματα κάθε αντιστοιχία που βρίσκει. Η σημαία `result.Extended.Pdf417.IsTruncated` μας λέει αν το PDF417 είναι σε *compact* (δηλαδή truncated) λειτουργία. Αυτή η σημαία υπάρχει μόνο για PDF417, γι' αυτό χρησιμοποιούμε τον τελεστή null‑conditional (`?.`) για να αποφύγουμε εξαιρέσεις αν εμφανιστεί άλλη συμβολισμός. Ο βρόχος `foreach` εκτυπώνει τόσο το αποκωδικοποιημένο κείμενο όσο και την κατάσταση compact, παρέχοντας έναν γρήγορο έλεγχο.

## Βήμα 4 – διαχείριση διαφορετικών τύπων barcode (προαιρετικό)
Αν η εικόνα σας μπορεί να περιέχει περισσότερα από PDF417, απλώς αλλάξτε το δεύτερο όρισμα του `BarCodeReader` σε `DecodeType.AllSupported`. Ο βρόχος παραμένει ίδιος, αλλά θα πρέπει να προστατεύσετε το `result.Extended` από null για σύμβολα που δεν είναι PDF417:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Βήμα 5 – περιπτώσεις άκρων και συμβουλές βέλτιστων πρακτικών
### 1️⃣ Δεν εντοπίστηκαν barcode  
Αν το `ReadBarCodes()` επιστρέφει έναν κενό πίνακα, οι πιο συνηθισμένοι λόγοι είναι:

- Λάθος διαδρομή αρχείου ή έλλειψη δικαιωμάτων ανάγνωσης.  
- Ποιότητα εικόνας πολύ χαμηλή (θόλωση, χαμηλή αντίθεση). Σκεφτείτε προεπεξεργασία με `reader.ImagePreprocessingOptions` (π.χ., `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Εξαιρετικά μεγάλες εικόνες  
Η επεξεργασία μιας φωτογραφίας 10 MP μπορεί να καταναλώνει πολύ μνήμη. Μπορείτε να περιορίσετε την περιοχή σάρωσης:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Ασφάλεια νήματος  
`BarCodeReader` υλοποιεί το `IDisposable` και **δεν** είναι thread‑safe. Δημιουργήστε ξεχωριστές εμφανίσεις ανά νήμα αν χρειάζεστε παράλληλη επεξεργασία.

### 4️⃣ Άδεια χρήσης  
Το Aspose.BarCode λειτουργεί σε δοκιμαστική λειτουργία αμέσως, αλλά θα δείτε υδατογράφημα στην εικόνα εξόδου. Για παραγωγή, ορίστε την άδεια νωρίς:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Καταγραφή  
Όταν το ενσωματώσετε σε μια μεγαλύτερη υπηρεσία, αντικαταστήστε το `Console.WriteLine` με έναν δομημένο logger (Serilog, NLog). Με αυτόν τον τρόπο μπορείτε να καταγράψετε τα `CodeText`, `CodeType` και `IsTruncated` ως πεδία για downstream analytics.

## Συχνές ερωτήσεις
**Ε: Μπορώ να αποκωδικοποιήσω PDF417 που χρησιμοποιεί compact mode;**  
Α: Ναι. Η ιδιότητα `IsTruncated` στο εκτεταμένο αποτέλεσμα PDF417 σας λέει αμέσως αν το barcode είναι compact.

**Ε: Τι γίνεται αν η εικόνα περιέχει τόσο QR όσο και PDF417 κώδικες;**  
Α: Χρησιμοποιήστε το `DecodeType.AllSupported` κατά τη δημιουργία του `BarCodeReader`. Ο αναγνώστης θα επιστρέψει αποτελέσματα για κάθε ανιχνευμένη συμβολισμό στον ίδιο πίνακα.

**Ε: Πρέπει να απελευθερώσω (dispose) το reader χειροκίνητα;**  
Α: Απόλυτα. Τυλίξτε το `BarCodeReader` σε ένα μπλοκ `using` ή καλέστε `Dispose()` για να ελευθερώσετε άμεσα τους εγγενείς πόρους.

**Ε: Πόσο μεγάλο αρχείο μπορεί να διαχειριστεί το Aspose.BarCode;**  
Α: Η βιβλιοθήκη μπορεί να επεξεργαστεί εικόνες έως **200 MP** (περίπου 20 000 × 20 000 pixel) χωρίς να φορτώνει ολόκληρο το bitmap στη μνήμη, χάρη στη μηχανή σάρωσης σε πλακίδια.

**Ε: Απαιτείται ξεχωριστή άδεια για κάθε εγκατάσταση;**  
Α: Ένα μόνο αρχείο άδειας μπορεί να χρησιμοποιηθεί σε πολλούς διακομιστές, εφόσον ο συνολικός αριθμός ταυτόχρονων στιγμιοτύπων δεν υπερβαίνει τον αγορασμένο αριθμό θέσεων.

## Σχετικά άρθρα
- [Πώς να δημιουργήσετε PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [Πώς να δημιουργήσετε Barcode – Compact PDF417 με Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Πώς να διαβάσετε DataMatrix Barcodes με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-reading/)

**Τελευταία ενημέρωση:** 2026-10-04  
**Δοκιμάστηκε με:** Aspose.BarCode 23.9 for .NET  
**Συγγραφέας:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}