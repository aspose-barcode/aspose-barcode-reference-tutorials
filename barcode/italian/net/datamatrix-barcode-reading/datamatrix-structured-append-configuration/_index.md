---
date: 2026-06-14
description: Scopri come leggere i datamatrix e generare codici a barre structured
  append in .NET usando Aspose.BarCode, la libreria di codici a barre veloce e affidabile.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Configurazione Structured Append di DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Come leggere DataMatrix Append con Aspose.BarCode per .NET
url: /it/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurazione Structured Append di DataMatrix con Aspose.BarCode per .NET

Se sei uno sviluppatore alla ricerca di **come leggere datamatrix** usando structured append nelle tue applicazioni .NET, Aspose.BarCode per .NET è la tua soluzione di riferimento. In questa guida passo‑passo, ti mostreremo come generare e decodificare codici a barre DataMatrix suddivisi su più simboli. Alla fine di questo tutorial sarai in grado di creare, configurare e leggere codici a barre DataMatrix structured append con Aspose.BarCode per .NET.

## Risposte rapide
- **Quale libreria gestisce DataMatrix structured append?** Aspose.BarCode per .NET.
- **Quanti simboli può contenere una singola sequenza structured append?** Fino a 16 simboli DataMatrix.
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita funziona per sviluppo e test.
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Posso leggere il codice a barre senza un file immagine?** Sì, è possibile decodificare da un array di byte o da uno stream.

## Che cos'è come leggere datamatrix?
**come leggere datamatrix** si riferisce al processo di decodifica dei simboli DataMatrix e, quando applicabile, all'assemblaggio dei pezzi di una sequenza structured‑append per recuperare il payload di dati originale. Aspose.BarCode fornisce supporto integrato per questo flusso di lavoro, gestendo automaticamente l'ordinamento dei simboli e la concatenazione dei dati.

## Perché usare Aspose.BarCode per DataMatrix structured append?
Aspose.BarCode supporta **30+ simbologie di codici a barre** e può decodificare immagini fino a **10.000 × 10.000 px** in meno di **200 ms** su hardware server tipico. La libreria offre anche **distribuzione a zero dipendenze**, il che significa che non sono necessarie DLL native aggiuntive, e funziona su runtime .NET Windows, Linux e macOS.

## Prerequisiti

Prima di immergerti nel tutorial, avrai bisogno di:

1. Aspose.BarCode for .NET Library – scaricala da [qui](https://releases.aspose.com/barcode/net/).
2. Puoi anche sfogliare altri prodotti Aspose [qui](https://releases.aspose.com/).
3. Un ambiente di sviluppo .NET come Visual Studio 2022 o Visual Studio Code con l'estensione C#.

Ora, iniziamo a creare e leggere codici a barre DataMatrix structured append.

## Importa Namespace

Il primo passo è importare i namespace che espongono l'API del codice a barre.

La classe `BarCodeWriter` è il punto di ingresso di Aspose.BarCode per creare codici a barre, mentre `BarCodeReader` gestisce la decodifica.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ora che hai importato i namespace richiesti, generiamo un codice a barre structured‑append.

## Come leggere i codici a barre DataMatrix structured append?
Carica l'immagine generata (o lo stream) in un `BarCodeReader`, abilita l'opzione `ReadStructuredAppend` e chiama `ReadBarcode`. Il lettore restituirà automaticamente i dati combinati e esporrà i dettagli della sequenza come `StructuredAppendFileId`, `StructuredAppendTotalCount` e `StructuredAppendSegmentId`. Il risultato combinato viene restituito come una singola stringa, e puoi anche recuperare gli identificatori dei singoli segmenti tramite la proprietà `StructuredAppendSegmentId` del lettore per elaborazioni personalizzate.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

In questo passaggio, utilizziamo il lettore per estrarre l'ID del codice a barre, il conteggio totale e l'ID del file, confermando che la configurazione structured‑append è stata interpretata correttamente.

## Passo 1: Configura Structured Append di DataMatrix
Per creare un codice a barre DataMatrix structured append, è necessario impostare la sua configurazione. Questo include la definizione del percorso della directory, l'ID del codice a barre, il numero di codici a barre e l'ID del file.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

In questo passaggio, abbiamo configurato il codice a barre DataMatrix con i parametri desiderati.

## Problemi comuni e soluzioni
- **Ordine dei segmenti errato:** Assicurati che i valori di `StructuredAppendSegmentId` siano sequenziali a partire da 0; altrimenti il lettore non può ricomporre correttamente i dati.
- **Conteggio totale non corrispondente:** `StructuredAppendTotalCount` deve essere lo stesso per tutti i simboli; una discrepanza farà trattare la sequenza come incompleta dal lettore.
- **Qualità dell'immagine:** Immagini a bassa risoluzione possono causare errori di decodifica. Puntare ad almeno **300 dpi** quando si rende il codice a barre in bitmap.

## Domande frequenti

### Q1: Cos'è DataMatrix structured append e perché viene utilizzato?
R1: DataMatrix structured append è una funzionalità che consente di suddividere una grande quantità di dati in più codici a barre più piccoli. È particolarmente utile quando lo spazio per un singolo codice a barre è limitato o quando è necessario organizzare i dati in modo efficiente. È comunemente usato nella logistica, nella sanità e nella produzione.

### Q2: Posso usare Aspose.BarCode per .NET nel mio progetto open‑source?
R2: Sì, Aspose.BarCode per .NET offre una versione di prova gratuita che puoi utilizzare nei progetti open‑source. Puoi trovare la versione di prova [qui](https://releases.aspose.com/).

### Q3: È disponibile supporto della community per Aspose.BarCode per .NET?
R3: Sì, puoi cercare supporto nella community e interagire con altri utenti sul forum Aspose.BarCode [qui](https://forum.aspose.com/c/barcode/13).

### Q4: Come posso ottenere una licenza temporanea per Aspose.BarCode per .NET?
R4: Se hai bisogno di una licenza temporanea per valutazione o test, puoi ottenerla da [qui](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.BarCode per .NET supporta altri tipi di codici a barre?
R5: Sì, Aspose.BarCode per .NET supporta un'ampia gamma di tipi di codici a barre, inclusi QR code, Code 128, EAN‑13 e molti altri. Puoi esplorare la documentazione completa [qui](https://reference.aspose.com/barcode/net/) per vedere l'elenco completo dei tipi di codici a barre supportati.

---

**Ultimo aggiornamento:** 2026-06-14  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati
- [Programmazione del lettore DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Genera codici a barre DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Configurazione macro Master DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}