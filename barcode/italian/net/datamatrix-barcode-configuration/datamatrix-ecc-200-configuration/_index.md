---
date: 2026-08-02
description: Scopri come creare un codice a barre DataMatrix, generare datamatrix
  e esplorare la generazione di codici a barre ad alta densità con Aspose.BarCode
  per progetti .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Configurazione DataMatrix ECC 200
og_description: Crea codice a barre DataMatrix con Aspose.BarCode per .NET. Questo
  tutorial mostra la generazione di codici a barre ad alta densità, la configurazione
  temporanea della licenza Aspose e il codice C# passo‑passo.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Crea codice a barre DataMatrix – Guida Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Come creare il codice a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET
url: /it/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre DataMatrix (ECC 200) con Aspose.BarCode per .NET

## Introduzione

In questa guida **creerai un codice a barre DataMatrix** (ECC 200) usando Aspose.BarCode per .NET. Che tu stia costruendo un tracciatore di inventario, un sistema di punto vendita o automatizzando flussi di lavoro documentali, un codice a barre ad alta densità può memorizzare molti dati in uno spazio ridotto. Ti guideremo passo passo attraverso ogni configurazione, spiegheremo perché ogni impostazione è importante e ti forniremo snippet C# pronti all'uso.

## Risposte rapide
- **Quale libreria è la migliore per DataMatrix in .NET?** Aspose.BarCode per .NET  
- **Quale livello ECC fornisce ECC 200?** Correzione di errore ad alta densità per una scansione robusta.  
- **È necessaria una licenza per eseguire il campione?** Una licenza temporanea funziona per la valutazione; è richiesta una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Posso esportare PNG, JPEG o TIFF?** Sì – il metodo `Save` supporta più formati immagine.

## Cos'è DataMatrix ECC 200?

DataMatrix ECC 200 è un codice a barre bidimensionale ad alta densità che può memorizzare fino a 2.335 caratteri alfanumerici o 1.556 byte di dati binari in un compatto schema quadrato o rettangolare. Utilizza la correzione di errore Reed‑Solomon per recuperare moduli persi o danneggiati, rendendolo ideale per applicazioni come marcatura di parti aerospaziali, etichettatura farmaceutica e logistica, dove l'affidabilità è fondamentale.

## Perché utilizzare la generazione di codici a barre Aspose?

Aspose.BarCode supporta **oltre 30 simbologie**, può renderizzare immagini fino a 10.000 × 10.000 px senza caricare l'intero file in memoria e fornisce output deterministico su Windows, Linux e macOS. La sua API consente di controllare ogni parametro di rendering, rendendola la scelta più flessibile per scenari di **generazione di codici a barre ASP.NET**.

## Prerequisiti

1. **Ambiente di sviluppo** – Visual Studio con il framework .NET appropriato installato.  
2. **Aspose.BarCode per .NET** – Scarica e installa dal sito web, [qui](https://releases.aspose.com/barcode/net/).  
3. **Licenza** – Ottieni una licenza temporanea per i test da [qui](https://purchase.aspose.com/temporary-license/).  
4. **Nozioni di base su C#** – Familiarità con la sintassi C# e la struttura del progetto.

Ora che abbiamo coperto le basi, passiamo alla configurazione di DataMatrix ECC 200.

## Importare gli spazi dei nomi

Lo spazio dei nomi `Aspose.BarCode.Generation` contiene tutte le classi necessarie per la creazione del codice a barre. Importalo all'inizio del tuo file:

```csharp
using Aspose.BarCode.Generation;
```

## Come creare un codice a barre DataMatrix (ECC 200) passo dopo passo

Per produrre un codice a barre DataMatrix ECC 200 devi semplicemente caricare i dati da codificare, configurare alcuni parametri chiave sul `BarcodeGenerator` e poi chiamare `Save` per scrivere il file immagine. Questo flusso in tre passaggi gestisce la codifica, la correzione di errore e la selezione del formato di output, consentendoti di integrare la creazione del codice a barre in qualsiasi applicazione .NET con codice minimo.

### Passo 1: Inizializzare il Barcode Generator

`BarcodeGenerator` è la classe principale di Aspose.BarCode che crea e renderizza i codici a barre. Accetta il tipo di simbologia e il testo da codificare.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Sostituisci `"Your Directory Path"` con la cartella in cui desideri salvare l'immagine.

### Passo 2: Impostare XDimension e Tipo ECC

`XDimension` definisce la dimensione in pixel di ogni modulo DataMatrix, mentre `DataMatrixEcc` seleziona il livello di correzione di errore. ECC 200 fornisce la massima capacità di correzione per questa simbologia.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Regola il valore dei pixel se ti servono moduli più grandi o più piccoli; valori tipici sono 4‑6 px per la visualizzazione su schermo e 8‑10 px per etichette stampate.

### Passo 3: Generare e salvare l'immagine del codice a barre

Il metodo `Save` scrive il codice a barre su file. Puoi scegliere PNG, JPEG o TIFF passando il valore corrispondente dell'enumerazione `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` o `BarCodeImageFormat.Tiff` se il tuo flusso di lavoro richiede un formato diverso.

## Problemi comuni e risoluzione

| Sintomo | Probabile causa | Correzione |
|---------|----------------|------------|
| Il codice a barre appare sfocato | XDimension troppo basso | Aumenta `XDimension.Pixels` a 6‑8 |
| La scansione fallisce su mobile | Livello ECC errato | Assicurati che `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Il file non viene creato | Stringa di percorso non valida | Usa un percorso assoluto o verifica che la cartella esista |

## Domande frequenti

**D: Posso usare questo codice in un'app console .NET Core?**  
R: Sì, la stessa API funziona in progetti .NET Core, .NET 5 e .NET 6.

**D: Come cambio il formato di output in JPEG?**  
R: Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Jpeg` nella chiamata a `Save`.

**D: È possibile incorporare il codice a barre direttamente in un PDF?**  
R: Sì – genera prima l'immagine, poi aggiungila a un PDF usando Aspose.PDF o qualsiasi libreria PDF.

**D: Cosa succede se devo codificare caratteri Unicode?**  
R: DataMatrix supporta UTF‑8; basta passare la stringa Unicode al generatore come mostrato.

**D: La libreria supporta la generazione batch di più codici a barre?**  
R: Assolutamente – inserisci il codice di generazione in un ciclo e varia i dati/valori per ogni iterazione.

## Conclusione

Abbiamo coperto tutto ciò che ti serve per **creare un codice a barre DataMatrix** (ECC 200) con Aspose.BarCode per .NET: dai prerequisiti e importazioni degli spazi dei nomi alla configurazione della X‑dimension, alla selezione del livello ECC e al salvataggio dell'immagine nel formato preferito. Sperimenta con le numerose proprietà aggiuntive — come margine, colore di sfondo e rotazione — per perfezionare l'output per il tuo caso d'uso specifico.

Se incontri difficoltà, la community è pronta ad aiutarti sul [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Buona programmazione!

---

**Ultimo aggiornamento:** 2026-08-02  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [How to Generate DataMatrix ECC 000-140 Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}