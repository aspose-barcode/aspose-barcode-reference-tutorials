---
title: Genera codici a barre DataMatrix con Aspose.BarCode per .NET
linktitle: Versioni di DataMatrix
second_title: API Aspose.BarCode .NET
description: Scopri come generare codici a barre DataMatrix in .NET utilizzando Aspose.BarCode per .NET. Dimensioni personalizzate, supporto ECC e altro ancora.
type: docs
weight: 12
url: /it/net/datamatrix-barcode-reading/datamatrix-versions/
---
Se stai cercando una soluzione affidabile per generare codici a barre DataMatrix nelle tue applicazioni .NET, Aspose.BarCode per .NET è la strada da percorrere. In questa guida passo passo ti guideremo attraverso il processo di utilizzo di Aspose.BarCode per .NET per creare codici a barre DataMatrix. Suddivideremo ogni esempio in più passaggi, assicurandoti che tu possa seguirlo facilmente.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:
- Un ambiente di sviluppo con supporto .NET.
-  Una copia di Aspose.BarCode per .NET, da cui puoi scaricare[questo link](https://releases.aspose.com/barcode/net/).
- Conoscenza base di C# e del framework .NET.

Ora esploriamo le versioni di DataMatrix e come generarle utilizzando Aspose.BarCode per .NET.

## Importa spazi dei nomi

In qualsiasi progetto C# è essenziale importare gli spazi dei nomi necessari. Nel caso di Aspose.BarCode, dovrai includere quanto segue:

```csharp
using Aspose.BarCode.Generation;
```

 Questo spazio dei nomi fornisce l'accesso a`BarcodeGenerator` classe, che è fondamentale per generare codici a barre.

Ora suddividiamo l'esempio in più passaggi.

## Passaggio 1: imposta il percorso della directory

Inizia definendo il percorso della directory in cui desideri salvare i codici a barre DataMatrix generati.

```csharp
string path = "Your Directory Path";
```

 Sostituire`"Your Directory Path"` con il percorso effettivo in cui desideri salvare le immagini del codice a barre.

## Passaggio 2: inizializzare il generatore di codici a barre

 Crea un'istanza di`BarcodeGenerator` class e specificare il tipo di codice a barre come`DataMatrix`. Puoi anche fornire i dati che desideri codificare nel codice a barre.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Il codice per generare codici a barre va qui
}
```

## Passaggio 3: configurare le proprietà del codice a barre

È possibile personalizzare varie proprietà del codice a barre DataMatrix, come le sue dimensioni e il tipo ECC (Error Correction Code). Ecco un esempio di impostazione della dimensione X su 4 pixel e scelta di ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Passaggio 4: imposta la versione di DataMatrix e salva

È possibile specificare la versione di DataMatrix impostando il numero di righe e colonne. Dopo aver configurato la versione, salvare l'immagine del codice a barre.

Ad esempio, per creare un codice a barre DataMatrix con 22 righe e 22 colonne utilizzando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Allo stesso modo, puoi generare un codice a barre con parametri diversi modificando la versione e il tipo ECC secondo necessità.

## Passaggio 5: ripetere per altre versioni

È possibile ripetere il passaggio 4 per altre versioni di DataMatrix. Ad esempio, per creare un codice a barre con 12 righe e 64 colonne utilizzando ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Passaggio 6: cambiare tipo di ECC

Se desideri modificare il tipo ECC in Ecc140, puoi farlo aggiornando la proprietà ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Passaggio 7: genera codici a barre con versioni diverse ed ECC

Ripetere il passaggio 4 per altre versioni di DataMatrix e tipi di ECC, salvando ciascun codice a barre con un nome file univoco.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Ora che hai imparato come generare codici a barre DataMatrix utilizzando Aspose.BarCode per .NET, puoi facilmente integrare questa funzionalità nelle tue applicazioni .NET.

## Conclusione

Aspose.BarCode per .NET semplifica il processo di generazione di codici a barre DataMatrix nelle tue applicazioni .NET. Con questa guida passo passo puoi creare codici a barre con diverse versioni e tipi ECC, offrendo flessibilità e personalizzazione per soddisfare le tue esigenze specifiche.

 Se hai domande o hai bisogno di assistenza, non esitare a visitare il[Aspose.BarCode per la documentazione .NET](https://reference.aspose.com/barcode/net/) o controlla il[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) per supporto.

## Domande frequenti

### D1: Cos'è l'ECC nei codici a barre DataMatrix?

R1: L'ECC (Error Correction Code) è un componente vitale dei codici a barre DataMatrix che aiuta a garantire l'integrità dei dati. Diversi livelli di ECC forniscono diversi gradi di correzione degli errori.

### Q2: Posso generare codici a barre DataMatrix con dimensioni personalizzate utilizzando Aspose.BarCode per .NET?

R2: Sì, puoi personalizzare le dimensioni dei codici a barre DataMatrix impostando il numero di righe e colonne come dimostrato nel tutorial.

### Q3: Dove posso scaricare Aspose.BarCode per .NET?

 A3: È possibile scaricare Aspose.BarCode per .NET da[questo link](https://releases.aspose.com/barcode/net/).

### Q4: È disponibile una prova gratuita per Aspose.BarCode per .NET?

 A4: Sì, puoi accedere a una prova gratuita di Aspose.BarCode per .NET[Qui](https://releases.aspose.com/).

### Q5: Come posso ottenere una licenza temporanea per Aspose.BarCode per .NET?

 A5: Per ottenere una licenza temporanea per Aspose.BarCode per .NET, visitare[questo link](https://purchase.aspose.com/temporary-license/).