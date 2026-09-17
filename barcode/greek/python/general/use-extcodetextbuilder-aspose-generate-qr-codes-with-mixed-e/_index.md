---
category: general
date: 2026-07-18
description: Χρησιμοποιήστε το extcodetextbuilder της Aspose για να δημιουργήσετε
  QR κώδικες που συνδυάζουν απλό ASCII και κείμενο Ρώσικης σε UTF‑8. Μάθετε τη δημιουργία
  QR κώδικα με Aspose.Barcode σε Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: el
lastmod: 2026-07-18
og_description: Χρησιμοποιήστε το extcodetextbuilder της Aspose για να συνδυάσετε
  απλά και κωδικοποιημένα σε UTF‑8 τμήματα σε έναν κώδικα QR. Ακολουθήστε αυτόν τον
  οδηγό βήμα‑βήμα για το Aspose.Barcode σε Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: χρησιμοποιήστε το extcodetextbuilder aspose – Δημιουργήστε QR κώδικες με
  μεικτό κείμενο ECI
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'χρησιμοποιήστε το extcodetextbuilder aspose: Δημιουργία QR κωδίκων με μεικτό
  κείμενο ECI'
url: /el/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# χρήση extcodetextbuilder aspose – Δημιουργία QR Codes με Μικτό Κείμενο ECI

Έχετε αναρωτηθεί ποτέ πώς να **use extcodetextbuilder aspose** ενσωματώσετε τόσο απλό αγγλικό όσο και κυριλλικό κείμενο σε ένα μόνο QR Code; Δεν είστε μόνοι. Πολλοί προγραμματιστές συναντούν πρόβλημα όταν πρέπει να συνδυάσουν δεδομένα ASCII και μη‑ASCII, ειδικά όταν ο σαρωτής‑στόχος απαιτεί σωστές ενδείξεις ECI (Extended Channel Interpretation).  

Σε αυτό το tutorial θα περάσουμε βήμα‑βήμα τις ακριβείς ενέργειες για να δημιουργήσουμε ένα QR Code που μεταφέρει το “HELLO123” **και** τη ρωσική λέξη “Привет”, όλα με το Python API του Aspose.Barcode. Στο τέλος θα έχετε ένα έτοιμο‑για‑εκτέλεση script, θα καταλάβετε γιατί κάθε κλήση είναι σημαντική, και θα ξέρετε πώς να προσαρμόσετε τη διαδικασία για άλλες γλώσσες ή μορφές δεδομένων.

## Τι Θα Μάθετε

- Πώς να **initialize ExtCodetextBuilder** και να προσθέσετε τμήματα plain plus ECI‑encoded.  
- Γιατί η τιμή **ECI encoding** `3` αντιστοιχεί σε UTF‑8 και πώς αυτό επηρεάζει το σκανάρισμα.  
- Η ακριβής ακολουθία για τη ρύθμιση ενός **QR Code generator** με Aspose.Barcode.  
- Πώς να αποθηκεύσετε την παραγόμενη εικόνα και να επαληθεύσετε το μικτό περιεχόμενο.  

**Prerequisites** – χρειάζεστε Python 3.8+, το πακέτο `aspose-barcode` εγκατεστημένο (`pip install aspose-barcode`), και έναν φάκελο όπου μπορείτε να γράψετε εικόνες. Τίποτα άλλο.

---

## χρήση extcodetextbuilder aspose για δημιουργία μικτού codetext

Το πρώτο που χρειάζεται είναι μια παρουσία `ExtCodetextBuilder`. Σκεφτείτε το ως ένα pattern builder που ενώνει διαφορετικά κομμάτια κειμένου ενώ αυτόματα εισάγει τα σωστά σήματα ECI στο παρασκήνιο.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Γιατί είναι σημαντικό:**  
- `add_plain_codetext` διατηρεί τα δεδομένα όπως είναι, κάτι τέλειο για αριθμούς ή αγγλικά γράμματα.  
- `add_eci_codetext` εισάγει ένα τμήμα ECI (`[ECI:3]`) πριν από τη δοθείσα συμβολοσειρά, λέγοντας σε κάθε συμβατό αναγνώστη ότι τα επόμενα byte είναι UTF‑8. Χωρίς αυτό, ο σαρωτής θα ερμηνεύσει τα κυριλλικά byte ως άχρηστοι χαρακτήρες.

> **Pro tip:** Αν χρειάζεστε διαφορετικό σύνολο χαρακτήρων, αλλάξτε την τιμή `eci_encoding` σύμφωνα με τον πίνακα ECI (π.χ., `26` για ISO‑8859‑1).  

---

## Αρχικοποίηση δημιουργίας QR Code με Aspose.Barcode

Τώρα που έχουμε ένα σωστά μορφοποιημένο `extended_codetext`, μπορούμε να το περάσουμε στον QR Code generator. Το Aspose.Barcode αφαιρεί την πολυπλοκότητα της χαμηλού επιπέδου δημιουργίας QR matrix, επιτρέποντάς σας να εστιάσετε στα δεδομένα.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Τι συμβαίνει εδώ;**  
- `BarcodeGenerator()` δημιουργεί ένα νέο αντικείμενο generator με προεπιλεγμένες ρυθμίσεις (μέγεθος, ανάλυση κ.λπ.).  
- `set_symbology` ενημερώνει τη μηχανή ότι θέλουμε QR Code αντί για, π.χ., Code128.  

Αν χρειάζεστε υψηλότερο επίπεδο διόρθωσης σφαλμάτων, μπορείτε να καλέσετε `qr_generator.parameters.barcode.qr_error_level = ...` πριν ορίσετε το codetext.

---

## Ανάθεση του extended codetext στον QR generator

Με τον generator έτοιμο, το επόμενο βήμα είναι απλώς η τροφοδοσία της μικτής συμβολοσειράς που χτίσαμε νωρίτερα.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Γιατί να μην χρησιμοποιήσετε `set_codetext`;**  
`set_codetext` αντιμετωπίζει την είσοδο ως απλό κείμενο, αφαιρώντας τυχόν σήματα ECI. `set_extended_codetext` διατηρεί τα ακατέργαστα byte, συμπεριλαμβανομένου του τμήματος ECI, εξασφαλίζοντας ότι ο σαρωτής βλέπει τη σωστή εναλλαγή γλώσσας.

---

## Αποθήκευση εικόνας QR Code και επαλήθευση του αποτελέσματος

Τέλος, γράφουμε το QR Code στο δίσκο. Το Aspose.Barcode υποστηρίζει PNG, JPEG, BMP και άλλα· το PNG είναι ασφαλής προεπιλογή επειδή διατηρεί τα δεδομένα lossless.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Τώρα θα πρέπει να έχετε ένα αρχείο PNG στη συγκεκριμένη θέση. Ανοίξτε το με οποιαδήποτε εφαρμογή σάρωσης QR που υποστηρίζει ECI (τα περισσότερα σύγχρονα smartphones το κάνουν). Σαρώστε μία φορά – θα δείτε “HELLO123”. Σαρώστε ξανά (ή χρησιμοποιήστε σάρωσης που εμφανίζει ακατέργαστα δεδομένα) – θα δείτε επίσης “Привет”. Τα δύο τμήματα εμφανίζονται ως ένα ενιαίο payload, ακριβώς όπως το χτίσαμε.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: use extcodetextbuilder aspose QR code example showing mixed ECI text*  
*Κείμενο alt εικόνας: παράδειγμα QR code με χρήση extcodetextbuilder aspose που δείχνει μικτό κείμενο ECI*

## Πλήρες, Έτοιμο‑για‑Εκτέλεση Script

Συνδυάζοντας τα πάντα, εδώ είναι το πλήρες πρόγραμμα που μπορείτε να αντιγράψετε‑και‑επικολλήσετε σε ένα αρχείο με όνομα `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Τρέξτε το με:

```bash
python qr_mixed_eci.py
```

Θα δείτε ένα μήνυμα στην κονσόλα που επιβεβαιώνει τη θέση αποθήκευσης, και το PNG θα εμφανιστεί ακριβώς εκεί που το υποδείξατε.

---

## Συχνές Ερωτήσεις & Ακραίες Περιπτώσεις

### Τι γίνεται αν ο σαρωτής μου δεν αναγνωρίζει το κυριλλικό τμήμα;

Βεβαιωθείτε ότι η εφαρμογή σάρωσης διαφημίζει υποστήριξη ECI. Παλαιότερος εξοπλισμός μπορεί να αγνοήσει το τμήμα ECI και να αντιμετωπίσει τα byte ως ISO‑8859‑1, με αποτέλεσμα ακατανόητους χαρακτήρες.

### Μπορώ να προσθέσω περισσότερα από δύο τμήματα;

Απόλυτα. Καλέστε `add_plain_codetext` ή `add_eci_codetext` όσες φορές χρειάζεται. Ο builder θα τα ενώνει με τη σειρά που καλείτε τις μεθόδους.

### Πώς αλλάζω το μέγεθος του QR Code ή το χρώμα του προσκηνίου;

Χρησιμοποιήστε το αντικείμενο `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Υπάρχει τρόπος ενσωμάτωσης δυαδικών δεδομένων (π.χ., μικρό αρχείο) μαζί με κείμενο;

Ναι. Χρησιμοποιήστε `add_binary_codetext` με έναν πίνακα byte, και συνδυάστε το με ένα κατάλληλο ECI αν τα δυαδικά δεδομένα αντιπροσωπεύουν συγκεκριμένο σύνολο χαρακτήρων. Ο builder θα διαχειριστεί τις απαραίτητες εναλλαγές λειτουργίας.

## Συμπέρασμα

Τώρα ξέρετε **πώς να χρησιμοποιήσετε extcodetextbuilder aspose** για να δημιουργήσετε QR Codes που συνδυάζουν άψογα απλό ASCII και κείμενο Ρωσικής κωδικοποιημένο σε UTF‑8. Εκμεταλλευόμενοι το `ExtCodetextBuilder`, ορίζοντας τη σωστή **ECI encoding**, και τροφοδοτώντας το αποτέλεσμα σε έναν **Aspose.Barcode QR Code generator**, λαμβάνετε μια ενιαία, σύμφωνη με τα πρότυπα εικόνα που λειτουργεί σε σύγχρονους σαρωτές.  

Από εδώ, δοκιμάστε να αντικαταστήσετε το `eci_encoding=3` με άλλους αναγνωριστικούς γλώσσας, ή πειραματιστείτε με επιπλέον τμήματα plain για να χτίσετε πολύγλωσσα payloads. Μπορείτε επίσης να εξερευνήσετε τις επιλογές `BarCodeImageFormat` για έξοδο σε SVG ή PDF αν χρειάζεστε διανυσματικά γραφικά.  

Καλή προγραμματιστική, και μη διστάσετε να αφήσετε σχόλιο αν συναντήσετε δυσκολίες—η ανατροφοδότησή σας βοηθά να βελτιώσουμε αυτά τα guides!

## Τι Θα Μάθετε Στη Σύντομη Μελλοντική

Τα παρακάτω tutorials καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάστηκαν σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να κατακτήσετε πρόσθετες δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις υλοποίησης στα δικά σας έργα.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}