---
date: 2026-08-02
description: Guida passo‑passo su come leggere il codice a barre DataMatrix C# e generare
  l'immagine del codice a barre C# utilizzando Aspose.BarCode per .NET con codifica
  automatica.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Modalità di codifica DataMatrix (Auto)
og_description: Scopri come leggere il codice a barre DataMatrix C# e generarlo in
  modalità Auto utilizzando Aspose.BarCode per .NET. Questo tutorial copre l'installazione,
  il codice e la risoluzione dei problemi.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Come leggere il codice a barre DataMatrix C# – Modalità Auto
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Come leggere il codice a barre DataMatrix C# – Modalità Auto
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere il codice a barre DataMatrix C# – Modalità Auto

Nel mondo digitale di oggi, in rapida evoluzione, **how to read datamatrix** rapidamente e in modo affidabile è essenziale per il tracciamento dell'inventario, la gestione sicura dei documenti e molti altri scenari aziendali. Questo tutorial ti guida nella generazione di un codice a barre DataMatrix in modalità *Auto* con Aspose.BarCode per .NET e poi mostra come leggere quel codice a barre in C#. Che tu stia seguendo una guida tutorial sui codici a barre o abbia bisogno di un esempio di codice pronto all'uso, terminerai con una soluzione pronta per la produzione che puoi inserire in qualsiasi progetto .NET.

## Risposte rapide
- **Che cosa fa la modalità “Auto”?** Consente ad Aspose.BarCode di selezionare automaticamente lo schema di codifica migliore per i tuoi dati.  
- **Quale libreria è necessaria?** Aspose.BarCode per .NET (disponibile versione di prova gratuita).  
- **Posso leggere il codice a barre nella stessa app?** Sì – usa `BarCodeReader` con `DecodeType.DataMatrix`.  
- **Ho bisogno di una licenza per la produzione?** È necessaria una licenza commerciale per l'uso in produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` è la classe di Aspose.BarCode per la scansione delle immagini e il recupero delle informazioni del codice a barre.

## Che cos'è la lettura del codice a barre DataMatrix C#?
Leggere un codice a barre DataMatrix in C# significa decodificare la matrice bidimensionale di moduli neri e bianchi nel testo o nei dati originali. Aspose.BarCode astrae l'elaborazione di immagine a basso livello, così puoi concentrarti sulla logica di business mentre la libreria gestisce automaticamente la correzione degli errori, la selezione della dimensione del simbolo e il supporto Unicode.

## Perché usare Aspose.BarCode per generare l'immagine del codice a barre C#?
Aspose.BarCode seleziona automaticamente la codifica ottimale, supporta **oltre 30 simbologie di codici a barre**, e può generare simboli DataMatrix fino a **1558 × 1558 moduli** – molto più grandi della maggior parte dei concorrenti. Funziona su Windows, Linux e macOS senza dipendenze native, fornendoti un'unica API cross‑platform per la generazione e la lettura.

## Prerequisiti

1. **.NET Environment** – Installa l'ultima runtime .NET dal [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode for .NET** – Scarica la libreria dal [website](https://releases.aspose.com/barcode/net/).  

## Importazione degli spazi dei nomi
Lo spazio dei nomi `Aspose.BarCode` contiene tutte le classi necessarie per la creazione e la lettura dei codici a barre. Importalo all'inizio del tuo file prima di qualsiasi altro codice.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ora che gli spazi dei nomi sono in posizione, procediamo passo‑per‑passo attraverso il codice.

## Passo 1: Impostare il percorso della directory
Scegli una cartella dove verrà salvato il PNG generato (o qualsiasi formato supportato). Questo percorso può essere assoluto o relativo al tuo progetto.

```csharp
string path = "Your Directory Path";
```

Sostituisci `"Your Directory Path"` con la cartella che preferisci. Mantenere la cartella di output configurabile rende il tutorial riutilizzabile in diversi ambienti.

## Passo 2: Creare un codice a barre DataMatrix in modalità Auto
`DataMatrixEncodeMode.Auto` indica al generatore di selezionare automaticamente lo schema di codifica ottimale per i dati forniti.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Sentiti libero di sostituire il testo di esempio con qualsiasi stringa per cui devi **how to generate datamatrix**. La modalità auto passerà automaticamente tra Base‑256, ASCII o altri schemi per ottenere il simbolo più piccolo possibile.

## Passo 3: Leggere il codice a barre (leggere il codice a barre DataMatrix C#)
`BarCodeReader` è la classe di Aspose.BarCode per la scansione delle immagini e il recupero delle informazioni del codice a barre. Supporta la lettura da stream, file e oggetti bitmap, rendendola ideale per scenari di **read barcode from file**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Questo frammento decodifica l'immagine appena generata e stampa il testo originale sulla console, dimostrando un ciclo completo dalla generazione alla lettura.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|-------|-------|-----|
| **Nessun codice a barre rilevato** | Risoluzione dell'immagine troppo bassa | Aumenta `XDimension.Pixels` (ad es., a 6) |
| **Caratteri spazzatura** | Codifica ECI errata | Imposta `ECIEncoding` per corrispondere ai tuoi dati (UTF‑8, ASCII, ecc.) |
| **Eccezione su `ReadBarCodes`** | Bitmap rilasciata prima della lettura | Mantieni l'istanza `Bitmap` viva fino a dopo la lettura |

## Domande frequenti

**Q: Cos'è la modalità di codifica DataMatrix "Auto"?**  
A: Consente ad Aspose.BarCode di selezionare automaticamente il metodo di codifica ottimale per i dati forniti, semplificando il processo di **how to generate datamatrix**.

**Q: Posso personalizzare le dimensioni del codice a barre generato?**  
A: Sì – regola `generator.Parameters.Barcode.XDimension.Pixels` per modificare la dimensione del modulo.

**Q: Aspose.BarCode per .NET è adatto per uso commerciale?**  
A: Assolutamente. Acquista una licenza dal [website](https://purchase.aspose.com/buy).

**Q: È disponibile una versione di prova gratuita?**  
A: Sì, puoi provare Aspose.BarCode con una versione di prova gratuita dal [this link](https://releases.aspose.com/).

**Q: Quali opzioni di codifica sono disponibili per i codici a barre DataMatrix?**  
A: Aspose.BarCode supporta UTF‑8, ASCII e altre codifiche ECI; imposta il valore desiderato tramite `ECIEncoding`.

## Conclusione

Ora hai un esempio completo, pronto per la produzione, che **legge il codice a barre DataMatrix C#**, genera il codice a barre in modalità Auto e verifica il risultato—tutto usando Aspose.BarCode per .NET. Sperimenta con testi, dimensioni e impostazioni ECI diversi per adattarli al tuo scenario specifico, e consulta la [documentation](https://reference.aspose.com/barcode/net/) ufficiale per personalizzazioni più approfondite.

---

**Ultimo aggiornamento:** 2026-08-02  
**Testato con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come leggere i codici a barre DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/)
- [Configurazione Structured Append di DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Programmazione del lettore DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}