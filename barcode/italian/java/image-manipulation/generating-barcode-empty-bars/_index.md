---
date: 2026-04-12
description: Scopri come creare un codice a barre Code128 con barre vuote in Java
  usando Aspose.BarCode. Questa guida ti mostra come generare rapidamente immagini
  di codici a barre Java.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Generazione di codice a barre con barre vuote
second_title: Aspose.BarCode Java API
title: Come creare un codice a barre Code128 con barre vuote in Java
url: /it/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare un codice a barre Code128 con barre vuote in Java

## Introduzione

Integrare la generazione di barcode nelle applicazioni Java è una necessità frequente, sia che tu stia costruendo sistemi di inventario, piattaforme di ticketing o soluzioni point‑of‑sale. Con **Aspose.BarCode for Java**, puoi **creare immagini di barcode Code128** in poche righe di codice. In questo tutorial vedremo i passaggi per **generare immagini di barcode Java** con barre vuote (non riempite), offrendoti il pieno controllo sullo stile visivo del barcode.

## Risposte rapide
- **Quale libreria?** Aspose.BarCode for Java  
- **Caso d'uso principale?** Creare barcode Code128 con barre vuote per design UI personalizzati  
- **Prerequisiti?** Java JDK 8+, Aspose.BarCode JAR, accesso in scrittura a una cartella per l'immagine di output  
- **Tempo tipico di implementazione?** 5‑10 minuti per un esempio base  
- **Posso personalizzare i colori?** Sì – l'API offre ampie opzioni di styling  

## Cos'è un barcode Code128?

Code128 è una simbologia di barcode lineare ad alta densità che codifica l'intero set di caratteri ASCII. È ampiamente usata in logistica, spedizioni e retail perché può rappresentare dati alfanumerici in modo compatto. Per impostazione predefinita, Aspose.BarCode rende le barre Code128 come rettangoli solidi; impostando la proprietà **FilledBars** a `false` le trasforma in barre vuote (contorno), utile per branding stilistico.

## Perché usare Aspose.BarCode per Java?

- **Set di funzionalità ricco** – supporta oltre 50 tipi di barcode, inclusi QR, DataMatrix e PDF417.  
- **Nessuna dipendenza esterna** – un unico JAR funziona su qualsiasi runtime Java.  
- **Controllo fine** – puoi regolare larghezza delle barre, colori, font e la proprietà `FilledBars`.  
- **Cross‑platform** – funziona su Windows, Linux e macOS senza librerie native.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Ambiente di sviluppo Java** – JDK 8 o successivo installato e `JAVA_HOME` configurato.  
2. **Aspose.BarCode per Java** – scarica l'ultimo JAR dalla [pagina di download](https://releases.aspose.com/barcode/java/).  
3. **Directory dei documenti** – una cartella sul tuo computer dove verrà salvata l'immagine del barcode generato.

## Importare i pacchetti

Nel tuo progetto Java, importa le classi necessarie per lavorare con Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Queste importazioni ti danno accesso al generatore di barcode, all'enumerazione dei formati immagine e alla gestione delle eccezioni.

## Passo 1: Configurare la directory delle risorse

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Sostituisci `"Your Document Directory"` con il percorso assoluto della cartella creata nei prerequisiti. È qui che verrà scritto il file PNG.

## Passo 2: Creare un'istanza del generatore di barcode Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Qui istanziamo `BarcodeGenerator` con la simbologia **CODE_128** e il testo di esempio `"TEXT"`. Questo è un **esempio di generatore di barcode Java** che puoi adattare a qualsiasi stringa tu debba codificare.

## Passo 3: Impostare la proprietà FilledBars su false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Impostando `FilledBars` a `false`, il barcode generato mostrerà barre vuote invece di solide, ottenendo l'effetto visivo desiderato.

## Passo 4: Salvare l'immagine del barcode

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Il metodo `save` scrive il barcode nella directory specificata in formato PNG. Puoi cambiare `BarCodeImageFormat.PNG` in `JPG`, `BMP` o `TIFF` se è necessario un tipo di immagine diverso.

## Casi d'uso comuni

- **Branding personalizzato** – le barre vuote possono essere sovrapposte a pattern o colori di sfondo.  
- **Asset pronti per la stampa** – genera PNG ad alta risoluzione da includere in fatture o etichette di spedizione.  
- **Generazione dinamica** – crea barcode al volo in servizi web o applicazioni desktop.

## Suggerimenti per la risoluzione dei problemi

- **Percorso non valido** – assicurati che `dataDir` termini con un separatore di file (`/` o `\\`) o concatena usando `File.separator`.  
- **Licenza richiesta** – una versione di prova funziona per la valutazione, ma è necessaria una licenza completa per la produzione.  
- **Caratteri non supportati** – Code128 supporta l'intero set ASCII; evita caratteri Unicode a meno che non passi a un'altra simbologia.

## Conclusione

Ora sai come **creare immagini di barcode Code128** con barre vuote usando Aspose.BarCode for Java. Questo approccio semplice ti consente di generare rapidamente grafiche di barcode personalizzabili, sia che tu stia costruendo uno strumento di inventario desktop sia un'API basata su cloud.

## FAQ

### È Aspose.BarCode compatibile con tutti gli ambienti di sviluppo Java?
Sì, Aspose.BarCode è progettato per integrarsi senza problemi con qualsiasi IDE o sistema di build Java, inclusi Maven, Gradle e progetti JAR semplici.

### Posso personalizzare l'aspetto del barcode generato?
Assolutamente! Oltre a `FilledBars`, puoi modificare colori, larghezza delle barre, margini e persino aggiungere testo leggibile dall'uomo usando l'ampia API.

### È disponibile una versione di prova per Aspose.BarCode?
Sì, puoi esplorare le funzionalità di Aspose.BarCode ottenendo una prova gratuita [qui](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.BarCode?
Per qualsiasi domanda o assistenza, visita il [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Dove posso trovare la documentazione dettagliata per Aspose.BarCode?
La documentazione completa è disponibile [qui](https://reference.aspose.com/barcode/java/).

**Domande aggiuntive**

**Q: Come genero un'immagine di barcode in un formato diverso, ad esempio JPEG?**  
A: Cambia il secondo argomento di `save` in `BarCodeImageFormat.JPEG`.

**Q: Posso generare più barcode in un ciclo?**  
A: Sì – istanzia un nuovo `BarcodeGenerator` all'interno del tuo ciclo o riutilizza la stessa istanza con un nuovo `CodeText`.

---

**Last Updated:** 2026-04-12  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}