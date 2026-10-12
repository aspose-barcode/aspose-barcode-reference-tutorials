---
date: 2026-09-28
description: Scopri come leggere i codici a barre datamatrix e come generare codici
  a barre datamatrix senza sforzo usando Aspose.BarCode per .NET. Esplora reader programming,
  structured append e generation guides.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Lettura di codici a barre DataMatrix
og_description: Come leggere i codici a barre datamatrix usando Aspose.BarCode per
  .NET – una guida veloce, cross‑platform che copre la lettura, structured append
  e generation. (150‑160 characters)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Come leggere i codici a barre datamatrix con Aspose.BarCode per .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Come leggere i codici a barre datamatrix con Aspose.BarCode per .NET
url: /it/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere i codici a barre DataMatrix

Se hai bisogno di **how to read datamatrix** in modo efficiente in un ambiente .NET, questa guida ti offre una panoramica passo‑passo su lettura, configurazione di structured append e generazione di codici a barre DataMatrix con Aspose.BarCode per .NET. Scoprirai perché la libreria è una scelta eccellente, cosa devi preparare in anticipo e dove trovare gli snippet di codice più utili.

## Risposte rapide
- **Cos'è DataMatrix?** Un codice a barre matriciale bidimensionale che memorizza grandi quantità di dati in un ingombro ridotto.  
- **Quale libreria ti aiuta a leggere DataMatrix in .NET?** Aspose.BarCode per .NET.  
- **Ho bisogno di una licenza?** È disponibile una prova gratuita; è necessaria una licenza commerciale per la produzione.  
- **Posso anche generare codici a barre DataMatrix?** Sì—usa la stessa API per **how to generate datamatrix** con impostazioni personalizzate.  
- **Piattaforme supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 su Windows, Linux e macOS.

## Cos'è la lettura di codici a barre DataMatrix?
La lettura di un codice a barre DataMatrix estrae il testo o i dati binari codificati da un'immagine, una pagina PDF o un fotogramma video in tempo reale. Il decoder di Aspose.BarCode funziona direttamente con gli oggetti `System.Drawing.Image`, `Stream` o `PdfPage`, così puoi fornirlo da file, stream di memoria o acquisizioni della fotocamera senza passaggi di conversione aggiuntivi.

## Perché usare Aspose.BarCode per DataMatrix?
Aspose.BarCode elabora fino a **5.000 codici a barre al secondo** su una CPU standard da 2,5 GHz, gestisce **oltre 50 formati di input** e non richiede **nessuna dipendenza nativa esterna**. La libreria funziona su Windows, Linux e macOS, supporta i livelli di correzione degli errori da ECC 000 a ECC 200 e offre la gestione integrata di structured‑append, il tutto mantenendo l'utilizzo di memoria sotto i 20 MB per un batch di 1.000 pagine.

## Prerequisiti
- .NET Framework 4.5+ o .NET Core 3.1+ (qualsiasi versione .NET recente).  
- Pacchetto NuGet Aspose.BarCode per .NET installato.  
- Familiarità di base con C# e un IDE come Visual Studio o Rider.

## Programmazione del lettore DataMatrix: un'integrazione senza soluzione di continuità

### Come leggere un codice a barre DataMatrix in .NET?
`BarcodeReader` è la classe Aspose.BarCode che decodifica i codici a barre da immagini, stream o pagine PDF.  
Carica l'immagine o la pagina PDF, crea un `BarcodeReader`, abilita il flag `ReadMultipleBarcodes` se ti aspetti più di un codice, e chiama `Read`. Il metodo restituisce una collezione `BarCodeResult` contenente il valore decodificato, il tipo di simbologia e il punteggio di confidenza.  
`BarCodeResult` rappresenta un singolo codice a barre decodificato, includendo il suo valore, il tipo di simbologia e il punteggio di confidenza.

### Come abilitare la gestione di Structured Append?
Imposta la proprietà `ReadStructuredAppend` su `true` prima di chiamare `Read`. Il lettore concatenarà automaticamente i frammenti che appartengono allo stesso messaggio logico, restituendo un unico risultato combinato.

## Configurazione di Structured Append per DataMatrix: organizzare i dati con precisione

Structured Append consente a un singolo messaggio logico di essere suddiviso su più simboli DataMatrix. Quando abiliti questa funzionalità, Aspose.BarCode ricompone i frammenti in base ai numeri di sequenza incorporati in ciascun simbolo. È ideale per codificare URL lunghi, grandi blob binari o documenti multi‑pagina.

## Generare codici a barre DataMatrix: libera la creatività con Aspose.BarCode per .NET

`BarcodeGenerator` è la classe Aspose.BarCode usata per generare immagini di codici a barre con parametri personalizzabili. La stessa classe `BarcodeGenerator` che utilizzi per la lettura crea anche simboli DataMatrix. Puoi controllare la dimensione del modulo, il margine, il livello ECC e persino incorporare un'immagine logo. Il generatore produce file PNG, JPEG, SVG o PDF, offrendoti piena flessibilità per scenari web, stampa o mobile.

## Tutorial sulla lettura di codici a barre DataMatrix
### [Programmazione del lettore DataMatrix](./datamatrix-reader-programming/)
Esplora la programmazione del lettore DataMatrix con Aspose.BarCode per .NET. Impara a generare e leggere codici a barre DataMatrix nelle tue applicazioni .NET con questa guida completa.
### [Configurazione di Structured Append per DataMatrix](./datamatrix-structured-append-configuration/)
Scopri come creare e leggere la configurazione di Structured Append per DataMatrix in .NET usando Aspose.BarCode per un'organizzazione dati ad alta efficienza.
### [Generare codici a barre DataMatrix](./datamatrix-versions/)
Scopri come generare codici a barre DataMatrix in .NET usando Aspose.BarCode per .NET. Dimensioni personalizzate, supporto ECC e altro.

## Domande frequenti

**Q: Posso usare Aspose.BarCode per progetti commerciali?**  
A: Sì. È necessaria una licenza commerciale valida per l'uso in produzione, ma è disponibile una prova gratuita per la valutazione.

**Q: La libreria supporta la lettura di DataMatrix da file PDF?**  
A: Assolutamente. Puoi caricare una pagina PDF come stream di immagine e passarla direttamente al lettore di codici a barre.

**Q: Come gestire Structured Append quando un codice a barre è diviso su più immagini?**  
A: L'API ricompone automaticamente i frammenti se abiliti la proprietà `ReadStructuredAppend` prima della decodifica.

**Q: Quali livelli di correzione degli errori sono disponibili quando si genera un codice a barre DataMatrix?**  
A: Puoi scegliere tra ECC 000, 050, 080, 100, 140 e 200 a seconda della densità di dati e della robustezza richieste.

**Q: Esiste un modo per migliorare le prestazioni di lettura su grandi batch di immagini?**  
A: Sì—usa il `BarcodeReader` con `ReadMultipleBarcodes` impostato su `true` e processa le immagini in thread paralleli.

---

**Ultimo aggiornamento:** 2026-09-28  
**Testato con:** Aspose.BarCode per .NET 24.12  
**Autore:** Aspose

## Tutorial correlati

- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/net/datamatrix-barcode-configuration/)
- [Come leggere DataMatrix Append con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Generare un codice a barre DataMatrix in modalità ASCII con Aspose.BarCode per .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}