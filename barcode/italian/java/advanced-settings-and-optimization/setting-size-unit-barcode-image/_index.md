---
date: 2026-02-07
description: Scopri come utilizzare Aspose Barcode per Java per creare un codice a
  barre CODE_128, generare un'immagine del codice a barre in Java e impostare unità
  di dimensione precise—perfetto per i codici a barre per sistemi di inventario o
  per la generazione di etichette di spedizione.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 'aspose barcode java: Crea codice a barre CODE_128 con unità di misura'
url: /it/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java: Crea codice a barre CODE_128 con unità di misura

## Introduzione

In questo tutorial passo‑a‑passo **utilizzerai aspose barcode java** per creare un codice a barre CODE_128, generare un'immagine di codice a barre java e controllare con precisione l'unità di misura dell'output. Che tu stia costruendo un codice a barre per un sistema di inventario, un generatore di etichette di spedizione, o qualsiasi applicazione basata su Java che richiede codici a barre affidabili, Aspose.BarCode per Java ti offre piena flessibilità con poche righe di codice.

## Risposte rapide
- **Di quale libreria ho bisogno?** Aspose.BarCode per Java (aspose barcode java).
- **Quale tipo di codice a barre è coperto?** CODE_128 (crea codice a barre code128 java).
- **Come faccio a impostare l'unità di dimensione?** Usa la proprietà `BarHeight` con `.setPoint()`.
- **Posso generare immagini Java di codici a barre in altri formati?** Sì: PNG, JPEG, BMP, ecc.
- **Quali sono i prerequisiti?** JDK installato, libreria Aspose.BarCode e Java IDE.

## Cos'è **crea codice a barre codice128 java**?

Creare un codice a barre CODE_128 in Java significa istanziare la classe `BarcodeGenerator` con l'enumerazione `EncodeTypes.CODE_128` e fornire la stringa di dati che desideri codificare. Questa simbologia è ampiamente utilizzata nella logistica perché supporta l'intero set di caratteri ASCII e offre un'elevata densità di dati, rendendola ideale per scenari di codice a barre per sistemi di inventario.

## Perché utilizzare Aspose.BarCode per **generare immagini Java di codici a barre**?

- **Controllo completo sulle dimensioni**: puoi impostare l'altezza della barra, la dimensione del modulo e la risoluzione dell'immagine.
- **Nessuna dipendenza esterna** – puro Java, funziona su qualsiasi piattaforma che supporti il ​​JDK.

- **Ampia personalizzazione** – colori, font, margini e persino codici QR sono supportati.

- **Prestazioni elevate** – genera immagini in millisecondi, ideale per l'elaborazione batch e i flussi di lavoro di generazione di codici a barre per etichette di spedizione.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – versione 8 o successiva installata sul tuo computer.

2. **Libreria Aspose.BarCode per Java** – scarica l'ultimo JAR dal sito web di Aspose (versione di prova o con licenza).

3. **Un IDE Java** – come IntelliJ IDEA, Eclipse o VS Code con estensioni Java.

## Importazione degli spazi dei nomi

Aggiungi le importazioni necessarie all'inizio della tua classe Java per poter accedere all'API di Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Come **generare un'immagine di codice a barre in Java** con Aspose.BarCode?

Di seguito è riportato il flusso di lavoro completo. Ogni passaggio è spiegato in modo semplice e i blocchi di codice originali sono mantenuti esattamente come erano.

### Passaggio 1: Definire la directory delle risorse

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso assoluto dove desideri salvare l'immagine del codice a barre. Questa cartella conterrà i file PNG/JPEG generati che potrai successivamente incorporare in fatture, bolle di consegna o report di inventario.

### Passaggio 2: Istanziare l'oggetto codice a barre

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Qui **create code128 barcode java** passando `EncodeTypes.CODE_128` e la stringa di dati `"1234567"`.

### Passaggio 3: Impostare l'altezza della barra (unità di misura)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

Il metodo `setPoint()` definisce l'altezza in punti (1 punto = 1/72 di pollice). Regola questo valore per soddisfare i requisiti del tuo layout—valori più alti producono barre più alte, spesso necessarie per etichette di spedizione ad alta risoluzione.

### Passaggio 4: Salvare l'immagine

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

La chiamata `save()` scrive il codice a barre generato nella cartella specificata. Il formato dell'immagine è dedotto dall'estensione del file (JPEG in questo caso). Puoi passare a PNG, BMP o TIFF semplicemente cambiando l'estensione.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |

|-------|--------|-----|
| **Immagine non creata** | Il percorso `dataDir` non è corretto o mancano i permessi di scrittura. | Verificare che la cartella esista e che l'applicazione disponga dei permessi di scrittura. |
| **Il codice a barre appare troppo piccolo** | L'altezza della barra impostata in punti è troppo bassa per il DPI scelto. | Aumentare il valore passato a `setPoint()` o regolare il DPI dell'immagine tramite `bb.getParameters().getImage().setResolution()`. |
| **Caratteri non supportati** | CODE_128 supporta solo ASCII; è stato passato Unicode. | Utilizzare una simbologia diversa (ad esempio, QR_CODE) per i dati non ASCII. |

## Domande frequenti

**D: Aspose.BarCode per Java è adatto sia alla generazione che al riconoscimento di codici a barre?**
R: Sì, la libreria supporta sia la generazione che il riconoscimento di un'ampia gamma di simbologie.

**D: Posso personalizzare l'aspetto delle immagini dei codici a barre generate?**
R: Certamente. Puoi cambiare i colori, aggiungere didascalie, modificare i margini e persino incorporare loghi utilizzando l'ampia API `Parameters`.

**D: Come posso ottenere una licenza temporanea per Aspose.BarCode per Java?**
R: Visita [qui](https://purchase.aspose.com/temporary-license/) per richiedere una licenza temporanea di valutazione.

**D: Dove posso trovare supporto per Aspose.BarCode per Java?**
R: Il forum della community di Aspose.BarCode è il posto migliore per ottenere aiuto. Consulta il [forum](https://forum.aspose.com/c/barcode/13) per trovare risposte e porre nuove domande.

**D: Quali sono le simbologie di codici a barre supportate da Aspose.BarCode per Java?**
R: La libreria supporta decine di simbologie, tra cui CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 e molte altre.

### Suggerimenti aggiuntivi (Suggerimento per professionisti)

- **Elaborazione batch:** Inserire i passaggi precedenti in un ciclo per generare centinaia di codici a barre per caricamenti di inventario in blocco.
- **Controllo della risoluzione:** Utilizzare `bb.getParameters().getImage().setResolution(300)` per produrre immagini a 300 dpi, ideali per etichette di stampa di alta qualità.

---

**Ultimo aggiornamento:** 07/02/2026
**Testato con:** Aspose.BarCode per Java 24.12 (ultima versione al momento della stesura)
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}