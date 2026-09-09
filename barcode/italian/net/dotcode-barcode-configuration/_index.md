---
date: 2026-06-14
description: Scopri come generare codici a barre DotCode con Aspose.BarCode per .NET,
  coprendo il rapporto d'aspetto, le modalità di codifica, il testo esteso e l'inizializzazione
  del lettore.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Come generare codici a barre DotCode – Guida di configurazione
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Come generare codici a barre DotCode – Guida di configurazione
url: /it/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare codici a barre DotCode – Guida alla configurazione

## Introduzione
**Come generare DotCode** codici a barre rapidamente e in modo affidabile è una necessità comune per gli sviluppatori che creano soluzioni di inventario, tracciamento o scansione mobile. In questo tutorial ti guideremo attraverso tutte le opzioni di configurazione offerte da Aspose.BarCode per .NET per i simboli DotCode—regolazioni del rapporto d'aspetto, modalità di codifica Auto e Bytes, gestione del testo esteso, inizializzazione del lettore, layout righe/colonne e modalità structured‑append. Alla fine sarai in grado di produrre immagini DotCode di dimensioni perfette e alta densità che rispettano gli standard del settore e si integrano perfettamente in qualsiasi applicazione .NET.

## Risposte rapide
- **Qual è la classe principale per creare un codice a barre DotCode?** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **Quale proprietà controlla il rapporto d'aspetto?** `BarCodeImageAspectRatio`.
- **Posso passare dalla codifica Auto a Bytes?** Sì, tramite la proprietà `EncodeMode`.
- **È necessario un lettore separato per DotCode?** No, lo stesso `BarcodeGenerator` può decodificare quando viene chiamato `ReadBarcode`.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Come generare codici a barre DotCode usando Aspose.BarCode per .NET?
`BarcodeGenerator` è la classe principale in Aspose.BarCode per creare immagini di codici a barre. Carica il `BarcodeGenerator` con `EncodeTypes.DotCode`, imposta le proprietà desiderate (rapporto d'aspetto, modalità di codifica, righe/colonne, ecc.) e chiama `GenerateBarCodeImage()` — la libreria restituisce un `System.Drawing.Image` pronto all'uso o un array di byte. Questo flusso di lavoro a singolo passaggio gestisce tutti i dettagli di codifica a basso livello, supporta formati di output come PNG, JPEG e SVG, e può generare immagini fino a 10 000 × 10 000 px senza consumare memoria eccessiva.

## Cos'è un codice a barre DotCode?
Un codice a barre DotCode è una simbologia 2D ad alta densità e forma quadrata che memorizza fino a 1 200 caratteri numerici o 800 alfanumerici in una matrice compatta di punti. È ottimizzato per l'etichettatura di piccoli pacchi e la scansione mobile, offrendo velocità di lettura elevate anche su fotocamere a bassa risoluzione.

## Perché usare DotCode con Aspose.BarCode?
Aspose.BarCode supporta **20+** tipi di codici a barre 2D, incluso DotCode, e può elaborare file più grandi di **200 MB** senza caricare l'intera immagine in memoria. La libreria garantisce una precisione di scansione del **99,9 %** su fotocamere di smartphone standard e fornisce livelli di correzione d'errore integrati per ridurre al minimo i fallimenti di lettura.

## Prerequisiti
- .NET Framework 4.5 o superiore, o .NET Core 3.1 / .NET 5+.
- Aspose.BarCode per .NET (ultima versione consigliata).
- Una chiave di licenza temporanea o completa (la versione di prova funziona per lo sviluppo).

## Personalizzazione del rapporto d'aspetto DotCode
Il **rapporto d'aspetto** determina quanto la matrice DotCode appare allungata o schiacciata. Usa la proprietà `BarCodeImageAspectRatio` per impostare un valore tra **0,5** (più alto) e **2,0** (più largo). Un rapporto di **1,0** produce un simbolo perfettamente quadrato, che è il valore predefinito e funziona meglio per la maggior parte degli scanner.

> **Suggerimento:** Quando si stampano etichette strette, un rapporto di **0,75** spesso migliora la leggibilità senza sacrificare la capacità dei dati.

## Modalità di codifica DotCode (Auto)
In modalità **Auto** la libreria analizza la stringa di input e seleziona automaticamente la codifica più efficiente (numerica, alfanumerica o byte). Questo massimizza la densità dei dati e riduce le dimensioni complessive del simbolo.

> **Risposta diretta:** Imposta `EncodeMode = EncodeModes.Auto` sul `BarcodeGenerator` per consentire ad Aspose.BarCode di decidere la codifica ottimale per i tuoi dati, garantendo il DotCode più piccolo possibile mantenendo tutti i caratteri.

## Modalità di codifica DotCode (Bytes)
Quando è necessario memorizzare dati binari o array di byte pre‑codificati, scegli la modalità **Bytes**. Questo costringe il generatore a trattare l'input come byte grezzi, bypassando il rilevamento automatico del set di caratteri.

> **Risposta diretta:** Usa `EncodeMode = EncodeModes.Bytes` e fornisci un payload `byte[]` per inserire informazioni binarie come identificatori crittografati o file compressi direttamente nel simbolo DotCode.

## Configurazione del testo esteso del codice DotCode
Il testo esteso del codice consente di allegare informazioni supplementari che non fanno parte del payload principale dei dati ma possono essere visualizzate accanto al codice a barre in report o interfacce grafiche. Imposta la proprietà `ExtendedCodeText` su qualsiasi stringa (fino a **256** caratteri) e scegli un font tramite `ExtendedCodeTextFont`.

> **Consiglio professionale:** Abbina il testo esteso a una dimensione del font più piccola (ad esempio, 8 pt) per mantenere un ingombro visivo ridotto fornendo comunque un contesto leggibile dall'uomo.

## Inizializzazione del lettore DotCode
`BarCodeReader` è la classe utilizzata per decodificare i codici a barre da immagini o stream. Leggere un'immagine DotCode è semplice quanto la generazione. Istanzia un `BarCodeReader` con lo stream dell'immagine e specifica `EncodeTypes.DotCode`. Chiama `ReadBarCode()` per recuperare la stringa decodificata.

> **Risposta diretta:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – questo singolo blocco decodifica il simbolo senza dipendenze esterne.

## Configurazione di righe e colonne DotCode
DotCode consente un controllo esplicito sul numero di righe e colonne, che influisce sulla dimensione del simbolo e sulla capacità di correzione degli errori. Usa le proprietà `Rows` e `Columns` per impostare valori tra **10** e **144**. Matrici più grandi aumentano la capacità di dati e la robustezza.

> **Best practice:** Per le etichette di inventario che devono resistere a manipolazioni brusche, configura **Rows = 64** e **Columns = 64** per aggiungere ridondanza extra.

## Configurazione della modalità Structured Append DotCode
Structured Append consente di suddividere un grande payload su più simboli DotCode che possono essere letti in sequenza. Imposta `StructuredAppend = true` e definisci `StructuredAppendCount` e `StructuredAppendIndex` per ogni parte.

> **Risposta diretta:** Abilita `StructuredAppend` su ogni `BarcodeGenerator`, assegna un indice unico (a partire da 1) e imposta il conteggio totale; la libreria inserirà automaticamente le informazioni di collegamento necessarie.

## Problemi comuni e soluzioni
- **Codice a barre illeggibile su schermi a bassa risoluzione:** Aumenta la proprietà `Resolution` ad almeno **300 dpi** prima della generazione.
- **Avvisi di troncamento dei dati:** Verifica che la lunghezza dell'input non superi il massimo per le righe/colonne selezionate; regola le dimensioni o passa alla modalità Bytes se necessario.
- **Scadenza della licenza durante lo sviluppo:** Usa una licenza temporanea ottenuta dal portale Aspose; sostituiscila con una chiave permanente prima del deployment in produzione.

## Domande frequenti

**Q: Posso generare codici a barre DotCode in formato SVG?**  
A: Sì, imposta `BarCodeImageFormat = BarCodeImageFormat.Svg` sul generatore per ottenere un output vettoriale scalabile.

**Q: È possibile inserire un logo all'interno di un simbolo DotCode?**  
A: Aspose.BarCode non supporta l'inserimento diretto di un logo per DotCode, ma è possibile sovrapporre un'immagine dopo la generazione usando librerie grafiche standard.

**Q: Come funziona la correzione degli errori per DotCode?**  
A: La simbologia include correzione d'errore Reed‑Solomon integrata; aumentare righe/colonne eleva automaticamente il livello di correzione.

**Q: È necessaria una libreria separata per leggere DotCode da un PDF?**  
A: No, lo stesso `BarCodeReader` può estrarre DotCode da pagine PDF, immagini o stream senza strumenti aggiuntivi.

**Q: Qual è la dimensione massima dei dati per un singolo simbolo DotCode?**  
A: Fino a **1 200** caratteri numerici o **800** caratteri alfanumerici, a seconda della configurazione di righe/colonne scelta.

---

**Ultimo aggiornamento:** 2026-06-14  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

## Tutorial di configurazione del codice a barre DotCode
### [Personalizza il rapporto d'aspetto DotCode](./dotcode-aspect-ratio-customization/)
Impara a personalizzare il rapporto d'aspetto del codice a barre DotCode usando Aspose.BarCode per .NET. Crea codici a barre su misura per le tue applicazioni senza sforzo.
### [Modalità di codifica DotCode (Auto)](./dotcode-encoding-mode-auto/)
Esplora la Modalità di codifica DotCode (Auto) in Aspose.BarCode per .NET, uno strumento potente per la generazione di codici a barre. Impara come generare codici a barre DotCode passo dopo passo. Consulta la documentazione, scarica la libreria e ottieni licenze temporanee.
### [Modalità di codifica DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Impara la codifica DotCode con Aspose.BarCode per .NET: guida passo passo per generare codici a barre.
### [Configurazione del testo esteso del codice DotCode](./dotcode-extended-code-text-configuration/)
Genera la Configurazione del testo esteso del codice DotCode con facilità usando Aspose.BarCode per .NET. Segui la nostra guida passo passo per una creazione efficiente dei codici a barre.
### [Inizializzazione del lettore DotCode](./dotcode-reader-initialization/)
Scopri come inizializzare il lettore DotCode usando Aspose.BarCode per .NET. Crea codici a barre DotCode con facilità per varie applicazioni.
### [Configurazione di righe e colonne DotCode](./dotcode-rows-columns-configuration/)
Impara a configurare righe e colonne DotCode con Aspose.BarCode per .NET. Genera codici a barre 2D precisi e personalizzabili senza sforzo.
### [Configurazione della modalità Structured Append DotCode](./dotcode-structured-append-mode-configuration/)
Impara a configurare la modalità Structured Append DotCode con Aspose.BarCode per .NET e crea codici a barre efficienti.

## Tutorial correlati

- [Personalizza il rapporto d'aspetto DotCode con Aspose.BarCode per .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Configurazione del testo esteso del codice DotCode con Aspose.BarCode per .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Modalità di codifica DotCode (Auto) in Aspose.BarCode per .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}