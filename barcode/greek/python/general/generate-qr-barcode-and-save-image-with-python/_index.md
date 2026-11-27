---
category: general
date: 2026-11-27
description: Δημιουργήστε QR κώδικα σε Python χρησιμοποιώντας το Aspose.Barcode και
  μάθετε πώς να αποθηκεύετε γρήγορα την εικόνα του κώδικα στο δίσκο.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: el
lastmod: 2026-11-27
og_description: Δημιουργήστε κωδικό QR σε Python με το Aspose.Barcode και αποθηκεύστε
  αμέσως την εικόνα του κωδικού. Ακολουθήστε το πλήρες παράδειγμα για να δημιουργήσετε,
  προσαρμόσετε και αποθηκεύσετε κωδικούς QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Δημιουργία QR barcode και αποθήκευση εικόνας με Python – οδηγός βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Δημιουργία QR κώδικα και αποθήκευση εικόνας με Python
url: /el/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία QR barcode και αποθήκευση εικόνας με Python

Αν χρειάζεστε **να δημιουργήσετε QR barcode** σε μια εφαρμογή Python, αυτός ο οδηγός σας δείχνει πώς να το κάνετε χρησιμοποιώντας τη βιβλιοθήκη Aspose.Barcode. Θα μάθετε επίσης τον σωστό τρόπο **να αποθηκεύσετε την εικόνα του barcode** σε τοπικό φάκελο, να ανακτήσετε λεπτομέρειες έκδοσης της βιβλιοθήκης και να διαχειριστείτε εκτεταμένα τμήματα κειμένου (codetext).

Η δημιουργία QR κωδίκων είναι συχνή απαίτηση για συστήματα εισιτηρίων, κινητές πληρωμές και παρακολούθηση προϊόντων. Στο τέλος αυτού του tutorial θα έχετε ένα έτοιμο‑για‑εκτέλεση script που παράγει ένα αρχείο εικόνας QR barcode και εκτυπώνει πληροφορίες έκδοσης για σκοπούς εντοπισμού σφαλμάτων ή συμμόρφωσης.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* Python 3.8 ή νεότερη έκδοση εγκατεστημένη.
* Το πακέτο `aspose-barcode`. Εγκαταστήστε το με `pip install aspose-barcode`.
* Δικαιώματα εγγραφής στον φάκελο όπου θα αποθηκευτεί η εικόνα του barcode.

Δεν απαιτούνται πρόσθετες εξωτερικές υπηρεσίες· η διαδικασία εκτελείται εξ ολοκλήρου τοπικά.

## Βήμα 1: Δημιουργία εκτεταμένου codetext με `ExtCodetextBuilder`

Το εκτεταμένο codetext σάς επιτρέπει να συνδυάσετε απλό κείμενο και τμήματα ECI (Extended Channel Interpretation) σε έναν μόνο QR κώδικα. Αυτό είναι χρήσιμο όταν χρειάζεται να ενσωματώσετε χαρακτήρες από διαφορετικά σύνολα χαρακτήρων, όπως το σύμβολο του ευρώ.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Γιατί είναι σημαντικό αυτό το βήμα:**  
`ExtCodetextBuilder` συναρμολογεί την τελική συμβολοσειρά που θα επεξεργαστεί ο κωδικοποιητής QR. Χωρίς τη δημιουργία του εκτεταμένου codetext, το barcode θα περιείχε μόνο απλούς χαρακτήρες ASCII και δεν θα μπορούσε να αναπαραστήσει σύμβολα ειδικά για την τοπική γλώσσα.

## Βήμα 2: Ανάκτηση της συνδυασμένης εκτεταμένης συμβολοσειράς codetext

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Η έξοδος εμφανίζεται ως:

```
Extended codetext: ABC123[ECI3]€123
```

Ο δείκτης `[ECI3]` σε αγκύλες λέει στον κωδικοποιητή QR να μεταβεί στο καθορισμένο σύνολο χαρακτήρων για τους επόμενους χαρακτήρες.

## Βήμα 3: Δημιουργία του QR barcode χρησιμοποιώντας το εκτεταμένο codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Εξήγηση:**  
`BarcodeGenerator` λαμβάνει δύο ορίσματα: τον τύπο barcode (`QR`) και τα δεδομένα προς κωδικοποίηση (`extended_codetext`). Ο γεννήτορας προετοιμάζει όλες τις εσωτερικές δομές που απαιτούνται για την απόδοση.

## Βήμα 4: Αποθήκευση της παραγόμενης εικόνας barcode

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Γιατί πρέπει να χρησιμοποιήσετε αυτήν την προσέγγιση:**  
Η κλήση του `save` γράφει απευθείας την εικόνα στο δίσκο χρησιμοποιώντας τη μορφή που προκύπτει από την επέκταση του αρχείου. Η μέθοδος υποστηρίζει PNG, JPEG, BMP και TIFF, προσφέροντάς σας ευελιξία για διαφορετικούς καταναλωτές.

### Επαλήθευση της αποθηκευμένης εικόνας

Ανοίξτε το αρχείο `output/qr_extended.png` με οποιονδήποτε προβολέα εικόνων. Θα πρέπει να δείτε έναν QR κώδικα που, όταν σαρωθεί, επιστρέφει τη συμβολοσειρά `ABC123€123`. Οι περισσότερες σύγχρονες εφαρμογές σάρωσης QR σε κινητά διαχειρίζονται αυτόματα το τμήμα ECI.

## Βήμα 5: Ανάκτηση πληροφοριών έκδοσης Aspose.BarCode (προαιρετικό αλλά χρήσιμο)

Η γνώση της ακριβούς έκδοσης της βιβλιοθήκης Aspose.BarCode βοηθά όταν χρειάζεται να αναφέρετε σφάλματα ή να επαληθεύσετε τη συμβατότητα.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Τυπική έξοδος:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Πλήρες script – αντιγράψτε, επικολλήστε και εκτελέστε

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Η εκτέλεση του script παράγει την εικόνα QR code και εκτυπώνει τόσο το εκτεταμένο codetext όσο και τις λεπτομέρειες έκδοσης στην κονσόλα.

## Συνηθισμένες παραλλαγές και ειδικές περιπτώσεις

| Κατάσταση | Συνιστώμενη προσαρμογή |
|-----------|------------------------|
| **Διαφορετικό σύνολο χαρακτήρων** | Αλλάξτε το αναγνωριστικό ECI που περνιέται στη `add_eci_codetext`. Για UTF‑8 χρησιμοποιήστε `5`. |
| **Υψηλότερη διόρθωση σφαλμάτων** | Ορίστε `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` πριν καλέσετε το `save`. |
| **Προσαρμοσμένο μέγεθος εικόνας** | Χρησιμοποιήστε `barcode.parameters.image_width` και `barcode.parameters.image_height` για να ελέγξετε τις διαστάσεις σε εικονοστοιχεία. |
| **Έξοδος μη‑PNG** | Αλλάξτε την επέκταση αρχείου στο `output_path` σε `.jpg` ή `.bmp`. Η βιβλιοθήκη επιλέγει αυτόματα τον σωστό κωδικοποιητή. |

## Pro tips

* **Δημιουργήστε το φάκελο εξόδου** προγραμματιστικά αν ενδέχεται να μην υπάρχει:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Επικυρώστε τον QR code** μετά τη δημιουργία διαβάζοντάς τον ξανά με `aspose.barcode.BarcodeReader`. Αυτό διασφαλίζει ότι τα κωδικοποιημένα δεδομένα ταιριάζουν με τις προσδοκίες, ειδικά όταν χρησιμοποιούνται τμήματα ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Συμβουλή απόδοσης** – επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarcodeGenerator` αν χρειάζεται να δημιουργήσετε πολλούς QR κώδικες σε βρόχο. Επαναρυθμίστε την ιδιότητα `code_text` αντί να δημιουργείτε νέο αντικείμενο σε κάθε επανάληψη.

## Συμπέρασμα

Τώρα γνωρίζετε πώς να **δημιουργήσετε QR barcode** σε Python με Aspose.Barcode, να δημιουργήσετε ένα εκτεταμένο codetext που συνδυάζει απλό κείμενο και τμήματα ECI, και να **αποθηκεύσετε σωστά την εικόνα barcode** στο δίσκο. Το script δείχνει επίσης πώς να ανακτήσετε πληροφορίες έκδοσης της βιβλιοθήκης για εντοπισμό προβλημάτων.

Επόμενα βήματα που μπορείτε να εξερευνήσετε περιλαμβάνουν:

* Προσθήκη λογότυπου ή προσαρμοσμένων χρωμάτων στον QR κώδικα.
* Ενσωμάτωση του QR barcode απευθείας σε PDF με Aspose.PDF.
* Αυτοματοποίηση μαζικής δημιουργίας για μεγάλα σύνολα δεδομένων.

Νιώστε ελεύθεροι να πειραματιστείτε με διαφορετικά payloads, επίπεδα διόρθωσης σφαλμάτων και μορφές εικόνας. Καλή κωδικοποίηση!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στα δικά σας έργα.

- [Πώς να δημιουργήσετε εικόνα QR Code σε Python με Aspose.Barcode – Πλήρης Οδηγός](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Πώς να δημιουργήσετε barcode Code 128 και να αποθηκεύσετε την εικόνα barcode με Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Πώς να δημιουργήσετε barcode DataMatrix σε Python με Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}