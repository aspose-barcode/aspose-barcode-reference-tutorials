---
date: 2026-08-17
description: Scopri come creare un codice a barre DataMatrix con caratteri macro utilizzando
  Aspose.BarCode per .NET e impara a utilizzare DataMatrix nelle tue applicazioni.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Configurazione Macro DataMatrix
og_description: Scopri come creare un codice a barre DataMatrix con caratteri macro
  utilizzando Aspose.BarCode per .NET. Questa guida fornisce codice passo‑passo, opzioni
  di personalizzazione e consigli di verifica per una generazione affidabile del codice
  a barre.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Crea un codice a barre DataMatrix con caratteri macro utilizzando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Come creare un codice a barre DataMatrix con caratteri macro in .NET
url: /it/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre DataMatrix con caratteri macro in .NET

## Introduzione

Generare un **codice a barre DataMatrix** che includa caratteri macro consente di inserire informazioni di riferimento aggiuntive in un piccolo simbolo quadrato. In questo tutorial imparerai a **creare un codice DataMatrix** con caratteri macro usando Aspose.BarCode per .NET, personalizzare dimensioni e correzione degli errori, e verificare immediatamente il risultato. Alla fine sarai pronto a incorporare codici a barre abilitati ai macro in etichette di prodotto, documenti o dispositivi medici.

## Risposte rapide
- **Qual è la libreria principale?** Aspose.BarCode per .NET  
- **Posso creare un codice DataMatrix con caratteri macro?** Sì – imposta la proprietà `MacroCharacters`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza Aspose valida per l'uso in produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **È disponibile una prova gratuita?** Assolutamente – scaricala dal sito ufficiale di Aspose.

## Prerequisiti

Prima di immergerti nella configurazione dei macro, assicurati di avere quanto segue:

1. **Visual Studio** – qualsiasi edizione recente funzionerà.  
2. **Aspose.BarCode per .NET** – scaricala da [il link di download](https://releases.aspose.com/barcode/net/).  
3. **Conoscenze di base di .NET** – familiarità con C# e l'ecosistema .NET.

## Importare gli spazi dei nomi

Iniziamo includendo gli spazi dei nomi necessari per la generazione e il riconoscimento dei codici a barre.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Che cos'è “generare codice DataMatrix” con caratteri macro?

`MacroCharacters` consente ai codici DataMatrix di includere simboli macro che fanno riferimento a dati aggiuntivi. Utilizzando caratteri macro come Macro05 o Macro06, un singolo codice a barre può puntare a un set di dati più ampio o a una sequenza di codici correlati, utile nella logistica, nella produzione e nel tracciamento dei documenti dove è necessario codificare in modo compatto informazioni collegate.

## Perché usare Aspose.BarCode per generare un codice DataMatrix?

Aspose.BarCode ti offre un controllo preciso su dimensione, livello di correzione degli errori e impostazioni macro del DataMatrix, supportando oltre 30 simbologie di codici a barre e gestendo file fino a 10 MB senza caricare l'intera immagine in memoria. La sua implementazione cross‑platform .NET funziona su .NET Framework, .NET Core e .NET 5/6, e include il riconoscimento integrato così puoi convalidare il codice a barre istantaneamente.

## Guida passo‑passo

### Passo 1: configurare il progetto

Crea una nuova Applicazione Console (o qualsiasi progetto .NET) in Visual Studio. Aggiungi un riferimento alle DLL di Aspose.BarCode che hai ottenuto dal download.

### Passo 2: configurazione macro DataMatrix

Il cuore del tutorial – qui creiamo effettivamente **un codice DataMatrix** con un carattere macro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Suggerimento:** Sostituisci `"ASPOSE"` con qualsiasi stringa tu voglia codificare. Il carattere macro (`Macro05`) indica ai lettori che questo codice a barre fa parte di una sequenza macro.

### Passo 3: personalizzare i parametri del codice a barre per la correzione degli errori

Prima di salvare, puoi modificare impostazioni aggiuntive:

- **XDimension** – controlla la dimensione di ogni modulo (pixel).  
- **Margin**, **ErrorCorrection**, e **EncodingMode** – tutti accessibili tramite `gen.Parameters.Barcode.DataMatrix`.

### Passo 4: salvare il codice a barre

Il frammento sopra salva l'immagine come `DataMatrixMacro.png` nella cartella specificata. PNG è loss‑less, rendendolo ideale per ulteriori elaborazioni.

### Passo 5: riconoscere il codice a barre

`BarCodeReader` è la classe di Aspose.BarCode per decodificare i codici a barre dalle immagini. Usando `BarCodeReader` leggiamo immediatamente l'immagine generata per confermare che il carattere macro e i dati siano corretti. Questa convalida end‑to‑end è particolarmente utile durante i test automatizzati.

## Come utilizzare DataMatrix in scenari reali?

Puoi applicare i codici DataMatrix con caratteri macro all'etichettatura dei prodotti, collegando numeri di serie a un database centrale, al tracciamento dei documenti incorporando un riferimento a un record digitale, e alle etichette di apparecchiature sanitarie che memorizzano dati di pazienti o dispositivi in un simbolo piccolo e leggibile. Questi casi d'uso riducono l'inserimento manuale dei dati e migliorano la tracciabilità.

## Problemi comuni e soluzioni

| Problema | Motivo | Correzione |
|----------|--------|------------|
| Codice a barre non riconosciuto | `XDimension` errato o bassa risoluzione dell'immagine | Aumenta `XDimension.Pixels` a 4‑6 e salva come PNG o TIFF |
| Carattere macro ignorato | Il lettore non supporta la modalità macro | Usa uno scanner/lettore che supporti esplicitamente i macro DataMatrix (ad esempio versioni più recenti di ZXing) |
| Percorso non trovato | Variabile `path` non valida | Assicurati che la directory esista o usa `Path.Combine` con `Environment.CurrentDirectory` |

## Domande frequenti

**D: Cos'è Aspose.BarCode per .NET?**  
R: Aspose.BarCode per .NET è una libreria potente che consente agli sviluppatori .NET di generare e riconoscere codici a barre in vari formati, inclusi DataMatrix, QR e altri.

**D: Perché dovrei usare i codici DataMatrix?**  
R: I codici DataMatrix sono compatti, altamente affidabili e possono memorizzare grandi quantità di dati, rendendoli ideali per produzione, logistica e sanità.

**D: Dove posso trovare la documentazione per Aspose.BarCode per .NET?**  
R: Puoi trovare la documentazione su [la documentazione di Aspose.BarCode per .NET](https://reference.aspose.com/barcode/net/).

**D: È disponibile una prova gratuita per Aspose.BarCode per .NET?**  
R: Sì, puoi scaricare una prova gratuita da [il link della prova gratuita](https://releases.aspose.com/).

**D: Dove posso ottenere supporto per Aspose.BarCode per .NET?**  
R: Se hai domande o necessiti di supporto, visita il forum di Aspose.BarCode per .NET su [il forum di supporto](https://forum.aspose.com/c/barcode/13).

---

**Ultimo aggiornamento:** 2026-08-17  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Crea codice a barre aspose .net - Configurazione del testo del codice DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Come generare codici DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Configurazione Structured Append DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}