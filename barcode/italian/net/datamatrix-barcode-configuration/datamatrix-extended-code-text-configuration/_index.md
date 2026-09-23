---
date: 2026-09-23
description: Scopri come utilizzare Aspose.BarCode per generare un codice a barre
  DataMatrix con testo di codice esteso in .NET, ideale per applicazioni di inventario
  e logistica.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Configurazione del testo di codice esteso DataMatrix
og_description: Come utilizzare Aspose.BarCode per generare un codice a barre DataMatrix
  con testo di codice esteso in .NET. Segui una guida rapida passo‑passo per soluzioni
  di inventario e logistica.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Come utilizzare Aspose.BarCode per creare il testo del codice DataMatrix
  in .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Come utilizzare Aspose.BarCode per creare il testo del codice DataMatrix in
  .NET
url: /it/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come utilizzare Aspose.BarCode per creare il testo del codice DataMatrix in .NET

Integrare i codici a barre nelle moderne applicazioni .NET non è più un compito di nicchia—è un requisito fondamentale per l'inventario, la logistica e le soluzioni di scansione mobile. In questa guida **imparerai come utilizzare Aspose.BarCode** per configurare un codice a barre DataMatrix con testo esteso, generare l'immagine e verificarla programmaticamente. Vedrai perché questo approccio è ideale per creare codici a barre per l'inventario e come si integra nei progetti .NET Core o .NET 6.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.BarCode per .NET  
- **Quale tipo di codice a barre?** DataMatrix con testo esteso  
- **Posso usare .NET Core / .NET 6?** Sì, l'API è cross‑platform  
- **Ho bisogno di una licenza per i test?** Una versione di prova funziona per lo sviluppo; è necessaria una licenza per la produzione  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un esempio base  

## Cos'è Aspose.BarCode per .NET?
Aspose.BarCode per .NET è una libreria commerciale che consente agli sviluppatori di generare e riconoscere più di 30 simbologie di codici a barre, tra cui DataMatrix, QR e Code 128, e di produrre immagini fino a 10.000 × 10.000 pixel senza dipendenze esterne. Supporta .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6/7.

## Perché utilizzare il testo esteso DataMatrix?
Il testo esteso DataMatrix consente di incorporare più schemi di codifica—UTF‑8, C40, Text, X12—in un unico simbolo, permettendo fino a **3116 codewords** (circa 155 KB di dati) in un quadrato compatto. Questa capacità è perfetta per l'etichettatura di prodotti multilingue, il tracciamento di dispositivi medici e il packaging intelligente dove è necessario combinare ID alfanumerici con payload binari.

## Prerequisiti
Prima di iniziare, verifica di avere quanto segue:

1. **Aspose.BarCode for .NET** – scaricala dal sito ufficiale **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **A .NET development environment** – Visual Studio, Rider o VS Code con il .NET SDK.  
3. **Basic C# knowledge** – dovresti sentirti a tuo agio con classi, namespace e la direttiva `using`.

## Importa i namespace
Aggiungi i namespace richiesti all'inizio del tuo file C# affinché il compilatore sappia dove trovare le classi del codice a barre.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Questi namespace ti danno accesso sia alle funzionalità di generazione che di riconoscimento dei codici a barre.

## Come configurare il testo esteso DataMatrix?
Carica il builder, aggiungi i segmenti desiderati e lascia che Aspose.BarCode gestisca automaticamente i marcatori ECI. Questo paragrafo di risposta diretta ti indica i passaggi esatti: crea un `DataMatrixExtCodetextBuilder`, aggiungi segmenti Unicode, C40, plain‑text e Text mode, quindi recupera la stringa combinata per il generatore.

### Passo 1: Definisci la cartella di output
Specifica dove verrà salvata l'immagine del codice a barre generata. Sostituisci il segnaposto con un percorso valido sulla tua macchina.

```csharp
string path = "Your Directory Path";
```

### Passo 2: Costruisci il testo esteso
`DataMatrixExtCodetextBuilder` è una classe di supporto che assembla il testo esteso secondo la specifica DataMatrix. Inserisce automaticamente i marcatori ECI (Extended Channel Interpretation) richiesti.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Questo esempio dimostra come è possibile combinare caratteri Unicode, codifica C40, testo semplice e modalità Text in un unico simbolo DataMatrix.

### Passo 3: Genera la stringa finale del codetext
Dopo aver configurato tutte le parti, recupera la stringa combinata che Aspose.BarCode incorporerà nel codice a barre.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Passo 4: Crea il codice a barre DataMatrix
`BarcodeGenerator` è la classe principale che produce le immagini dei codici a barre. Istanziala con `EncodeTypes.DataMatrix` e il testo esteso, quindi imposta parametri visivi come la dimensione X, il formato immagine e il testo opzionale leggibile dall'uomo.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Il codice sopra **crea un barcode Aspose .NET** con il testo esteso desiderato e lo salva come file PNG.

### Passo 5: Verifica il codice a barre leggendo nuovamente
`BarCodeReader` verifica che il simbolo generato possa essere decodificato correttamente, cosa essenziale per pipeline di test automatizzate e controllo qualità.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Se tutto è configurato correttamente, la console mostrerà il testo esteso esatto che hai creato in precedenza.

## Problemi comuni e risoluzione
| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| Codice a barre non leggibile | Dimensione X troppo bassa | Aumenta `XDimension.Pixels` (es., 4 → 6) |
| Caratteri illeggibili | Codifica ECI errata | Assicurati che `ECIEncodings.UTF8` corrisponda al set di caratteri |
| File non salvato | Percorso non valido | Usa un percorso assoluto o assicurati che la cartella esista |
| Eccezione di licenza | Versione di prova scaduta | Applica una licenza temporanea o completa (vedi FAQ) |

## Domande frequenti
### Q1: Cos'è Aspose.BarCode per .NET?
A1: Aspose.BarCode per .NET è una libreria potente che consente agli sviluppatori di generare e riconoscere una vasta gamma di simbologie di codici a barre, tra cui DataMatrix, QR, Code128 e altro.

### Q2: Dove posso trovare la documentazione per Aspose.BarCode per .NET?
A2: Puoi accedere al riferimento completo dell'API **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: È disponibile una versione di prova gratuita per Aspose.BarCode per .NET?
A3: Sì, una versione di prova gratuita può essere scaricata da **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Come posso ottenere una licenza temporanea per i test?
A4: Le licenze temporanee sono fornite per scopi di valutazione e possono essere richieste su **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Dove posso ottenere supporto o fare domande su Aspose.BarCode per .NET?
A5: Il forum ufficiale di Aspose.BarCode è il posto migliore per chiedere aiuto: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Ultimo aggiornamento:** 2026-09-23  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati
- [Come generare codici a barre DataMatrix usando Aspose.BarCode per .NET – Guida passo‑passo](/barcode/net/datamatrix-barcode-configuration/)
- [Genera un codice a barre DataMatrix in modalità ASCII con Aspose.BarCode per .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Genera un codice a barre Aztec con codifica testo usando Aspose.BarCode per .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}