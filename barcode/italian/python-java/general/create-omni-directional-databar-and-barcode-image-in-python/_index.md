---
category: general
date: 2026-08-12
description: Crea un databar omnidirezionale con Python e impara come generare un'immagine
  di codice a barre in Python usando Aspose.BarCode. Segui la guida passo passo per
  una soluzione completa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: it
lastmod: 2026-08-12
og_description: Crea un databar omnidirezionale con Python e genera un'immagine di
  codice a barre in pochi minuti. Questo tutorial mostra un esempio completo e eseguibile.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Crea una databar omnidirezionale – guida completa in Python
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Crea immagine di databar e codice a barre omnidirezionale in Python
url: /it/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea omni directional databar e immagine di barcode in Python

Se hai bisogno di **create omni directional databar** in un progetto Python, questa guida ti mostra come farlo e anche come **create barcode image python** usando la libreria Aspose.BarCode. Otterrai uno script pronto all'esecuzione che produce due file PNG con diversi rapporti d'aspetto.

Generare un DataBar che segue la specifica Omni‑directional è una necessità comune per applicazioni di vendita al dettaglio e logistica. Il tutorial copre l'installazione, la configurazione della X‑dimension, la regolazione del rapporto d'aspetto e il salvataggio delle immagini finali. Non sono richiesti servizi esterni; tutto viene eseguito localmente.

## Cosa ti servirà

* Python 3.8 o versioni successive installato sulla tua macchina.
* Accesso a un terminale o prompt dei comandi.
* Permessi di scrittura su una cartella dove verranno salvate le immagini del codice a barre.

L'unica dipendenza di terze parti è **Aspose.BarCode for Python via .NET**, che supporta il tipo Omni‑directional DataBar fin da subito.

## Passo 1: Installa Aspose.BarCode per Python

Aspose.BarCode fornisce la classe `BarcodeGenerator` usata nel codice di esempio. Installa il pacchetto con `pip`:

```bash
pip install aspose-barcode
```

Il pacchetto include i binding necessari per il runtime .NET, quindi non è necessario installare separatamente il .NET SDK.

## Passo 2: Importa la libreria e crea il generatore

La prima riga dello script crea un generatore per un Omni‑directional DataBar impilato. Il valore GTIN‑14 `(01)12345678901231` è usato come dato di esempio.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Perché questo passo è importante*: La costante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` indica alla libreria di codificare il valore come Omni‑directional DataBar, che è il formato richiesto da molti scanner point‑of‑sale.

## Passo 3: Imposta la X‑dimension (larghezza del modulo)

La X‑dimension definisce la larghezza del modulo di barra più piccolo. Un valore di `2` pixel produce un codice a barre chiaro e leggibile senza dimensioni eccessive del file.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Perché questo passo è importante*: Regolare la X‑dimension ti permette di bilanciare leggibilità e dimensioni dell'immagine. Una X‑dimension troppo piccola può risultare poco leggibile su stampanti a bassa risoluzione.

## Passo 4: Configura il rapporto d'aspetto e salva la prima immagine

Il rapporto d'aspetto influenza l'altezza complessiva del DataBar rispetto alla sua larghezza. Un rapporto d'aspetto di `15` crea uno stile visivo compatto.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Suggerimento**: Usa `pathlib.Path` per costruire il percorso di output, che crea automaticamente le directory mancanti.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Passo 5: Cambia il rapporto d'aspetto per un secondo stile visivo e salva un'altra immagine

Modificando il rapporto d'aspetto a `30` si ottiene un codice a barre più alto, che può essere richiesto da hardware scanner specifici.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Perché questo passo è importante*: Diversi rivenditori e dispositivi di scansione hanno vincoli di dimensioni differenti. Fornire entrambi i rapporti d'aspetto in un unico script ti consente di generare lo stile esatto di cui hai bisogno senza duplicare il codice.

## Script completo – create omni directional databar and barcode image python

Di seguito trovi l'esempio completo e eseguibile che incorpora tutti i passaggi precedenti. Salvalo come `generate_databar.py` ed eseguilo con `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Output previsto

Eseguendo lo script vengono creati i seguenti file:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Entrambe le immagini mostrano un Omni‑directional DataBar valido che può essere scansionato dall'attrezzatura retail standard.

![esempio di creazione di immagine di databar omni directional barcode in Python](example_databar.png "crea immagine di databar omni directional barcode python")

*L'immagine sopra è un segnaposto che illustra i due file PNG salvati.*

## Gestione dei problemi comuni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| `ImportError: No module named aspose` | Aspose.BarCode non installato o installato in un ambiente diverso. | Attiva l'ambiente virtuale corretto ed esegui `pip install aspose-barcode`. |
| `PermissionError` when saving | Lo script non ha i permessi di scrittura per la cartella di destinazione. | Scegli una directory di tua proprietà o esegui lo script con i privilegi appropriati. |
| Barcode does not scan | X‑dimension troppo bassa o rapporto d'aspetto incompatibile con lo scanner. | Aumenta `x_dimension.pixels` a 3 o 4 e prova diversi valori di `aspect_ratio` (es., 20, 25). |
| Missing .NET runtime | Aspose.BarCode dipende dal runtime .NET su Windows/Linux. | Installa l'ultimo runtime .NET dal sito di Microsoft; la documentazione del pacchetto fornisce indicazioni specifiche per piattaforma. |

## Estendere l'esempio

Puoi adattare lo script per generare altre varianti di DataBar (es., `DATABAR_STACKED`, `DATABAR_EXPANDED`). Sostituisci la costante `EncodeTypes` di conseguenza:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Se hai bisogno di incorporare il codice a barre in un PDF, Aspose.PDF per Python può importare direttamente il file PNG oppure puoi usare il metodo `save` con `BarCodeImageFormat.Pdf`.

## Conclusione

Questo tutorial ha mostrato come **create omni directional databar** e come **create barcode image python** usando Aspose.BarCode. Ora disponi di uno script completo e riproducibile che genera due file PNG con diversi rapporti d'aspetto, gestisce le problematiche comuni e può essere esteso ad altri formati di codice a barre.

Successivamente, esplora la generazione di QR code, l'aggiunta del codice a barre a fatture PDF o l'automazione dell'elaborazione batch per grandi cataloghi di prodotti. Ognuno di questi argomenti si basa sullo stesso modello `BarcodeGenerator` mostrato qui. Buona programmazione!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera immagine di codice a barre – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Crea immagine di codice a barre DotCode – righe & colonne (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Come creare un'immagine di codice a barre e renderizzarla in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}