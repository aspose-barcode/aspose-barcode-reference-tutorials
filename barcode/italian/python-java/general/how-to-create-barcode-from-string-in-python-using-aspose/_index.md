---
category: general
date: 2026-10-15
description: Crea un codice a barre da una stringa con Aspose.Barcode per Python.
  Scopri come generare il codice a barre, impostare le dimensioni e salvarlo come
  PNG in pochi minuti.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: it
lastmod: 2026-10-15
og_description: Crea un codice a barre da una stringa con Aspose.Barcode per Python.
  Questo tutorial ti mostra passo passo come generare un codice a barre postale e
  salvarlo come PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Crea codice a barre da una stringa in Python – Guida Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Come creare un codice a barre da una stringa in Python usando Aspose
url: /it/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un barcode da una stringa in Python usando Aspose

Se hai bisogno di **creare un barcode da una stringa** rapidamente, Aspose.Barcode per Python lo rende semplice. In questa guida vedrai esattamente **come generare barcode** immagini, regolare la dimensione X e salvare il risultato come file PNG—tutto con poche righe di codice.

Otterrai anche un **esempio completo di generatore di barcode** che potrai copiare‑incollare nel tuo progetto. Non sono necessari script esterni né configurazioni complesse, e il tutorial funziona con l'attuale versione Aspose.Barcode 23.10.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- Python 3.8+ installato sulla tua macchina  
- Una licenza attiva di Aspose.Barcode per Python (la versione di prova gratuita è valida per la valutazione)  
- `pip install aspose-barcode` eseguito nel tuo ambiente virtuale  

Questi elementi garantiscono che il codice venga eseguito senza errori di import.

## Creare un barcode da una stringa con Aspose.Barcode (Python)

Il primo passo è istanziare il `BarcodeGenerator` con la simbologia desiderata—in questo caso il barcode postale **Planet**—e la stringa che vuoi codificare.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Perché è importante:**  
`EncodeTypes.Planet` indica ad Aspose di utilizzare la simbologia postale Planet, progettata per l'ordinamento della posta in molti paesi. Il secondo argomento (`"123456"`) è la stringa grezza che verrà codificata nel barcode. Modificando questo valore puoi **creare un barcode da una stringa** per qualsiasi codice postale o numero di tracciamento di cui hai bisogno.

## Come generare un barcode con dimensioni personalizzate

La larghezza del modulo di un barcode postale (la dimensione X) spesso deve corrispondere alle specifiche di stampa. Aspose ti consente di impostare la larghezza in pixel mentre calcola automaticamente l'altezza.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Perché potresti modificarla:**  
Una dimensione X più grande rende le barre più spesse, il che può migliorare l'affidabilità della scansione su stampanti a bassa risoluzione. Al contrario, un valore più piccolo riduce le dimensioni dell'immagine per l'uso sul web. Questa riga dimostra **come generare barcode** immagini che soddisfano requisiti di dimensione precisi.

## Salva l'immagine del barcode

Dopo aver configurato il generatore, basta chiamare `save`. Il metodo accetta il percorso di output e il formato immagine desiderato.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Cosa ottieni:**  
Un file PNG chiamato `PostalPlanetAuto.png` contenente il barcode Planet che codifica "123456". Puoi aprire il file con qualsiasi visualizzatore di immagini per verificare il risultato.

![Screenshot di un barcode postale generato salvato come PNG](barcode_example.png){.align-center alt="Screenshot di un barcode postale generato salvato come PNG"}

## Esempio completo di generatore di barcode

Di seguito trovi lo script completo, pronto per l'esecuzione, che include tutti i passaggi precedenti. Copialo in un file chiamato `generate_postal_barcode.py` ed esegui `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Output previsto

Eseguendo lo script si ottiene:

```
Barcode saved to PostalPlanetAuto.png
```

…e crea un file `PostalPlanetAuto.png` che appare così:

![Barcode Planet generato](barcode_example.png){.align-center alt="Barcode Planet generato salvato come PNG"}

## Varianti comuni e casi limite

| Situazione | Cosa cambiare | Perché |
|-----------|----------------|-----|
| **Simbologia diversa** (ad es., Code128) | Sostituire `EncodeTypes.Planet` con `EncodeTypes.Code128` | Consente di **generare barcode** per etichette di inventario, non solo per codici postali. |
| **Stringhe di dati più lunghe** | Assicurati che la simbologia scelta supporti la lunghezza; per Planet devi mantenere 6 cifre. | Previene `ValueError` a runtime. |
| **Risoluzione più alta** | Aumentare `x_dimension.pixels` a 6 o 8. | Produce barre più spesse per la stampa ad alta DPI. |
| **Altri formati immagine** | Usare `BarCodeImageFormat.JPEG` o `BarCodeImageFormat.GIF`. | Utile quando PNG non è adatto al tuo flusso di lavoro. |
| **Esecuzione in un servizio web** | Sostituire la chiamata `save` del file system con uno stream `BytesIO` e restituire i byte. | Abilita la generazione di barcode al volo in Flask o Django. |

**Consiglio professionale:** Valida sempre la stringa di input prima di chiamare `BarcodeGenerator`. Dati non validi (lunghezza errata, caratteri non numerici per Planet) genereranno un'eccezione e interromperanno la tua applicazione.

## Come generare un barcode in un endpoint Flask (passo opzionale successivo)

Se vuoi esporre l'**esempio di generatore di barcode** come API REST, puoi avvolgere la funzione `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Questo frammento mostra come **generare barcode** su richiesta senza scrivere su disco, utile per micro‑servizi.

## Conclusione

Ora sai come **creare un barcode da una stringa** in Python usando Aspose.Barcode, come **generare barcode** con dimensioni personalizzate e come **salvare** il risultato come file PNG. L'**esempio completo di generatore di barcode** include la validazione dell'input, la gestione degli errori e una funzione riutilizzabile che puoi integrare in applicazioni più grandi.

Successivamente, esplora altre simbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) o incorpora il generatore in un framework web come Flask o Django. Entrambi i passaggi approfondiranno la tua comprensione della libreria **aspose barcode python** e ampliano i modi in cui puoi **generare barcode postali** per progetti reali.

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare barcode in Python – guida completa passo‑passo](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Crea barcode PNG in Python – Guida completa Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Come generare barcode con ECI usando Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}