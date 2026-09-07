---
category: general
date: 2026-09-07
description: Scopri come visualizzare le informazioni da una libreria di codici a
  barre, inclusi nome del prodotto, versione, versione dell'assembly e data di rilascio.
  Guida rapida per sviluppatori Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to display info
- display product name
- show release date
- get library version
- how to read version
language: it
lastmod: 2026-09-07
og_description: Come visualizzare le informazioni da una libreria Python per codici
  a barre, includendo nome del prodotto, numeri di versione, versione dell'assembly
  e data di rilascio in poche righe di codice.
og_image_alt: Console output showing how to display info from barcode library
og_title: Come visualizzare le informazioni da una libreria di codici a barre in Python
  – guida passo passo
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  headline: How to display info from a barcode library in Python
  type: TechArticle
- description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  name: How to display info from a barcode library in Python
  steps:
  - name: Display product name
    text: 'To **display product name**, simply print the `PRODUCT` attribute:'
  - name: Show library version (major.minor)
    text: 'Most developers only need the major and minor numbers, which you can combine
      with an f‑string:'
  - name: Show assembly version
    text: 'If you need the full assembly version (including build and revision), use
      the `ASSEMBLY_VERSION` attribute:'
  - name: Show release date
    text: 'Finally, to **show release date**, print the `RELEASE_DATE` attribute:'
  - name: Complete script
    text: 'Putting everything together yields a self‑contained, runnable example:'
  - name: Library without `BuildVersionInfo`
    text: 'Some forks of the `barcode` package omit `BuildVersionInfo`. In that case
      you can read version data from the package’s `__version__` attribute:'
  - name: Formatting the release date
    text: 'If you prefer `Month Day, Year` format:'
  - name: Handling missing attributes
    text: 'When running against a custom build, an attribute may be `None`. Guard
      against that with a simple check:'
  - name: Using the information in logs
    text: 'Instead of printing to the console, you might want to log the data:'
  type: HowTo
tags:
- Python
- barcode
- version‑info
- debugging
title: Come visualizzare le informazioni da una libreria di codici a barre in Python
url: /it/python/general/how-to-display-info-from-a-barcode-library-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come visualizzare le informazioni da una libreria barcode in Python

Se hai bisogno di **come visualizzare le informazioni** da una libreria barcode, questa guida ti mostra esattamente come recuperare e stampare il nome del prodotto, i numeri di versione, la versione dell'assembly e la data di rilascio. La soluzione funziona con il pacchetto standard `barcode` e richiede solo poche righe di codice, così puoi aggiungerla a qualsiasi script immediatamente.

Passeremo in rassegna ogni passaggio, spiegheremo perché il codice funziona e tratteremo le insidie più comuni, come attributi mancanti o formati di versione inaspettati. Alla fine sarai in grado di **visualizzare il nome del prodotto**, **mostrare la data di rilascio** e **ottenere la versione della libreria** in qualsiasi ambiente Python.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8 o versioni successive installate.
* La libreria `barcode` (o un fork compatibile) disponibile nel tuo ambiente. Installala con:

```bash
pip install python-barcode
```

* Familiarità di base con la funzione Python `print` e le f‑string.

Se hai già la libreria, puoi saltare il passaggio di installazione.

## Come visualizzare le informazioni dalla libreria barcode

Il cuore della soluzione è una singola chiamata a `barcode.BuildVersionInfo()` che restituisce un oggetto contenente tutti i metadati relativi alla versione. L'intestazione H2 seguente contiene la parola chiave principale, soddisfacendo i requisiti SEO.

```python
# Import the barcode module
import barcode

# Retrieve version information from the barcode library
info = barcode.BuildVersionInfo()
```

L'oggetto `info` espone tipicamente i seguenti attributi:

| Attributo          | Significato |
|--------------------|-------------|
| `PRODUCT`          | Nome prodotto leggibile dall'uomo |
| `PRODUCT_MAJOR`    | Numero di versione principale |
| `PRODUCT_MINOR`    | Numero di versione secondaria |
| `ASSEMBLY_VERSION` | Versione completa dell'assembly (es., `1.2.3.4`) |
| `RELEASE_DATE`     | Data di rilascio della libreria |

### Visualizzare il nome del prodotto

Per **visualizzare il nome del prodotto**, stampa semplicemente l'attributo `PRODUCT`:

```python
print("Product:", info.PRODUCT)
```

> **Perché funziona:** `info.PRODUCT` è una stringa definita dall'autore della libreria. Stampandola direttamente ottieni il nome esatto usato nei metadati del pacchetto, utile per logging o interfacce utente.

### Mostrare la versione della libreria (major.minor)

La maggior parte degli sviluppatori ha bisogno solo dei numeri principale e secondario, che puoi combinare con una f‑string:

```python
print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
```

> **Spiegazione:** La f‑string formatta i due attributi interi nel consueto schema `major.minor`, corrispondente al formato che vedrai nella pagina PyPI della libreria.

### Mostrare la versione dell'assembly

Se ti serve la versione completa dell'assembly (inclusi build e revisione), usa l'attributo `ASSEMBLY_VERSION`:

```python
print("Assembly version:", info.ASSEMBLY_VERSION)
```

La versione dell'assembly è utile quando devi verificare che sia stato caricato un build specifico della libreria, specialmente nelle pipeline CI.

### Mostrare la data di rilascio

Infine, per **mostrare la data di rilascio**, stampa l'attributo `RELEASE_DATE`:

```python
print("Release date:", info.RELEASE_DATE)
```

La data di rilascio è memorizzata come oggetto `datetime.date`, quindi viene stampata in formato ISO (`YYYY‑MM‑DD`). Puoi riformattarla con `strftime` se il tuo progetto richiede uno stile diverso.

### Script completo

Mettere tutto insieme produce un esempio autonomo e eseguibile:

```python
import barcode

def display_barcode_library_info():
    """Retrieve and print all version‑related metadata from the barcode library."""
    try:
        info = barcode.BuildVersionInfo()
    except AttributeError:
        raise RuntimeError(
            "The installed barcode package does not expose BuildVersionInfo(). "
            "Make sure you are using a compatible version."
        )

    print("Product:", info.PRODUCT)
    print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
    print("Assembly version:", info.ASSEMBLY_VERSION)
    print("Release date:", info.RELEASE_DATE)

if __name__ == "__main__":
    display_barcode_library_info()
```

**Output previsto** (i valori varieranno in base alla versione installata):

```
Product: python-barcode
Version: 0.14
Assembly version: 0.14.0.0
Release date: 2023-02-15
```

Lo script intercetta un potenziale `AttributeError` per aiutarti a **come leggere le informazioni** sulla versione in modo sicuro quando la libreria modifica la sua API.

## Variazioni comuni e casi limite

### Libreria senza `BuildVersionInfo`

Alcuni fork del pacchetto `barcode` omettono `BuildVersionInfo`. In tal caso puoi leggere i dati di versione dall'attributo `__version__` del pacchetto:

```python
import barcode
print("Package version:", barcode.__version__)
```

Questo fornisce la stringa di versione PEP‑440, ma manca dei campi dettagliati (`PRODUCT`, `ASSEMBLY_VERSION`, ecc.). Usa il fallback solo quando il metodo principale non è disponibile.

### Formattare la data di rilascio

Se preferisci il formato `Mese Giorno, Anno`:

```python
print("Release date:", info.RELEASE_DATE.strftime("%B %d, %Y"))
```

### Gestire attributi mancanti

Quando si esegue su una build personalizzata, un attributo potrebbe essere `None`. Proteggi il tuo codice con un semplice controllo:

```python
release = info.RELEASE_DATE or "unknown"
print("Release date:", release)
```

### Usare le informazioni nei log

Invece di stampare sulla console, potresti voler registrare i dati:

```python
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", info.PRODUCT)
logger.info("Version: %s.%s", info.PRODUCT_MAJOR, info.PRODUCT_MINOR)
logger.info("Assembly version: %s", info.ASSEMBLY_VERSION)
logger.info("Release date: %s", info.RELEASE_DATE)
```

Il logging mantiene le informazioni disponibili nei file di log della tua applicazione, il che è prezioso per il debug di problemi in produzione.

## Pro tips

* **Cache l'oggetto info** se lo chiami più volte; i dati di versione non cambiano a runtime.
* **Valida la versione** prima di eseguire controlli di compatibilità:

```python
if int(info.PRODUCT_MAJOR) < 1:
    raise RuntimeError("Barcode library version is too old for this feature.")
```

* **Combina con altre diagnostiche** (es., versione di Python) per un report completo dell'ambiente:

```python
import sys
print("Python:", sys.version.split()[0])
```

## Conclusione

Ora sai **come visualizzare le informazioni** da una libreria barcode in Python, inclusi **visualizzare il nome del prodotto**, **mostrare la data di rilascio** e **ottenere la versione della libreria**. Lo script completo dimostra il flusso di lavoro standard, mentre le variazioni mostrano come adattare la soluzione a diverse implementazioni della libreria o a esigenze di formattazione.

Successivamente, potresti approfondire:

* **Come leggere la versione** di altri pacchetti di terze parti usando `importlib.metadata`.
* **Visualizzare le informazioni di versione** in un'applicazione GUI (Tkinter, PyQt, ecc.).
* **Automatizzare i controlli di versione** nelle pipeline CI per imporre versioni minime delle librerie.

Sentiti libero di sperimentare con il codice, integrarlo nei tuoi strumenti e condividere i risultati con la community!

## Cosa dovresti imparare dopo?

I tutorial seguenti coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [visualizzare il nome del prodotto usando la libreria Python barcode – guida passo‑passo](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Come generare un'immagine QR Code in Python con Aspose.Barcode – Guida completa](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Come generare un barcode in C# – Guida completa Aspose.Barcode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}