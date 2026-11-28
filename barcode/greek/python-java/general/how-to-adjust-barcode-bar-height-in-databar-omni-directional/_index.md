---
category: general
date: 2026-11-27
description: Μάθετε πώς να ρυθμίσετε το ύψος των γραμμών του barcode σε έναν δημιουργό
  barcode DataBar Omni‑Directional. Ο κώδικας βήμα‑προς‑βήμα δείχνει τη ρύθμιση του
  ύψους σε 30 px και 60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: el
lastmod: 2026-11-27
og_description: Ρυθμίστε το ύψος των γραμμών του barcode σε έναν γεννήτρια DataBar
  Omni‑Directional με Python. Ακολουθήστε τον πλήρη οδηγό για να ορίσετε τα ύψη, τη
  διάσταση X και να αποθηκεύσετε εικόνες PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Ρύθμιση του ύψους της μπάρας barcode στη γεννήτρια DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Πώς να ρυθμίσετε το ύψος των γραμμών του barcode στον δημιουργό DataBar Omni‑Directional
url: /el/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσαρμόσετε το ύψος των γραμμών του barcode σε γεννήτρια DataBar Omni‑Directional

Αν χρειάζεται να **προσαρμόσετε το ύψος των γραμμών του barcode** για ένα barcode DataBar Omni‑Directional, αυτός ο οδηγός σας δείχνει ακριβώς πώς. Θα δείτε ένα πλήρες, εκτελέσιμο παράδειγμα Python που αλλάζει το ύψος των γραμμών από 30 px σε 60 px ενώ διατηρεί το X‑dimension και τη μορφή εικόνας σταθερά.

Η αλλαγή των οπτικών διαστάσεων ενός barcode είναι συχνή απαίτηση όταν το barcode πρέπει να ταιριάζει σε συγκεκριμένο μέγεθος ετικέτας ή οδηγία σχεδίασης. Εκτός από το ύψος των γραμμών, μπορεί να θέλετε επίσης να ρυθμίσετε το **X‑dimension** (μέγεθος μονάδας) ή να επιλέξετε διαφορετική **μορφή εικόνας barcode** όπως PNG ή JPEG.

Σε αυτό το tutorial θα:

* Εγκαταστήσετε τη απαιτούμενη βιβλιοθήκη (GroupDocs.Barcode for Python)
* Δημιουργήσετε έναν γεννήτρια DataBar Omni‑Directional barcode
* Ορίσετε το μέγεθος μονάδας με `XDimension`
* Προσαρμόσετε την ιδιότητα ύψους γραμμής δύο φορές
* Αποθηκεύσετε τις παραγόμενες εικόνες στη ζητούμενη **BarCodeImageFormat**

Δεν απαιτείται προηγούμενη εμπειρία με το GroupDocs API—απλώς βασικές γνώσεις Python.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

* Python 3.8 ή νεότερη έκδοση εγκατεστημένη
* Πακέτο `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Δικαιώματα εγγραφής σε φάκελο όπου θα αποθηκευτούν τα αρχεία PNG

Αν δεν γνωρίζετε το **DataBar Omni‑Directional barcode**, κωδικοποιεί έναν 14‑ψήφιο GTIN και χρησιμοποιείται εκτενώς στο λιανικό εμπόριο για σάρωση από οποιαδήποτε προσανατολισμό.

## Βήμα 1: Ρύθμιση του γεννήτρια DataBar Omni‑Directional barcode

Πρώτα, εισάγετε τις απαραίτητες κλάσεις και δημιουργήστε τον γεννήτρια με τα δεδομένα GTIN που θέλετε να κωδικοποιήσετε.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Γιατί είναι σημαντικό:* Η σταθερά `EncodeTypes.DatabarOmniDirectional` λέει στη βιβλιοθήκη να παράγει τη συμβολική Omni‑Directional. Η συμβολοσειρά δεδομένων περιλαμβάνει το AI `(01)` που υποδεικνύει τιμή GTIN‑14.

## Βήμα 2: Ορισμός του X‑dimension (μέγεθος μονάδας)

Το X‑dimension ελέγχει το πλάτος της πιο στενής γραμμής. Μια κοινή τιμή για απόδοση στην οθόνη είναι **2 px ανά μονάδα**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Η χρήση μιας συνεπούς **set XDimension** εξασφαλίζει ότι το barcode κλιμακώνεται σωστά σε διαφορετικούς εκτυπωτές και σαρωτές.

## Βήμα 3: Προσαρμογή του ύψους γραμμής σε 30 px και αποθήκευση της εικόνας

Τώρα αλλάζουμε την ιδιότητα ύψους γραμμής. Το πρώτο ύψος που θα χρησιμοποιήσουμε είναι **30 px**, κατάλληλο για μικρές ετικέτες.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Η σταθερά `BarCodeImageFormat.Png` επιλέγει τη **μορφή εικόνας barcode** PNG, η οποία διατηρεί την απώλεια‑απώλειας ποιότητα.

### Αναμενόμενο αποτέλεσμα

Το αρχείο `DatabarBarHeight30Pixels.png` περιέχει ένα DataBar Omni‑Directional barcode των γραμμών του οποίες έχουν ύψος 30 px. Παρακάτω υπάρχει μια εικονική προεπισκόπηση:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Συμβουλή:** Αν ανοίξετε το PNG σε πρόγραμμα επεξεργασίας εικόνας, θα δείτε το ακριβές ύψος των γραμμών. Οι στενές γραμμές έχουν πλάτος 2 px, όπως ορίστηκε νωρίτερα.

## Βήμα 4: Αλλαγή του ύψους γραμμής σε 60 px για υψηλότερο barcode

Για εφαρμογές που απαιτούν μεγαλύτερο οπτικό αποτύπωμα—π.χ. ετικέτα φορτίου—μπορείτε να αυξήσετε το ύψος γραμμής σε **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Μόνο η ιδιότητα `BarHeight` αλλάζει· το X‑dimension και η κωδικοποίηση παραμένουν τα ίδια, ώστε το barcode να παραμένει αναγνώσιμο.

## Βήμα 5: Αποθήκευση της ενημερωμένης εικόνας barcode

Τέλος, γράψτε το υψηλότερο barcode σε δεύτερο αρχείο PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Αναμενόμενο αποτέλεσμα

Το αρχείο `DatabarBarHeight60Pixels.png` δείχνει τα ίδια δεδομένα κωδικοποιημένα, αλλά κάθε γραμμή έχει τώρα ύψος 60 px. Η οπτική διαφορά απεικονίζεται παρακάτω:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Πλήρες, εκτελέσιμο παράδειγμα

Συνδυάζοντας όλα τα παραπάνω, εδώ είναι το πλήρες script που μπορείτε να αντιγράψετε‑επικολλήσετε σε αρχείο με όνομα `adjust_barcode_height.py` και να τρέξετε άμεσα.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Τρέξτε το script:

```bash
python adjust_barcode_height.py
```

Θα πρέπει να δείτε δύο αρχεία PNG στον φάκελο `output`, το καθένα να αντανακλά το ύψος γραμμής που ορίσατε.

## Συχνές ερωτήσεις και ειδικές περιπτώσεις

| Ερώτηση | Απάντηση |
|----------|--------|
| **Μπορώ να χρησιμοποιήσω JPEG αντί για PNG;** | Ναι. Αντικαταστήστε το `BarCodeImageFormat.Png` με `BarCodeImageFormat.Jpeg`. Το JPEG είναι με απώλειες, γι' αυτό προτιμήστε PNG για ακριβή σάρωση. |
| **Τι γίνεται αν χρειάζομαι ύψος γραμμής που δεν είναι πολλαπλάσιο του 10;** | Η ιδιότητα `BarHeight.Pixels` δέχεται οποιαδήποτε ακέραια τιμή. Απλώς ορίστε τον επιθυμητό αριθμό pixel (π.χ., `45`). |
| **Επηρεάζει η αλλαγή του ύψους γραμμής τα κωδικοποιημένα δεδομένα;** | Όχι. Αλλάζει μόνο την οπτική αναπαράσταση· η υποκείμενη συμβολοσειρά δεδομένων παραμένει αμετάβλητη. |
| **Πώς αλλάζω το X‑dimension μετά την αποθήκευση της πρώτης εικόνας;** | Μπορείτε να τροποποιήσετε το `gen.parameters.barcode.x_dimension.pixels` οποτεδήποτε πριν καλέσετε το `save()`. Η αλλαγή θα ισχύσει για τις επόμενες εικόνες. |
| **Είναι ο γεννήτρια thread‑safe;** | Η παρουσία `BarcodeGenerator` δεν εγγυάται thread‑safety. Δημιουργήστε ξεχωριστό αντικείμενο ανά νήμα αν παράγετε barcodes ταυτόχρονα. |

## Συμπέρασμα

Τώρα ξέρετε πώς να **προσαρμόσετε το ύψος των γραμμών** σε γεννήτρια DataBar Omni‑Directional barcode χρησιμοποιώντας Python. Ο οδηγός κάλυψε τη δημιουργία του γεννήτρια, τον ορισμό του **X‑dimension**, την τροποποίηση της ιδιότητας **barcode bar height** και την αποθήκευση εικόνων στη ζητούμενη **μορφή εικόνας barcode**.

Από εδώ μπορείτε να πειραματιστείτε με άλλα ύψη, διαφορετικά μεγέθη μονάδας ή να μεταβείτε σε εναλλακτικές μορφές εικόνας όπως JPEG ή BMP. Μπορείτε επίσης να εξερευνήσετε πρόσθετες δυνατότητες **barcode generator python** όπως η προσθήκη κειμένου αναγνώσιμου από άνθρωπο ή η αλλαγή χρωματικών σχημάτων.

Καλή προγραμματιστική δουλειά, και κρατήστε τα barcodes σας καθαρά και τέλεια διαστασιοποιημένα!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις ώστε να κατακτήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Πώς να ορίσετε το πλάτος και να προσαρμόσετε το ύψος για ένα GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Δημιουργία omni directional databar και εικόνας barcode σε Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – αλλαγή ύψους barcode](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}