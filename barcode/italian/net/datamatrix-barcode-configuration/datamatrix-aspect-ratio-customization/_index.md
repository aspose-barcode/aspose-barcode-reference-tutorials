---
date: 2026-05-30
description: Scopri come creare un barcode PNG con un rapporto d'aspetto DataMatrix
  personalizzato utilizzando Aspose.BarCode per .NET. Guida passo passo per la generazione
  di barcode e la personalizzazione delle dimensioni.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Personalizzazione del Rapporto d'aspetto DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Crea Barcode PNG – Rapporto d'aspetto DataMatrix – Aspose.BarCode
url: /it/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea PNG di Codice a Barre – Rapporto d'Aspetto DataMatrix – Aspose.BarCode

Generare un **barcode PNG** con un rapporto d'aspetto DataMatrix personalizzato è una necessità comune quando è necessario **creare file barcode PNG** che si adattino a vincoli di layout specifici. In questo tutorial illustreremo i passaggi esatti per **creare file barcode PNG** usando Aspose.BarCode per .NET, spiegheremo perché potresti voler regolare il rapporto d'aspetto e ti mostreremo come perfezionare l'output per la tua applicazione.

## Risposte Rapide
- **Che cosa controlla il “rapporto d'aspetto”?** Definisce la proporzione larghezza‑altezza dei moduli DataMatrix.  
- **Posso esportare PNG, JPEG o SVG?** Sì – il metodo `Save` supporta PNG, JPEG, BMP, GIF, TIFF, SVG e PDF.  
- **Ho bisogno di una licenza per questa funzionalità?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza completa per la produzione.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Quanti valori di rapporto d'aspetto sono validi?** Qualsiasi valore float positivo; i valori tipici sono 0,5 – 2,0.

## Cos'è un codice a barre DataMatrix e perché regolare il suo rapporto d'aspetto?
Un codice a barre DataMatrix è un codice a matrice bidimensionale che memorizza grandi quantità di dati in un quadrato compatto. Regolare il **rapporto d'aspetto** consente di allungare o comprimere i moduli orizzontalmente, il che è utile quando è necessario inserire il codice a barre in colonne strette o etichette larghe senza compromettere l'affidabilità della scansione.

## Perché usare Aspose.BarCode per creare PNG di codice a barre?
Aspose.BarCode supporta **7 formati immagine** — PNG, JPEG, BMP, GIF, TIFF, SVG e PDF — e può elaborare **oltre 50 formati di input e output** in memoria, gestendo documenti con centinaia di pagine senza caricare l'intero file. La libreria fornisce un'API fluida che consente di generare un codice a barre DataMatrix in una singola riga di codice, garantendo un rendering pixel‑perfect e piena compatibilità .NET.

## Prerequisiti
Prima di iniziare a personalizzare i rapporti d'aspetto DataMatrix, assicurati di avere i seguenti prerequisiti in ordine:

1. **Visual Studio** – qualsiasi versione recente va bene.  
2. **Aspose.BarCode for .NET** – scaricalo [qui](https://releases.aspose.com/barcode/net/).  
3. Puoi anche esplorare altre versioni di prodotti Aspose [qui](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – il tuo progetto deve puntare a una versione supportata.

## Importa Namespace
Per prima cosa, devi importare il namespace necessario nel tuo progetto C#:

`using Aspose.BarCode.Generation;` importa il namespace che contiene le classi per la generazione di codici a barre.  

```csharp
using Aspose.BarCode.Generation;
```

> **Suggerimento:** Mantieni questa istruzione `using` in cima al tuo file in modo che la classe `BarcodeGenerator` sia sempre disponibile.

## Come creare PNG di codice a barre con rapporto d'aspetto personalizzato?
Carica il `BarcodeGenerator`, imposta il tipo DataMatrix, regola la proprietà `AspectRatio` e chiama `Save`. Questo modello a una riga crea un PNG di codice a barre che rispetta il rapporto specificato, e la libreria gestisce automaticamente il ridimensionamento dei moduli e le zone di silenzio.

`BarcodeGenerator` crea un'immagine di codice a barre dalla simbologia e dai dati specificati.

### Passo 1: Configura il tuo progetto
Crea un nuovo progetto console o Windows Forms in Visual Studio e aggiungi un riferimento al DLL di Aspose.BarCode.

### Passo 2: Inizializza un Generatore di Codice a Barre
Istanzialo con la simbologia DataMatrix e i dati che desideri codificare:

`BarcodeGenerator` crea un'immagine di codice a barre dalla simbologia e dai dati specificati.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Questa riga crea un generatore pronto a produrre un codice a barre DataMatrix che contiene il testo di esempio.

### Passo 3: Personalizza il Rapporto d'Aspetto e Salva i File PNG
Ora puoi modificare il **rapporto d'aspetto** e salvare ogni versione come immagine PNG:

`AspectRatio` imposta la proporzione larghezza‑altezza dei moduli DataMatrix.  
`Save` scrive l'immagine del codice a barre generata in un file nel formato scelto.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- La prima chiamata crea un codice a barre con proporzioni quadrate (`AspectRatio = 1`).  
- La seconda chiamata comprime il codice a barre orizzontalmente (`AspectRatio = 0.5`), producendo un aspetto più largo.

Ora hai due file **barcode PNG** con diversi rapporti d'aspetto pronti per l'uso in report, etichette o elementi UI.

## Problemi Comuni & Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **L'immagine generata è sfocata** | Aumenta il parametro `Resolution` prima di salvare (`gen.Parameters.ImageResolution = 300`). |
| **Il codice a barre non viene letto** | Assicurati che il rapporto d'aspetto rimanga tra 0,5 – 2,0 e mantieni una zona di silenzio sufficiente (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Errori di percorso file** | Usa `Path.Combine` per costruire il percorso di output e verifica che la cartella esista. |

## Domande Frequenti

**Q:** Posso personalizzare il rapporto d'aspetto di altri tipi di codici a barre usando Aspose.BarCode per .NET?  
**A:** Sì, molti codici a barre 2‑D (ad esempio QR, PDF417) supportano la regolazione del rapporto d'aspetto tramite i loro specifici oggetti parametro.

**Q:** È disponibile una versione di prova gratuita per Aspose.BarCode per .NET?  
**A:** Sì, è possibile accedere a una versione di prova gratuita di Aspose.BarCode per .NET [qui](https://releases.aspose.com/).

**Q:** Dove posso acquistare una licenza per Aspose.BarCode per .NET?  
**A:** È possibile acquistare una licenza sul sito web di Aspose [qui](https://purchase.aspose.com/buy).

**Q:** Aspose.BarCode per .NET è compatibile con diverse versioni del .NET Framework?  
**A:** Sì, funziona con .NET Framework 4.x, .NET Core 3.1+ e le ultime versioni di .NET.

**Q:** Posso generare codici a barre in diversi formati con Aspose.BarCode per .NET?  
**A:** Assolutamente – PNG, JPEG, BMP, GIF, TIFF, SVG e PDF sono tutti supportati nativamente.

## Conclusione
Personalizzare il **rapporto d'aspetto** di un codice a barre DataMatrix e **creare file barcode PNG** è semplice con Aspose.BarCode per .NET. Seguendo i passaggi sopra, puoi generare codici a barre di dimensioni perfette che soddisfano i requisiti di layout esatti del tuo progetto. Esplora parametri aggiuntivi come `Resolution`, `Margin` e `Color` per affinare ulteriormente l'output, e considera le capacità di `generate datamatrix barcode` quando costruisci applicazioni friendly per la scansione in Visual Studio.

Per approfondire, consulta la [documentazione](https://reference.aspose.com/barcode/net/) ufficiale o unisciti alla community sul [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ultimo Aggiornamento:** 2026-05-30  
**Testato Con:** Aspose.BarCode 24.12 per .NET  
**Autore:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial Correlati

- [Genera Codice a Barre DataMatrix – Guida Pro con Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Come Generare Codici a Barre DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Padroneggia la Codifica DataMatrix in ASCII con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}