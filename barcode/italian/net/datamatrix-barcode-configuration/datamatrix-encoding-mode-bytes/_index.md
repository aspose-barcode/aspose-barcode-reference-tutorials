---
date: 2026-01-25
description: Scopri come creare file PNG di codici a barre con Aspose.BarCode per
  .NET codificando DataMatrix in modalità Bytes. Segui questa guida di generazione
  di codici a barre per un'implementazione semplice.
linktitle: DataMatrix Encoding Mode (Bytes)
second_title: Aspose.BarCode .NET API
title: Crea PNG di codice a barre con Aspose.BarCode per .NET – Byte DataMatrix
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea PNG di Codice a Barre – Codifica DataMatrix in Bytes con Aspose.BarCode per .NET

## Risposte Rapide
- **Cosa significa “create barcode PNG”?** Si riferisce alla generazione di un'immagine raster PNG che contiene un codice a barre.
- **Quale libreria è la migliore per questo?** Aspose.BarCode per .NET fornisce un'API completa per la creazione e il riconoscimento dei codici a barre.
- **Ho bisogno di una licenza?** Una versione di prova gratuita è sufficiente per lo sviluppo; è necessaria una licenza commerciale per la produzione.
- **Posso leggere nuovamente il codice a libreria include un BarCodeReader per **leggere i dati del codice a barre DataMatrix**.
- **Quali versionNET 5/6/7.

## Come creare PNG di codice aci nel processouenti prerequisiti pronti:

1. Aspose.BarCode per .NET: Per iniziare, devi avere la libreria Aspose.BarCode per .NET installata. Puoi scaricarla da [qui](https://releases.aspose.com/barcode/net/).

2. Il tuo ambiente di sviluppo: Assicurati di avere un ambiente di sviluppo configurato, inclusi Visual Studio o qualsiasi altro IDE a tua scelta.

3. Conoscenza di base di C#: Questo tutorial presuppone che tu abbia una comprensione di base della programmazione C#.

Con questi prerequisiti in ordine, sei pronto per iniziare a codificare dati nel formato DataMatrix usando la modalità Bytes.

## Importare gli Spazi dei Nomi

Per utilizzare Aspose.BarCode per .NET, dovrai importare gli spazi dei nomi necessari nel tuo codice C#. Aggiungi le seguenti righe all'inizio del tuo file di codice:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Ora, suddividiamo il processo di codifica dei dati nel formato DataMatrix usando la modalità Bytes in più passaggi.

## Step 1: Initialize the BarcodeGenerator

Crea un oggetto BarcodeGenerator, specificando EncodeType come DataMatrix, e i dati che desideri codificare. Puoi sostituire `"Your Directory Path"` con il percorso reale dove vuoi salvare l'immagine del codice a barre.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## Step 2: Set DataMatrix Encode Mode to Bytes

Imposta la modalità di codifica DataMatrix su Bytes usando il seguente codice:

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

## Step 3: Set Display Text

Puoi impostare il testo visualizzato per il tuo codice a barre. In questo esempio, lo abbiamo impostato su "Bytes mode."

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

## Step 4: Save the Barcode Image

Salva l'immagine del codice a barre generata nel percorso specificato. In questo caso, viene salvata come "DataMatrixEncodeModeBytes.png."

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

## Step 5: Try to Recognize

Ora, proviamo a riconoscere il codice a barre DataMatrix codificato. Useremo il BarCodeReader per farlo.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

## Step 6: Iterate and Display Results

Itera attraverso i risultati e visualizza i dati codificati.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Con questi passaggi, hai **creato con successo un PNG di codice a barre** in modalità DataMatrix Bytes con Aspose.BarCode per .NET. Questa potente libreria semplifica la generazione e il riconoscimento dei codici a barre, rendendola uno strumento essenziale per gli sviluppatori.

Ora sei pronto a integrare la codifica e la decodifica dei codici a barre nelle tue applicazioni .NET con facilità, grazie ad Aspose.BarCode.

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare Aspose.BarCode per .NET per **creare file PNG di codice a barre** nel formato DataMatrix usando la modalità Bytes. Seguendo questi semplici passaggi, puoi migliorare le tue applicazioni con robuste capacità di generazione e riconoscimento dei codici a barre. Se incontri problemi, la community di Aspose.BarCode è pronta ad aiutarti.

Se hai domande o riscontri problemi, non esitare a chiedere assistenza alla community di Aspose.BarCode su [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

## FAQ's

### Q1: Cos'è la modalità di codifica DataMatrix?

A1: La modalità di codifica DataMatrix è un metodo utilizzato per codificare dati in un formato di codice a barre 2D. Offre varie opzioni di codifica, inclusa la modalità Bytes, adatta per codificare dati binari.

### Q2: Come posso ottenere una versione di prova gratuita di Aspose.BarCode per .NET?

A2: Puoi ottenere una versione di prova gratuita di Aspose.BarCode per .NET da [qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.BarCode per .NET?

A3: La documentazione per Aspose.BarCode per .NET è disponibile [qui](https://reference.aspose.com/barcode/net/).

### Q4: Aspose.BarCode per .NET è adatto per uso commerciale?

A4: Sì, Aspose.BarCode per .NET è adatto per uso commerciale. Puoi acquistare una licenza da [qui](https://purchase.aspose.com/buy).

### Q5: Posso utilizzare una licenza temporanea per Aspose.BarCode per .NET?

A5: Sì, puoi ottenere una licenza temporanea per Aspose.BarCode per .NET da [qui](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Come faccio a **leggere il codice a barre DataMatrix** dopo averlo creato?**  
A: Usa la classe `BarCodeReader` con `DecodeType.DataMatrix` come mostrato nel Passo 5 e Passo 6 dell'esempio di codice.

**Q: Posso cambiare le dimensioni del PNG generato?**  
A: Sì, regola `gen.Parameters.Barcode.XDimension.Pixels` o imposta i parametri `ImageWidth` e `ImageHeight` prima di chiamare `Save`.

**Q: E se devo codificare testo invece di bytes?**  
A: Cambia la modalità di codifica a `DataMatrixEncodeMode.Text` e fornisci la stringa da codificare.

**Q: C'è un modo per nascondere il testo leggibile dall'uomo sul codice a barre?**  
A: Imposta `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = false` per nascondere il testo visualizzato.

**Q: Aspose.BarCode supporta .NET Core?**  
A: Assolutamente— la libreria funziona con .NET Core, .NET 5, .NET 6 e versioni successive.

---

**Ultimo aggiornamento:** 2026-01-25  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}