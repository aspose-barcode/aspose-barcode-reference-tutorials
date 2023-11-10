---
title: Codifica Databar GS1 unidimensionale
linktitle: Codifica Databar GS1 unidimensionale
second_title: API Aspose.BarCode .NET
description: Impara a creare codici a barre codificati Databar GS1 in .NET utilizzando Aspose.BarCode. Genera codici a barre con facilità. Segui la nostra guida passo passo.
type: docs
weight: 18
url: /it/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

In questo tutorial ti guideremo attraverso il processo di creazione di codici a barre codificati Databar GS1 unidimensionali utilizzando la libreria Aspose.BarCode per .NET. Che tu stia cercando di generare codici a barre con la codifica GS1 o senza, abbiamo la soluzione che fa per te. Questa guida passo passo ti aiuterà a comprendere i prerequisiti, a importare gli spazi dei nomi e a dimostrare ogni esempio per creare facilmente codici a barre codificati Databar GS1.

## Prerequisiti

Prima di immergerci nel codice, assicurati di avere i seguenti prerequisiti:

1.  Aspose.BarCode per .NET: dovresti avere Aspose.BarCode per .NET installato. Se non l'hai già fatto, puoi scaricarlo da[Qui](https://releases.aspose.com/barcode/net/).

2.  Percorso della directory: Sostituisci`"Your Directory Path"` negli esempi di codice con il percorso effettivo in cui desideri salvare le immagini del codice a barre generate.

Ora che hai pronti i prerequisiti necessari, procediamo alla parte di codifica.

## Importazione di spazi dei nomi

Per iniziare, è necessario importare gli spazi dei nomi rilevanti per Aspose.BarCode. Aggiungi le seguenti righe di codice all'inizio del tuo progetto .NET:

```csharp
using Aspose.BarCode;
using System;
```

## Passaggio 1: inizializzare il generatore di codici a barre

Il primo passaggio consiste nell'inizializzare l'oggetto BarcodeGenerator con il tipo di codifica desiderato. In questo caso, stiamo utilizzando la codifica Databar Extended. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Passaggio 2: genera un codice a barre con la codifica GS1

Ora imposteremo il testo del codice con il controllo GS1Encoding e salveremo l'immagine del codice a barre generata. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Passaggio 3: generare un codice a barre con codifica variabile

In questo passaggio, genereremo un codice a barre con testo in codice variabile senza controllo GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Passaggio 4: gestire l'eccezione per il controllo della codifica GS1

Se provi a generare un codice a barre con testo in codice variabile con il controllo GS1Encoding abilitato, verrà generata un'eccezione. Ecco come puoi gestirlo:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Ora hai creato con successo codici a barre codificati Databar GS1 unidimensionali con Aspose.BarCode per .NET. Puoi esplorare e personalizzare ulteriormente la generazione del codice a barre in base ai tuoi requisiti specifici.

## Conclusione

In questo tutorial, abbiamo trattato il processo di generazione di codici a barre codificati Databar GS1 unidimensionali utilizzando Aspose.BarCode per .NET. Abbiamo discusso i prerequisiti, importato gli spazi dei nomi necessari e fornito una guida passo passo per la creazione di codici a barre con codifica variabile e con codifica GS1.

 Con Aspose.BarCode per .NET, la generazione di codici a barre diventa un'attività semplice, offrendo flessibilità e controllo sulle esigenze di creazione di codici a barre. Se riscontri problemi o hai domande, non esitare a visitare il[Documentazione Aspose.BarCode](https://reference.aspose.com/barcode/net/) o cercare aiuto su[Forum di supporto Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Domande frequenti

### 1. Qual è la codifica GS1 nei codici a barre?
La codifica GS1 è uno standard utilizzato nei codici a barre per garantire la corretta struttura e identificazione dei dati. Viene comunemente utilizzato per gli articoli nei settori della vendita al dettaglio, della sanità e della logistica per facilitare il monitoraggio accurato e lo scambio di informazioni.

### 2. Posso personalizzare l'aspetto dei codici a barre generati?
Sì, puoi personalizzare l'aspetto dei codici a barre generati con Aspose.BarCode per .NET. Hai il controllo su vari parametri come dimensione, colore e stile.

### 3. Dove posso trovare risorse e documentazione aggiuntive per Aspose.BarCode?
 È possibile trovare documentazione completa ed esempi su[Documentazione Aspose.BarCode](https://reference.aspose.com/barcode/net/). È una risorsa preziosa per l'apprendimento e la risoluzione dei problemi.

### 4. È disponibile una versione di prova per Aspose.BarCode?
 Sì, puoi ottenere una versione di prova gratuita di Aspose.BarCode per .NET da[Qui](https://releases.aspose.com/).

### 5. Come posso acquistare una licenza per Aspose.BarCode per .NET?
 Per acquistare una licenza per Aspose.BarCode per .NET, visitare il sito[pagina di acquisto](https://purchase.aspose.com/buy) sul sito di Aspose.
