---
date: 2026-06-09
description: Scopri come creare un codice a barre DataMatrix in modalità ASCII utilizzando
  Aspose.BarCode per .NET. Questa guida mostra come generare rapidamente un codice
  a barre in C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Modalità di codifica DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crea il codice a barre DataMatrix in modalità ASCII con Aspose.BarCode per
  .NET
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea codice a barre DataMatrix in modalità ASCII con Aspose.BarCode per .NET

## Introduzione

Pronto a **creare codici a barre DataMatrix** che utilizzano la efficiente codifica ASCII? In questo tutorial imparerai a generare un codice a barre DataMatrix in modalità ASCII usando Aspose.BarCode per .NET. Ti guideremo passo passo — dall'impostazione del progetto al salvataggio dell'immagine finale — così potrai aggiungere la generazione di codici a barre alle tue applicazioni C# in pochi minuti.

## Risposte rapide
- **Qual è la libreria migliore per DataMatrix in .NET?** Aspose.BarCode for .NET  
- **Quante righe di codice sono necessarie?** Circa 5‑7 righe per un codice ASCII di base  
- **È necessaria una licenza?** Una versione di prova gratuita funziona per lo sviluppo; è richiesta una licenza per la produzione  
- **Piattaforme supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Posso cambiare dimensioni o colori?** Sì, Aspose.BarCode espone proprietà per le dimensioni e i colori di primo piano/sfondo  

## Cos'è il codice a barre DataMatrix?
DataMatrix è un codice a barre bidimensionale che memorizza testo e dati binari in un compatto schema quadrato.  
Un codice a barre DataMatrix codifica le informazioni in una griglia di moduli neri e bianchi, consentendo fino a 2.335 caratteri alfanumerici in un unico simbolo. È ampiamente utilizzato nella produzione, nella logistica e nella sanità perché può essere stampato a dimensioni molto ridotte mantenendo un'elevata leggibilità.

## Come creare un codice a barre DataMatrix in modalità ASCII?
Carica lo spazio dei nomi Aspose.BarCode, istanzia un `BarcodeGenerator`, imposta `EncodeMode` su **EncodeMode.ASCII**, assegna la tua stringa di dati e chiama `Save` per scrivere il file immagine. Questo approccio produce un codice a barre DataMatrix perfettamente conforme con codifica solo ASCII in poche righe di codice C#.

## Perché usare la codifica ASCII per DataMatrix?
La modalità ASCII è la codifica predefinita e più efficiente per dati di testo semplice, offrendo la dimensione di simbolo più piccola possibile per stringhe alfanumeriche. Supporta tutti i 128 caratteri ASCII, elabora i dati più velocemente rispetto alle modalità estese e garantisce la massima compatibilità con scanner legacy che si aspettano simboli ASCII standard.

## Prerequisiti

1. **Ambiente di sviluppo** – Visual Studio, Rider o qualsiasi IDE compatibile con C#.  
2. **Aspose.BarCode for .NET** – Scarica l'ultimo pacchetto da [here](https://releases.aspose.com/barcode/net/).  
   - Documentazione: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Supporto della community: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Conoscenza di base di C#** – Familiarità con la struttura dei progetti .NET ti aiuterà a seguire i passaggi rapidamente.  
4. **Altri prodotti Aspose** possono essere trovati [here](https://releases.aspose.com/).

## Importa gli spazi dei nomi

Per iniziare, aggiungi le direttive `using` richieste in cima al tuo file C#:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Questi spazi dei nomi ti danno accesso alla classe `BarcodeGenerator` e ai tipi relativi alle immagini necessari per salvare l'output.

## Passo 1: Crea una directory

Scegli una cartella dove verranno memorizzate le immagini dei codici a barre generate. Sostituisci `"Your Directory Path"` con un percorso assoluto o relativo che esiste sul tuo computer.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Il codice garantisce che la directory esista prima di tentare di scrivere file, evitando errori di runtime.

## Passo 2: Codifica dei dati in modalità ASCII

La classe `BarcodeGenerator` crea e configura le immagini dei codici a barre. L'enumerazione `DataMatrixEncodeMode` seleziona l'algoritmo di codifica per i simboli DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Dopo aver eseguito il codice, troverai `datamatrix_ascii.png` nella cartella specificata. L'immagine contiene un codice a barre DataMatrix che codifica la stringa `"1234567890"` usando la modalità ASCII compatta.

## Problemi comuni e soluzioni

- **Errori di accesso ai file** – Assicurati che l'applicazione abbia i permessi di scrittura sulla cartella di destinazione. Eseguire Visual Studio come amministratore può risolvere i problemi di permessi su Windows.  
- **Dimensione del simbolo errata** – Se il codice a barre appare troppo grande o troppo piccolo, modifica `generator.Parameters.Image.Width` e `Height` o lascia che Aspose calcoli automaticamente la dimensione ottimale omettendo queste proprietà.  
- **Caratteri non supportati** – La modalità ASCII accetta solo caratteri nell'intervallo 0‑127. Per dati Unicode, passa a `DataMatrixEncodeMode.Base256` o a un'altra modalità appropriata.

## Domande frequenti

**Q: Posso usare questo in un'applicazione commerciale?**  
A: Sì, è necessaria una licenza Aspose valida per l'uso in produzione; è disponibile una versione di prova gratuita per la valutazione.

**Q: La libreria funziona con .NET Core?**  
A: Assolutamente – Aspose.BarCode supporta pienamente .NET Core 3.1+, .NET 5, .NET 6 e versioni successive.

**Q: Quanti caratteri posso codificare in modalità ASCII?**  
A: Fino a 2.335 caratteri alfanumerici possono essere inseriti in un singolo simbolo DataMatrix usando la codifica ASCII.

**Q: Posso cambiare il colore di primo piano o di sfondo del codice a barre?**  
A: Sì, regola `generator.Parameters.Image.ForeColor` e `BackColor` a qualsiasi valore `System.Drawing.Color`.

**Q: Dove posso trovare esempi più avanzati?**  
A: La documentazione ufficiale contiene decine di esempi che coprono dimensioni personalizzate, colori e livelli di correzione degli errori.

## FAQ

### Q1: Posso usare Aspose.BarCode per .NET con altri linguaggi di programmazione oltre a C#?
A1: Aspose.BarCode supporta più linguaggi di programmazione, ma questo tutorial si concentra su C#.

### Q2: Quali sono le diverse modalità di codifica disponibili nei codici a barre DataMatrix?
A2: I codici a barre DataMatrix supportano varie modalità di codifica, tra cui ASCII, C40, Text e Base256. Ogni modalità è adatta a diversi tipi di dati.

### Q3: Posso personalizzare l'aspetto del codice a barre generato, come dimensione e colore?
A3: Sì, Aspose.BarCode offre un'ampia gamma di parametri per personalizzare l'aspetto del codice a barre, inclusi dimensione, colore e altro.

### Q4: È disponibile una versione di prova gratuita di Aspose.BarCode per .NET?
A4: Sì, puoi provare Aspose.BarCode per .NET con una versione di prova gratuita da [here](https://releases.aspose.com/).

### Q5: Dove posso acquistare una licenza per Aspose.BarCode per .NET?
A5: Puoi acquistare una licenza dal sito Aspose [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutorial correlati

- [Codifica DataMatrix in byte con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Leggi codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Come generare codici a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}