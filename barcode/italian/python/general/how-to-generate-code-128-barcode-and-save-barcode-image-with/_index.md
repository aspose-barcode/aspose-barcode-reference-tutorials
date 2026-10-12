---
category: general
date: 2026-09-23
description: Scopri come generare un codice a barre Code 128 e salvare l’immagine
  del codice a barre usando Aspose.BarCode in Python – guida passo passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: it
lastmod: 2026-09-23
og_description: Genera un codice a barre Code 128 e salva l’immagine del codice a
  barre con Aspose.BarCode in Python. Segui questo esempio completo per creare, personalizzare
  ed esportare il codice a barre come file PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Genera codice a barre Code 128 e salva l’immagine del codice a barre – Guida
  Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Come generare un codice a barre Code 128 e salvare l’immagine del codice a
  barre con Aspose.BarCode
url: /it/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un codice a barre Code 128 e salvare l'immagine del codice a barre con Aspose.BarCode

Se devi **generare un codice a barre Code 128** e **salvare l'immagine del codice a barre** in un progetto Python, questo tutorial mostra i passaggi esatti. Utilizzando `ExtCodetextBuilder` di Aspose.BarCode puoi incorporare segmenti di testo plain e Unicode in un unico payload, quindi renderizzare il risultato come file PNG.

Vedrai uno script completo e eseguibile, una spiegazione di ogni riga e consigli per le difficoltà più comuni, come la gestione della codifica ECI o la scelta della cartella di output corretta. Nessuna documentazione esterna è necessaria—basta copiare, incollare ed eseguire.

## Prerequisiti

Prima di iniziare, assicurati di avere:

* Python 3.8+ installato.
* Il pacchetto `aspose.barcode` (installalo con `pip install aspose-barcode`).
* Permessi di scrittura nella directory in cui verrà salvato il PNG.

Il codice funziona con qualsiasi simbologia supportata da Aspose.BarCode, ma l’esempio si concentra su **Code 128** perché codifica in modo efficiente dati alfanumerici e supporta set di caratteri estesi.

## Passo 1: Importare le classi richieste

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Perché questo passo?* L’importazione delle classi ti dà accesso al builder per il codetext esteso, al writer che crea l’immagine e all’helper di versione che può essere utile per il debug degli aggiornamenti della libreria.

## Passo 2: Costruire il codetext esteso

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` ti consente di mescolare dati ASCII plain e Unicode in un unico payload del codice a barre. Il byte ECI (Extended Channel Interpretation) `0x03` indica allo scanner che i byte successivi sono codificati in UTF‑8, fondamentale per lingue come russo, cinese o arabo.

## Passo 3: Configurare il barcode writer per Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Impostare `encode_type` su `CODE_128` istruisce il writer a renderizzare un **codice a barre Code 128**. La proprietà `code_text` riceve la stringa estesa costruita nel passo precedente.

## Passo 4: Salvare l’immagine del codice a barre come PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Il metodo `save` scrive il codice a barre su un file. Usare `BarCodeImageFormat.PNG` garantisce compressione loss‑less e ampia compatibilità con applicazioni web e mobile.

## Passo 5 (opzionale): Verificare la versione della libreria Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Conoscere la versione esatta della libreria è utile quando devi segnalare bug o confrontare il comportamento tra diverse release.

## Output previsto

L’esecuzione dello script produce un output console simile a:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Il PNG generato (`extended_codetext.png`) appare così:

![Codice a barre Code 128 generato in Python salvato come immagine PNG](images/code128_extended.png)

*L’immagine mostra un codice a barre Code 128 che codifica sia la stringa ASCII `ABC123` sia la parola russa “Пример”.*

## Domande comuni e gestione dei casi limite

| Domanda | Risposta |
|----------|--------|
| **Posso usare una simbologia diversa?** | Sì. Sostituisci `BarCodeEncodeMode.CODE_128` con qualsiasi altra modalità supportata, ad esempio `QR`, `EAN_13` o `PDF_417`. |
| **Cosa succede se il mio testo Unicode contiene emoji?** | Le emoji sono anch’esse caratteri UTF‑8, quindi la stessa chiamata `add_eci_codetext` funziona. Assicurati che lo scanner di destinazione supporti l’ECI che utilizzi. |
| **Come modifico le dimensioni dell’immagine?** | Imposta `writer.x_dimension` e `writer.bar_height` prima di chiamare `save`. |
| **Quale cartella devo usare per `output_path`?** | Qualsiasi cartella in cui il processo Python abbia permessi di scrittura. Usa `os.makedirs` con `exist_ok=True` per crearla automaticamente. |

## Consigli professionali

* **Evita di hard‑codare i percorsi.** Usa `os.path.join` e `Path` del modulo `pathlib` per garantire compatibilità cross‑platform.
* **Valida il codice a barre.** Dopo il salvataggio, puoi leggere nuovamente l’immagine con `barcode.BarCodeReader` per confermare che il testo codificato corrisponda a `extended_codetext`.
* **Suggerimento sulle prestazioni.** Se generi molti codici a barre in un ciclo, riutilizza una singola istanza di `BarCodeWriter` e aggiorna solo `code_text` ad ogni iterazione.

## Conclusione

Ora sai come **generare un codice a barre Code 128** con dati ASCII e Unicode misti e **salvare l’immagine del codice a barre** come PNG usando Aspose.BarCode in Python. Lo script completo copre la costruzione del codetext esteso, la configurazione del writer, l’esportazione dell’immagine e il controllo della versione della libreria.

Da qui puoi approfondire:

* Aggiungere colori di sfondo/foreground (`writer.back_color`, `writer.fore_color`).
* Incorporare il codice a barre in PDF con `Aspose.PDF`.
* Usare la classe `BarCodeReader` per decodificare l’immagine salvata e verificare automaticamente il contenuto.

Buon coding e sentiti libero di sperimentare con altre simbologie e formati immagine!

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare ulteriori funzionalità dell’API ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}