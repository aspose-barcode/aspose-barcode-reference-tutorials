---
category: general
date: 2026-11-20
description: Μάθετε πώς να χρησιμοποιείτε το ECI, να δημιουργείτε QR από κείμενο,
  να καθαρίζετε τον δημιουργό και να αποθηκεύετε την εικόνα QR χρησιμοποιώντας τη
  βιβλιοθήκη barcode της Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: el
lastmod: 2026-11-20
og_description: Πώς να χρησιμοποιήσετε το ECI για να δημιουργήσετε QR από κείμενο,
  να καθαρίσετε τον δημιουργό QR και να αποθηκεύσετε την εικόνα QR – ένας πλήρης οδηγός
  βήμα‑προς‑βήμα.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Πώς να χρησιμοποιήσετε το ECI στη δημιουργία κωδίκων QR με την Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Πώς να χρησιμοποιήσετε το ECI στη δημιουργία QR κωδίκων με Python
url: /el/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να χρησιμοποιήσετε το ECI στη δημιουργία QR κώδικα με Python

Αν χρειάζεστε **πώς να χρησιμοποιήσετε eci** κατά τη δημιουργία QR κωδίκων, αυτός ο οδηγός δείχνει τα ακριβή βήματα. Θα δείτε πώς να δημιουργήσετε QR από κείμενο, να καθαρίσετε τον builder και τέλος να αποθηκεύσετε την εικόνα QR — όλα με λίγες γραμμές Python.

Οι QR κώδικες που περιέχουν πολυγλωσσικά δεδομένα συχνά απαιτούν ένα τμήμα Extended Channel Interpretation (ECI) ώστε οι σαρωτές να γνωρίζουν ποιο σύνολο χαρακτήρων να εφαρμόσουν. Αυτό το tutorial σας καθοδηγεί στη δημιουργία ενός επεκταμένου codetext, στον καθαρισμό του builder όταν τον επαναχρησιμοποιείτε και στην αποθήκευση του αποτελέσματος ως αρχείο PNG.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:

- Εγκατεστημένο Python 3.8+.
- Το πακέτο Aspose.BarCode for Python via .NET (ή οποιαδήποτε συμβατή βιβλιοθήκη `barcode` που παρέχει `ExtCodetextBuilder` και `BarcodeGenerator`).
- Βασική εξοικείωση με τις έννοιες των QR κωδίκων.

Εγκαταστήστε τη βιβλιοθήκη με pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Χρησιμοποιήστε ένα εικονικό περιβάλλον (virtual environment) για να αποφύγετε συγκρούσεις εκδόσεων.

## Βήμα 1: Εισαγωγή των απαιτούμενων κλάσεων

Οι κύριες κλάσεις με τις οποίες θα δουλέψετε είναι `ExtCodetextBuilder` για την κατασκευή του επεκταμένου codetext και `BarcodeGenerator` για την απόδοση του QR κώδικα.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Αυτές οι εισαγωγές σας δίνουν πρόσβαση στις μεθόδους του builder (`add_plain_codetext`, `add_eci_codetext`, κ.λπ.) και στις συναρτήσεις του generator όπως `set_code_text`, `set_symbology` και `save`.

## Βήμα 2: Δημιουργία και διαμόρφωση του ExtCodetextBuilder

Η δημιουργία ενός νέου αντικειμένου builder είναι το πρώτο συγκεκριμένο παράδειγμα του **πώς να χρησιμοποιήσετε eci**. Μπορείτε επίσης να καθαρίσετε τον builder αργότερα αν χρειαστεί να τον επαναχρησιμοποιήσετε.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Η κλήση `clear()` εξασφαλίζει ότι ο builder ξεκινάει με καθαρή κατάσταση, κάτι απαραίτητο όταν δημιουργείτε πολλαπλούς QR κώδικες σε βρόχο.

## Βήμα 3: Προσθήκη απλού (μη‑ECI) codetext

Το απλό κείμενο δεν χρειάζεται τμήμα ECI. Χρησιμοποιήστε `add_plain_codetext` για συμβολοσειρές συμβατές με ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Ο builder τώρα περιέχει το απλό τμήμα `"HelloWorld"`.

## Βήμα 4: Προσθήκη τμήματος κωδικοποιημένου με ECI

Εδώ είναι ο πυρήνας του **πώς να χρησιμοποιήσετε eci**: καθορίζετε την τιμή ECI (26 για UTF‑8) και παρέχετε τη Unicode συμβολοσειρά που θέλετε να κωδικοποιήσετε. Αυτό επιτρέπει στον QR κώδικα να μεταφέρει Ρωσικά, Κινέζικα ή οποιαδήποτε άλλη γλώσσα που δεν καλύπτεται από το προεπιλεγμένο σύνολο ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Γιατί είναι σημαντικό:** Χωρίς τον δείκτη ECI, ένας σαρωτής θα ερμηνεύσει τα bytes χρησιμοποιώντας το προεπιλεγμένο σύνολο χαρακτήρων και θα εμφανίσει ακατάληπτους χαρακτήρες για κείμενο που δεν είναι ASCII.

## Βήμα 5: Ανάκτηση του συνδυασμένου επεκταμένου codetext

Αφού προσθέσετε όλα τα απαιτούμενα τμήματα, πάρτε την τελική συμβολοσειρά που θα περάσει στον QR generator.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Η εκτυπωμένη τιμή φαίνεται περίπου έτσι:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Η ακριβής μορφή εξαρτάται από τη βιβλιοθήκη, αλλά το σημαντικό είναι ότι ο δείκτης ECI (`[ECI26]`) προηγείται του payload UTF‑8.

## Βήμα 6: Δημιουργία του QR κώδικα χρησιμοποιώντας το συνδυασμένο κείμενο

Τώρα μπορείτε να **δημιουργήσετε QR από κείμενο** περνώντας το επεκταμένο codetext στο `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Όταν ανοίξετε το `qr_extended.png`, θα εμφανιστεί ένας QR κώδικας που κωδικοποιεί τόσο τη απλή αγγλική συμβολοσειρά όσο και το ρωσικό χαιρετισμό. Σαρώνοντας το με έναν σύγχρονο QR σαρωτή θα εμφανιστούν σωστά τα “HelloWorld” και “Привет”.

### Γιατί πρέπει να καλέσετε `clear()` πριν επαναχρησιμοποιήσετε τον builder

Αν δημιουργείτε πολλαπλούς QR κώδικες σε βρόχο, η παράλειψη του `clear()` θα συγχωνεύσει παλιά τμήματα με νέα, παράγοντας έναν άκυρο κώδικα. Εδώ είναι ένα γρήγορο πρότυπο:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Αυτό το απόσπασμα δείχνει **πώς να καθαρίσετε τον builder** και **πώς να δημιουργήσετε QR από κείμενο** επανειλημμένα.

## Ακραίες περιπτώσεις και κοινά προβλήματα

| Κατάσταση | Σε τι πρέπει να προσέξετε | Πώς να το αντιμετωπίσετε |
|-----------|---------------------------|--------------------------|
| **Μη υποστηριζόμενη τιμή ECI** | Η βιβλιοθήκη ρίχνει `InvalidArgumentException`. | Χρησιμοποιήστε μόνο τιμές ECI που αναφέρονται στην προδιαγραφή (π.χ. 26 για UTF‑8, 20 για Shift‑JIS). |
| **Πολύ μεγάλο συνδυασμένο κείμενο** | Η έκδοση QR μπορεί να υπερβεί τη μέγιστη χωρητικότητα. | Αυξήστε αυτόματα την έκδοση QR (`qr_generator.set_qr_version(QRVersion.AUTO)`) ή χωρίστε τα δεδομένα σε πολλαπλούς QR κώδικες. |
| **Σφάλματα δικαιωμάτων συστήματος αρχείων** | Η `save` αποτυγχάνει με `IOError`. | Βεβαιωθείτε ότι ο προορισμός υπάρχει και ότι η διαδικασία έχει δικαιώματα εγγραφής. |
| **Λανθασμένη εμφάνιση charset** | Ο σαρωτής εμφανίζει ακατάληπτους χαρακτήρες. | Επαληθεύστε ότι η τιμή ECI ταιριάζει με την πραγματική κωδικοποίηση της συμβολοσειράς. |

## Πλήρες εκτελέσιμο παράδειγμα

Παρακάτω υπάρχει ένα αυτόνομο script που μπορείτε να αντιγράψετε, να επικολλήσετε και να εκτελέσετε. Περιλαμβάνει όλες τις εισαγωγές, τον χειρισμό σφαλμάτων και σχόλια για σαφήνεια.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Η εκτέλεση αυτού του script παράγει το `output/qr_extended.png`, έναν QR κώδικα που κωδικοποιεί σωστά τόσο το αγγλικό όσο και το ρωσικό κείμενο.

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να χρησιμοποιήσετε eci** κατά την κατασκευή QR κωδίκων, **πώς να καθαρίσετε τον QR builder** πριν τον επαναχρησιμοποιήσετε, **πώς να δημιουργήσετε QR από κείμενο** και τα ακριβή βήματα για **να αποθηκεύσετε εικόνα QR** με Python. Ακολουθώντας το παραπάνω μοτίβο, μπορείτε να ενσωματώσετε οποιαδήποτε Unicode συμβολοσειρά σε έναν QR κώδικα διατηρώντας την κατάσταση του builder προβλέψιμη.

### Τι ακολουθεί;

- Εξερευνήστε άλλες τιμές ECI για γλώσσες όπως τα Κινέζικα (ECI 20) ή ISO‑8859‑5.
- Ρυθμίστε τα επίπεδα διόρθωσης σφαλμάτων (`qr_generator.set_error_correction_level`) για βελτιωμένη αξιοπιστία σάρωσης.
- Συνδυάστε πολλαπλά τμήματα ECI σε έναν QR για μηνύματα μεικτής γλώσσας.

Καλό κώδικα και καλή δημιουργία πολυγλωσσικών QR κωδίκων!

## Τι πρέπει να μάθετε στη συνέχεια;

Οι παρακάτω οδηγίες καλύπτουν στενά συναφή θέματα που επεκτείνουν τις τεχνικές που παρουσιάζονται σε αυτόν τον οδηγό. Κάθε πόρος περιλαμβάνει πλήρη λειτουργικά παραδείγματα κώδικα με βήμα‑βήμα εξηγήσεις για να σας βοηθήσουν να κυριαρχήσετε επιπλέον δυνατότητες του API και να εξερευνήσετε εναλλακτικές προσεγγίσεις στην υλοποίηση των δικών σας έργων.

- [Πώς να δημιουργήσετε barcode με ECI χρησιμοποιώντας Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Πώς να δημιουργήσετε εικόνα QR Code σε Python με Aspose.Barcode – Πλήρης Οδηγός](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Πώς να δημιουργήσετε barcode σε Python – πλήρης οδηγός βήμα‑βήμα](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}