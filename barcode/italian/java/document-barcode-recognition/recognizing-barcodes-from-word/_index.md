---
date: 2025-12-19
description: Scopri come leggere i codici a barre Java da documenti Word usando Aspose.BarCode.
  Questa guida copre la generazione di immagini di codici a barre, l'inserimento di
  esse in Word e l'estrazione delle immagini per la lettura dei codici a barre.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Come leggere i codici a barre Java da documenti Word
url: /it/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come leggere barcode java da documenti Word

## Introduzione

Lavorare con i barcode nelle applicazioni Java è una necessità comune, soprattutto quando tali barcode sono incorporati all'interno di file Microsoft Word. In questo tutorial imparerai **come leggere barcode java** da un documento Word usando Aspose.BarCode per Java. Vedremo come generare un'immagine di barcode, aggiungere il barcode a un file Word, estrarre le immagini dal documento Word e, infine, decodificare il barcode con un esempio di lettore di barcode Java.

## Risposte rapide
- **Quale libreria viene utilizzata?** Aspose.BarCode per Java (con Aspose.Words per la gestione delle immagini)  
- **Posso aggiungere barcode a Word?** Sì – genera l'immagine quindi inseriscila con Aspose.Words  
- **Come estraggo le immagini da Word?** Usa `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Esiste un esempio di lettore di barcode Java?** Il codice nel Passo 3 mostra un esempio completo  
- **Quali sono i prerequisiti?** JDK, Aspose.BarCode per Java, un IDE (Eclipse/IntelliJ)

## Cos'è il riconoscimento di barcode in Java?
Il riconoscimento di barcode in Java si riferisce al processo di rilevamento e decodifica dei simboli barcode da immagini o documenti utilizzando una libreria come Aspose.BarCode. Consente alle applicazioni di leggere automaticamente codici prodotto, ID di inventario o qualsiasi dato codificato senza inserimento manuale.

## Perché leggere barcode java da documenti Word?
Incorporare i barcode direttamente nei file Word è utile per contratti, etichette di spedizione o report dove è necessaria una rappresentazione visiva del codice. Essere in grado di **estrarre immagini da Word** e decodificarle programmaticamente elimina la necessità di scansioni manuali e riduce gli errori.

## Prerequisiti

Prima di iniziare, assicurati di avere:

- **Java Development Kit (JDK)** – un JDK recente installato sulla tua macchina.  
- **Aspose.BarCode per Java** – scarica la libreria dal sito ufficiale [qui](https://releases.aspose.com/barcode/java/).  
- **Integrated Development Environment (IDE)** – come Eclipse o IntelliJ IDEA per scrivere ed eseguire il codice.

## Importare i pacchetti

Nel tuo progetto Java, importa i pacchetti Aspose.BarCode e Aspose.Words necessari:

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

## Passo 1: Generare un'immagine di barcode (generate barcode image java)

Per prima cosa, crea un'immagine di barcode usando Aspose.BarCode. Questa immagine sarà poi **added barcode to word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Passo 2: Inserire l'immagine di barcode in un documento Word (insert image into word)

Ora utilizzeremo Aspose.Words per **insert image into word** e salvare il documento:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Passo 3: Riconoscere i barcode dal documento Word (java barcode reader example)

Infine, estrai ogni immagine dal file Word ed esegui il **java barcode reader example** per decodificare il barcode:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Nota:** Il ciclo sopra dimostra **extract images from word**, salva ogni immagine e poi decodifica il barcode usando lo stesso percorso file immagine. Regola i percorsi (`dataDir`) secondo le esigenze del tuo ambiente.

## Problemi comuni e consigli

- **Discrepanze nei percorsi dei file** – Assicurati che `dataDir` punti a una cartella valida; altrimenti il lettore lancerà una `FileNotFoundException`.  
- **Tipi di barcode non supportati** – L'esempio utilizza `CODE_39_STANDARD`. Se ti servono QR, DataMatrix, ecc., modifica sia `EncodeTypes` sia `DecodeType` di conseguenza.  
- **Prestazioni** – Per documenti di grandi dimensioni, considera di elaborare le immagini con stream paralleli per velocizzare il riconoscimento.

## Domande frequenti (FAQ)

### Q: Posso usare Aspose.BarCode per Java in progetti commerciali?
Sì, Aspose.BarCode per Java è disponibile per uso commerciale. Puoi trovare i dettagli della licenza [qui](https://purchase.aspose.com/buy).

### Q: È disponibile una versione di prova gratuita per Aspose.BarCode per Java?
Sì, puoi esplorare le funzionalità di Aspose.BarCode per Java scaricando la prova gratuita [qui](https://releases.aspose.com/).

### Q: Come ottengo supporto per Aspose.BarCode per Java?
Per qualsiasi assistenza o domanda, visita il forum di Aspose.BarCode [qui](https://forum.aspose.com/c/barcode/13).

### Q: Sono disponibili licenze temporanee per Aspose.BarCode per Java?
Sì, puoi ottenere licenze temporanee [qui](https://purchase.aspose.com/temporary-license/).

### Q: Dove posso trovare la documentazione per Aspose.BarCode per Java?
Consulta la documentazione completa [qui](https://reference.aspose.com/barcode/java/).

## Altre FAQ

**Q: Posso leggere altre simbologie di barcode oltre a Code 39?**  
A: Assolutamente. Basta cambiare `EncodeTypes` durante la generazione e `DecodeType` durante la lettura per corrispondere alla simbologia desiderata (es. `EncodeTypes.QR`, `DecodeType.QR`).

**Q: Questo approccio funziona anche con file .docx?**  
A: Sì. Aspose.Words gestisce sia i formati `.doc` sia `.docx` in modo trasparente; lo stesso codice funziona per entrambi.

**: Come posso migliorare la precisione del riconoscimento per immagini a bassa risoluzione?**  
A: Aumenta i DPI quando salvi l'immagine di barcode (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) o utilizza un formato immagine di qualità superiore come PNG.

---

**Ultimo aggiornamento:** 2025-12-19  
**Testato con:** Aspose.BarCode per Java 24.11 e Aspose.Words per Java 24.11  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}