---
category: general
date: 2026-07-27
description: Δημιουργήστε αντικείμενο μετρητή Aspose σε Python και ορίστε τα δημόσια
  και ιδιωτικά κλειδιά χωρίς κόπο. Μάθετε βήμα‑βήμα την αδειοδότηση για το Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create metered object aspose
- set public private keys
language: el
lastmod: 2026-07-27
og_description: Δημιουργήστε αντικείμενο μετρημένου τύπου Aspose σε Python. Αυτός
  ο οδηγός δείχνει πώς να ορίσετε δημόσια και ιδιωτικά κλειδιά για την άδεια Aspose.Barcode
  με σαφή παραδείγματα.
og_image_alt: Screenshot of Python code creating a metered object Aspose
og_title: Δημιουργία Μετρημένου Αντικειμένου Aspose – Πλήρης Οδηγός Python
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create metered object Aspose in Python and set public private keys
    effortlessly. Learn step‑by‑step licensing for Aspose.Barcode.
  headline: Create Metered Object Aspose – Complete Python Guide
  type: TechArticle
- description: Create metered object Aspose in Python and set public private keys
    effortlessly. Learn step‑by‑step licensing for Aspose.Barcode.
  name: Create Metered Object Aspose – Complete Python Guide
  steps:
  - name: Why two keys?
    text: '- **Public key** identifies your account on the Aspose server. - **Private
      key** authenticates the request, ensuring only you can consume the metered usage.'
  - name: 1. Missing Keys or Empty Strings
    text: 'If either key is an empty string, `set_metered_key` will raise a `ValueError`.
      Guard against this early:'
  - name: 2. Network Failures During Activation
    text: 'Metered licensing requires a live HTTP request. Wrap the activation in
      a retry loop if you expect flaky connectivity:'
  - name: 3. Switching Between Development and Production Keys
    text: 'You may have separate keys for testing and production. Store them in environment
      variables to avoid hard‑coding:'
  type: HowTo
tags:
- Aspose
- Python
- Barcode Licensing
title: Δημιουργία Μετρημένου Αντικειμένου Aspose – Πλήρης Οδηγός Python
url: /el/python/general/create-metered-object-aspose-complete-python-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία Metered Object Aspose – Πλήρης Οδηγός Python

Έχετε αναρωτηθεί ποτέ πώς να **create metered object aspose** σε ένα έργο Python; Ίσως να δημιουργείτε ένα πρωτότυπο σαρωτή barcode και το βήμα της αδειοδότησης να σας προκαλεί προβλήματα. Τα καλά νέα είναι ότι η ρύθμιση μιας μετρημένης άδειας είναι αρκετά απλή μόλις γνωρίζετε τις σωστές κλήσεις. Σε αυτό το tutorial θα περάσουμε από τον ακριβή κώδικα που χρειάζεστε για να **set public private keys**, θα εξηγήσουμε γιατί κάθε γραμμή είναι σημαντική, και θα σας δείξουμε πώς να επαληθεύσετε ότι η άδεια είναι ενεργή.

Θα καλύψουμε τα πάντα, από την εγκατάσταση του πακέτου Aspose.Barcode μέχρι τη διαχείριση κοινών προβλημάτων όπως λείπουν κλειδιά ή προβλήματα δικτύου. Στο τέλος θα έχετε ένα εκτελέσιμο script που ξεκλειδώνει τη πλήρη δύναμη του Aspose.Barcode χωρίς καμία εικασία.

---

## Προαπαιτήσεις – Τι Θα Χρειαστείτε

- Python 3.8+ εγκατεστημένο (συνιστάται η τελευταία σταθερή έκδοση)
- Πρόσβαση στα δημόσια και ιδιωτικά metered κλειδιά του Aspose (τα λαμβάνετε από το portal του Aspose μετά την εγγραφή)
- Σύνδεση στο internet για την αρχική ενεργοποίηση της μετρημένης άδειας
- Βασική εξοικείωση με τις εισαγωγές Python και τη διαχείριση εξαιρέσεων

Δεν απαιτούνται επιπλέον εξαρτήσεις πέρα από το `aspose.barcode`.

## Βήμα 1: Εγκατάσταση του Πακέτου Aspose.Barcode

Πρώτα απ' όλα—αν δεν έχετε ήδη κατεβάσει τη βιβλιοθήκη από το PyPI, κάντε το τώρα. Το όνομα του πακέτου είναι `aspose-barcode`.

```bash
pip install aspose-barcode
```

> **Pro tip:** Χρησιμοποιήστε ένα εικονικό περιβάλλον (`python -m venv venv`) ώστε το έργο σας να παραμένει καθαρό και μπορείτε να αναβαθμίσετε το Aspose χωρίς να επηρεάσετε άλλες εφαρμογές.

## Βήμα 2: Εισαγωγή του Module Aspose.Barcode

Με το πακέτο εγκατεστημένο, η πρώτη γραμμή του script σας πρέπει να εισάγει το module. Αυτό σας δίνει πρόσβαση στην κλάση `Metered` που θα χρειαστούμε αργότερα.

```python
# Step 2: Import the Aspose.Barcode package
import aspose.barcode
```

Γιατί η εισαγωγή στην αρχή; Η Python φορτώνει τα modules μία φορά ανά συνεδρία του interpreter, έτσι η τοποθέτηση της εισαγωγής στην αρχή διατηρεί το script καθαρό και αποτρέπει τυχαίες κυκλικές εισαγωγές.

## Βήμα 3: Δημιουργία Metered Object – Ο Πυρήνας της Αδειοδότησης

Τώρα φτάνουμε στην ουσία: **create metered object aspose**. Σκεφτείτε την κλάση `Metered` ως τον φύλακα που επικοινωνεί με τον διακομιστή αδειοδότησης του Aspose.

```python
# Step 3: Instantiate the Metered object
metered = aspose.barcode.Metered()
```

Όταν δημιουργείτε ένα αντικείμενο `Metered`, δεν έχει ακόμη διαπιστευτήρια. Είναι απλώς ένας κενός κοντέινερ που περιμένει τα κλειδιά σας. Αν προσπαθήσετε να χρησιμοποιήσετε οποιαδήποτε λειτουργία barcode πριν ορίσετε τα κλειδιά, θα αντιμετωπίσετε ένα `LicenseException`.

## Βήμα 4: Ορισμός των Δημόσιων και Ιδιωτικών Metered Κλειδιών σας

Αυτή είναι η ενότητα όπου **set public private keys**. Αντικαταστήστε τα placeholders με τις πραγματικές συμβολοσειρές που λάβατε από το Aspose.

```python
# Step 4: Set your public and private metered keys
public_key = "YOUR_PUBLIC_KEY"
private_key = "YOUR_PRIVATE_KEY"

# Apply the keys to the Metered object
metered.set_metered_key(public_key, private_key)
```

### Γιατί δύο κλειδιά;

- **Public key** αναγνωρίζει τον λογαριασμό σας στον διακομιστή Aspose.
- **Private key** πιστοποιεί το αίτημα, διασφαλίζοντας ότι μόνο εσείς μπορείτε να καταναλώσετε τη μετρημένη χρήση.

Και τα δύο απαιτούνται· η παράλειψη ενός θα προκαλέσει ένα `LicenseException` με σαφές μήνυμα σφάλματος.

## Βήμα 5: Επαλήθευση της Ενεργοποίησης της Άδειας

Είναι ένα πράγμα να καλέσετε το `set_metered_key`; είναι άλλο να επιβεβαιώσετε ότι το Aspose αποδέχτηκε πραγματικά τα κλειδιά. Η κλάση `Metered` παρέχει τη μέθοδο `get_usage()` που επιστρέφει τον τρέχοντα αριθμό χρήσεων. Αν η κλήση πετύχει, η άδειά σας είναι ενεργή.

```python
try:
    usage = metered.get_usage()
    print(f"Metered license activated! Current usage: {usage}")
except Exception as e:
    print("License activation failed:", e)
```

**Αναμενόμενη έξοδος (πρώτη εκτέλεση):**

```
Metered license activated! Current usage: 1
```

Αν δείτε σφάλμα όπως `Invalid license keys` ή `Network unreachable`, ελέγξτε ξανά τις συμβολοσειρές κλειδιών και τη σύνδεσή σας στο internet.

## Βήμα 6: Χρήση του Aspose.Barcode Τώρα που Έχετε Άδεια

Μόλις η άδεια επικυρωθεί, μπορείτε ελεύθερα να δημιουργήσετε ή να διαβάσετε barcodes. Εδώ είναι ένα γρήγορο παράδειγμα που δημιουργεί ένα barcode Code128 και το αποθηκεύει ως PNG.

```python
# Example: Generate a simple barcode
barcode_generator = aspose.barcode.BarcodeGenerator(
    symbology_type=aspose.barcode.SymbologyType.CODE_128,
    code_text="1234567890"
)

# Save to file
barcode_generator.save("barcode.png")
print("Barcode generated and saved as barcode.png")
```

Επειδή η μετρημένη άδεια είναι ήδη ενεργή, αυτή η λειτουργία δεν θα προκαλέσει σφάλματα αδειοδότησης.

## Διαχείριση Συνηθισμένων Ακραίων Περιπτώσεων

### 1. Λείπουν Κλειδιά ή Κενές Συμβολοσειρές
Αν κάποιο κλειδί είναι κενή συμβολοσειρά, το `set_metered_key` θα προκαλέσει ένα `ValueError`. Προστατέψτε το νωρίς:

```python
if not public_key or not private_key:
    raise ValueError("Both public and private keys must be provided.")
```

### 2. Αποτυχίες Δικτύου Κατά τη Διάρκεια της Ενεργοποίησης
Η μετρημένη αδειοδότηση απαιτεί ένα ζωντανό HTTP αίτημα. Τυλίξτε την ενεργοποίηση σε βρόχο επανάληψης αν αναμένετε ασταθή σύνδεση:

```python
import time

max_retries = 3
for attempt in range(1, max_retries + 1):
    try:
        metered.set_metered_key(public_key, private_key)
        break  # success!
    except Exception as e:
        if attempt == max_retries:
            raise
        print(f"Attempt {attempt} failed ({e}), retrying in 2 seconds...")
        time.sleep(2)
```

### 3. Εναλλαγή μεταξύ Κλειδιών Ανάπτυξης και Παραγωγής
Μπορεί να έχετε ξεχωριστά κλειδιά για δοκιμές και παραγωγή. Αποθηκεύστε τα σε μεταβλητές περιβάλλοντος για να αποφύγετε το hard‑coding:

```python
import os

public_key = os.getenv("ASPOSE_PUBLIC_KEY")
private_key = os.getenv("ASPOSE_PRIVATE_KEY")
```

Θυμηθείτε να φορτώσετε το αρχείο `.env` ή να ρυθμίσετε το CI/CD pipeline σας αναλόγως.

## Πλήρες Λειτουργικό Script

Συνδυάζοντας όλα, εδώ είναι ένα μοναδικό αρχείο που μπορείτε να τρέξετε αμέσως:

```python
import os
import time
import aspose.barcode

# -------------------------------------------------
# Configuration – replace with your actual keys
# -------------------------------------------------
public_key = os.getenv("ASPOSE_PUBLIC_KEY", "YOUR_PUBLIC_KEY")
private_key = os.getenv("ASPOSE_PRIVATE_KEY", "YOUR_PRIVATE_KEY")

if not public_key or not private_key:
    raise ValueError("Both public and private keys must be set.")

# -------------------------------------------------
# Step 1: Create the Metered object (create metered object aspose)
# -------------------------------------------------
metered = aspose.barcode.Metered()

# -------------------------------------------------
# Step 2: Set public and private keys (set public private keys)
# -------------------------------------------------
max_retries = 3
for attempt in range(1, max_retries + 1):
    try:
        metered.set_metered_key(public_key, private_key)
        print("License keys applied successfully.")
        break
    except Exception as exc:
        if attempt == max_retries:
            raise RuntimeError("Failed to activate metered license.") from exc
        print(f"Attempt {attempt} failed ({exc}), retrying...")
        time.sleep(2)

# -------------------------------------------------
# Step 3: Verify activation
# -------------------------------------------------
try:
    usage = metered.get_usage()
    print(f"Metered license active – usage count: {usage}")
except Exception as e:
    print("Could not verify license usage:", e)

# -------------------------------------------------
# Step 4: Generate a sample barcode (optional)
# -------------------------------------------------
generator = aspose.barcode.BarcodeGenerator(
    symbology_type=aspose.barcode.SymbologyType.CODE_128,
    code_text="1234567890"
)

output_path = "sample_barcode.png"
generator.save(output_path)
print(f"Sample barcode saved to {output_path}")
```

Τρέξτε το με:

```bash
python aspose_metered_demo.py
```

Αν όλα είναι σωστά συνδεδεμένα, θα δείτε τον αριθμό χρήσεων να εκτυπώνεται και ένα αρχείο `sample_barcode.png` να εμφανίζεται στον ίδιο φάκελο.

## Συμπέρασμα

Μόλις **created a metered object Aspose**, ορίσαμε τα **public and private keys**, επαληθεύσαμε την ενεργοποίηση, και ακόμη δημιουργήσαμε ένα barcode για να αποδείξουμε ότι λειτουργεί. Τα βήματα είναι σκόπιμα απλά, αλλά καλύπτουν το γιατί και το πώς χρειάζεστε για μια αξιόπιστη υλοποίηση.

Τώρα μπορείτε να ενσωματώσετε αυτή τη ροή αδειοδότησης σε μεγαλύτερες εφαρμογές—είτε είναι μια web υπηρεσία που δημιουργεί QR codes κατ' απαίτηση ή ένα desktop εργαλείο που διαβάζει barcodes αποθέματος. Θυμηθείτε να διαχειρίζεστε τα λείποντα κλειδιά, τις επαναλήψεις δικτύου, και τη διαμόρφωση βάσει περιβάλλοντος για να διατηρήσετε το σύστημα παραγωγής ανθεκτικό.

**Επόμενα βήματα;** Εξερευνήστε άλλες δυνατότητες του Aspose.Barcode όπως η ανάγνωση barcodes από εικόνες, η προσαρμογή επιλογών συμβολισμού, ή η ενσωμάτωση με Flask/Django για ένα RESTful barcode API. Όλα αυτά βασίζονται στην ίδια βάση μετρημένης αδειοδότησης που μόλις δημιουργήσαμε.

Καλή προγραμματιστική δουλειά, και εύχομαι τα barcode projects σας να είναι πάντα χωρίς σφάλματα!

## Τι Να Μάθετε Στη Σειρά;

Τα παρακάτω tutorials καλύπτουν στενά σχετικές θεματικές που βασίζονται στις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Δημιουργία Codabar Barcode με Aspose.Barcode – Generator & Reader API](/barcode/english/)
- [Δημιουργία Barcode Java - Ορισμός Κειμένου Κώδικα με χρήση Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Δημιουργία Barcode Java – Ορισμός Ανάλυσης Εικόνας με Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}