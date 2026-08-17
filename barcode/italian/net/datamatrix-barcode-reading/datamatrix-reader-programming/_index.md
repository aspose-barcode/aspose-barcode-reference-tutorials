---
date: 2026-08-17
description: Esplora la programmazione del lettore DataMatrix con Aspose.BarCode per
  .NET. Scopri come generare e leggere codici a barre DataMatrix nelle tue applicazioni
  .NET con questa guida completa.
keywords:
- create barcode image .net
- barcode reader guide
- generate datamatrix c#
- c# barcode recognition library
- barcode image handling c#
lastmod: 2026-08-17
linktitle: Programmazione Lettore DataMatrix
og_description: Crea immagine di codice a barre .NET usando Aspose.BarCode per generare
  e leggere codici DataMatrix. Questa guida mostra la configurazione passo‑passo,
  snippet di codice e le migliori pratiche per la gestione delle immagini di codici
  a barre in C#.
og_image_alt: Tutorial image showing DataMatrix barcode generated with Aspose.BarCode
  in a .NET application
og_title: Crea immagine di codice a barre .NET con Aspose.BarCode DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  headline: Create barcode image .NET with Aspose.BarCode for DataMatrix
  type: TechArticle
- description: Explore DataMatrix reader programming with Aspose.BarCode for .NET.
    Learn how to generate and read DataMatrix barcodes in your .NET applications with
    this comprehensive guide.
  name: Create barcode image .NET with Aspose.BarCode for DataMatrix
  steps:
  - name: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
    text: '**Visual Studio** (any recent edition) with a supported .NET runtime installed.'
  - name: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download it from the [download page](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
    text: '**Basic C# knowledge** – you should be comfortable creating a console or
      desktop project.'
  type: HowTo
- questions:
  - answer: It embeds configuration data in a DataMatrix symbol so a scanner can automatically
      set parameters like illumination or decoding mode.
    question: What is DataMatrix reader programming?
  - answer: The library offers a unified API for over 50 barcode types, high‑performance
      encoding/decoding, and full .NET Core support.
    question: Why choose Aspose.BarCode for .NET?
  - answer: A trial version is available for evaluation; a commercial license is required
      for production deployments.
    question: Can I use Aspose.BarCode for free?
  - answer: You can request a short‑term license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license?
  - answer: You can buy a full license from the [Aspose purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase a full license?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- DataMatrix
- Aspose.BarCode
- barcode generation
- C# barcode
- create barcode image
title: Crea immagine di codice a barre .NET con Aspose.BarCode per DataMatrix
url: /it/net/datamatrix-barcode-reading/datamatrix-reader-programming/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea immagine barcode .NET con Aspose.BarCode per DataMatrix

In questo tutorial imparerai come **creare immagine barcode .NET** applicazioni che generano e leggono codici DataMatrix usando Aspose.BarCode. Che tu abbia bisogno di incorporare barcode nelle etichette di produzione o di automatizzare il tracciamento dell'inventario, questa guida ti accompagna passo passo—dalla configurazione del progetto alla lettura del barcode—così potrai implementare rapidamente una soluzione affidabile.

## Risposte rapide
- **Cosa significa “reader programming”?** Codifica i simboli DataMatrix in modo che uno scanner possa configurarsi automaticamente.  
- **Quali versioni .NET sono supportate?** Aspose.BarCode funziona con .NET Framework 4.0+, .NET Core 2.0+ e .NET 5/6+.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova gratuita è sufficiente per i test; è necessaria una licenza commerciale per la produzione.  
- **Quanti formati di barcode gestisce Aspose.BarCode?** Oltre 50 simbologie 1D e 2D, incluse DataMatrix, QR e PDF417.  
- **Posso leggere il barcode senza salvare un file immagine?** Sì—usa un `MemoryStream` per elaborare l'immagine interamente in memoria.

## Cos'è la programmazione del lettore barcode DataMatrix?
La programmazione del lettore barcode DataMatrix è la tecnica di incorporare dati di configurazione speciali all'interno di un simbolo DataMatrix in modo che uno scanner possa regolare automaticamente l'illuminazione, la modalità di decodifica e altri parametri operativi quando il simbolo viene rilevato. Questo approccio riduce la necessità di configurazioni manuali dello scanner e migliora il throughput in ambienti ad alto volume come linee di produzione o sistemi di smistamento in magazzino.

## Perché usare Aspose.BarCode per .NET?
Aspose.BarCode per .NET offre un'API unificata che supporta più di 50 simbologie di barcode, può gestire immagini multi‑megabyte senza caricare l'intero file in memoria e fornisce codifica e decodifica in sub‑millisecondi su hardware server tipico, rendendola una scelta ad alte prestazioni sia per applicazioni desktop che basate su cloud che richiedono un'elaborazione affidabile dei barcode.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Visual Studio** (qualsiasi edizione recente) con un runtime .NET supportato installato.  
2. **Aspose.BarCode per .NET** – scaricalo dalla [pagina di download](https://releases.aspose.com/barcode/net/).  
3. **Conoscenza base di C#** – dovresti sentirti a tuo agio nel creare un progetto console o desktop.

## Importa namespace

`Aspose.BarCode` fornisce le classi core per la generazione e lettura di barcode, mentre `System.Drawing` gestisce la manipolazione delle immagini.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

## Cos'è la classe `BarcodeGenerator`?
La classe `BarcodeGenerator` è l'oggetto principale di Aspose.BarCode per creare immagini barcode in memoria; incapsula tutte le impostazioni necessarie a definire la simbologia, l'aspetto visivo, le opzioni di codifica e il formato di output, consentendo agli sviluppatori di generare barcode di alta qualità con una singola chiamata di metodo.

## Come definire il percorso della directory
Definisci una cartella dove l'immagine barcode generata sarà salvata.  

```csharp
string path = "Your Directory Path";
```

Sostituisci `"Your Directory Path"` con la cartella reale sul tuo computer.

## Come inizializzare il generatore DataMatrix
Crea un'istanza di `BarcodeGenerator`, imposta la simbologia su DataMatrix e abilita la programmazione del lettore.

```csharp
System.Console.WriteLine("DataMatrixReaderProgramming:");

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    // Set a flag that indicates data is encoded for reader programming
    generator.Parameters.Barcode.DataMatrix.IsReaderProgramming = true;
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Impostazioni chiave:

- `XDimension = 4` pixel controlla la dimensione del modulo.  
- `IsReaderProgramming = true` indica allo scanner che il simbolo contiene dati di configurazione.

## Come generare l'immagine barcode
Chiama il metodo `Save` per scrivere l'immagine nel percorso scelto.

```csharp
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

L'immagine viene salvata in formato PNG per impostazione predefinita, ma è possibile scegliere JPEG, BMP o TIFF.

## Come leggere il barcode
Usa `BarCodeReader` per decodificare l'immagine salvata e verificare il flag di programmazione del lettore. La classe `BarCodeReader` è il componente core per la decodifica dei barcode; legge un'immagine, rileva le simbologie supportate e espone proprietà come `IsReaderProgrammable` che indicano se il simbolo DataMatrix contiene informazioni di programmazione del lettore.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();
        Console.WriteLine("Is reader programming: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.IsReaderProgramming);
    }
}
```

Il lettore restituisce `IsReaderProgrammable` = `true` quando il flag è stato codificato correttamente.

## Problemi comuni e risoluzione
- **Immagine non trovata** – Verifica che il percorso della directory termini con una barra rovesciata (`\`) o usa `Path.Combine`.  
- **Il lettore restituisce false** – Assicurati che `IsReaderProgramming` sia impostato **prima** di chiamare `Save`.  
- **Formato immagine non supportato** – Usa PNG o JPEG; BMP e TIFF potrebbero richiedere codec aggiuntivi su versioni più vecchie di Windows.

## Domande frequenti

**Q: Cos'è la programmazione del lettore DataMatrix?**  
A: Incorpora dati di configurazione in un simbolo DataMatrix in modo che uno scanner possa impostare automaticamente parametri come l'illuminazione o la modalità di decodifica.

**Q: Perché scegliere Aspose.BarCode per .NET?**  
A: La libreria offre un'API unificata per oltre 50 tipi di barcode, codifica/decodifica ad alte prestazioni e pieno supporto .NET Core.

**Q: Posso usare Aspose.BarCode gratuitamente?**  
A: È disponibile una versione di prova per la valutazione; è necessaria una licenza commerciale per le distribuzioni in produzione.

**Q: Come posso ottenere una licenza temporanea?**  
A: Puoi richiedere una licenza a breve termine dalla [pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

**Q: Come posso acquistare una licenza completa?**  
A: Puoi acquistare una licenza completa dalla [pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

**Q: La libreria è compatibile con le ultime versioni .NET?**  
A: Sì, supporta .NET Framework 4.0+, .NET Core 2.0+ e .NET 5/6+.

## Conclusione

Seguendo questa guida ora sai come **creare soluzioni barcode image .NET** che generano simboli DataMatrix e li leggono con Aspose.BarCode. Integra questi snippet in qualsiasi progetto C#—desktop, service o web—per automatizzare i flussi di lavoro dei barcode in ambienti di produzione, logistica o sanità.

Per approfondire, consulta la [documentazione](https://reference.aspose.com/barcode/net/) ufficiale o unisciti alla community sul [forum di supporto Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ultimo aggiornamento:** 2026-08-17  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose

## Tutorial correlati

- [Come leggere i barcode DataMatrix con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-reading/)
- [Come generare barcode DataMatrix (ECC 200) con Aspose.BarCode per .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Crea Barcode PNG – Rapporto d'aspetto DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}