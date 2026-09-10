---
category: general
date: 2026-09-10
description: Κωδικοποιήστε μη‑ASCII χαρακτήρες σε κώδικα QR και αποθηκεύστε την εικόνα
  του QR κώδικα με έναν απλό κατασκευαστή Python. Ακολουθήστε έναν οδηγό βήμα‑βήμα
  χρησιμοποιώντας το ExtCodetextBuilder και το BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: el
lastmod: 2026-09-10
og_description: Κωδικοποιήστε μη‑ASCII χαρακτήρες σε κώδικα QR και αποθηκεύστε την
  εικόνα του κώδικα QR χρησιμοποιώντας Python. Αυτό το σεμινάριο δείχνει πώς να δημιουργήσετε
  εκτεταμένο κείμενο κώδικα, να δημιουργήσετε έναν κώδικα QR και να αποθηκεύσετε την
  εικόνα.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Κωδικοποίηση μη‑ASCII χαρακτήρων σε κώδικα QR και αποθήκευση εικόνας QR
  – βήμα‑βήμα οδηγός Python
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Κωδικοποίηση μη ASCII χαρακτήρων σε κώδικα QR και αποθήκευση εικόνας κώδικα
  QR
url: /el/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κωδικοποίηση μη ASCII χαρακτήρων σε QR code και αποθήκευση εικόνας QR code

Αν χρειάζεται να **κωδικοποιήσετε μη ASCII χαρακτήρες** σε ένα QR code, αυτός ο οδηγός σας δείχνει ακριβώς πώς να το κάνετε και στη συνέχεια **να αποθηκεύσετε την εικόνα QR code** στο δίσκο. Είτε διαχειρίζεστε ρωσικά, κινέζικα ή emoji, το ExtCodetextBuilder σας επιτρέπει να συνδυάσετε απλό κείμενο και τμήματα κωδικοποιημένα με ECI χωρίς χειροκίνητη διαχείριση byte.

Θα μάθετε πώς να δημιουργήσετε μια επεκταμένη συμβολοσειρά codetext, να παράγετε ένα QR code που την καταλαβαίνει, και τέλος να γράψετε την εικόνα του barcode σε αρχείο. Το tutorial υποθέτει βασικές γνώσεις Python και ότι έχετε εγκατεστημένο το SDK `barcode`.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* Εγκατεστημένο Python 3.8+.
* Το πακέτο Python `barcode` (ή το αντίστοιχο SDK) που παρέχει `ExtCodetextBuilder`, `CodetextEncodingType` και `BarcodeGenerator`.
* Δικαιώματα εγγραφής στον φάκελο όπου θέλετε να **αποθηκεύσετε την εικόνα QR code**.

Μπορείτε να εγκαταστήσετε το SDK με pip (αντικαταστήστε `barcode-sdk` με το πραγματικό όνομα του πακέτου):

```bash
pip install barcode-sdk
```

## Βήμα 1: Δημιουργία ενός extended codetext builder

Το πρώτο βήμα είναι η δημιουργία ενός αντικειμένου `ExtCodetextBuilder`. Αυτό το αντικείμενο συλλέγει πολλαπλά τμήματα κειμένου και παράγει μία ενιαία συμβολοσειρά που η συμβολική αναπαράσταση QR code μπορεί να ερμηνεύσει.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Γιατί είναι σημαντικό*: Τα QR codes υποστηρίζουν **extended codetext**, που σημαίνει ότι μπορείτε να ενσωματώσετε διάφορες λειτουργίες κωδικοποίησης (plain, ECI, κ.λπ.) σε ένα barcode. Ο builder αφαιρεί την ανάγκη για χαμηλού επιπέδου μορφοποίηση σύμφωνα με το πρότυπο QR.

## Βήμα 2: Προσθήκη τμήματος plain‑text

Το plain text είναι η προεπιλεγμένη λειτουργία και λειτουργεί για χαρακτήρες ASCII. Η προσθήκη του πρώτα παρέχει μια αναγνώσιμη εναλλακτική λύση για scanners που αγνοούν το ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Αν παραλείψετε αυτό το βήμα, το QR code θα περιέχει μόνο το τμήμα ECI, το οποίο ορισμένοι παλαιότεροι αναγνώστες ενδέχεται να μην αποκωδικοποιήσουν σωστά.

## Βήμα 3: Προσθήκη τμήματος κωδικοποιημένου με ECI για μη‑ASCII χαρακτήρες

Για να συμπεριλάβετε χαρακτήρες εκτός του εύρους ASCII—όπως κυριλλικά, κινέζικα ή emojis—πρέπει να ορίσετε μια κωδικοποίηση ECI (Extended Channel Interpretation). Εδώ χρησιμοποιούμε UTF‑8 για τη ρωσική λέξη “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Γιατί λειτουργεί*: Το πρότυπο QR ορίζει τιμές ECI που λένε στον scanner ποιο σύνολο χαρακτήρων να εφαρμόσει. Χωρίς το σήμα ECI, τα ακατέργαστα byte θα ερμηνευτούν ως ISO‑8859‑1, οδηγώντας σε ακατανόητο αποτέλεσμα.

## Βήμα 4: Ανάκτηση της συνδυασμένης extended codetext συμβολοσειράς

Αφού προσθέσετε όλα τα επιθυμητά τμήματα, καλέστε `get_extended_codetext()` για να λάβετε την τελική συμβολοσειρά που περιμένει ο δημιουργός barcode.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Η εκτυπωμένη τιμή φαίνεται σαν μια σειρά ελεγκτικών χαρακτήρων ακολουθούμενη από το πραγματικό κείμενο, αλλά δεν χρειάζεται ποτέ να την αναλύσετε χειροκίνητα.

## Βήμα 5: Δημιουργία QR code χρησιμοποιώντας το extended codetext

Τώρα δημιουργήστε ένα `BarcodeGenerator`, ορίστε τη συμβολική αναπαράσταση σε QR (η μόνη κοινή 2‑Δ συμβολική αναπαράσταση που υποστηρίζει extended codetext) και περάστε τη συνδυασμένη συμβολοσειρά.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Συμβουλή*: Αν δοκιμάσετε την ίδια διαδικασία με Code‑128 ή DataMatrix, το SDK θα ρίξει εξαίρεση επειδή αυτές οι μορφές δεν μπορούν να ερμηνεύσουν σήματα ECI.

## Βήμα 6: Αποθήκευση της εικόνας QR code

Τέλος, γράψτε το barcode σε αρχείο PNG. Εδώ είναι που **αποθηκεύετε την εικόνα QR code** για μελλοντική χρήση.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Βεβαιωθείτε ότι ο φάκελος `output` υπάρχει ή δημιουργήστε τον με `os.makedirs('output', exist_ok=True)` πριν καλέσετε το `save`.

### Πλήρες εκτελέσιμο παράδειγμα

Συνδυάζοντας όλα τα βήματα παίρνετε ένα αυτόνομο script που μπορείτε να τρέξετε αμέσως:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Αναμενόμενη έξοδος** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Ανοίγοντας το `qr_extended.png` με οποιονδήποτε QR scanner θα εμφανίσει `HelloWorldПривет`. Οι scanners που καταλαβαίνουν το ECI θα εμφανίσουν σωστά τους κυριλλικούς χαρακτήρες· οι άλλοι θα δείξουν μόνο το μέρος ASCII.

## Συχνές ερωτήσεις & ειδικές περιπτώσεις

| Ερώτηση | Απάντηση |
|----------|--------|
| *Μπορώ να χρησιμοποιήσω άλλες κωδικοποιήσεις όπως Shift‑JIS;* | Ναι. Αντικαταστήστε το `CodetextEncodingType.UTF_8` με `CodetextEncodingType.SHIFT_JIS` και δώστε το κατάλληλο κείμενο. |
| *Τι γίνεται αν τα συνδυασμένα δεδομένα υπερβούν τη χωρητικότητα του QR;* | Τα QR codes έχουν όρια έκδοσης (μέχρι 177 × 177 modules). Αν ο builder ρίξει εξαίρεση μεγέθους, είτε αυξήστε το επίπεδο διόρθωσης σφαλμάτων είτε χωρίστε τα δεδομένα σε πολλαπλά QR codes. |
| *Πρέπει να ορίσω συγκεκριμένη έκδοση QR;* | Το SDK επιλέγει αυτόματα τη μικρότερη έκδοση που χωράει τα δεδομένα. Μπορείτε να εξαναγκάσετε μια έκδοση με `qr_generator.set_qr_version(10)` αν χρειαστεί. |
| *Θα είναι η εικόνα διαφανής;* | Από προεπιλογή το SDK γράφει PNG με λευκό φόντο. Χρησιμοποιήστε `qr_generator.set_background_color(Color.Transparent)` πριν το `save` αν χρειάζεστε διαφάνεια. |

## Συμπέρασμα

Σε αυτό το tutorial μάθατε πώς να **κωδικοποιήσετε μη ASCII χαρακτήρες** σε QR code χρησιμοποιώντας το `ExtCodetextBuilder` και στη συνέχεια **να αποθηκεύσετε την εικόνα QR code** με το `BarcodeGenerator`. Η διαδικασία περιλαμβάνει τη δημιουργία μιας extended codetext συμβολοσειράς, την προσθήκη τόσο plain όσο και ECI‑κωδικοποιημένων τμημάτων, τη δημιουργία της QR συμβολικής αναπαράστασης, και τέλος τη γραφή του αρχείου εικόνας.

Από εδώ μπορείτε να εξερευνήσετε:

* Προσθήκη περισσότερων τμημάτων ECI (διαφορετικές γλώσσες ή emojis).
* Ρύθμιση επιπέδων διόρθωσης σφαλμάτων QR για μεγαλύτερη αξιοπιστία.
* Ενσωμάτωση του παραγόμενου PNG σε PDF ή ιστοσελίδες.

Καλή προγραμματιστική δουλειά και απολαύστε τη δημιουργία πολυγλωσσικών QR codes!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικό κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [Πώς να δημιουργήσετε εικόνα QR Code σε Python με Aspose.Barcode – Οδηγός πλήρης](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Δημιουργία barcode Code128 με Aspose.Barcode Python – Οδηγός πλήρης](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Εμφάνιση ονόματος προϊόντος χρησιμοποιώντας τη βιβλιοθήκη barcode Python – Οδηγός βήμα‑βήμα](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}