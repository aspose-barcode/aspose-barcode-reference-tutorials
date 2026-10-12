---
category: general
date: 2026-09-29
description: Visualizza il nome del prodotto in Python mentre stampi la data di rilascio
  e recuperi i dettagli della versione dalla libreria barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: it
lastmod: 2026-09-29
og_description: Mostra il nome del prodotto in Python e impara a stampare la data
  di rilascio, ottenere la versione e mostrare la versione minore con poche righe
  di codice.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Mostra il nome del prodotto e le informazioni sulla versione in Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Visualizza nome del prodotto e informazioni sulla versione in Python
url: /it/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Visualizza il nome del prodotto e le informazioni sulla versione in Python

Se hai bisogno di **visualizzare il nome del prodotto** da una libreria, questa guida ti mostra esattamente come fare. Imparerai anche a **stampare la data di rilascio**, **ottenere la versione** e **mostrare la versione minore** usando codice Python conciso.

Molti sviluppatori integrano funzionalità di scansione o generazione di codici a barre e devono esporre i metadati della libreria agli utenti o ai log. Questo tutorial copre tutto il necessario per recuperare e presentare queste informazioni in modo affidabile.

## Cosa imparerai

* Recupera le informazioni sulla versione dalla libreria `barcode`.  
* **Visualizza il nome del prodotto** insieme ai numeri di versione maggiore e minore.  
* **Stampa la data di rilascio** in un formato leggibile dall'uomo.  
* Gestisci gli attributi mancanti in modo elegante.  

**Prerequisiti**  
* Python 3.8 o superiore.  
* Accesso al pacchetto `barcode` (installalo con `pip install python-barcode` o la libreria che fornisce `BuildVersionInfo`).  

---

## Come visualizzare il nome del prodotto e le informazioni sulla versione in Python

Il primo passo è importare la libreria e chiamare il metodo che restituisce un oggetto version‑info. L'oggetto contiene attributi come `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` e `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Perché funziona**  
`BuildVersionInfo()` restituisce un oggetto leggero i cui attributi sono popolati al momento dell'importazione. Accedere direttamente agli attributi evita I/O aggiuntivo e garantisce che i dati visualizzati corrispondano alla versione della libreria effettivamente utilizzata dal tuo codice.

### Output previsto

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

I valori esatti dipendono dalla versione installata della libreria barcode.

---

## Come ottenere la versione dalla libreria barcode

Se hai bisogno solo dei numeri di versione, puoi omettere la stampa del nome del prodotto e concentrarti sui campi numerici.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Gli attributi `PRODUCT_MAJOR` e `PRODUCT_MINOR` seguono il versionamento semantico, consentendoti di confrontare le versioni programmaticamente.*

---

## Come stampare la data di rilascio

La data di rilascio è memorizzata come stringa nel formato `YYYY‑MM‑DD`. Per presentarla in una locale diversa, convertila prima in un oggetto `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Suggerimento:** Convalida sempre la stringa della data prima di analizzarla per evitare `ValueError` quando la libreria cambia il suo formato.

---

## Mostra la versione minore accanto a quella maggiore

A volte è necessario visualizzare separatamente la versione minore, ad esempio quando si registrano avvisi di compatibilità.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Consiglio professionale:** Usa la versione minore per attivare i flag delle funzionalità:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Gestione degli attributi mancanti (casi limite)

Le versioni più vecchie della libreria barcode potrebbero non esporre tutti gli attributi. Avvolgi l'accesso agli attributi in `getattr` con valori predefiniti sensati.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Questo schema garantisce che il tuo script non vada mai in crash a causa di un campo mancante, rendendolo robusto per pipeline CI che potrebbero essere eseguite su più versioni della libreria.

---

## Esempio completo e eseguibile

Di seguito trovi lo script completo che combina tutte le migliori pratiche: convalida degli attributi, formattazione della data e output chiaro.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Eseguendo questo script su un sistema con la libreria barcode installata si ottiene un output simile all'esempio precedente, ma ora protegge dai campi mancanti e formatta la data in modo gradevole.

---

## Conclusione

Ora sai come **visualizzare il nome del prodotto**, **stampare la data di rilascio**, **ottenere la versione**, **stampare il prodotto** e **mostrare la versione minore** usando un flusso di lavoro Python semplice. L'esempio completo dimostra l'accesso affidabile agli attributi, la gestione delle date e il confronto delle versioni—abilità che puoi riutilizzare per qualsiasi libreria di terze parti che espone oggetti di metadati.

**Passaggi successivi**

* Esplora gli altri metodi di metadati della libreria barcode, come `BuildCommitInfo()`.  
* Integra l'output in un framework di logging (ad esempio, `logging.info`).  
* Confronta le versioni programmaticamente per imporre versioni minime richieste nella tua applicazione.

Sentiti libero di sperimentare con diversi formati di output o di estendere lo script per scrivere le informazioni su un file a scopo di audit. Buon coding!  

![Output del terminale che mostra il nome del prodotto e i dettagli della versione](image.png "Terminal output")


## Cosa dovresti imparare dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [visualizza il nome del prodotto usando la libreria Python barcode – guida passo‑passo](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Come stampare la versione di Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Come generare un codice a barre con Aspose.BarCode in Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}