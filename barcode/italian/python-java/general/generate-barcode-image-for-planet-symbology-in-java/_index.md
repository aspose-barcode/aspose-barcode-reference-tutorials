---
category: general
date: 2026-10-18
description: Genera un'immagine di codice a barre per la simbologia Planet usando
  Java. Impara a creare un codice a barre Planet con dimensioni personalizzate e barre
  vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: it
lastmod: 2026-10-18
og_description: Genera un'immagine del codice a barre per la simbologia Planet in
  Java. Questo tutorial mostra come creare un codice a barre Planet con dimensioni
  personalizzate del codice a barre e barre di contorno.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Genera immagine di codice a barre per la simbologia Planet – Guida Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Genera immagine di codice a barre per la simbologia Planet in Java
url: /it/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genera immagine barcode per la simbologia Planet in Java

Se hai bisogno di **generare un'immagine barcode** per la simbologia Planet, questa guida ti accompagna passo passo nel processo completo. Che tu stia costruendo un sistema di automazione postale o una soluzione di tracciamento personalizzata, imparerai a **creare un barcode Planet** con **dimensioni barcode personalizzate** e barre di contorno (vuote).

L'esempio utilizza la libreria Aspose.BarCode per Java, che fornisce un'API fluida per ogni principale standard di barcode. Non sono necessari strumenti aggiuntivi di elaborazione immagini e il codice funziona su qualsiasi runtime Java 8+.

## Prerequisiti

* Java 8 o versioni successive installato (il tutorial è stato testato con JDK 17).
* Maven o Gradle per gestire le dipendenze.
* Familiarità di base con la sintassi Java e il concetto di barcode.

Se sei nuovo a Maven, puoi creare un progetto semplice con `mvn archetype:generate` e aggiungere la dipendenza Aspose.BarCode mostrata di seguito.

## Aggiungi la dipendenza Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Consiglio:** Blocca il numero di versione per evitare cambiamenti inaspettati che potrebbero rompere il codice quando la libreria viene aggiornata.

## Passo 1: Inizializza il generatore di barcode per la simbologia Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Perché questo passo è importante:**  
`EncodeTypes.PLANET` indica alla libreria di utilizzare la specifica del barcode Planet, comunemente usata per i servizi postali. La stringa di dati `"123456"` è il payload che apparirà nell'immagine generata.

## Passo 2: Imposta dimensioni barcode personalizzate (dimensione X)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Perché questo passo è importante:**  
La *dimensione X* definisce quanto è larga ogni singola barra. Impostandola a **4 pixel**, ottieni un barcode facilmente leggibile dalla maggior parte degli scanner e che si adatta comunque a un'etichetta standard. Modificare questo valore è il modo principale per ottenere **dimensioni barcode personalizzate**.

## Passo 3: Usa barre vuote (contorno) invece di barre solide

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Perché questo passo è importante:**  
`setFilledBars(false)` indica al renderer di disegnare solo i contorni delle barre, lasciando l'interno trasparente. Questo stile è spesso richiesto per i barcode postali dove lo sfondo può contenere altre informazioni stampate.

## Passo 4: Salva l'immagine barcode come PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Perché questo passo è importante:**  
Scegliere `BarCodeImageFormat.Png` ti fornisce un'immagine senza perdita di qualità che preserva i bordi nitidi delle barre di contorno. Il percorso del file può essere qualsiasi directory a cui hai accesso in scrittura; l'esempio utilizza una cartella `output` relativa alla radice del progetto.

### Output previsto

Eseguendo il programma si crea un file simile all'immagine qui sotto:

![Immagine barcode generata per la simbologia Planet](/images/planet-barcode.png){.align-center alt="Immagine barcode generata che mostra un barcode Planet con barre di contorno vuote"}

L'immagine mostra un **barcode Planet** con barre sottili e vuote, corrispondenti esattamente alle dimensioni personalizzate impostate.

## Variazioni comuni e casi limite

| Situazione | Adeguamento |
|------------|-------------|
| **Lunghezza dati diversa** | I barcode Planet supportano fino a 12 caratteri numerici. Modifica di conseguenza il secondo argomento del costruttore. |
| **Risoluzione più alta** | Aumenta la dimensione X (`setPixels`) o imposta `YDimension` per controllare l'altezza delle barre. |
| **Barcode a colori** | Usa `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` per cambiare il colore delle barre. |
| **Salvataggio come SVG** | Sostituisci `BarCodeImageFormat.Png` con `BarCodeImageFormat.Svg` per un output vettoriale. |
| **Esecuzione su Android** | Usa la versione Android‑compatible di Aspose.BarCode per Android e sostituisci i percorsi del file system con `Context.getFilesDir()`. |

> **Attenzione:** Impostare la dimensione X troppo bassa (ad esempio, 1 pixel) può rendere il barcode illeggibile su stampanti a bassa risoluzione. Testa sempre con uno scanner reale dopo aver modificato le dimensioni.

## Codice sorgente completo per copia‑incolla veloce

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Copia il codice in un file chiamato `PlanetBarcodeDemo.java`, posizionalo in `src/main/java/com/example/barcode/`, esegui `mvn compile exec:java` e vedrai il risultato della **generazione dell'immagine barcode** nella cartella `output`.

## Conclusione

Ora sai come **generare un'immagine barcode** per la simbologia Planet in Java, come **creare un barcode Planet** con **dimensioni barcode personalizzate**, e come passare da barre solide a barre vuote per uno stile visivo più pulito. L'esempio completo dimostra ogni chiamata API necessaria, dall'inizializzazione del generatore al salvataggio di un file PNG.

**Passi successivi** – esplora altri tipi di barcode (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) e sperimenta con opzioni immagine aggiuntive come colore di sfondo, margini e impostazioni DPI. Se devi incorporare il barcode in un PDF, combina questo codice con Aspose.PDF per Java per una soluzione end‑to‑end senza interruzioni.

Buon coding!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come creare barcode Planet con barre piene e vuote](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [crea immagine barcode Planet – Guida passo‑a‑passo](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Come generare barcode java: Crea un'immagine barcode esatta](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}