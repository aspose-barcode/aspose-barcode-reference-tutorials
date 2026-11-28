---
category: general
date: 2026-11-27
description: Impara a creare codici a barre con testo e a generare codici a barre
  planet in Python—guida passo‑passo per output PNG ad alta risoluzione.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: it
lastmod: 2026-11-27
og_description: Crea un codice a barre con testo e genera il codice a barre planet
  in Python. Segui questa guida completa per ottenere un PNG ad alta risoluzione.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Crea un codice a barre con testo in Python – genera facilmente il codice
  a barre Planet
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Come creare un codice a barre con testo usando il formato Planet in Python
url: /it/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre con testo usando il formato Planet in Python

Se hai bisogno di **creare un codice a barre con testo** per un sistema di spedizione, questo tutorial ti mostra esattamente come farlo. Vedrai un esempio conciso, end‑to‑end, che genera un codice a barre Planet, regola la risoluzione e salva il risultato come immagine PNG.

Generare codici a barre è una necessità comune per applicazioni di logistica, inventario e biglietteria. In questa guida imparerai non solo **come generare file di codice a barre**, ma anche perché ogni passaggio di configurazione è importante e come evitare le insidie tipiche.

## Cosa imparerai

* Configurare il generatore di codici a barre Planet con testo personalizzato.  
* Regolare la dimensione X per aumentare la nitidezza dell'immagine.  
* Salvare il codice a barre come file PNG che può essere stampato o visualizzato sul web.  
* Estendere l'esempio ad altri tipi di codice a barre o formati di output.  

**Prerequisiti**

* Python 3.8 o versioni successive.  
* Il pacchetto `aspose-barcode` (o qualsiasi libreria compatibile che fornisca `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).  
* Familiarità di base con la programmazione Python.  

Puoi installare il pacchetto richiesto con:

```bash
pip install aspose-barcode
```

---

## Passo 1: Creare un codice a barre con testo – inizializzare il generatore

La prima cosa da fare è creare un'istanza di `BarcodeGenerator` che sappia quale simbologia utilizzare e quale testo codificare. Per un codice a barre Planet il valore enum `EncodeTypes.Planet` indica alla libreria di seguire la specifica USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Perché è importante:**  
L'oggetto `BarcodeGenerator` incapsula tutte le impostazioni per il codice a barre. Fornire il testo al momento della costruzione garantisce che il valore codificato sia immutabile per il resto del processo, eliminando così eventuali incongruenze accidentali.

---

## Passo 2: Regolare le impostazioni – come generare un codice a barre con risoluzione più alta

Un codice a barre a bassa risoluzione può apparire sfocato quando stampato su una stampante di etichette. La dimensione X (larghezza del modulo) controlla la dimensione di ogni singola barra. Impostandola a 4 pixel si ottiene un'immagine nitida, ad alta risoluzione, adatta alla maggior parte delle stampanti moderne.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Spiegazione:**  
* `gen.parameters.barcode.x_dimension.pixels` mappa direttamente alla larghezza fisica di un singolo modulo.  
* Un valore di **4** significa che ogni barra è larga quattro pixel, corrispondente approssimativamente a 0,127 mm a 300 dpi — ben entro l'intervallo consigliato per i codici a barre USPS Planet.  

**Consiglio professionale:** Se ti serve un DPI diverso, calcola la larghezza in pixel di conseguenza (ad esempio, 2 pixel per 150 dpi, 8 pixel per 600 dpi).

---

## Passo 3: Salvare l'immagine – generare il codice a barre Planet come PNG

Ora che il generatore è configurato, puoi renderizzare il codice a barre in un file immagine. PNG è loss‑less, garantendo che il pattern dei moduli rimanga intatto.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Risultato:**  
Eseguendo lo script viene creato un file chiamato `PostalPlanetBarHeightNone.png` che contiene un codice a barre Planet che codifica la stringa “123456”. Le dimensioni dell'immagine saranno approssimativamente 200 × 100 pixel, a seconda della dimensione X scelta.

---

## Opzionale: Verificare il codice a barre visivamente

Puoi aprire rapidamente il PNG generato con qualsiasi visualizzatore di immagini per confermare che il codice a barre sia nitido e che il testo leggibile dall'uomo sia presente sotto il pattern.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Se l'immagine appare sfocata, torna al **Passo 2** e aumenta la dimensione X finché le barre non saranno chiaramente definite.

---

## Varianti comuni e casi limite

| Situazione | Regolazione |
|-----------|------------|
| **Lunghezza del testo diversa** | I codici a barre Planet supportano fino a 12 caratteri numerici. Se superi questo limite, la libreria solleverà un'eccezione. |
| **Formato di output alternativo** | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Bmp` per altri casi d'uso. |
| **Colori personalizzati di primo piano/sfondo** | Usa `gen.parameters.barcode.barcode_color = Color.Blue` e `gen.parameters.barcode.back_color = Color.White`. |
| **Nessun testo leggibile** | Imposta `gen.parameters.barcode.hide_code_text = True` per generare un codice a barre senza la didascalia inferiore. |
| **Generazione batch** | Itera su una lista di stringhe, crea un nuovo `BarcodeGenerator` per ciascuna e salvali in file con nomi univoci. |

Queste varianti ti consentono di **generare file di codice a barre planet** che si adattano a un'ampia gamma di requisiti aziendali.

---

## Script completo – pronto da eseguire

Di seguito trovi lo script completo e autonomo che puoi copiare, incollare ed eseguire. Include tutti gli import, la gestione degli errori e i commenti.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Spiegazione dello script**

* La funzione `create_planet_barcode` incapsula i tre passaggi principali, rendendo il codice riutilizzabile.  
* La convalida dell'input garantisce che tu segua la specifica Planet (solo numerico, max 12 cifre).  
* La funzione crea automaticamente la cartella di output, così non è necessario gestire manualmente le directory.  
* Dopo la generazione, lo script apre l'immagine usando Pillow (`PIL`) per una verifica immediata.

---

## Conclusione

Ora sai come **creare un codice a barre con testo** e **generare file di codice a barre planet** in Python. La guida ha coperto l'inizializzazione, la regolazione della risoluzione e l'output del file, insieme a personalizzazioni opzionali e casi limite comuni.  

Da qui puoi:

* Sostituire `EncodeTypes.Planet` con altre simbologie (ad esempio `EncodeTypes.Code128`) per riutilizzare lo stesso modello.  
* Integrare la funzione in un servizio web che restituisce immagini di codici a barre su richiesta.  
* Sperimentare con l'elaborazione batch per produrre migliaia di codici a barre per invii di massa.  

Sentiti libero di adattare lo script alle esigenze del tuo progetto e condividere i risultati nei commenti. Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità aggiuntive dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come generare un codice a barre in Python – guida completa passo‑passo](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Creare un codice a barre PNG in Python – guida passo‑passo](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Come creare un codice a barre planet PNG con Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}