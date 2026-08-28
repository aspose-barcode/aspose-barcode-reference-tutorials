---
category: general
date: 2026-07-30
description: Crea un codice a barre Databar Stacked Omnidirectional in Python. Segui
  questa guida passo‑passo per configurare il rapporto d'aspetto, la XDimension e
  esportare PNG usando un generatore di codici a barre Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: it
lastmod: 2026-07-30
og_description: Crea un codice a barre Databar Stacked Omnidirectional in Python.
  Questo tutorial mostra come impostare XDimension, regolare il rapporto d'aspetto
  del DataBar e salvare come PNG con BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Crea codice a barre Databar Stacked Omnidirezionale – Tutorial Python
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
title: Crea un codice a barre Databar impilato omnidirezionale in Python
url: /it/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea un Databar Stacked Omnidirectional Barcode in Python

Hai mai dovuto **creare un databar stacked omnidirectional** barcode in Python ma non sapevi da dove cominciare? Non sei solo: molti sviluppatori si trovano davanti a questo ostacolo quando usano per la prima volta la classe `BarcodeGenerator`. La buona notizia è che l’intero processo è piuttosto lineare una volta comprese le proprietà chiave.

In questa guida percorreremo un esempio completo, eseguibile, che utilizza un **python barcode generator** per impostare l’XDimension, regolare il rapporto d’aspetto del DataBar e infine esportare due file PNG. Alla fine avrai una solida comprensione di come generare simboli stacked omnidirectional di alta qualità per qualsiasi progetto di inventario o logistica.

## Cosa Imparerai

- Come istanziare un generatore **databar stacked omnidirectional** con un payload GTIN‑14.  
- Perché la **dimensione pixel XDimension** è importante per l’affidabilità della scansione.  
- L’impatto del **rapporto d’aspetto DataBar** sulla larghezza rispetto all’altezza delle righe.  
- Come salvare il risultato come file **BarCodeImageFormat PNG**.  
- Consigli per riutilizzare lo stesso oggetto generatore per produrre più varianti senza sovraccarico di memoria.

### Prerequisiti

- Python 3.8+ (la libreria che usiamo è pure‑Python, non richiede wheel compilate).  
- Il pacchetto `barcode-generator` (installalo con `pip install barcode-generator`).  
- Una cartella in cui è possibile scrivere – lo script salverà lì due immagini PNG.

Se sei a tuo agio con le importazioni di base in Python e con il codice orientato agli oggetti, sei pronto a partire.

## Crea Databar Stacked Omnidirectional Barcode – Panoramica dei Passaggi

Di seguito suddividiamo il flusso di lavoro in sei passaggi di dimensioni gestibili. Ogni passaggio è un blocco di codice autonomo che puoi copiare‑incollare in una REPL o in un file script. Sentiti libero di sperimentare – modificare il rapporto d’aspetto o l’XDimension ti darà immediatamente uno stile visivo diverso.

---

## Passo 1: Crea il Generatore Databar Stacked Omnidirectional

La prima cosa da fare è **creare un'istanza del generatore databar stacked omnidirectional**, passando l’enumerazione `EncodeTypes` appropriata e la stringa dei dati.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Perché è importante:** Il flag `EncodeTypes.DatabarStackedOmniDirectional` indica alla libreria di produrre un simbolo stacked omnidirectional, l’unica variante DataBar in grado di codificare fino a 14 cifre mantenendo la leggibilità da qualsiasi angolazione.

---

## Configura la Dimensione Pixel XDimension

La **dimensione pixel XDimension** controlla il modulo più piccolo (la barra nera più sottile). Un valore di `2` pixel funziona bene nella maggior parte degli scenari di visualizzazione su schermo.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Consiglio esperto:** Se prevedi di stampare il codice a barre a DPI elevati, aumenta questo valore a 3 o 4 per evitare bordi sfocati.

---

## Regola il Rapporto d’Aspetto DataBar (15)

Il **rapporto d’aspetto DataBar** determina quanto è larga ogni riga rispetto alla sua altezza. Un rapporto d’aspetto di `15` produce righe più larghe, preferite da molti scanner per una cattura veloce del movimento.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Perché 15?** La specifica ufficiale GS1 raccomanda un rapporto compreso tra 10 e 20 per i simboli stacked omnidirectional. Scegliamo `15` come valore predefinito equilibrato.

---

## Esporta il Barcode come PNG Usando BarCodeImageFormat

Ora che il generatore è configurato, salviamo l’immagine. L’enumerazione `BarCodeImageFormat.Png` garantisce un output lossless, perfetto per l’elaborazione successiva.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Cosa vedrai:** Apri il PNG risultante; dovresti notare un codice a barre pulito, ad alto contrasto, con righe relativamente larghe.

---

## Cambia il Rapporto d’Aspetto DataBar a 30

A volte servono righe più alte anziché più larghe – ad esempio per adattarsi a un’etichetta stretta. Passare il **rapporto d’aspetto DataBar** a `30` rende ogni riga più alta.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Caso limite:** Rapporti molto alti (es. >40) possono far superare l’altezza tipica delle etichette, quindi testali su una stampante reale prima di adottarli.

---

## Esporta nuovamente il Barcode con il Nuovo Rapporto d’Aspetto

Infine, riutilizziamo lo stesso oggetto `barcode_generator` per scrivere un secondo PNG. Non è necessario ricreare il generatore – basta modificare la proprietà e chiamare nuovamente `Save`.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Risultato:** Ora disponi di due file PNG – uno con righe larghe (`AR15`) e l’altro con righe alte (`AR30`). Confrontali fianco a fianco per decidere quale funziona meglio con il tuo scanner.

---

## Esempio Completo Funzionante

Mettendo insieme tutti i pezzi, ecco lo script completo che puoi eseguire subito. Sostituisci `YOUR_DIRECTORY` con un percorso assoluto sul tuo computer.

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

**Output previsto** (nella console):

```
✅ Two PNG files created – AR15 and AR30
```

E due file immagine appariranno nella cartella di destinazione, pronti per i test di scansione.

---

## Conclusione

Abbiamo appena **creato codici a barre databar stacked omnidirectional** in Python, regolato la **dimensione pixel XDimension**, sperimentato due diverse impostazioni del **rapporto d’aspetto DataBar** e esportato i risultati come file **BarCodeImageFormat PNG**. L’intero flusso di lavoro si riduce a poche righe di codice, ma ti offre il pieno controllo sulle caratteristiche visive più importanti per gli scanner.

Qual è il prossimo passo? Prova a cambiare il payload con un GTIN diverso, gioca con i colori convertendo il PNG in un’immagine a palette, o genera un report PDF che includa entrambi i PNG affiancati. La classe `BarcodeGenerator` è sufficientemente flessibile da gestire tutti questi scenari, quindi sentiti libero di sperimentare.

Hai domande su un caso d’uso specifico o incontri un errore? Lascia un commento qui sotto, sarò felice di aiutarti. Buona programmazione!

## Cosa Dovresti Imparare Dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API e a esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}