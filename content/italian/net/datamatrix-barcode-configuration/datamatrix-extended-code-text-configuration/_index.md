---
title: Configurazione del testo del codice DataMatrix con Aspose.BarCode per .NET
linktitle: Configurazione testo codice esteso DataMatrix
second_title: API Aspose.BarCode .NET
description: Impara a configurare il testo del codice esteso DataMatrix utilizzando Aspose.BarCode per .NET. Genera, riconosci e integra codici a barre nelle tue applicazioni .NET.
type: docs
weight: 17
url: /it/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
---
Nel mondo dello sviluppo software, l'integrazione dei codici a barre è diventata una necessità fondamentale per varie applicazioni. Con l'aiuto di librerie come Aspose.BarCode per .NET, puoi generare e riconoscere facilmente i codici a barre nelle tue applicazioni .NET. Questo tutorial ti guiderà attraverso il processo di configurazione del testo in codice esteso DataMatrix utilizzando Aspose.BarCode per .NET. Prima di immergerci nei dettagli, diamo un'occhiata ai prerequisiti per questa guida.

## Prerequisiti

Prima di iniziare, assicurati di avere a disposizione quanto segue:

1. Aspose.BarCode per la libreria .NET
Avrai bisogno di Aspose.BarCode per .NET installato. Se non lo hai già fatto, puoi scaricarlo dal sito[Qui](https://releases.aspose.com/barcode/net/).

2. Un ambiente di sviluppo .NET
Per seguire questo tutorial, dovresti avere un ambiente di sviluppo .NET configurato sul tuo sistema. Puoi utilizzare Visual Studio o qualsiasi altro IDE preferito.

3. Conoscenza di base di C#
Per questo tutorial è essenziale una conoscenza di base della programmazione C#.

Ora che disponi degli strumenti e delle conoscenze necessari, analizziamo il processo di configurazione del testo del codice esteso DataMatrix utilizzando Aspose.BarCode per .NET in semplici istruzioni dettagliate.

## Importa spazi dei nomi

Il primo passo per lavorare con Aspose.BarCode per .NET è importare gli spazi dei nomi richiesti. Aggiungi i seguenti spazi dei nomi al tuo codice:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Questi spazi dei nomi forniscono le classi e i metodi necessari per lavorare con i codici a barre.

## Passaggio 1: configurazione del testo del codice esteso DataMatrix

In questo passaggio ti guideremo attraverso il processo di configurazione del testo in codice esteso DataMatrix.

## Passaggio 2: definire il percorso della directory

 È necessario specificare il percorso della directory in cui si desidera salvare il codice a barre DataMatrix generato. Sostituire`"Your Directory Path"` con il percorso effettivo sul tuo sistema.

```csharp
string path = "Your Directory Path";
```

## Passaggio 3: creare il testo in codice

 Per creare il testo in codice per il codice a barre DataMatrix, utilizzerai il file`DataMatrixExtCodetextBuilder`. Questo builder ti consente di aggiungere vari tipi di testo in codice con codifiche diverse.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Questo codice configura il testo del codice con un mix di codifiche diverse.

## Passaggio 4: genera testo in codice

Dopo aver configurato il testo del codice, generare la stringa del testo del codice DataMatrix.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

## Passaggio 5: generazione del codice a barre DataMatrix

Ora crea il codice a barre DataMatrix utilizzando il testo in codice generato. È inoltre possibile impostare vari parametri per il codice a barre, come la dimensione X e la visualizzazione del testo del codice.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Questo codice genera e salva l'immagine del codice a barre DataMatrix con le impostazioni specificate.

## Passaggio 6: provare a riconoscere

 Per garantire che il codice a barre possa essere riconosciuto, è possibile utilizzare il file`BarCodeReader`classe per leggere il codice a barre.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Questo passaggio convalida il codice a barre generato tentando di riconoscerlo.

Congratulazioni! Hai configurato correttamente il testo del codice esteso DataMatrix utilizzando Aspose.BarCode per .NET. Ora puoi integrare questa funzionalità nelle tue applicazioni .NET.

## Conclusione

In questo tutorial, abbiamo esplorato il processo di configurazione del testo in codice esteso DataMatrix utilizzando Aspose.BarCode per .NET. Abbiamo trattato i prerequisiti, le istruzioni dettagliate e dimostrato come generare e riconoscere il codice a barre. Con questa conoscenza, puoi migliorare le tue applicazioni .NET aggiungendo funzionalità di generazione e riconoscimento di codici a barre.

## Domande frequenti

### Q1: Cos'è Aspose.BarCode per .NET?

A1: Aspose.BarCode per .NET è una potente libreria che consente agli sviluppatori di generare e riconoscere codici a barre nelle applicazioni .NET. Supporta un'ampia gamma di simbologie di codici a barre e offre varie opzioni di personalizzazione.

### Q2: Dove posso trovare la documentazione per Aspose.BarCode per .NET?

A2: È possibile accedere alla documentazione per Aspose.BarCode per .NET[Qui](https://reference.aspose.com/barcode/net/).

### Q3: È disponibile una prova gratuita per Aspose.BarCode per .NET?

 A3: Sì, puoi ottenere una versione di prova gratuita di Aspose.BarCode per .NET[Qui](https://releases.aspose.com/).

### Q4: Come posso ottenere una licenza temporanea per Aspose.BarCode per .NET?

 R4: Se hai bisogno di una licenza temporanea per scopi di test o valutazione, puoi ottenerne una[Qui](https://purchase.aspose.com/temporary-license/).

### Q5: Dove posso ottenere supporto o porre domande su Aspose.BarCode per .NET?

 A5: Per qualsiasi supporto o domanda relativa ad Aspose.BarCode per .NET, è possibile visitare il forum Aspose.BarCode[Qui](https://forum.aspose.com/c/barcode/13).