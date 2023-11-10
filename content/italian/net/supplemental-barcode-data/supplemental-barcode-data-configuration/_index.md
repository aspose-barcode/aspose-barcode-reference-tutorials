---
title: Creazione di dati di codici a barre supplementari con Aspose.BarCode per .NET
linktitle: Configurazione dati codice a barre supplementare
second_title: API Aspose.BarCode .NET
description: Genera dati di codici a barre supplementari con Aspose.BarCode per .NET. Personalizza facilmente i codici a barre EAN-2 e EAN-5. Guida dettagliata per gli sviluppatori .NET.
type: docs
weight: 10
url: /it/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

Nel mondo della generazione e personalizzazione dei codici a barre, Aspose.BarCode per .NET si distingue come uno strumento potente e versatile. Che tu sia uno sviluppatore esperto o abbia appena iniziato, questa guida passo passo ti guiderà attraverso il processo di configurazione di dati di codici a barre supplementari utilizzando Aspose.BarCode per .NET. 

## Prerequisiti

Prima di immergerci nel mondo dei dati supplementari dei codici a barre, assicurati di disporre dei seguenti prerequisiti:

- Un ambiente di sviluppo configurato con Visual Studio o qualsiasi altro strumento di sviluppo .NET.
-  Una copia di Aspose.BarCode per .NET. Se non l'hai già fatto, puoi scaricarlo[Qui](https://releases.aspose.com/barcode/net/).
- Conoscenza base della programmazione C#.
- Una directory in cui è possibile salvare le immagini dei codici a barre generate.

## Importazione di spazi dei nomi

Innanzitutto, assicurati di avere gli spazi dei nomi necessari inclusi nel codice C# per funzionare con Aspose.BarCode per .NET. Importa gli spazi dei nomi richiesti all'inizio del file C#:

```csharp
using Aspose.BarCode.Generation;
```

Ora suddividiamo il processo di configurazione dei dati supplementari del codice a barre in più passaggi.

## Passaggio 1: impostazione del percorso della directory

 Nel codice C#, definisci il percorso della directory in cui desideri salvare le immagini del codice a barre generate. Sostituire`"Your Directory Path"` con il percorso effettivo della directory.

```csharp
string path = "Your Directory Path";
```

## Passaggio 2: creazione di un generatore di codici a barre

 Crea un'istanza di`BarcodeGenerator` specificando il tipo di codice a barre e i dati che desideri codificare. In questo esempio utilizziamo un codice a barre EAN-13 con i dati "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Passaggio 3: personalizzazione delle dimensioni del codice a barre

Imposta le dimensioni del codice a barre, come la dimensione X (la larghezza dell'elemento più piccolo nel codice a barre) e lo spazio supplementare. In questo esempio, impostiamo la dimensione X su 2 pixel e lo spazio supplementare su 20 pixel.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Passaggio 4: configurazione del supplemento EAN-2

Per configurare un codice a barre supplementare EAN-2, impostare i dati supplementari sul valore desiderato. In questo caso lo impostiamo su "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Passaggio 5: salvataggio dell'immagine del codice a barre

Salva l'immagine del codice a barre generata nella directory specificata con un nome significativo. In questo esempio, salviamo il codice a barre supplementare EAN-2 come "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Passaggio 6: configurazione del supplemento EAN-5

 Per configurare un codice a barre supplementare EAN-5, è sufficiente modificare il file`SupplementData` al valore desiderato. Qui lo impostiamo su "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Passaggio 7: salvataggio dell'immagine del codice a barre (EAN-5)

Infine, salva l'immagine del codice a barre supplementare EAN-5 nella directory specificata. In questo caso, lo salviamo come "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Ora hai configurato e generato con successo dati di codici a barre supplementari utilizzando Aspose.BarCode per .NET. È possibile utilizzare questo approccio per creare un'ampia gamma di tipi di codici a barre con diversi dati supplementari.

## Conclusione

Aspose.BarCode per .NET è un potente strumento per la generazione e la personalizzazione di codici a barre. In questa guida, abbiamo seguito passo dopo passo il processo di configurazione e generazione di dati supplementari sui codici a barre. Con i giusti prerequisiti e un po' di codifica, puoi lavorare in modo efficiente con i dati dei codici a barre e soddisfare le tue esigenze specifiche.

 Per ulteriori informazioni e utilizzo avanzato, fare riferimento a[Aspose.BarCode per la documentazione .NET](https://reference.aspose.com/barcode/net/).

## Domande frequenti

### Posso utilizzare Aspose.BarCode per .NET nel mio progetto .NET Core?
Sì, Aspose.BarCode per .NET è compatibile con .NET Core.

### È disponibile una prova gratuita per Aspose.BarCode per .NET?
 Sì, puoi provarlo gratuitamente visitando[questo link](https://releases.aspose.com/).

### Dove posso ottenere una licenza temporanea per Aspose.BarCode per .NET?
 È possibile ottenere una licenza temporanea da[questo link](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode supporta un'ampia gamma di tipi di codici a barre?
Sì, supporta vari tipi di codici a barre, inclusi EAN-13, QR Code, Code 128 e altri.

### Posso personalizzare l'aspetto dei codici a barre generati?
Assolutamente, puoi personalizzare dimensioni, colori e altri aspetti dei codici a barre per soddisfare le tue esigenze.
