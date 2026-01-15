---
date: 2026-01-15
description: Scopri come salvare file PNG utilizzando la modalità di codifica DataMatrix
  (C40) con Aspose.BarCode per .NET – un tutorial passo passo sui codici a barre.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: Come salvare PNG usando DataMatrix C40 con Aspose.BarCode
url: /it/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modalità di codifica Master DataMatrix (C40) con Aspose.BarCode per .NET

## Introduzione

Se stai cercando una guida chiara e pratica su **come salvare PNG** mentre generi codici a barre DataMatrix, sei nel posto giusto. Che tu stia costruendo un sistema di inventario, un generatore di etichette di spedizione o qualsiasi soluzione che richieda codici a barre compatti ad alta densità, padroneggiare la modalità di codifica C40 ti offrirà sia efficienza di dimensione sia una rappresentazione dati affidabile. In questo tutorial percorreremo un processo di creazione di **codice a barre passo passo**, dai prerequisiti al risultato finale in PNG, utilizzando Aspose.BarCode per .NET.

## Risposte rapide
- **A cosa si riferisce “how to save png”?** Salvataggio del codice a barre generato come file immagine PNG.  
- **Quale modalità di codifica è trattata?** Codifica DataMatrix C40.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per i test; per la produzione è richiesta una licenza.  
- **Posso eseguirlo su .NET Core?** Sì, Aspose.BarCode supporta .NET Framework e .NET Core.  
- **Quale formato di file viene prodotto?** Immagine PNG (Portable Network Graphics).

## Come salvare PNG con la codifica DataMatrix C40
Il salvataggio del codice a barre come PNG è l'ultimo passaggio dopo aver configurato il generatore. Il metodo `Save` accetta il percorso del file, il nome desiderato e il formato immagine (`BarCodeImageFormat.Png`). Questo garantisce che il codice a barre sia memorizzato in un formato loss‑less compatibile con browser, stampanti e dispositivi mobili.

## Che cos’è la modalità di codifica DataMatrix (C40)?
C40 è un set di caratteri efficiente per dati alfanumerici, che consente di inserire più informazioni in un simbolo DataMatrix più piccolo. È particolarmente utile quando è necessario codificare testo contenente lettere, numeri e un insieme limitato di caratteri speciali.

## Perché usare Aspose.BarCode per .NET?
- **Controllo completo** su dimensioni del codice a barre, correzione errori e modalità di codifica.  
- **Generazione zero‑dependency** – nessun servizio esterno richiesto.  
- **Supporto cross‑platform** per .NET Framework, .NET Core e .NET 5/6+.  

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere quanto segue:

1. **Ambiente di sviluppo .NET** – Visual Studio, Rider o qualsiasi IDE che supporti C#.  
2. **Aspose.BarCode per .NET** – installato tramite NuGet o l’installer ufficiale. Consulta la [documentazione](https://reference.aspose.com/barcode/net/) per i dettagli.  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio con namespace, classi e istruzioni using.  
4. **Cartella con permessi di scrittura** – una directory sul tuo computer dove verrà salvato il PNG.

## Importazione dei namespace necessari

Aggiungi il namespace richiesto all’inizio del tuo file sorgente C# per poter accedere alle classi di generazione del codice a barre:

```csharp
using Aspose.BarCode.Generation;
```

## Generazione del codice a barre passo passo

Di seguito trovi una panoramica **passo passo** del codice a barre. Ogni passaggio è spiegato in termini semplici e i blocchi di codice originali sono mantenuti invariati per comodità di copia‑incolla.

### Passo 1: Definisci il percorso della directory
Imposta la cartella in cui verrà memorizzata l’immagine PNG. Sostituisci il segnaposto con un percorso reale sul tuo computer.

```csharp
string path = "Your Directory Path";
```

### Passo 2: Configura la generazione del codice a barre
Crea un’istanza di `BarcodeGenerator`, specifica `EncodeTypes.DataMatrix` e fornisci i dati da codificare.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Passo 3: Personalizza il codice a barre
Configura la X‑dimension (larghezza in pixel dei moduli) e imposta la modalità di codifica su C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Passo 4: Salva l’immagine del codice a barre
Infine, salva il codice a barre generato come file PNG. Questa è la risposta concreta a **come salvare png** con Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Quando esegui il programma, troverai `DataMatrixEncodeModeC40.png` nella cartella specificata, pronto per essere usato in report, etichette o pagine web.

## Problemi comuni e suggerimenti

- **Percorso non valido** – Verifica che la directory esista e che tu abbia i permessi di scrittura; altrimenti `gen.Save` genererà un’eccezione.  
- **Modalità di codifica errata** – Se devi codificare caratteri al di fuori del set C40, passa a `DataMatrixEncodeMode.Auto` o a un’altra modalità appropriata.  
- **Dimensione immagine** – Regola `XDimension.Pixels` per aumentare o diminuire le dimensioni complessive del codice a barre senza compromettere la leggibilità.

## Domande frequenti

**D: Che cos’è la modalità di codifica DataMatrix (C40)?**  
R: C40 è uno schema di codifica alfanumerico compatto per i simboli DataMatrix, ideale per testi che includono lettere, numeri e un numero limitato di caratteri speciali.

**D: Dove posso trovare la documentazione di Aspose.BarCode per .NET?**  
R: Puoi trovare la documentazione [qui](https://reference.aspose.com/barcode/net/). Fornisce indicazioni dettagliate su tutti i tipi di codice a barre e le opzioni di codifica.

**D: Aspose.BarCode per .NET è compatibile con tutte le versioni di .NET?**  
R: Sì, la libreria supporta un’ampia gamma di versioni .NET, da .NET Framework 4.5+ a .NET 6 e successive.

**D: Posso provare Aspose.BarCode per .NET prima di acquistarlo?**  
R: Sì, puoi esplorare una versione di prova gratuita di Aspose.BarCode per .NET visitando [questo link](https://releases.aspose.com/). Ti permette di testare le funzionalità e le capacità della libreria.

**D: Dove posso ottenere supporto per Aspose.BarCode per .NET?**  
R: Puoi trovare una community di supporto e accedere all’assistenza per Aspose.BarCode per .NET sul [forum Aspose](https://forum.aspose.com/c/barcode/13).

## Conclusione

Seguendo questa guida **passo passo**, ora sai esattamente **come salvare PNG** generati con la codifica DataMatrix C40 usando Aspose.BarCode per .NET. Questo approccio ti offre il controllo totale sull’aspetto, le dimensioni e la rappresentazione dei dati del codice a barre, facilitando l’integrazione di codici a barre di alta qualità in qualsiasi applicazione .NET.

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** Aspose.BarCode 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}