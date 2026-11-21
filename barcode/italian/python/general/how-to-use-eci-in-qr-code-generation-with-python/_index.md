---
category: general
date: 2026-11-20
description: Scopri come usare l'ECI, generare QR da testo, svuotare il builder e
  salvare l'immagine QR usando la libreria Python barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: it
lastmod: 2026-11-20
og_description: Come utilizzare ECI per generare QR da testo, cancellare il costruttore
  QR e salvare l'immagine QR – una guida completa passo passo.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Come utilizzare ECI nella generazione di codici QR con Python
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
title: Come usare ECI nella generazione di codici QR con Python
url: /it/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come usare ECI nella generazione di codici QR con Python

Se hai bisogno di **how to use eci** quando crei codici QR, questa guida mostra i passaggi esatti. Vedrai come generare QR da testo, cancellare il builder e infine salvare l'immagine QR—tutto con poche righe di Python.

I codici QR che contengono dati multilingue spesso richiedono un segmento Extended Channel Interpretation (ECI) affinché gli scanner sappiano quale set di caratteri applicare. Questo tutorial ti guida nella creazione di un codetext esteso, nella cancellazione del builder quando lo ri‑utilizzi e nella persistenza del risultato come file PNG.

## Prerequisiti

- Python 3.8+ installato.
- Il pacchetto Aspose.BarCode per Python via .NET (o qualsiasi libreria `barcode` compatibile che fornisca `ExtCodetextBuilder` e `BarcodeGenerator`).
- Familiarità di base con i concetti dei codici QR.

Installa la libreria con pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Usa un ambiente virtuale per evitare conflitti di versione.

## Passo 1: Importa le classi richieste

Le classi principali con cui lavorerai sono `ExtCodetextBuilder` per costruire il codetext esteso e `BarcodeGenerator` per generare il codice QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Queste importazioni ti danno accesso ai metodi del builder (`add_plain_codetext`, `add_eci_codetext`, ecc.) e alle funzioni del generatore `set_code_text`, `set_symbology` e `save`.

## Passo 2: Crea e configura l'ExtCodetextBuilder

Creare una nuova istanza del builder è il primo esempio concreto di **how to use eci**. Puoi anche cancellare il builder in seguito se hai bisogno di riutilizzarlo.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Chiamare `clear()` garantisce che il builder inizi con uno stato pulito, il che è essenziale quando si generano più codici QR in un ciclo.

## Passo 3: Aggiungi codetext plain (non‑ECI)

Il testo plain non richiede un segmento ECI. Usa `add_plain_codetext` per stringhe compatibili ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Il builder ora contiene il segmento plain `"HelloWorld"`.

## Passo 4: Aggiungi un segmento codificato ECI

Ecco il cuore di **how to use eci**: specifichi il valore ECI (26 per UTF‑8) e fornisci la stringa Unicode che desideri codificare. Questo permette al codice QR di contenere russo, cinese o qualsiasi altra lingua non coperta dal set predefinito ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** Senza l'indicatore ECI, uno scanner interpreterebbe i byte usando il set di caratteri predefinito e mostrerebbe caratteri illeggibili per il testo non‑ASCII.

## Passo 5: Recupera la stringa codetext estesa combinata

Dopo aver aggiunto tutti i segmenti richiesti, recupera la stringa finale che verrà passata al generatore QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Il valore stampato appare più o meno così:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Il formato esatto dipende dalla libreria, ma la parte importante è che il marcatore ECI (`[ECI26]`) precede il payload UTF‑8.

## Passo 6: Genera il codice QR usando il testo combinato

Ora puoi **generate QR from text** passando il codetext esteso a `BarcodeGenerator`.

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

Quando apri `qr_extended.png`, appare un codice QR che codifica sia la stringa inglese plain sia il saluto russo. Scansionandolo con uno scanner QR moderno verrà visualizzato correttamente “HelloWorld” e “Привет”.

### Perché dovresti chiamare `clear()` prima di riutilizzare il builder

Se generi più codici QR in un ciclo, dimenticare di cancellare il builder concatenarà i vecchi segmenti con quelli nuovi, producendo un codice non valido. Ecco un modello rapido:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Questo snippet illustra **how to clear builder** e **how to generate QR from text** ripetutamente.

## Casi limite e problemi comuni

| Situazione | Cosa controllare | Come gestire |
|-----------|-------------------|---------------|
| **Valore ECI non supportato** | La libreria solleva `InvalidArgumentException`. | Usa solo i valori ECI elencati nella specifica (ad esempio 26 per UTF‑8, 20 per Shift‑JIS). |
| **Testo combinato molto lungo** | La versione QR potrebbe superare la capacità massima. | Incrementa automaticamente la versione QR (`qr_generator.set_qr_version(QRVersion.AUTO)`) o dividi i dati su più codici QR. |
| **Errori di permessi del file‑system** | `save` fallisce con `IOError`. | Assicurati che la directory di destinazione esista e che il processo abbia i permessi di scrittura. |
| **Visualizzazione errata del charset** | Lo scanner mostra caratteri illeggibili. | Verifica che il valore ECI corretto corrisponda alla codifica effettiva della stringa. |

## Esempio completo eseguibile

Di seguito è riportato uno script autonomo che puoi copiare, incollare ed eseguire. Include tutte le importazioni, la gestione degli errori e i commenti per chiarezza.

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

Eseguendo questo script si genera `output/qr_extended.png`, un codice QR che codifica correttamente sia il testo inglese sia quello russo.

## Conclusione

Ora sai **how to use eci** quando costruisci codici QR, come **clear the QR builder** prima del riutilizzo, come **generate QR from text**, e i passaggi esatti per **save QR image** con Python. Seguendo il modello sopra, puoi incorporare qualsiasi stringa Unicode in un codice QR mantenendo lo stato del builder prevedibile.

### Cosa c’è dopo?

- Esplora altri valori ECI per lingue come il cinese (ECI 20) o ISO‑8859‑5.
- Regola i livelli di correzione degli errori (`qr_generator.set_error_correction_level`) per migliorare l'affidabilità della scansione.
- Combina più segmenti ECI in un unico QR per messaggi multilingua.

Buon coding e divertiti a creare codici QR multilingue!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare barcode con ECI usando Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Come generare immagine QR Code in Python con Aspose.Barcode – Guida completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Come generare barcode in Python – guida completa passo‑passo](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}