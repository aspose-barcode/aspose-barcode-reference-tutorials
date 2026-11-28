---
category: general
date: 2026-11-27
description: Scopri come regolare l'altezza delle barre del codice a barre in un generatore
  DataBar Omni‑Directional. Il codice passo‑passo mostra come impostare le altezze
  a 30 px e 60 px.
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
language: it
lastmod: 2026-11-27
og_description: Regola l'altezza delle barre del codice a barre in un generatore DataBar
  Omni‑Directional con Python. Segui la guida completa per impostare le altezze, la
  dimensione X e salvare le immagini PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Regola l'altezza delle barre del codice a barre nel generatore DataBar Omni‑Directional
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
title: Come regolare l'altezza delle barre del codice a barre nel generatore DataBar
  Omni‑Directional
url: /it/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come regolare l'altezza delle barre del codice a barre nel generatore DataBar Omni‑Directional

Se hai bisogno di **regolare l'altezza delle barre del codice a barre** per un codice DataBar Omni‑Directional, questa guida ti mostra esattamente come fare. Vedrai un esempio Python completo e eseguibile che cambia l'altezza delle barre da 30 px a 60 px mantenendo costanti la X‑dimension e il formato immagine.

Modificare le dimensioni visive di un codice a barre è una necessità comune quando il codice deve adattarsi a una dimensione di etichetta specifica o a una linea guida di design. Oltre all'altezza delle barre, potresti anche voler regolare la **X‑dimension** (dimensione del modulo) o scegliere un diverso **formato immagine del codice a barre** come PNG o JPEG.

In questo tutorial tu:

* Installare la libreria richiesta (GroupDocs.Barcode per Python)
* Creare un generatore di codice a barre DataBar Omni‑Directional
* Impostare la dimensione del modulo con `XDimension`
* Regolare la proprietà dell'altezza della barra due volte
* Salvare le immagini risultanti nel **BarCodeImageFormat** desiderato

Nessuna esperienza pregressa con l'API di GroupDocs è necessaria — basta una conoscenza di base di Python.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installato
* Pacchetto `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Permessi di scrittura su una cartella dove verranno salvati i file PNG

Se non conosci il **codice a barre DataBar Omni‑Directional**, esso codifica un GTIN a 14 cifre ed è ampiamente usato nel retail per la scansione da qualsiasi orientamento.

## Passo 1: Configurare il generatore di codice a barre DataBar Omni‑Directional

Per prima cosa, importa le classi necessarie e istanzia il generatore con i dati GTIN che desideri codificare.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Perché è importante:* La costante `EncodeTypes.DatabarOmniDirectional` indica alla libreria di produrre la simbologia Omni‑Directional. La stringa di dati include l'AI `(01)` che identifica un valore GTIN‑14.

## Passo 2: Definire la X‑dimension (dimensione del modulo)

La X‑dimension controlla la larghezza della barra più stretta. Un valore comune per il rendering su schermo è **2 px per modulo**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Utilizzare un **set XDimension** coerente garantisce che il codice a barre venga scalato correttamente su diverse stampanti e scanner.

## Passo 3: Regolare l'altezza della barra a 30 px e salvare l'immagine

Ora modifichiamo la proprietà dell'altezza della barra. La prima altezza che utilizzeremo è **30 px**, adatta per etichette piccole.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

La costante `BarCodeImageFormat.Png` seleziona il **formato immagine del codice a barre** PNG, che preserva la qualità senza perdita.

### Risultato atteso

Il file `DatabarBarHeight30Pixels.png` contiene un codice a barre DataBar Omni‑Directional le cui barre sono alte 30 px. Di seguito è mostrata un'anteprima segnaposto:

![Codice a barre DataBar con altezza barra 30 px](images/databar_30px.png "Codice a barre DataBar con altezza barra 30 px")

> **Suggerimento:** Se apri il PNG in un editor di immagini, vedrai l'esatta altezza della barra. Le barre strette sono larghe 2 px, come definito in precedenza.

## Passo 4: Cambiare l'altezza della barra a 60 px per un codice a barre più alto

Per applicazioni che richiedono un'impronta visiva più grande — come un'etichetta di spedizione — è possibile aumentare l'altezza della barra a **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Solo la proprietà `BarHeight` cambia; la X‑dimension e la codifica rimangono invariate, quindi il codice a barre resta leggibile.

## Passo 5: Salvare l'immagine del codice a barre aggiornato

Infine, scrivi il codice a barre più alto in un secondo file PNG.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Risultato atteso

Il file `DatabarBarHeight60Pixels.png` mostra gli stessi dati codificati, ma ogni barra è ora alta 60 px. La differenza visiva è illustrata di seguito:

![Codice a barre DataBar con altezza barra 60 px](images/databar_60px.png "Codice a barre DataBar con altezza barra 60 px")

## Esempio completo, eseguibile

Riunendo tutto, ecco lo script completo che puoi copiare‑incollare in un file chiamato `adjust_barcode_height.py` ed eseguire direttamente.

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

Esegui lo script:

```bash
python adjust_barcode_height.py
```

Dovresti vedere due file PNG nella cartella `output`, ciascuno con l'altezza della barra impostata.

## Domande comuni e casi particolari

| Domanda | Risposta |
|----------|--------|
| **Posso usare JPEG invece di PNG?** | Sì. Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg`. JPEG è con perdita, quindi è preferibile PNG per una scansione precisa. |
| **E se ho bisogno di un'altezza della barra che non è un multiplo di 10?** | La proprietà `BarHeight.Pixels` accetta qualsiasi valore intero. Basta assegnare il numero di pixel desiderato (ad esempio `45`). |
| **Modificare l'altezza della barra influisce sui dati codificati?** | No. Cambia solo la rappresentazione visiva; la stringa dei dati sottostante rimane identica. |
| **Come posso cambiare la X‑dimension dopo aver salvato la prima immagine?** | Puoi modificare `gen.parameters.barcode.x_dimension.pixels` in qualsiasi momento prima di chiamare `save()`. La modifica verrà applicata alle immagini successive. |
| **Il generatore è thread‑safe?** | L'istanza `BarcodeGenerator` non è garantita come thread‑safe. Crea un'istanza separata per thread se generi codici a barre in modo concorrente. |

## Conclusione

Ora sai come **regolare l'altezza delle barre del codice a barre** in un generatore DataBar Omni‑Directional usando Python. Il tutorial ha coperto la creazione del generatore, l'impostazione della **X‑dimension**, la modifica della proprietà **barcode bar height**, e il salvataggio delle immagini nel **formato immagine del codice a barre** desiderato.

Da qui puoi sperimentare altre altezze, diverse dimensioni del modulo, o passare a formati immagine alternativi come JPEG o BMP. Potresti anche esplorare ulteriori funzionalità **barcode generator python** come aggiungere testo leggibile dall'uomo o cambiare gli schemi di colore.

Buona programmazione, e mantieni i tuoi codici a barre nitidi e perfettamente dimensionati!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell'API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come impostare larghezza e regolare altezza per un codice a barre GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Creare databar omni‑directional e immagine del codice a barre in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – cambiare altezza del codice a barre](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}