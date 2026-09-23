---
category: general
date: 2026-09-23
description: Μάθετε πώς να δημιουργείτε γραμμωτό κώδικα Code 128 και να αποθηκεύετε
  την εικόνα του γραμμωτού κώδικα χρησιμοποιώντας το Aspose.BarCode σε Python – οδηγός
  βήμα‑προς‑βήμα.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: el
lastmod: 2026-09-23
og_description: Δημιουργήστε γραμμωτό κώδικα Code 128 και αποθηκεύστε την εικόνα του
  γραμμωτού κώδικα με το Aspose.BarCode σε Python. Ακολουθήστε αυτό το πλήρες παράδειγμα
  για να δημιουργήσετε, να προσαρμόσετε και να εξάγετε τον γραμμωτό κώδικα ως αρχείο
  PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Δημιουργία barcode Code 128 και αποθήκευση εικόνας barcode – Οδηγός Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Πώς να δημιουργήσετε γραμμωτό κώδικα Code 128 και να αποθηκεύσετε την εικόνα
  του γραμμωτού κώδικα με το Aspose.BarCode
url: /el/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε γραμμωτό κώδικα Code 128 και να αποθηκεύσετε την εικόνα του γραμμωτού κώδικα με το Aspose.BarCode

Αν χρειάζεστε **δημιουργία γραμμωτού κώδικα Code 128** και **αποθήκευση εικόνας γραμμωτού κώδικα** σε ένα έργο Python, αυτό το tutorial δείχνει τα ακριβή βήματα. Χρησιμοποιώντας το `ExtCodetextBuilder` του Aspose.BarCode μπορείτε να ενσωματώσετε απλό κείμενο και τμήματα Unicode σε ένα ενιαίο payload, και στη συνέχεια να αποδώσετε το αποτέλεσμα ως αρχείο PNG.

Θα δείτε ένα πλήρες, εκτελέσιμο script, εξήγηση κάθε γραμμής, και συμβουλές για κοινά προβλήματα όπως η διαχείριση κωδικοποίησης ECI ή η επιλογή του σωστού φακέλου εξόδου. Δεν απαιτείται εξωτερική τεκμηρίωση — απλώς αντιγράψτε, επικολλήστε και εκτελέστε.

## Προαπαιτούμενα

* Python 3.8+ εγκατεστημένο.
* Το πακέτο `aspose.barcode` (εγκαταστήστε το με `pip install aspose-barcode`).
* Δικαίωμα εγγραφής στον φάκελο όπου θα αποθηκευτεί το PNG.

Ο κώδικας λειτουργεί με οποιαδήποτε συμβολική γραμματοσειρά υποστηρίζεται από το Aspose.BarCode, αλλά το παράδειγμα εστιάζει στο **Code 128** επειδή κωδικοποιεί αποδοτικά αλφαριθμητικά δεδομένα και υποστηρίζει επεκταμένα σύνολα χαρακτήρων.

## Βήμα 1: Εισαγωγή των απαιτούμενων κλάσεων

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Γιατί αυτό το βήμα;* Η εισαγωγή των κλάσεων σας δίνει πρόσβαση στον builder για επεκταμένο κείμενο, στον writer που δημιουργεί την εικόνα, και στον βοηθό έκδοσης που μπορεί να είναι χρήσιμος για εντοπισμό σφαλμάτων σε ενημερώσεις της βιβλιοθήκης.

## Βήμα 2: Δημιουργία του επεκταμένου κειμένου κώδικα

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Το `ExtCodetextBuilder` σας επιτρέπει να συνδυάσετε απλό ASCII και δεδομένα Unicode σε ένα ενιαίο payload γραμμωτού κώδικα. Το byte ECI (Extended Channel Interpretation) `0x03` ενημερώνει το σαρωτή ότι τα επόμενα bytes είναι κωδικοποιημένα σε UTF‑8, κάτι που είναι απαραίτητο για γλώσσες όπως τα Ρωσικά, τα Κινέζικα ή τα Αραβικά.

## Βήμα 3: Διαμόρφωση του barcode writer για Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Ορίζοντας το `encode_type` σε `CODE_128` υποδεικνύει στον writer να αποδώσει ένα **γραμμωτό κώδικα Code 128**. Η ιδιότητα `code_text` λαμβάνει το επεκταμένο κείμενο που δημιουργήθηκε στο προηγούμενο βήμα.

## Βήμα 4: Αποθήκευση της εικόνας του γραμμωτού κώδικα ως PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Η μέθοδος `save` γράφει τον γραμμωτό κώδικα σε αρχείο. Η χρήση του `BarCodeImageFormat.PNG` εξασφαλίζει συμπίεση χωρίς απώλειες και ευρεία συμβατότητα με εφαρμογές web και κινητών.

## Βήμα 5 (προαιρετικό): Επαλήθευση της έκδοσης της βιβλιοθήκης Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Η γνώση της ακριβούς έκδοσης της βιβλιοθήκης βοηθά όταν χρειάζεται να αναφέρετε σφάλματα ή να συγκρίνετε τη συμπεριφορά μεταξύ εκδόσεων.

## Αναμενόμενο αποτέλεσμα

Η εκτέλεση του script παράγει έξοδο κονσόλας παρόμοια με:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Το παραγόμενο PNG (`extended_codetext.png`) φαίνεται ως εξής:

![Γραμμωτός κώδικας Code 128 που δημιουργήθηκε με Python και αποθηκεύτηκε ως εικόνα PNG](images/code128_extended.png)

*Η εικόνα δείχνει έναν γραμμωτό κώδικα Code 128 που κωδικοποιεί τόσο τη συμβολοσειρά ASCII `ABC123` όσο και τη ρωσική λέξη “Пример”.*

## Συχνές ερωτήσεις και διαχείριση ειδικών περιπτώσεων

| Ερώτηση | Απάντηση |
|----------|--------|
| **Μπορώ να χρησιμοποιήσω διαφορετική συμβολική γραμματοσειρά;** | Ναι. Αντικαταστήστε το `BarCodeEncodeMode.CODE_128` με οποιαδήποτε άλλη υποστηριζόμενη λειτουργία όπως `QR`, `EAN_13`, ή `PDF_417`. |
| **Τι γίνεται αν το κείμενο Unicode περιέχει emojis;** | Τα emojis είναι επίσης χαρακτήρες UTF‑8, οπότε η ίδια κλήση `add_eci_codetext` λειτουργεί. Βεβαιωθείτε ότι ο στόχος σαρωτής υποστηρίζει το ECI που χρησιμοποιείτε. |
| **Πώς αλλάζω το μέγεθος της εικόνας;** | Ορίστε `writer.x_dimension` και `writer.bar_height` πριν καλέσετε το `save`. |
| **Ποιον φάκελο πρέπει να χρησιμοποιήσω για το `output_path`;** | Οποιονδήποτε φάκελο που η διαδικασία Python μπορεί να γράψει. Χρησιμοποιήστε `os.makedirs` με `exist_ok=True` για να τον δημιουργήσετε αυτόματα. |

## Επαγγελματικές συμβουλές

* **Αποφύγετε την σκληρή κωδικοποίηση διαδρομών.** Χρησιμοποιήστε `os.path.join` και `Path` από το module `pathlib` για συμβατότητα μεταξύ πλατφορμών.
* **Επικυρώστε τον γραμμωτό κώδικα.** Μετά την αποθήκευση, μπορείτε να διαβάσετε ξανά την εικόνα με `barcode.BarCodeReader` για να επιβεβαιώσετε ότι το κωδικοποιημένο κείμενο ταιριάζει με το `extended_codetext`.
* **Συμβουλή απόδοσης.** Αν δημιουργείτε πολλούς γραμμωτούς κώδικες σε βρόχο, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `BarCodeWriter` και ενημερώστε μόνο το `code_text` σε κάθε επανάληψη.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε γραμμωτό κώδικα Code 128** με μεικτά δεδομένα ASCII και Unicode και να **αποθηκεύσετε την εικόνα του γραμμωτού κώδικα** ως PNG χρησιμοποιώντας το Aspose.BarCode σε Python. Το πλήρες script καλύπτει τη δημιουργία επεκταμένου κειμένου κώδικα, τη διαμόρφωση του writer, την εξαγωγή της εικόνας και τον έλεγχο των εκδόσεων της βιβλιοθήκης.

Από εδώ μπορείτε να εξερευνήσετε:

* Προσθήκη χρωμάτων προσκηνίου/υποβάθρου (`writer.back_color`, `writer.fore_color`).
* Ενσωμάτωση του γραμμωτού κώδικα σε PDF με το `Aspose.PDF`.
* Χρήση της κλάσης `BarCodeReader` για αποκωδικοποίηση της αποθηκευμένης εικόνας και αυτόματη επαλήθευση του περιεχομένου.

Καλό κώδικα, και μη διστάσετε να πειραματιστείτε με άλλες συμβολικές γραμματοσειρές και μορφές εικόνας!

## Τι πρέπει να μάθετε στη συνέχεια;

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσει να κατακτήσετε πρόσθετες δυνατότητες API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία γραμμωτού κώδικα Code128 με Aspose.Barcode Python – Πλήρης Οδηγός](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Πώς να δημιουργήσετε γραμμωτό κώδικα σε Python – πλήρης οδηγός βήμα‑βήμα](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Πώς να δημιουργήσετε εικόνα QR Code σε Python με Aspose.Barcode – Πλήρης Οδηγός](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}