---
date: 2026-01-15
description: Guida tutorial passo‑passo per leggere codici a barre DataMatrix in C#
  e generare immagini di codici a barre in C# utilizzando Aspose.BarCode per .NET.
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
title: Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leggi il codice a barre DataMatrix C# – Genera modalità DataMatrix (Auto)

Nel mondo digitale odierno, in rapida evoluzione, essere in grado di **leggere il codice a barre DataMatrix C#** rapidamente e in modo affidabile è essenziale per tutto, dal tracciamento dell'inventario alla gestione sicura dei documenti. Questo tutorial ti guida nella generazione di un codice a barre DataMatrix in modalità *Auto* con Aspose.BarCode per .NET e poi mostra come leggere quel codice a barre in C#. Che tu stia seguendo una **guida tutorial sui codici a barre** o abbia semplicemente bisogno di un solido esempio di codice, terminerai questa guida con una soluzione funzionante da inserire nei tuoi progetti.

## Risposte rapide
- **Cosa fa la modalità “Auto”?** Consente ad Aspose.BarCode di selezionare automaticamente lo schema di codifica migliore per i tuoi dati.  
- **Quale libreria è necessaria?** Aspose.BarCode per .NET (disponibile versione di prova gratuita).  
- **Posso leggere il codice a barre nella stessa app?** Sì – utilizza `BarCodeReader` con `DecodeType.DataMatrix`.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per l'uso in produzione.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Che cos'è la lettura del codice a barre DataMatrix C#?
Leggere un codice a barre DataMatrix in C# significa decodificare la matrice bidimensionale di moduli neri e bianchi riportandola al testo o ai dati originali. Aspose.BarCode fornisce un'API semplice che astrae l'elaborazione di immagine a basso livello, permettendoti di concentrarti sulla logica di business.

## Perché usare Aspose.BarCode per generare l'immagine del codice a barre C#?
- **Affidabilità:** Gestisce tutti gli standard DataMatrix e seleziona automaticamente la codifica ottimale.  
- **Flessibilità:** Controllo completo su dimensioni, codifica ECI e formato immagine.  
- **Cross‑platform:** Funziona con applicazioni .NET Framework, .NET Core e .NET 5+.

## Prerequisiti

1. **Ambiente .NET** – Installa l'ultima runtime .NET dal [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode per .NET** – Scarica la libreria dal [website](https://releases.aspose.com/barcode/net/).  

## Importazione degli spazi dei nomi

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Ora che gli spazi dei nomi sono stati importati, procediamo passo‑passo attraverso il codice.

## Passo 1: Imposta il percorso della directory

```csharp
string path = "Your Directory Path";
```

Sostituisci `"Your Directory Path"` con la cartella in cui desideri salvare il PNG generato (o altro formato).

## Passo 2: Crea un codice a barre DataMatrix in modalità Auto

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

L'impostazione `DataMatrixEncodeMode.Auto` consente alla libreria di decidere la migliore codifica per il testo fornito. Sentiti libero di sostituire il testo di esempio con qualsiasi stringa per cui devi **generare barcode image C#**.

## Passo 3: Leggi il codice a barre (leggi DataMatrix barcode C#)

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Questo frammento decodifica l'immagine appena generata e stampa il testo originale nella console, dimostrando un ciclo completo dalla generazione alla lettura.

## Problemi comuni e soluzioni

| Problema | Causa | Correzione |
|----------|-------|------------|
| **Nessun codice a barre rilevato** | Risoluzione dell'immagine troppo bassa | Aumenta `XDimension.Pixels` (es., a 6) |
| **Caratteri spazzatura** | Codifica ECI errata | Imposta `ECIEncoding` in base ai tuoi dati (UTF‑8, ASCII, ecc.) |
| **Eccezione su `ReadBarCodes`** | Bitmap rilasciata prima della lettura | Mantieni l'istanza `Bitmap` viva fino a dopo la lettura |

## Domande frequenti

**D: Cos'è la modalità di codifica DataMatrix “Auto”?**  
R: Consente ad Aspose.BarCode di selezionare automaticamente il metodo di codifica ottimale per i dati forniti, semplificando il processo di **how to generate datamatrix barcode**.

**D: Posso personalizzare le dimensioni del codice a barre generato?**  
R: Sì – regola `generator.Parameters.Barcode.XDimension.Pixels` per modificare la dimensione del modulo.

**D: Aspose.BarCode per .NET è adatto per uso commerciale?**  
R: Assolutamente. Acquista una licenza dal [website](https://purchase.aspose.com/buy).

**D: È disponibile una versione di prova gratuita?**  
R: Sì, puoi provare Aspose.BarCode con una versione di prova gratuita da [this link](https://releases.aspose.com/).

**D: Quali opzioni di codifica sono disponibili per i codici a barre DataMatrix?**  
R: Aspose.BarCode supporta UTF‑8, ASCII e altre codifiche ECI; imposta il valore desiderato tramite `ECIEncoding`.

## Conclusione

Ora disponi di un esempio completo, pronto per la produzione, che **legge DataMatrix barcode C#**, genera il codice a barre in modalità Auto e verifica il risultato—tutto usando Aspose.BarCode per .NET. Sperimenta con testi, dimensioni e impostazioni ECI diversi per adattarli al tuo scenario specifico e consulta la [documentation](https://reference.aspose.com/barcode/net/) ufficiale per personalizzazioni più approfondite.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

---