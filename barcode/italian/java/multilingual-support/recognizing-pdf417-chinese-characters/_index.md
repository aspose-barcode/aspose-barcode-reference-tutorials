---
date: 2025-12-25
description: Scopri come estrarre testo da immagini di codici a barre, in particolare
  PDF417 con caratteri cinesi, utilizzando Aspose.BarCode per Java. Segui la nostra
  guida passo‑passo su come leggere i dati del codice a barre in modo efficiente.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Estrai testo dal codice a barre: caratteri cinesi PDF417 in Java'
url: /it/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai testo dal codice a barre: caratteri cinesi PDF417 in Java

## Introduzione

Integrare il riconoscimento dei codici a barre nelle applicazioni Java è una competenza preziosa, soprattutto quando è necessario **estrarre testo dal codice a barre** da immagini che contengono dati multilingue. In questo tutorial, ti guideremo nell'utilizzo di Aspose.BarCode per Java per riconoscere i codici a barre PDF417 con caratteri cinesi. Alla fine, saprai esattamente come leggere i dati del codice a barre e decodificarli in testo leggibile.

## Risposte rapide
- **Quale libreria supporta PDF417 con caratteri cinesi?** Aspose.BarCode for Java.  
- **Quale set di caratteri è necessario per la decodifica cinese?** MS936 (GBK).  
- **È necessaria una licenza per l'uso in produzione?** Sì, è richiesta una licenza commerciale.  
- **Posso eseguirlo su qualsiasi versione di Java?** Funziona con Java 8 e versioni successive.  
- **È disponibile una versione di prova gratuita?** Assolutamente – scaricala dal sito di Aspose.

## Cos'è “estrarre testo dal codice a barre”?

Estrarre testo da un codice a barre significa convertire i dati codificati nuovamente nella loro forma originale leggibile dall'uomo. Per i codici a barre PDF417 che memorizzano caratteri cinesi, ciò comporta anche la selezione della corretta codifica dei caratteri in modo che i byte corrispondano ai glifi appropriati.

## Perché usare Aspose.BarCode per Java?

Aspose.BarCode fornisce un supporto robusto per un'ampia gamma di simbologie di codici a barre, inclusi PDF417, e gestisce set di caratteri complessi fin da subito. Astrae l'elaborazione di immagini a basso livello, permettendoti di concentrarti sulla logica di business anziché sulle complessità della decodifica.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Java Development Kit (JDK)** – è consigliata l'ultima versione.  
2. **Aspose.BarCode for Java** – scaricalo da [qui](https://releases.aspose.com/barcode/java/).  
3. **Un'immagine di codice a barre PDF417** che contenga caratteri cinesi (ad esempio `barcode.png`).

## Importa pacchetti

Nel tuo progetto Java, importa le classi necessarie per lavorare con Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Passo 1: Imposta la directory del documento

Specifica la cartella in cui si trova l'immagine del codice a barre:

```java
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso reale sul tuo computer.

## Passo 2: Carica l'immagine del codice a barre

Crea un'istanza di `BarCodeReader` che punti al file PNG e indichi al lettore di cercare la simbologia PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Passo 3: Leggi il codice a barre

Itera attraverso i risultati di rilevamento, estrai l'array di byte grezzo e decodificalo usando il set di caratteri GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Questo ciclo **estrae testo dal codice a barre** e stampa i caratteri cinesi decodificati sulla console.

## Come leggere un codice a barre con PDF417?

Il codice sopra dimostra **come leggere i dati del codice a barre** passo dopo passo:

1. **Inizializza** il lettore con il corretto `DecodeType`.  
2. **Itera** su ogni `BarCodeResult` restituito.  
3. **Converti** i byte grezzi usando il charset appropriato (`MS936` per il cinese).  

Se il tuo codice a barre contiene altre lingue, basta cambiare il charset con quello corrispondente ai tuoi dati.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| Caratteri illeggibili dopo la decodifica | Verifica di utilizzare il charset corretto (`MS936` per GBK). |
| Nessun codice a barre rilevato | Assicurati che la qualità dell'immagine sia alta e che il codice a barre non sia ruotato; puoi pre‑elaborare l'immagine se necessario. |
| Restituiti risultati multipli | PDF417 può memorizzare più segmenti; itera attraverso tutti i risultati come mostrato. |

## Domande frequenti (FAQ)

### Posso usare Aspose.BarCode per Java in progetti commerciali?
Sì, puoi usare Aspose.BarCode per Java in progetti commerciali. Per i dettagli sulla licenza, visita [qui](https://purchase.aspose.com/buy).

### È disponibile una versione di prova gratuita?
Sì, puoi accedere a una versione di prova gratuita di Aspose.BarCode per Java [qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.BarCode?
Visita il forum di Aspose.BarCode [qui](https://forum.aspose.com/c/barcode/13) per qualsiasi supporto o domanda.

### Posso ottenere una licenza temporanea per scopi di test?
Sì, puoi ottenere una licenza temporanea [qui](https://purchase.aspose.com/temporary-license/).

### Dove posso trovare la documentazione?
La documentazione è disponibile [qui](https://reference.aspose.com/barcode/java/).

**Domande aggiuntive**

**Q: E se la mia immagine del codice a barre è in formato JPEG?**  
A: Il `BarCodeReader` funziona con JPEG, PNG, BMP e altri formati di immagine comuni—basta cambiare l'estensione del file di conseguenza.

**Q: Posso decodificare i codici a barre da uno stream invece che da un file?**  
A: Sì, puoi passare un `InputStream` al costruttore `BarCodeReader` per la decodifica in tempo reale.

**Q: Aspose.BarCode supporta altri set di caratteri?**  
A: Assolutamente. Usa `Charset.forName("<your‑charset>")` per decodificare i byte per UTF‑8, ISO‑8859‑1, ecc.

## Conclusione

Ora hai imparato come **estrarre testo dal codice a barre** dalle immagini, in particolare i codici a barre PDF417 contenenti caratteri cinesi, usando Aspose.BarCode per Java. Questa capacità apre le porte a sistemi di inventario multilingue, automazione dei documenti e altro ancora. Sentiti libero di sperimentare altre simbologie e set di caratteri per ampliare la portata della tua applicazione.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}