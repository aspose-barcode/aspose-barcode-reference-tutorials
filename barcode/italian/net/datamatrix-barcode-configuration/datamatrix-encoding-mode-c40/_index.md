---
date: 2026-06-09
description: Scopri come generare codici a barre DataMatrix e salvare PNG usando la
  codifica C40 con Aspose.BarCode – guida completa per la generazione di codici a
  barre in .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Modalità di codifica DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Come generare PNG DataMatrix con C40 usando Aspose.BarCode
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master DataMatrix Encoding Mode (C40) con Aspose.BarCode per .NET

## Introduzione

In questo tutorial imparerai **come generare datamatrix** codici a barre e salvarli come file PNG utilizzando la modalità di codifica C40 con Aspose.BarCode per .NET. Che tu stia costruendo un sistema di inventario, un generatore di etichette di spedizione o qualsiasi soluzione che richieda simboli compatti ad alta densità, padroneggiare C40 ti offre simboli più piccoli senza sacrificare la leggibilità. Ti guideremo passo dopo passo — dall’impostazione dell’ambiente alla produzione del PNG finale — così potrai integrare immediatamente il codice nel tuo progetto.

## Risposte Rapide
- **A cosa si riferisce “come generare datamatrix”?** Creazione di un'immagine di codice a barre DataMatrix in modo programmatico.  
- **Quale modalità di codifica è trattata?** DataMatrix C40, uno schema alfanumerico efficiente.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso eseguirlo su .NET Core?** Sì, Aspose.BarCode supporta pienamente .NET Core, .NET 5, .NET 6 e versioni successive.  
- **Quale formato file viene prodotto?** PNG – un formato immagine senza perdita, adatto al web.

## Come Generare DataMatrix con Codifica C40

Carica i tuoi dati, configura il generatore e chiama `Save` — questo è il flusso di lavoro completo in tre passaggi concisi. La classe `BarcodeGenerator` gestisce la creazione del simbolo, mentre l’enumerazione `BarCodeImageFormat.Png` indica ad Aspose.BarCode di scrivere il risultato come file PNG. `Save` scrive l’immagine del codice a barre generata nel percorso file specificato nel formato scelto. Questo paragrafo di risposta diretta ti fornisce la soluzione end‑to‑end prima di approfondire ogni riga di codice.

## Cos'è la Modalità di Codifica DataMatrix (C40)?

`DataMatrixEncodeMode` è un’enumerazione che specifica quale schema di codifica Aspose.BarCode deve utilizzare per i simboli DataMatrix. L’opzione `DataMatrixEncodeMode.C40` seleziona la codifica alfanumerica C40, che raggruppa lettere, cifre e un insieme limitato di punteggiatura in meno moduli, riducendo la dimensione complessiva del simbolo mantenendo la leggibilità per il testo tipico di inventario. Questo schema efficiente è ideale quando è necessario codificare dati alfanumerici in forma compatta.

## Perché Usare Aspose.BarCode per .NET?

Aspose.BarCode fornisce **oltre 30 parametri configurabili** per dimensioni, livelli di correzione errori e modalità di codifica, e supporta **oltre 50 formati di immagine e codice a barre**. La libreria gira su **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, offrendo una generazione senza dipendenze che funziona su server, desktop e dispositivi mobili allo stesso modo.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

1. **Ambiente di sviluppo .NET** – Visual Studio, Rider o qualsiasi IDE che supporti C#.  
2. **Aspose.BarCode per .NET** – installato tramite NuGet o l'installer ufficiale. Vedi la [documentazione](https://reference.aspose.com/barcode/net/) per i dettagli.  
3. **Conoscenza base di C#** – dovresti sentirti a tuo agio con namespace, classi e istruzioni using.  
4. **Cartella con permessi di scrittura** – una directory sul tuo computer dove verrà salvato il PNG.

## Importare i Namespace Necessari

La classe `BarcodeGenerator` è il punto di ingresso per creare qualsiasi codice a barre. Aggiungi il namespace richiesto all’inizio del tuo file sorgente C# così da poter accedere all’API di generazione:

```csharp
using Aspose.BarCode.Generation;
```

## Generazione del Codice a Barre Passo‑per‑Passo

Di seguito trovi una **guida passo‑per‑passo** al codice a barre. Ogni passo è spiegato in linguaggio semplice, e i segnaposto originali sono mantenuti invariati per comodità di copia‑incolla.

### Passo 1: Definire il Percorso della Cartella
Imposta la cartella dove verrà memorizzata l’immagine PNG. Sostituisci il segnaposto con un percorso reale sul tuo computer.

```csharp
string path = "Your Directory Path";
```

### Passo 2: Configurare la Generazione del Codice a Barre
Crea un’istanza di `BarcodeGenerator`, specifica `EncodeTypes.DataMatrix` e fornisci i dati da codificare.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Passo 3: Personalizzare il Codice a Barre
Configura la X‑dimension (larghezza in pixel dei moduli) e imposta la modalità di codifica su C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Passo 4: Salvare l'Immagine del Codice a Barre
Infine, salva il codice a barre generato come file PNG. Questa è la risposta concreta a **come salvare png** con Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Quando esegui il programma, troverai `DataMatrixEncodeModeC40.png` nella cartella specificata, pronto per essere usato in report, etichette o pagine web.

## Problemi Comuni e Suggerimenti

- **Percorso non valido** – Assicurati che la directory esista e che tu abbia i permessi di scrittura; altrimenti `gen.Save` genererà un'eccezione.  
- **Modalità di codifica errata** – Se devi codificare caratteri al di fuori del set C40, passa a `DataMatrixEncodeMode.Auto` o a un’altra modalità appropriata.  
- **Dimensione immagine** – Regola `XDimension.Pixels` per aumentare o diminuire la dimensione complessiva del codice a barre senza influire sulla leggibilità.

## Domande Frequenti

**D: Cos'è la Modalità di Codifica DataMatrix (C40)?**  
R: C40 è uno schema di codifica alfanumerica compatto per i simboli DataMatrix, ideale per testi che includono lettere, numeri e un insieme limitato di caratteri speciali.

**D: Dove posso trovare la documentazione di Aspose.BarCode per .NET?**  
R: Puoi trovare la documentazione [qui](https://reference.aspose.com/barcode/net/). Fornisce indicazioni dettagliate su tutti i tipi di codice a barre e le opzioni di codifica.

**D: Aspose.BarCode per .NET è compatibile con tutte le versioni .NET?**  
R: Sì, la libreria supporta un’ampia gamma di versioni .NET, da .NET Framework 4.5+ a .NET 6 e versioni successive.

**D: Posso provare Aspose.BarCode per .NET prima di acquistarlo?**  
R: Sì, puoi esplorare una versione di prova gratuita di Aspose.BarCode per .NET visitando [questo link](https://releases.aspose.com/). Ti permette di testare le funzionalità e le capacità della libreria.

**D: Dove posso ottenere supporto per Aspose.BarCode per .NET?**  
R: Puoi trovare una community di supporto e accedere all’assistenza per Aspose.BarCode per .NET sul [forum Aspose](https://forum.aspose.com/c/barcode/13).

## Conclusione

Seguendo questa **guida passo‑per‑passo**, ora sai esattamente **come generare datamatrix** codici a barre e salvarli come file PNG utilizzando la modalità di codifica C40 con Aspose.BarCode per .NET. Questo approccio ti offre il pieno controllo sull’aspetto, la dimensione e la rappresentazione dei dati del codice a barre, facilitando l’integrazione di codici a barre di alta qualità in qualsiasi applicazione .NET.

---

**Last Updated:** 2026-06-09  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Codifica DataMatrix in Byte con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master Codifica DataMatrix in ASCII con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Come Generare Codici a Barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}