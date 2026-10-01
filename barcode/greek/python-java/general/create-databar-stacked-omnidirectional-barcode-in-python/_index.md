---
category: general
date: 2026-07-30
description: Δημιουργήστε γραμμωτό κώδικα Databar Stacked Omnidirectional σε Python.
  Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα για να ρυθμίσετε την αναλογία διαστάσεων,
  το XDimension και να εξάγετε PNG χρησιμοποιώντας έναν δημιουργό γραμμωτών κωδίκων
  σε Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: el
lastmod: 2026-07-30
og_description: Δημιουργήστε κωδικό Databar Stacked Omnidirectional σε Python. Αυτό
  το σεμινάριο δείχνει πώς να ορίσετε το XDimension, να ρυθμίσετε την αναλογία διαστάσεων
  του DataBar και να αποθηκεύσετε ως PNG με BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Δημιουργήστε γραμμωτό κώδικα Databar Stacked Omnidirectional – Οδηγός Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Δημιουργία Databar Stacked Omnidirectional Barcode σε Python
url: /el/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Databar Stacked Omnidirectional Barcode in Python

Έχετε ποτέ χρειαστεί να **create databar stacked omnidirectional** barcode σε Python αλλά δεν ήξερες από πού να ξεκινήσεις; Δεν είστε μόνοι—πολλοί προγραμματιστές αντιμετωπίζουν το ίδιο πρόβλημα όταν χρησιμοποιούν για πρώτη φορά την κλάση `BarcodeGenerator`. Τα καλά νέα είναι ότι η διαδικασία είναι αρκετά απλή μόλις κατανοήσετε τις βασικές ιδιότητες.

Σε αυτόν τον οδηγό θα περάσουμε βήμα-βήμα από ένα πλήρες, εκτελέσιμο παράδειγμα που χρησιμοποιεί έναν **python barcode generator** για να ορίσει το XDimension, να ρυθμίσει το DataBar aspect ratio και τελικά να εξάγει δύο αρχεία PNG. Στο τέλος θα έχετε μια στέρεη κατανόηση του πώς να δημιουργήσετε υψηλής ποιότητας stacked omnidirectional σύμβολα για οποιοδήποτε έργο αποθεμάτων ή logistics.

## What You’ll Learn

- Πώς να δημιουργήσετε μια παρουσία ενός **databar stacked omnidirectional** generator με φορτίο GTIN‑14.
- Γιατί το **XDimension pixel size** είναι σημαντικό για την αξιοπιστία της σάρωσης.
- Η επίδραση του **DataBar aspect ratio** στο πλάτος της σειράς σε σχέση με το ύψος.
- Πώς να αποθηκεύσετε το αποτέλεσμα ως αρχείο **BarCodeImageFormat PNG**.
- Συμβουλές για επαναχρησιμοποίηση του ίδιου αντικειμένου generator ώστε να παραχθούν πολλαπλές παραλλαγές χωρίς επιπλέον χρήση μνήμης.

### Prerequisites

- Python 3.8+ (η βιβλιοθήκη που χρησιμοποιούμε είναι pure‑Python, δεν απαιτούνται compiled wheels).
- Το πακέτο `barcode-generator` (εγκατάσταση μέσω `pip install barcode-generator`).
- Ένας φάκελος στον οποίο έχετε δικαιώματα εγγραφής – το script θα αποθηκεύσει δύο εικόνες PNG εκεί.

Αν είστε άνετοι με τις βασικές εισαγωγές Python και τον αντικειμενοστραφή κώδικα, είστε έτοιμοι να ξεκινήσετε.

## Create Databar Stacked Omnidirectional Barcode – Step Overview

Παρακάτω χωρίζουμε τη ροή εργασίας σε έξι μικρά βήματα. Κάθε βήμα είναι ένα αυτόνομο τμήμα κώδικα που μπορείτε να αντιγράψετε‑επικολλήσετε σε ένα REPL ή αρχείο script. Μη διστάσετε να πειραματιστείτε—αλλάζοντας το aspect ratio ή το XDimension θα έχετε αμέσως διαφορετικό οπτικό στυλ.

---

## Step 1: Create Databar Stacked Omnidirectional Generator

Το πρώτο που κάνουμε είναι να **create databar stacked omnidirectional** generator instance, περνώντας το κατάλληλο enum `EncodeTypes` και τη συμβολοσειρά δεδομένων.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Γιατί είναι σημαντικό:** Η σημαία `EncodeTypes.DatabarStackedOmniDirectional` λέει στη βιβλιοθήκη να παράγει ένα stacked omnidirectional σύμβολο, το μοναδικό DataBar variant που μπορεί να κωδικοποιήσει έως 14 ψηφία ενώ παραμένει αναγνώσιμο από οποιαδήποτε γωνία.

## Configure XDimension Pixel Size

Το **XDimension pixel size** ελέγχει το μικρότερο module (τη λεπτότερη μαύρη γραμμή). Μια τιμή `2` pixels λειτουργεί καλά για τις περισσότερες περιπτώσεις εμφάνισης σε οθόνη.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Συμβουλή:** Αν σκοπεύετε να εκτυπώσετε το barcode σε υψηλό DPI, αυξήστε αυτή την τιμή σε 3 ή 4 για να αποφύγετε θολές άκρες.

## Adjust DataBar Aspect Ratio (15)

Το **DataBar aspect ratio** καθορίζει πόσο πλατιά είναι κάθε σειρά σε σχέση με το ύψος της. Ένα aspect ratio `15` παράγει πιο πλατιές σειρές, κάτι που πολλοί scanners προτιμούν για γρήγορη λήψη κίνησης.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Γιατί 15;** Η επίσημη προδιαγραφή GS1 συνιστά ένα ratio μεταξύ 10 και 20 για stacked omnidirectional σύμβολα. Επιλέγουμε το `15` ως ισορροπημένη προεπιλογή.

## Export Barcode as PNG Using BarCodeImageFormat

Τώρα που ο generator είναι ρυθμισμένος, αποθηκεύουμε την εικόνα. Το enum `BarCodeImageFormat.Png` εξασφαλίζει lossless έξοδο, ιδανική για επεξεργασία downstream.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Τι θα δείτε:** Ανοίξτε το παραγόμενο PNG· θα πρέπει να παρατηρήσετε ένα καθαρό, υψηλής αντίθεσης barcode με σχετικά πλατιές σειρές.

## Change DataBar Aspect Ratio to 30

Μερικές φορές χρειάζεστε πιο ψηλές σειρές αντί για πλατιές—ίσως για να χωρέσει σε στενή ετικέτα. Η αλλαγή του **DataBar aspect ratio** σε `30` κάνει κάθε σειρά πιο ψηλή.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Ακραία περίπτωση:** Πολύ υψηλά ratios (π.χ., >40) μπορούν να κάνουν το barcode να υπερβεί τα τυπικά ύψη ετικετών, γι' αυτό δοκιμάστε σε πραγματικό εκτυπωτή πριν το υιοθετήσετε.

## Export Barcode Again with New Aspect Ratio

Τέλος, επαναχρησιμοποιούμε το ίδιο αντικείμενο `barcode_generator` για να γράψουμε ένα δεύτερο PNG. Δεν χρειάζεται να δημιουργήσετε ξανά τον generator—απλώς αλλάξτε την ιδιότητα και καλέστε ξανά το `Save`.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Αποτέλεσμα:** Τώρα έχετε δύο αρχεία PNG—ένα με πλατιές σειρές (`AR15`) και ένα με ψηλές σειρές (`AR30`). Συγκρίνετε τα δίπλα‑δίπλα για να αποφασίσετε ποιο λειτουργεί καλύτερα με τη ρύθμιση του scanner σας.

## Full Working Example

Συνδυάζοντας όλα, εδώ είναι το πλήρες script που μπορείτε να εκτελέσετε αμέσως. Αντικαταστήστε το `YOUR_DIRECTORY` με μια απόλυτη διαδρομή στο σύστημά σας.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Αναμενόμενη έξοδος** (στην κονσόλα σας):

```
✅ Two PNG files created – AR15 and AR30
```

Και δύο αρχεία εικόνας εμφανίζονται στον προορισμό φάκελο, έτοιμα για δοκιμές σάρωσης.

## Conclusion

Μόλις **created databar stacked omnidirectional** barcodes σε Python, ρυθμίσαμε το **XDimension pixel size**, πειραματιστήκαμε με δύο διαφορετικές ρυθμίσεις **DataBar aspect ratio** και εξάγαμε τα αποτελέσματα ως αρχεία **BarCodeImageFormat PNG**. Ολόκληρη η ροή εργασίας χωράει σε λίγες γραμμές, αλλά σας δίνει πλήρη έλεγχο πάνω στα οπτικά χαρακτηριστικά που μετράνε περισσότερο για τους scanners.

Τι ακολουθεί; Δοκιμάστε να αλλάξετε το payload σε διαφορετικό GTIN, παίξτε με τα χρώματα μετατρέποντας το PNG σε εικόνα με παλέτα, ή δημιουργήστε μια αναφορά PDF που ενσωματώνει και τα δύο PNG δίπλα‑δίπλα. Η κλάση `BarcodeGenerator` είναι αρκετά ευέλικτη για να αντιμετωπίσει όλα αυτά τα σενάρια, οπότε μη διστάσετε να πειραματιστείτε.

Έχετε ερωτήσεις σχετικά με κάποιο συγκεκριμένο use‑case ή αντιμετωπίζετε σφάλμα; Αφήστε ένα σχόλιο παρακάτω και θα χαρώ να βοηθήσω. Καλό coding!

## What Should You Learn Next?

Τα παρακάτω tutorials καλύπτουν στενά σχετιζόμενα θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε επιπλέον δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία εικόνας barcode – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}