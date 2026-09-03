---
date: 2026-05-30
description: Scopri come generare un codice a barre DataMatrix in modalità Bytes e
  leggere un codice a barre DataMatrix usando Aspose.BarCode for .NET – una guida
  passo‑passo sui codici a barre.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Modalità di codifica DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Genera codice a barre DataMatrix in modalità Bytes con Aspose.BarCode for .NET
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera codice a barre DataMatrix in modalità Bytes con Aspose.BarCode per .NET

In questo tutorial imparerai a **generare codice a barre DataMatrix** usando la modalità di codifica Bytes e poi **leggere il codice a barre DataMatrix** con Aspose.BarCode per .NET. Che tu stia costruendo un sistema di gestione del magazzino o un'app di ticketing mobile, la guida passo‑passo al codice a barre qui sotto ti mostra esattamente come configurare le impostazioni del generatore di codici a barre, produrre un'immagine ad alta qualità e decodificarla di nuovo—tutto in poche righe di C#.

## Risposte rapide
- **Posso generare un codice a barre DataMatrix in .NET?** Sì, usa `BarcodeGenerator` con `EncodeTypes.DataMatrix` e imposta `DataMatrixEncodeMode.Bytes`.
- **Quale metodo legge il codice a barre?** `BarCodeReader` legge l'immagine e restituisce il testo codificato.
- **Ho bisogno di una licenza per la produzione?** È necessaria una licenza commerciale; è disponibile una versione di prova gratuita.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Quanti byte posso codificare?** Fino a 1,555 byte in un singolo simbolo DataMatrix.

## Che cos'è generare un codice a barre DataMatrix?
**Generare un codice a barre DataMatrix** significa creare un codice a barre bidimensionale, di forma quadrata, che può memorizzare dati binari. Aspose.BarCode rende il simbolo come immagine PNG, JPG o SVG che qualsiasi scanner può decodificare. È ampiamente usato per il tracciamento dell'inventario, la gestione dei documenti e l'autenticazione perché fornisce alta densità di dati e capacità di correzione degli errori, rendendolo affidabile anche su stampe di bassa qualità.

## Perché usare la modalità di codifica Bytes?
La modalità Bytes ti consente di incorporare dati binari grezzi (fino a 1,555 byte) senza convertirli in testo, il che è ideale per numeri di serie, GUID o payload crittografati. Aspose.BarCode supporta **oltre 30 simbologie di codici a barre** e può elaborare **documenti di centinaia di pagine** senza caricare l'intero file in memoria, garantendo prestazioni rapide anche in scenari ad alto volume.

## Prerequisiti

Prima di immergerci nel processo di codifica, dovrai avere i seguenti prerequisiti pronti:

1. Aspose.BarCode per .NET: Per iniziare, devi avere la libreria Aspose.BarCode per .NET installata. Puoi scaricarla da [qui](https://releases.aspose.com/barcode/net/). Puoi trovare anche altri prodotti Aspose su [qui](https://releases.aspose.com/).
2. Il tuo ambiente di sviluppo: Assicurati di avere un ambiente di sviluppo configurato, inclusi Visual Studio o qualsiasi altro IDE a tua scelta.
3. Conoscenza di base di C#: Questo tutorial presuppone che tu abbia una comprensione di base della programmazione C#.

Per assistenza, visita [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

Con questi prerequisiti in atto, sei pronto per iniziare a codificare dati nel formato DataMatrix usando la modalità Bytes.

## Importa gli spazi dei nomi

Per utilizzare Aspose.BarCode per .NET, importa gli spazi dei nomi richiesti all'inizio del tuo file C#:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Ora che l'ambiente è pronto, seguiamo i passaggi esatti per **generare un codice a barre DataMatrix** e poi leggerlo.

## Come generare un codice a barre DataMatrix in modalità Bytes?

Carica il `BarcodeGenerator`, imposta la modalità di codifica su Bytes, configura il testo visualizzato opzionale, salva l'immagine e infine usa `BarCodeReader` per verificare il risultato—tutto in sei passaggi concisi. Questo approccio garantisce un codice a barre affidabile che aderisce allo standard ISO/IEC 16022.

### Passo 1: Inizializza il BarcodeGenerator

`BarcodeGenerator` è la classe principale usata per generare immagini di codici a barre per una data simbologia e dati.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Passo 2: Imposta la modalità di codifica DataMatrix su Bytes

`DataMatrixEncodeMode.Bytes` indica al generatore di trattare l'input come byte binari grezzi anziché come testo.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Passo 3: Imposta il testo visualizzato

La proprietà `CodeText` imposta il testo leggibile dall'uomo visualizzato sotto il simbolo del codice a barre.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Passo 4: Salva l'immagine del codice a barre

Il metodo `Save` scrive il codice a barre generato in un file immagine nel formato specificato.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Passo 5: Prova a riconoscere

`BarCodeReader` legge le immagini dei codici a barre ed estrae i dati codificati.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Passo 6: Itera e visualizza i risultati

Itera su `reader.ReadBarCodes()` per accedere a ciascun codice a barre rilevato e al suo `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Con questi passaggi, hai generato con successo **un codice a barre DataMatrix** in modalità Bytes e lo hai verificato usando Aspose.BarCode per .NET. La libreria astrae i dettagli di codifica a basso livello, così puoi concentrarti sulla logica di business piuttosto che sulla matematica dei codici a barre.

## Problemi comuni e soluzioni

- **I dati codificati sono troncati** – Assicurati che l'array di byte non superi 1,555 byte; altrimenti la libreria passerà automaticamente a una dimensione di simbolo più grande o genererà un'eccezione.
- **L'immagine appare sfocata** – Salva l'immagine a una risoluzione più alta (ad es., 300 dpi) impostando `generator.Parameters.ImageResolution` prima di chiamare `Save`.
- **Il lettore restituisce null** – Verifica che il percorso dell'immagine sia corretto e che il file non sia corrotto; conferma anche che `BarCodeReader` sia istanziato con `DecodeType.DataMatrix`.

## Domande frequenti

**Q: Cos'è la modalità di codifica DataMatrix?**  
A: La modalità di codifica DataMatrix definisce come i dati di input vengono trasformati nel pattern bidimensionale; la modalità Bytes memorizza direttamente i byte binari grezzi.

**Q: Come posso ottenere una prova gratuita di Aspose.BarCode per .NET?**  
A: Puoi ottenere una prova gratuita di Aspose.BarCode per .NET da [qui](https://releases.aspose.com/).

**Q: Dove posso trovare la documentazione per Aspose.BarCode per .NET?**  
A: La documentazione per Aspose.BarCode per .NET è disponibile [qui](https://reference.aspose.com/barcode/net/).

**Q: Aspose.BarCode per .NET è adatto per uso commerciale?**  
A: Sì, Aspose.BarCode per .NET è adatto per uso commerciale. Puoi acquistare una licenza da [qui](https://purchase.aspose.com/buy).

**Q: Posso usare una licenza temporanea per Aspose.BarCode per .NET?**  
A: Sì, puoi ottenere una licenza temporanea per Aspose.BarCode per .NET da [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-05-30  
**Testato con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Master DataMatrix Encoding in ASCII con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Come generare codici a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}