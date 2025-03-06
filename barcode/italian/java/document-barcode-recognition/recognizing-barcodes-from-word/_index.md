---
title: Riconoscimento semplice dei codici a barre da documenti Word
linktitle: Riconoscimento dei codici a barre da documenti Word
second_title: API Java Aspose.BarCode
description: Esplora la perfetta integrazione del riconoscimento dei codici a barre nelle tue applicazioni Java con Aspose.BarCode. Segui questo tutorial per riconoscere i codici a barre dai documenti Word.
weight: 12
url: /it/java/document-barcode-recognition/recognizing-barcodes-from-word/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Riconoscimento semplice dei codici a barre da documenti Word


## introduzione

Nel dinamico mondo della programmazione Java, la necessità di lavorare in modo efficiente con i codici a barre è in continua crescita. Riconoscere i codici a barre dai documenti Word è un requisito comune e, fortunatamente, Aspose.BarCode per Java fornisce una soluzione solida. In questo tutorial ti guideremo attraverso il processo di riconoscimento dei codici a barre dai documenti Word utilizzando Aspose.BarCode per Java.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di possedere i seguenti prerequisiti:

- Java Development Kit (JDK): Aspose.BarCode per Java richiede un ambiente di sviluppo Java. Assicurati di avere l'ultimo JDK installato sul tuo sistema.

-  Aspose.BarCode per Java: scarica e installa la libreria Aspose.BarCode per Java. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/barcode/java/).

- Ambiente di sviluppo integrato (IDE): scegli il tuo IDE preferito, come Eclipse o IntelliJ, per seguire gli esempi.

## Importa pacchetti

Nel tuo progetto Java, importa i pacchetti Aspose.BarCode necessari per iniziare:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Passaggio 1: genera l'immagine del codice a barre

Innanzitutto, crea un'immagine del codice a barre utilizzando Aspose.BarCode. Imposta il testo del codice e salva l'immagine:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Passaggio 2: aggiungi immagine al documento Word

Ora, inserisci l'immagine del codice a barre generata in un documento Word utilizzando Aspose.Words:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Passaggio 3: riconoscere i codici a barre dal documento Word

Successivamente, estrai le immagini dal documento Word e riconosci i codici a barre utilizzando Aspose.BarCode:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Estrai l'immagine in un file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Riconosci il codice a barre da questa immagine
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

Ripeti questi passaggi e riconoscerai con successo i codici a barre dai documenti Word utilizzando Aspose.BarCode per Java.

## Conclusione

In conclusione, sfruttando Aspose.BarCode per Java semplifica il processo di riconoscimento dei codici a barre dai documenti Word. Segui i passaggi sopra descritti e integrerai perfettamente il riconoscimento dei codici a barre nelle tue applicazioni Java.

## Domande frequenti (FAQ)

### D: Posso utilizzare Aspose.BarCode per Java in progetti commerciali?
 Sì, Aspose.BarCode per Java è disponibile per uso commerciale. Puoi trovare i dettagli della licenza[Qui](https://purchase.aspose.com/buy).

### D: È disponibile una prova gratuita per Aspose.BarCode per Java?
 Sì, puoi esplorare le funzionalità di Aspose.BarCode per Java scaricando la versione di prova gratuita[Qui](https://releases.aspose.com/).

### D: Come posso ottenere supporto per Aspose.BarCode per Java?
Per qualsiasi assistenza o domanda, visitare il forum Aspose.BarCode[Qui](https://forum.aspose.com/c/barcode/13).

### D: Sono disponibili licenze temporanee per Aspose.BarCode per Java?
 Sì, puoi ottenere licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).

### D: Dove posso trovare la documentazione per Aspose.BarCode per Java?
 Fare riferimento alla documentazione completa[Qui](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
