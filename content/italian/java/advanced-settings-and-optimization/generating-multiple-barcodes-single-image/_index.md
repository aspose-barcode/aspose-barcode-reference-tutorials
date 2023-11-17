---
title: Generazione di più codici a barre su una singola immagine in Java con Aspose.BarCode
linktitle: Generazione di più codici a barre su una singola immagine
second_title: API Java Aspose.BarCode
description: Genera più codici a barre su una singola immagine senza sforzo utilizzando Aspose.BarCode per Java. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 19
url: /it/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## introduzione

Nel dinamico mondo della programmazione Java, la creazione e la gestione efficiente dei codici a barre è fondamentale per varie applicazioni. Aspose.BarCode per Java semplifica questo processo, consentendo agli sviluppatori di generare più codici a barre su una singola immagine senza problemi. Questo tutorial ti guiderà attraverso i passaggi per raggiungere questo obiettivo utilizzando Aspose.BarCode in un ambiente Java.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:

- Conoscenza di base della programmazione Java.
- Java Development Kit (JDK) installato sul tuo sistema.
- Aspose.BarCode per la libreria Java scaricata e configurata. Puoi scaricarlo[Qui](https://releases.aspose.com/barcode/java/).
- Un ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA.

## Importa spazi dei nomi

Nel tuo progetto Java, importa gli spazi dei nomi necessari per accedere alla funzionalità Aspose.BarCode. Aggiungi le seguenti istruzioni di importazione all'inizio della tua classe Java:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Passaggio 1: impostare la directory delle risorse

Definire il percorso della directory delle risorse in cui verranno salvati i codici a barre generati. Questa directory è fondamentale per organizzare e gestire le immagini dei codici a barre.

```java
// Il percorso della directory delle risorse.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Passaggio 2: crea una raccolta di codici a barre

Inizializza una HashMap per memorizzare i dati del codice a barre. Ogni voce nella raccolta rappresenta un codice a barre con il rispettivo tipo di codifica.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Passaggio 3: genera immagini di codici a barre

Scorri la raccolta e genera immagini di codici a barre utilizzando la libreria Aspose.BarCode. Memorizza le immagini in un ArrayList per un'ulteriore elaborazione.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Passaggio 4: crea un'immagine combinata

Determinare la larghezza massima e l'altezza totale delle immagini del codice a barre. Crea un'immagine bufferizzata per combinare singole immagini di codici a barre in un'unica immagine di output.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```
## Passaggio 5: salva il risultato

Salva l'immagine combinata finale in una posizione file specificata.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Conclusione

Congratulazioni! Hai generato con successo più codici a barre su una singola immagine utilizzando Aspose.BarCode per Java. Questa potente libreria semplifica la gestione dei codici a barre, rendendola uno strumento prezioso per gli sviluppatori Java.

## Domande frequenti

### Q1: Posso personalizzare l'aspetto dei singoli codici a barre nell'immagine generata?

A1: Sì, Aspose.BarCode offre ampie opzioni di personalizzazione per l'aspetto del codice a barre, consentendoti di adattare lo stile di ciascun codice a barre alle tue preferenze.

### Q2: Aspose.BarCode è compatibile con diverse simbologie di codici a barre?

A2: Assolutamente! Aspose.BarCode supporta un'ampia gamma di simbologie, tra cui CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 e AZTEC, come dimostrato in questo tutorial.

### Q3: Come posso integrare Aspose.BarCode nel mio progetto Java?

 A3: Scarica semplicemente la libreria Aspose.BarCode per Java da[Qui](https://releases.aspose.com/barcode/java/) e seguire le istruzioni di installazione fornite nella documentazione.

### Q4: Posso utilizzare Aspose.BarCode per applicazioni commerciali?

 A4: Sì, puoi ottenere una licenza da[Qui](https://purchase.aspose.com/buy) utilizzare Aspose.BarCode per scopi commerciali.

### Q5: Sono disponibili opzioni di prova per Aspose.BarCode?

 A5: Certamente! Puoi esplorare le funzionalità di Aspose.BarCode ottenendo una licenza di prova gratuita[Qui](https://releases.aspose.com/).