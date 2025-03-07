---
title: Riconoscimento dei codici a barre da PDF in Java
linktitle: Riconoscimento dei codici a barre da PDF
second_title: API Java Aspose.BarCode
description: Scopri come riconoscere i codici a barre dai PDF in Java utilizzando Aspose.BarCode. Guida passo passo con esempi di codice. Aumenta l'efficienza della gestione dei tuoi dati!
weight: 11
url: /it/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Riconoscimento dei codici a barre da PDF in Java


## introduzione

Benvenuti nella nostra guida passo passo sul riconoscimento dei codici a barre dai PDF utilizzando Aspose.BarCode per Java. I codici a barre svolgono un ruolo cruciale nella gestione e nell'organizzazione dei dati e, con Aspose.BarCode, il processo diventa fluido. In questo tutorial ti guideremo attraverso l'intero processo, dall'impostazione dei prerequisiti necessari all'implementazione del codice per il riconoscimento del codice a barre in un file PDF.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:

1.  Aspose.BarCode per licenza Java: ottenere e configurare una licenza valida per Aspose.BarCode per Java. È possibile acquisire una licenza da[Richiedi l'acquisto](https://purchase.aspose.com/buy).

2.  Licenza Aspose.PDF: inoltre, imposta una licenza per Aspose.PDF, necessaria per lavorare con i file PDF. Puoi richiedere una licenza[Qui](https://purchase.aspose.com/temporary-license/).

3.  Scarica Aspose.BarCode per Java: scarica la libreria Aspose.BarCode da[Qui](https://releases.aspose.com/barcode/java/).

Ora che hai i prerequisiti necessari, procediamo con l'importazione dei pacchetti richiesti e iniziamo il nostro tutorial.

## Importa pacchetti

Nel tuo progetto Java, includi i pacchetti Aspose.BarCode e Aspose.PDF. Ecco uno snippet di codice di esempio per iniziare:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Passaggio 1: genera codice a barre e aggiungi a PDF

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Passaggio 2: crea PDF e aggiungi l'immagine del codice a barre

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Passaggio 3: estrai le immagini dal PDF

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Passaggio 4: riconoscere il codice a barre dalle immagini estratte

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Ripeti questi passaggi secondo necessità, modificando di conseguenza i nomi dei file e i percorsi.

## Conclusione

 Congratulazioni! Hai imparato con successo come riconoscere i codici a barre dai PDF utilizzando Aspose.BarCode per Java. Questo tutorial mirava a fornire una guida completa mantenendo semplicità e chiarezza. Sentiti libero di esplorare ulteriori caratteristiche e funzionalità offerte da Aspose.BarCode nel[documentazione](https://reference.aspose.com/barcode/java/).

## Domande frequenti (FAQ)

### D: Posso utilizzare Aspose.BarCode per Java senza licenza?
Sebbene Aspose.BarCode possa essere utilizzato senza licenza, si consiglia di ottenerne una per la piena funzionalità e di rispettare i termini di licenza.

### D: Come posso ottenere una licenza temporanea per Aspose.BarCode per Java?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### D: Esistono limitazioni sui tipi di codici a barre supportati da Aspose.BarCode?
Aspose.BarCode supporta un'ampia gamma di tipi di codici a barre. Fare riferimento alla documentazione per un elenco completo.

### D: È disponibile una versione di prova per Aspose.BarCode per Java?
 Sì, puoi scaricare la versione di prova da[Qui](https://releases.aspose.com/).

### D: Dove posso chiedere supporto o porre domande su Aspose.BarCode per Java?
 Visita Aspose.BarCode[Forum](https://forum.aspose.com/c/barcode/13) per supporto e discussioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
