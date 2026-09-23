---
date: 2026-04-08
description: Scopri come leggere i codici a barre da PDF in Java usando Aspose.BarCode.
  Questa guida mostra anche come generare immagini di codici a barre in Java ed estrarre
  immagini da PDF in Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Riconoscimento dei codici a barre da PDF
second_title: Aspose.BarCode Java API
title: Come leggere il codice a barre da PDF in Java usando Aspose.BarCode
url: /it/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# leggi codice a barre da pdf java

## Introduzione

Benvenuti alla nostra guida passo‑passo su **come leggere un codice a barre da PDF in Java** utilizzando Aspose.BarCode. I codici a barre sono essenziali per l'automazione della cattura dei dati e, con Aspose.BarCode, è possibile rilevarli senza problemi all'interno dei documenti PDF. In questo tutorial vi guideremo attraverso tutto ciò di cui avete bisogno — dall'impostazione delle licenze alla generazione di un'immagine di codice a barre Java, all'aggiunta di essa a un PDF, all'estrazione di immagini da PDF Java e infine alla lettura del codice a barre.

## Risposte rapide
- **Quale libreria è necessaria?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Posso generare un'immagine di codice a barre in Java?** Sì – la classe `BarcodeGenerator` consente di creare immagini PNG/JPEG.  
- **Come vengono estratte le immagini da un PDF?** Usa `PdfExtractor` di Aspose.PDF.  
- **Quale tipo di codice a barre è mostrato?** CODE‑39 (standard).  
- **È necessaria una licenza?** È richiesta una licenza valida di Aspose.BarCode e Aspose.PDF per l'uso in produzione.

## Perché usare Aspose.BarCode per Java?
- **Alta precisione** – supporta decine di simbologie e funziona su immagini a bassa risoluzione.  
- **Nessuna dipendenza esterna** – puro Java, nessuna libreria nativa.  
- **Integrazione completa con PDF** – combinare con Aspose.PDF per leggere o incorporare codici a barre direttamente nei file PDF.

## Prerequisiti

Prima di immergersi nel codice, assicuratevi di avere:

1. **Licenza Aspose.BarCode per Java** – ottenerla da [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Licenza Aspose.PDF** – necessaria per la manipolazione dei PDF; è possibile richiedere una licenza [qui](https://purchase.aspose.com/temporary-license/).  
3. **Libreria Aspose.BarCode** – scaricare l'ultimo JAR da [qui](https://releases.aspose.com/barcode/java/).  

Ora che avete i prerequisiti necessari, importiamo i pacchetti richiesti e iniziamo a codificare.

## Importa pacchetti

Nel vostro progetto Java, aggiungete le importazioni di Aspose.BarCode e Aspose.PDF. Questo blocco è invariato rispetto al tutorial originale:

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

## Passo 1: Genera un'immagine di codice a barre Java

Prima, creiamo un'immagine di codice a barre che inseriremo successivamente in un PDF. Questo dimostra la funzionalità **generate barcode image java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Passo 2: Crea un PDF e aggiungi l'immagine del codice a barre

Successivamente, costruiamo un nuovo documento PDF e inseriamo l'immagine del codice a barre appena generata.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Passo 3: Estrai immagini da PDF Java

Con il PDF pronto, dobbiamo estrarre l'immagine incorporata in modo che il codice a barre possa essere letto. Questo utilizza **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Passo 4: Riconosci il codice a barre dalle immagini estratte

Infine, forniamo ogni immagine estratta a `BarCodeReader` per recuperare il testo codificato.

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

Ripetete questi passaggi secondo necessità, adeguando i nomi dei file e i percorsi alla struttura del vostro progetto.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Nessun codice a barre rilevato** | Qualità dell'immagine troppo bassa o codice a barre troppo piccolo. | Aumentare la risoluzione dell'immagine durante il salvataggio (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` genera un'eccezione** | File PDF non trovato o percorso errato. | Verificare che `strPdfDoc` punti a un file esistente e che l'applicazione abbia i permessi di lettura. |
| **Licenza non applicata** | I componenti Aspose funzionano in modalità di prova, limitando l'output. | Caricare i file di licenza all'inizio del programma: `new License().setLicense("Aspose.BarCode.lic");` e analogamente per Aspose.PDF. |

## Domande frequenti (FAQ)

### D: Posso usare Aspose.BarCode per Java senza licenza?
Sebbene Aspose.BarCode possa essere usato senza licenza, è consigliato ottenerne una per la piena funzionalità e per rispettare i termini di licenza.

### D: Come posso ottenere una licenza temporanea per Aspose.BarCode per Java?
È possibile ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### D: Ci sono limitazioni sui tipi di codice a barre supportati da Aspose.BarCode?
Aspose.BarCode supporta un'ampia gamma di tipi di codici a barre. Consultare la documentazione per l'elenco completo.

### D: È disponibile una versione di prova per Aspose.BarCode per Java?
Sì, è possibile scaricare la versione di prova da [qui](https://releases.aspose.com/).

### D: Dove posso cercare supporto o fare domande su Aspose.BarCode per Java?
Visitate il [forum](https://forum.aspose.com/c/barcode/13) di Aspose.BarCode per supporto e discussioni.

## Conclusione

Congratulazioni! Avete imparato come **leggere un codice a barre da PDF in Java** usando Aspose.BarCode, come **generare un'immagine di codice a barre Java**, e come **estrarre immagini da PDF Java** per ulteriori elaborazioni. Sentitevi liberi di esplorare funzionalità aggiuntive come l'elaborazione batch, la gestione di diverse simbologie di codici a barre o l'integrazione con altri prodotti Aspose. Per dettagli più approfonditi, consultate la [documentazione](https://reference.aspose.com/barcode/java/) ufficiale.

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}