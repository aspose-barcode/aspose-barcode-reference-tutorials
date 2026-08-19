---
category: general
date: 2026-08-19
description: Πώς να δημιουργήσετε γραμμωτό κώδικα με ECI χρησιμοποιώντας το Aspose.Barcode
  για Python. Μάθετε πώς να προσθέσετε δεδομένα ECI, να συνδυάσετε απλό κείμενο και
  να αποθηκεύσετε την εικόνα σε έναν σαφή οδηγό.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: el
lastmod: 2026-08-19
og_description: Πώς να δημιουργήσετε γραμμωτό κώδικα με ECI χρησιμοποιώντας το Aspose.Barcode
  για Python. Ακολουθήστε αυτό το σεμινάριο για να μάθετε πώς να προσθέσετε δεδομένα
  ECI, να προσαρμόσετε την εμφάνιση και να αποθηκεύσετε το αποτέλεσμα.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Πώς να δημιουργήσετε γραμμωτό κώδικα με ECI χρησιμοποιώντας το Aspose.Barcode
  Python – βήμα‑βήμα
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Πώς να δημιουργήσετε γραμμωτό κώδικα με ECI χρησιμοποιώντας το Aspose.Barcode
  Python
url: /el/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε barcode με ECI χρησιμοποιώντας Aspose.Barcode Python

Αν χρειάζεστε να μάθετε **πώς να δημιουργήσετε barcode** που περιέχει τόσο απλούς χαρακτήρες όσο και δεδομένα κωδικοποιημένα με ECI, αυτός ο οδηγός παρουσιάζει τη διαδικασία από την αρχή μέχρι το τέλος. Θα δείτε ακριβώς **πώς να προσθέσετε eci** τμήματα, να προσαρμόσετε το μέγεθος και να αποθηκεύσετε την εικόνα στο δίσκο με ένα μόνο, εκτελέσιμο script.

Το tutorial καλύπτει:

* Ανάκτηση της έκδοσης της βιβλιοθήκης Aspose.Barcode (προαιρετικό αλλά χρήσιμο για εντοπισμό σφαλμάτων).  
* Δημιουργία μιας συμβολοσειράς extended codetext που αναμειγνύει απλούς και ECI‑κωδικοποιημένους χαρακτήρες.  
* Δημιουργία ενός barcode generator για μια συμβολική γλώσσα που υποστηρίζει extended codetext.  
* Προσαρμογή των διαστάσεων του barcode και αποθήκευση του τελικού αρχείου PNG.

Δεν απαιτείται εξωτερική τεκμηρίωση· αντιγράψτε τον κώδικα, εκτελέστε τον και θα έχετε μια εικόνα barcode που περιλαμβάνει κινέζους χαρακτήρες κωδικοποιημένους με ECI 26 (UTF‑8).

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* Python 3.8 ή νεότερη εγκατεστημένη.  
* Το πακέτο `aspose-barcode` εγκατεστημένο (`pip install aspose-barcode`).  
* Δικαιώματα εγγραφής στο φάκελο όπου σκοπεύετε να αποθηκεύσετε το αρχείο PNG.

Αν χρησιμοποιείτε εικονικό περιβάλλον, ενεργοποιήστε το πρώτα για να διατηρήσετε τις εξαρτήσεις απομονωμένες.

## Βήμα 1: Επαλήθευση της έκδοσης Aspose.Barcode (προαιρετικό)

Η γνώση της ακριβούς έκδοσης της βιβλιοθήκης βοηθά όταν χρειάζεται να αναφέρετε σφάλματα ή να συγκρίνετε δυνατότητες μεταξύ εκδόσεων.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Γιατί είναι σημαντικό*: Η έξοδος της έκδοσης επιβεβαιώνει ότι το runtime ταιριάζει με την τεκμηρίωση που ακολουθείτε. Διαφορετικές εκδόσεις μπορεί να υποστηρίζουν διαφορετικές τιμές ECI, οπότε αποτελεί έναν γρήγορο έλεγχο λογικής.

## Βήμα 2: Δημιουργία extended codetext με απλά και ECI‑κωδικοποιημένα τμήματα

Η Aspose.Barcode παρέχει το `ExtCodetextBuilder` για τη σύνδεση απλών δεδομένων και τμημάτων κωδικοποιημένων με ECI. Σε αυτό το παράδειγμα αναμειγνύουμε μια αριθμητική συμβολοσειρά με κινέζους χαρακτήρες.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Εξήγηση*:  
* `add_plain_codetext` εισάγει δεδομένα που η συμβολική γλώσσα του barcode αντιμετωπίζει ως συνηθισμένους χαρακτήρες.  
* `add_eci_codetext` λέει στον δημιουργό να προσθέσει έναν δείκτη ECI (εδώ **26**, που αντιστοιχεί σε UTF‑8) πριν από το κείμενο που παρέχεται. Αυτό είναι ακριβώς **πώς να προσθέσετε eci** δεδομένα σε ένα barcode.

Μπορείτε να καλέσετε το `add_eci_codetext` πολλές φορές για να ενσωματώσετε διάφορα μπλοκ γλωσσών. Ο builder διαχειρίζεται αυτόματα τις απαιτούμενες ακολουθίες διαφυγής.

## Βήμα 3: Επιλογή συμβολικής γλώσσας που υποστηρίζει extended codetext

Δεν κάθε τύπος barcode μπορεί να αποθηκεύσει τμήματα ECI. Code 128, QR και Data Matrix είναι κοινές επιλογές. Το παράδειγμα χρησιμοποιεί Code 128 επειδή υποστηρίζεται ευρέως και λειτουργεί καλά για μεικτά αλφαριθμητικά δεδομένα.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Γιατί Code 128;*: Δέχεται όλο το εύρος ASCII και τις ακολουθίες διαφυγής ECI που παράγει ο builder, καθιστώντας το ιδανικό για το σενάριο «πώς να δημιουργήσετε barcode» που αναμειγνύει απλό και κωδικοποιημένο κείμενο.

## Βήμα 4: Προσαρμογή εμφάνισης του barcode

Μπορείτε να ελέγξετε το μέγεθος, το ύψος, τα περιθώρια και πολλές άλλες οπτικές πτυχές μέσω του αντικειμένου `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Συμβουλή*: Αν σκοπεύετε να εκτυπώσετε το barcode, αυξήστε το `x_dimension` και το `bar_height` αναλογικά για να διατηρήσετε την αναγνωσιμότητα στο επιθυμητό DPI.

## Βήμα 5: Αποθήκευση της εικόνας barcode

Τέλος, γράψτε την παραγόμενη εικόνα σε αρχείο. Η Aspose.Barcode υποστηρίζει PNG, JPEG, BMP και πολλές άλλες μορφές.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Βεβαιωθείτε ότι ο φάκελος `output` υπάρχει ή δημιουργήστε τον με `os.makedirs("output", exist_ok=True)` πριν καλέσετε το `save`.

### Αναμενόμενο αποτέλεσμα

Όταν ανοίξετε το `extended_codetext.png`, θα πρέπει να δείτε ένα barcode Code 128 που κωδικοποιεί τη αριθμητική συμβολοσειρά `1234567890` ακολουθούμενη από τους κινέζους χαρακτήρες “特殊字符”. Η σάρωση του barcode με έναν σύγχρονο σαρωτή που σέβεται το ECI θα επιστρέψει την αρχική μεικτή συμβολοσειρά.

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode που δημιουργήθηκε με το παράδειγμα πώς να δημιουργήσετε barcode"}

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

### Τι κάνω αν χρειάζομαι διαφορετικό σύνολο χαρακτήρων;

Επιλέξτε την κατάλληλη τιμή ECI από τον πίνακα ISO/IEC 18004. Για παράδειγμα, το ECI 27 αντιπροσωπεύει ISO‑8859‑1 (Latin‑1). Αντικαταστήστε τον αριθμητικό αναγνωριστικό στο `add_eci_codetext` ανάλογα.

### Μπορώ να ενσωματώσω περισσότερα από ένα μπλοκ ECI;

Ναι. Καλέστε το `add_eci_codetext` πολλές φορές. Ο builder εισάγει τους απαραίτητους κωδικούς εναλλαγής ECI μεταξύ των μπλοκ, διατηρώντας τη σειρά που τα προσθέτετε.

### Υποστηρίζει ο δημιουργός QR codes με ECI;

Απολύτως. Αντικαταστήστε το `barcode.Symbology.CODE_128` με `barcode.Symbology.QR` και προσαρμόστε τυχόν QR‑συγκεκριμένες παραμέτρους (π.χ., επίπεδο διόρθωσης σφαλμάτων) μέσω του `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Πώς να διαχειριστώ πολύ μεγάλες συμβολοσειρές δεδομένων;

Για γραμμικά barcodes όπως το Code 128, το μέγιστο μήκος είναι περίπου 80 χαρακτήρες όταν χρησιμοποιείται extended codetext. Αν το υπερβείτε, σκεφτείτε να μεταβείτε σε μια δισδιάστατη συμβολική γλώσσα όπως QR ή Data Matrix, η οποία μπορεί να αποθηκεύσει χιλιάδες χαρακτήρες.

## Πλήρες, εκτελέσιμο script

Παρακάτω βρίσκεται το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑επικολλήσετε σε ένα αρχείο με όνομα `generate_extended_barcode.py` και να το εκτελέσετε άμεσα.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Τι Θα Μάθετε Στη Σύντομη Επόμενη

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να δημιουργήσετε εικόνα Barcode με προσαρμογή συμπληρωματικού χώρου χρησιμοποιώντας Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Πώς να δημιουργήσετε εικόνα Barcode σε Java με Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Πώς να δημιουργήσετε barcode DataMatrix με Aspose.BarCode για .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}