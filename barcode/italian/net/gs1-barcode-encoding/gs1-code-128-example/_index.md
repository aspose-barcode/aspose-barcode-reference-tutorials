---
date: 2026-09-08
description: Scopri come creare un codice a barre code 128 e generare codici a barre
  GS1 in C# con Aspose.BarCode per .NET. Guida passo‑passo, prerequisiti e personalizzazione
  senza codice.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Esempio GS1 Code 128
og_description: Scopri come creare un codice a barre code 128 e generare codici a
  barre GS1 in C# con Aspose.BarCode per .NET. Segui una guida passo‑passo per generare
  e salvare rapidamente le immagini del codice a barre.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Come creare un codice a barre code 128 con GS1 usando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Come creare un codice a barre code 128 con GS1 usando Aspose.BarCode
url: /it/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre code 128 con GS1 usando Aspose.BarCode

In questo tutorial imparerai a **creare un codice a barre code 128** conforme allo standard GS1 utilizzando la libreria Aspose.BarCode per .NET. Che tu abbia bisogno di un codice a barre per l'inventario, la spedizione o il punto vendita, questa guida ti accompagna passo passo—dalla configurazione dell'ambiente di sviluppo al salvataggio dell'immagine finale—così potrai iniziare a generare codici a barre affidabili in pochi minuti.

## Risposte rapide
- **Qual è la classe principale per generare un codice a barre?** `BarcodeGenerator` crea e configura l'immagine del codice a barre.  
- **Quale simbologia utilizza GS1 Code 128?** Utilizza il tipo `EncodeTypes.Code128` con formattazione dati specifica per GS1.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza commerciale per la produzione.  
- **Posso cambiare il formato dell'immagine?** Sì—salva come PNG, JPEG, BMP o TIFF modificando l'estensione del file.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

## Cos'è il codice a barre code 128?
`create code 128 barcode` si riferisce alla generazione di un codice a barre lineare che codifica dati alfanumerici usando la simbologia Code 128, ampiamente adottata nella logistica perché supporta l'intero set ASCII e può incorporare gli Identificatori di Applicazione GS1. Il codice a barre può memorizzare identificatori di prodotto, numeri di serie e altri dati personalizzati, rendendolo adatto a una vasta gamma di scenari aziendali.

## Perché usare Aspose.BarCode per GS1 Code 128?
Aspose.BarCode supporta **oltre 30 simbologie di codici a barre** e può generare immagini fino a **10.000 × 10.000 px** senza perdita di qualità, rendendolo adatto per la stampa di etichette ad alta risoluzione. La libreria valida automaticamente le strutture dati GS1, riducendo il rischio di codici a barre malformati nelle linee di produzione. Inoltre, offre ampie opzioni di personalizzazione per dimensione, colore e layout, aiutando a soddisfare rigorosi standard di settore.

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:

1. **Ambiente di sviluppo .NET** – Visual Studio 2022, Rider o qualsiasi IDE che supporti .NET 6+.  
2. **Aspose.BarCode per .NET** – scaricalo dalla **pagina di download di Aspose.BarCode per .NET** su [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) e aggiungi il pacchetto NuGet `Aspose.BarCode` al tuo progetto.  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio nella creazione di applicazioni console o Windows.  
4. **Comprensione di GS1 Code 128** – opzionale ma utile; GS1 utilizza Identificatori di Applicazione (AI) come `(01)` per GTIN e `(21)` per numeri di serie.

## Come creare un codice a barre code 128 passo passo

Carica la libreria, configura il tipo di codice a barre, imposta i dati GS1, personalizza le dimensioni e infine salva l'immagine. La risposta diretta alla domanda “come creare un codice a barre code 128?” è: **istanziare `BarcodeGenerator` con `EncodeTypes.Code128` e dati formattati GS1, regolare `XDimension` se necessario, quindi chiamare `Save` con il nome file e il formato desiderati**. Le sezioni seguenti scompongono ogni passaggio.

### Passo 1: imposta il percorso della directory
Definisci la cartella in cui verrà salvata l'immagine generata. Mantenere il percorso configurabile rende il codice riutilizzabile in diversi ambienti.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Sostituisci `"Your Directory Path"` con un percorso assoluto o relativo a cui la tua applicazione può scrivere, ad esempio `@"C:\\Barcodes"` o `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Passo 2: crea un codice GS1 Code 128
Crea il generatore di codice a barre, specifica la simbologia e fornisci dati formattati GS1. La stringa di dati deve includere gli Identificatori di Applicazione racchiusi tra parentesi.

```csharp
string path = "Your Directory Path";
```

L'esempio utilizza il GTIN `(01)12345678901231`, un numero di serie `(21)ASPOSE` e un AI personalizzato aggiuntivo `(30)9876`. Aspose.BarCode inserisce automaticamente il carattere FNC1 richiesto per la conformità GS1.

### Passo 3: personalizza i parametri del codice a barre
Regola i parametri visivi come `XDimension` (la larghezza della barra stretta) per controllare la densità del codice a barre. Puoi anche modificare altezza, colori e margini.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Impostare `XDimension = 2` produce un codice a barre facilmente leggibile dalla maggior parte dei lettori portatili mantenendo una dimensione dell'immagine contenuta.

### Passo 4: salva l'immagine del codice a barre
Salva il codice a barre generato su disco. Puoi scegliere PNG per qualità senza perdita, JPEG per file più piccoli o TIFF per flussi di lavoro di stampa. Il metodo `Save` scrive il file immagine nel formato indicato dall'estensione del file.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Sostituisci `GS1Code128Example.png` con qualsiasi nome file valido e un'estensione che corrisponda al formato di output desiderato.

### Passo 5: verifica il codice a barre (opzionale)
Dopo il salvataggio, puoi caricare nuovamente l'immagine nella tua applicazione o utilizzare uno scanner di codici a barre per confermare che i dati codificati corrispondano alla stringa originale. Questo passaggio è utile durante lo sviluppo e i test automatizzati.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Problemi comuni e suggerimenti per la risoluzione
- **FNC1 non rilevato** – Assicurati che la stringa di dati inizi con una parentesi aperta e includa AI GS1 validi; la libreria inserisce FNC1 automaticamente solo per i pattern riconosciuti.  
- **Immagine non salvata** – Verifica che la directory di destinazione esista e che l'applicazione abbia i permessi di scrittura. Usa `Directory.CreateDirectory(path)` per crearla al volo.  
- **Codice a barre troppo denso** – Diminuisci `XDimension` o aumenta l'altezza dell'immagine per dare ai lettori più spazio per leggere le barre strette.  
- **Caratteri non supportati** – Code 128 può codificare solo l'intero set ASCII; evita caratteri Unicode al di fuori di questo intervallo.

## Domande frequenti

**Q: Posso generare codici a barre in un'API web senza installare l'intero .NET Framework?**  
A: Sì, Aspose.BarCode funziona con .NET Core e .NET 5/6, quindi puoi esporre un endpoint REST leggero che restituisce immagini di codici a barre su richiesta.

**Q: La libreria supporta la generazione batch di più codici a barre?**  
A: Assolutamente. Scorri una collezione di stringhe di dati, istanzia un `BarcodeGenerator` per ciascuna e chiama `Save` all'interno del ciclo. La libreria è thread‑safe per l'elaborazione parallela.

**Q: È possibile incorporare il codice a barre direttamente in un PDF?**  
A: Usa Aspose.PDF per creare un documento PDF, quindi chiama `PdfPage.AddImage` con lo stream dell'immagine del codice a barre. Questo evita di scrivere file intermedi su disco.

**Q: Come posso garantire che il codice a barre soddisfi gli standard di qualità ISO/GS1?**  
A: Imposta `BarcodeGenerator.Options.Barcode.XDimension` a almeno 0,33 mm e abilita `BarHeight` in base alle dimensioni dell'etichetta. Aspose.BarCode valida il formato AI e genera un'eccezione per dati non validi.

**Q: Quali opzioni di licenza sono disponibili per l'uso in produzione?**  
A: Aspose offre modelli di licenza perpetua, in abbonamento e basati sul cloud. Una licenza di prova funziona per la valutazione, ma una licenza a pagamento rimuove il watermark di valutazione e sblocca tutte le funzionalità.

## Risorse aggiuntive

- **Documentazione** – Accedi al riferimento completo dell'API su [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Download** – Ottieni l'ultima versione della libreria da [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Prova gratuita** – Inizia una prova di 30 giorni su [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Acquista** – Acquista una licenza commerciale su [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Supporto** – Unisciti al forum della community su [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) per assistenza nella risoluzione dei problemi.

---

**Ultimo aggiornamento:** 2026-09-08  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come creare il codice a barre ITF-14 .NET – Tutorial completi Aspose.BarCode](/barcode/net/)
- [Genera codici a barre Databar 2D unidimensionali usando Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}