---
date: 2026-06-29
description: Μάθετε πώς να δημιουργήσετε barcode Codabar με έλεγχο αθροίσματος χρησιμοποιώντας
  το Aspose.BarCode για .NET. Οδηγός βήμα‑βήμα που καλύπτει τις λειτουργίες ελέγχου
  αθροίσματος Mod10 και Mod16.
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Υπολογισμός ελέγχου αθροίσματος Codabar
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Δημιουργία barcode Codabar με έλεγχο αθροίσματος (Aspose.BarCode .NET)
url: /el/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία γραμμικού κώδικα Codabar με άθροισμα ελέγχου (Aspose.BarCode .NET)

Το Codabar είναι μια ευρέως υιοθετημένη γραμμική συμβολή barcode που χρησιμοποιείται σε εφοδιαστική, βιβλιοθήκες και υγειονομική περίθαλψη. **Η δημιουργία ενός barcode Codabar με άθροισμα ελέγχου** βελτιώνει δραματικά την ακεραιότητα των δεδομένων εντοπίζοντας σφάλματα μεταγραφής πριν προκαλέσουν προβλήματα. Σε αυτό το tutorial θα μάθετε πώς να προσθέσετε άθροισμα ελέγχου όταν *δημιουργείτε barcode Codabar* με το Aspose.BarCode για .NET, και θα δείτε και τις δύο λειτουργίες άθροισης ελέγχου Mod10 και Mod16 σε δράση.

## Σύντομες Απαντήσεις
- **Τι σημαίνει το “add checksum” για το Codabar;** Προσθέτει ένα ψηφίο ανίχνευσης σφάλματος που επικυρώνει τα κωδικοποιημένα δεδομένα.  
- **Ποιες λειτουργίες άθροισης ελέγχου υποστηρίζονται;** Mod10 (standard) and Mod16 (higher‑accuracy).  
- **Χρειάζομαι άδεια για τη χρήση της λειτουργίας;** Yes – a valid Aspose.BarCode for .NET license is required for production.  
- **Ποιες εκδόσεις .NET είναι συμβατές;** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Πού αποθηκεύονται οι παραγόμενες εικόνες;** To the folder you specify in the `path` variable.

## Πώς να δημιουργήσετε barcode Codabar με άθροισμα ελέγχου;
Φορτώστε τα δεδομένα σας, ενεργοποιήστε το άθροισμα ελέγχου, επιλέξτε είτε `CodabarChecksumMode.Mod10` είτε `CodabarChecksumMode.Mod16`, και καλέστε `Save`. Το Aspose.BarCode διαχειρίζεται τον υπολογισμό και προσθέτει αυτόματα το ψηφίο άθροισης ελέγχου, ώστε να λαμβάνετε μια εικόνα έτοιμη για σάρωση με μία μόνο κλήση μεθόδου. Μπορείτε επίσης να καθορίσετε το φάκελο εξόδου, το όνομα αρχείου και τη μορφή εικόνας (π.χ., PNG) κατά την αποθήκευση.

## Γιατί να προσθέσετε άθροισμα ελέγχου σε barcode Codabar;
Η προσθήκη άθροισης ελέγχου μειώνει τα σφάλματα ενός χαρακτήρα έως **99.9%** και εντοπίζει τα περισσότερα λάθη ανταλλαγής θέσεων, κάτι που είναι ουσιώδες για βιομηχανίες όπως οι τράπεζες αίματος, όπου ένα σφάλμα ενός ψηφίου μπορεί να έχει σοβαρές συνέπειες. Επίσης, ικανοποιεί τις κανονιστικές απαιτήσεις για πολλά πρότυπα εφοδιαστικής.

## Προαπαιτούμενα
1. **Aspose.BarCode for .NET** – κατεβάστε την πιο πρόσφατη έκδοση από [εδώ](https://releases.aspose.com/barcode/net/).  
2. **C# development environment** – Visual Studio, VS Code, ή οποιοδήποτε IDE που υποστηρίζει .NET.

Τώρα που όλα είναι ρυθμισμένα, ας προχωρήσουμε στην υλοποίηση.

## Εισαγωγή Namespaces
Η κλάση `BarcodeGenerator` βρίσκεται στο namespace `Aspose.BarCode.Generation`. Εισάγετέ το στην αρχή του αρχείου σας:

`using Aspose.BarCode.Generation;`

## Τι είναι η κλάση BarcodeGenerator;
Η κλάση `BarcodeGenerator` είναι το βασικό αντικείμενο του Aspose.BarCode που δημιουργεί, διαμορφώνει και αποδίδει μια εικόνα barcode. Συμπεριλαμβάνει όλες τις ρυθμίσεις ειδικές για barcode όπως συμβολική, κείμενο, μέγεθος και επιλογές άθροισης ελέγχου, επιτρέποντάς σας να δημιουργείτε εικόνες με μία μόνο κλήση `Save`. Με την τροποποίηση της ιδιότητας `Parameters` μπορείτε να προσαρμόσετε την εμφάνιση, τη λειτουργία κωδικοποίησης και τις δυνατότητες ανίχνευσης σφαλμάτων για οποιονδήποτε υποστηριζόμενο τύπο barcode.

## Βήμα 1: Αρχικοποίηση του Barcode Generator
Δημιουργήστε μια παρουσία της `BarcodeGenerator`, καθορίστε τη συμβολή Codabar και παρέχετε τα δεδομένα που θέλετε να κωδικοποιήσετε. Αντικαταστήστε το `"Your Directory Path"` με τον πραγματικό φάκελο όπου θέλετε να αποθηκευτούν οι εικόνες.

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## Βήμα 2: Δημιουργία barcode Codabar **χωρίς** άθροισμα ελέγχου
Εάν ένα παλαιό σύστημα αναμένει ένα απλό barcode, ορίστε την επιλογή άθροισης ελέγχου σε `Default`. Αυτό απενεργοποιεί οποιοδήποτε επιπλέον ψηφίο.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## Βήμα 3: Δημιουργία barcode Codabar με άθροισμα ελέγχου **Mod10**
Ενεργοποιήστε το άθροισμα ελέγχου και επιλέξτε τον αλγόριθμο Mod10, που είναι η πιο κοινή λειτουργία για το Codabar.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## Βήμα 4: Δημιουργία barcode Codabar με άθροισμα ελέγχου **Mod16**
Για σενάρια υψηλότερης ανίχνευσης σφαλμάτων, μεταβείτε σε Mod16. Η αλλαγή περιορίζεται σε μία μόνο ανάθεση ιδιότητας.

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

Με αυτά τα τέσσερα απλά βήματα έχετε μάθει **πώς να δημιουργήσετε barcode Codabar** με άθροισμα ελέγχου και πώς να εναλλάσσετε μεταξύ των λειτουργιών Mod10 και Mod16 χρησιμοποιώντας το Aspose.BarCode για .NET.

## Συνηθισμένα Προβλήματα και Λύσεις

| Issue | Reason | Fix |
|-------|--------|-----|
| Η παραγόμενη εικόνα είναι κενή | `path` δείχνει σε φάκελο που δεν υπάρχει | Ensure the directory exists or call `Directory.CreateDirectory(path)` before saving |
| Το άθροισμα ελέγχου δεν εφαρμόστηκε | `IsChecksumEnabled` παραμένει στο `Default` | Set `IsChecksumEnabled = EnableChecksum.Yes` before saving |
| Λάθος λειτουργία άθροισης ελέγχου | Χρήση λανθασμένης τιμής enum | Use `CodabarChecksumMode.Mod10` or `CodabarChecksumMode.Mod16` as needed |

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω το άθροισμα ελέγχου Mod16 για κώδικες βιβλίων βιβλιοθηκών;**  
A: Απόλυτα. Το Mod16 παρέχει ισχυρότερη ανίχνευση σφαλμάτων, κάτι που είναι ωφέλιμο για περιβάλλοντα υψηλής παραγωγικότητας όπως οι βιβλιοθήκες.

**Q: Επηρεάζει η ενεργοποίηση του άθροισης ελέγχου την ταχύτητα σάρωσης;**  
A: Το πρόσθετο ψηφίο προσθέτει αμελητέο χρόνο επεξεργασίας· οι περισσότεροι σαρωτές το διαχειρίζονται χωρίς αισθητή καθυστέρηση.

**Q: Πώς μπορώ να επαληθεύσω το άθροισμα ελέγχου προγραμματιστικά;**  
A: Μετά τη δημιουργία του barcode, επανυπολογίστε το άθροισμα ελέγχου χρησιμοποιώντας το ίδιο `CodabarChecksumMode` και συγκρίνετε το με τον τελευταίο χαρακτήρα της κωδικοποιημένης συμβολοσειράς.

**Q: Μπορεί να προσαρμοστεί η εμφάνιση του ψηφίου άθροισης ελέγχου;**  
A: Ναι. Χρησιμοποιήστε τις ρυθμίσεις εμφάνισης του `BarcodeGenerator` (π.χ., `BarHeight`, `ForeColor`) για να μορφοποιήσετε ολόκληρο το barcode, συμπεριλαμβανομένου του ψηφίου άθροισης ελέγχου.

**Q: Τι γίνεται αν χρειαστεί να δημιουργήσω πολλαπλά barcodes σε βρόχο;**  
A: Δημιουργήστε μία μόνο `BarcodeGenerator`, ενημερώστε την ιδιότητα `CodeText` για κάθε επανάληψη και καλέστε `Save` με μοναδικό όνομα αρχείου κάθε φορά.

Αν αντιμετωπίσετε προκλήσεις, η κοινότητα Aspose.BarCode είναι έτοιμη να βοηθήσει στο [Φόρουμ Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Τελευταία Ενημέρωση:** 2026-06-29  
**Δοκιμή με:** Aspose.BarCode 24.11 for .NET  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## Σχετικά Μαθήματα

- [Δημιουργία Codabar Barcode με χαρακτήρες Έναρξης/Τερματισμού στο Aspose.BarCode για .NET](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Πλήρη Μαθήματα και Παραδείγματα του Aspose.BarCode για .NET](/barcode/net/)
- [Δημιουργία DataMatrix Barcode – Οδηγός Pro με Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}