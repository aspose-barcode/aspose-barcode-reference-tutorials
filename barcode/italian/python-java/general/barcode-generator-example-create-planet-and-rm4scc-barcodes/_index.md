---
category: general
date: 2026-10-24
description: Esempio di generatore di codici a barre che mostra come creare un codice
  a barre Planet e come impostare l'altezza del codice a barre usando Python. Segui
  la guida passo‑passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: it
lastmod: 2026-10-24
og_description: Esempio di generatore di codici a barre che dimostra come creare un
  codice a barre Planet e come impostare l'altezza del codice a barre in Python. Ottieni
  una soluzione completa e eseguibile.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Esempio di generatore di codici a barre – crea codici a barre Planet e RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Esempio di generatore di codici a barre – crea codici a barre Planet e RM4SCC
  con altezza personalizzata
url: /it/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Esempio di generatore di codici a barre – crea codici a barre Planet e RM4SCC con altezza personalizzata

Se stai cercando un **barcode generator example**, questa guida ti fornisce una soluzione completa, pronta‑all'uso. Vedrai **come creare un barcode Planet** immagini, imparerai **come impostare l'altezza del barcode** e comprenderai le piccole differenze tra il dimensionamento automatico e manuale.

Il tutorial percorre due scenari realistici: un barcode Planet che utilizza l'altezza predefinita (auto) e un barcode RM4SCC in cui l'altezza è forzata a 100 px. Alla fine potrai generare file PNG per qualsiasi tipo di barcode supportato con una singola API coerente.

## Prerequisiti

* Python 3.8 o versioni successive installato.
* Il pacchetto `aspose-barcode` (o qualsiasi libreria che fornisce `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`). Installalo con  

  ```bash
  pip install aspose-barcode
  ```
* Permesso di scrittura su una cartella dove verranno salvati i file PNG.

Non sono richieste dipendenze di sistema aggiuntive.

## Panoramica della soluzione

Il nucleo del **barcode generator example** consiste in tre passaggi riutilizzabili:

1. **Instantiate** un `BarcodeGenerator` con il valore desiderato di `EncodeTypes` e la stringa di dati.
2. **Configure** la X‑dimension (larghezza del modulo) e, se necessario, l'altezza del barcode.
3. **Save** l'immagine su disco in formato PNG.

Entrambi gli esempi condividono i passaggi 1 e 3; solo il passaggio 2 differisce perché il barcode Planet si affida al calcolo automatico dell'altezza della libreria, mentre il barcode RM4SCC dimostra **how to set barcode height** manualmente.

Di seguito è riportato un diagramma ad alto livello che illustra il flusso:

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Alt text: Esempio di generatore di codici a barre che mostra i codici Planet e RM4SCC con altezze diverse.*

## Come creare un barcode Planet – altezza automatica

Il barcode Planet fa parte della famiglia postale utilizzata da molti servizi postali nazionali. Nella maggior parte dei casi lasci che sia l'SDK a decidere l'altezza, il che mantiene le proporzioni visive corrette per lunghezze di dati variabili.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Perché funziona**

- `EncodeTypes.Planet` indica alla libreria di utilizzare la simbologia Planet.
- Impostare `x_dimension.pixels` a 4 assegna a ogni modulo una larghezza di 4 px, valore predefinito comune per le etichette stampate.
- Non viene impostata un'altezza esplicita; l'SDK calcola l'altezza ottimale in base ai dati e alla X‑dimension, motivo per cui questo è il **barcode generator example** più semplice per i codici postali.

**Risultato atteso**

Un file PNG 2‑D chiamato `PostalPlanetBarHeightAuto.png` che contiene un nitido barcode Planet. L'altezza sarà circa 30 px (a seconda della versione della libreria) e la larghezza sarà 4 px × numero di moduli.

## Come impostare l'altezza del barcode – esempio RM4SCC personalizzato

RM4SCC è un altro barcode postale che spesso richiede un'altezza fissa per corrispondere ai modelli di etichetta. Questa parte del tutorial mostra **how to set barcode height** a un conteggio di pixel preciso.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Perché funziona**

- `EncodeTypes.RM4SCC` seleziona la simbologia RM4SCC.
- La X‑dimension rimane a 4 px per mantenere la dimensione del modulo coerente tra entrambi i barcode.
- `bar_height.pixels = 100` forza il barcode ad essere esattamente 100 px in altezza, sovrascrivendo il calcolo automatico. Questo è il modo consigliato **how to set barcode height** quando il tuo layout richiede una dimensione specifica.

**Risultato atteso**

Un file PNG chiamato `PostalRM4SCCBarHeight100Pixels.png` che mostra un barcode RM4SCC alto. La larghezza è ancora determinata dalla X‑dimension, mentre l'altezza è fissata a 100 px, rendendolo adatto per stampanti di etichette ad alta risoluzione.

## Script completo – combina entrambi gli esempi

Se preferisci uno script unico che genera entrambe le immagini, copia il seguente codice in `generate_barcodes.py` ed eseguilo.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Spiegazione dello script**

- Due funzioni di supporto mantengono il codice DRY (Don’t Repeat Yourself) e facilitano l'estensione dello script per altre simbologie.
- La guardia `if __name__ == "__main__":` consente di importare il file come modulo senza eseguire la logica di generazione, utile per i test unitari.
- Tutti i parametri (stringa di dati, X‑dimension, altezza) sono espliciti, quindi lo script funge da riferimento **barcode generator example** per progetti futuri.

## Domande comuni e casi limite

| Question | Answer |
|----------|--------|
| *E se ho bisogno di una X‑dimension diversa?* | Modifica `x_dimension.pixels` con la larghezza del modulo desiderata. Valori più grandi aumentano la dimensione complessiva del barcode proporzionalmente. |
| *Posso generare altri formati immagine?* | Sì. Sostituisci `BarCodeImageFormat.Png` con `Jpg`, `Bmp` o `Gif` a seconda dell'enumerazione della libreria. |
| *Cosa succede se la stringa di dati contiene caratteri non validi?* | Il generatore lancia un `ArgumentException`. Convalida i dati rispetto al set di caratteri della simbologia prima di chiamare il costruttore. |
| *È possibile impostare un'altezza minima mantenendo il ridimensionamento automatico?* | Usa `gen.parameters.barcode.bar_height.min_pixels = <value>` (se l'SDK espone una proprietà `min_pixels`). Questo impedisce al barcode di ridursi al di sotto di una dimensione leggibile. |
| *Devo liberare le risorse del generatore?* | La classe `BarcodeGenerator` implementa `IDisposable` in .NET; in Python il garbage collector se ne occupa, ma puoi chiamare `gen.dispose()` se crei molte istanze in un ciclo. |

## Consigli per l'uso in produzione

- **Pro tip:** Conserva i valori di X‑dimension e altezza in un file di configurazione così da poterli modificare senza ricompilare.
- **Watch out for:** Usare un'altezza troppo piccola per la simbologia selezionata; gli scanner potrebbero non leggere il barcode.
- **Performance note:** Generare un grande batch di barcode è più veloce quando riutilizzi una singola istanza di `BarcodeGenerator` e cambi solo la proprietà `code_text` tra i salvataggi.

## Conclusione

Questo **barcode generator example** dimostra sia **how to create planet barcode** immagini con dimensionamento automatico sia **how to set barcode height** manualmente per i codici RM4SCC. Seguendo la guida passo‑passo potrai integrare la creazione di barcode in qualsiasi applicazione Python, personalizzare le dimensioni e produrre file PNG pronti per la stampa o la visualizzazione digitale.

### Prossimi passi

- Esplora simbologie aggiuntive come `EncodeTypes.Postnet` o `EncodeTypes.Code128` – si applica lo stesso schema.
- Sperimenta con **how to set barcode height** per codici QR o simboli DataMatrix; la maggior parte delle librerie espone una proprietà `bar_height` simile.
- Combina il generatore con una libreria PDF per incorporare i barcode direttamente in fatture o etichette di spedizione.

Sentiti libero di adattare lo script, condividere i tuoi risultati e farci sapere quali tipi di barcode aggiungerai prossimamente!

## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Come salvare PNG da un barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Come creare PNG di barcode Planet con Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Come usare un generatore di barcode C# per creare un barcode Planet](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}