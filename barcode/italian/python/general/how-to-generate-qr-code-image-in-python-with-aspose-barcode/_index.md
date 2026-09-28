---
category: general
date: 2026-07-15
description: Come generare un'immagine QR code in Python usando Aspose.Barcode. Impara
  passo passo la creazione di QR code con codetext esteso, codifica ECI e supporto
  Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: it
lastmod: 2026-07-15
og_description: Come generare un'immagine di codice QR in Python con Aspose.Barcode.
  Questa guida ti accompagna nella creazione di codici QR utilizzando codetext esteso,
  codifica ECI e caratteri Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Come generare un'immagine QR Code in Python – Tutorial completo di Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Come generare un'immagine QR Code in Python con Aspose.Barcode – Guida completa
url: /it/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come generare un'immagine QR Code in Python con Aspose.Barcode – Guida completa

Ti sei mai chiesto **come generare un'immagine QR code** in Python senza dover cercare tra decine di librerie? Non sei solo. Molti sviluppatori hanno bisogno di un modo affidabile per incorporare testo multilingue — pensa a russo, arabo o emoji — all'interno di un QR code, e le librerie integrate spesso non sono sufficienti.

Ecco la questione: Aspose.Barcode per Python rende tutto sorprendentemente semplice. In questo tutorial percorreremo passo passo le istruzioni, dall'installazione del pacchetto alla creazione di una stringa di codetext esteso che mescola ASCII semplice con Unicode codificato ECI. Alla fine avrai un'immagine QR code pronta all'uso salvata su disco.

## Cosa copre questa guida

- Installazione di **Aspose.Barcode** per Python (compatibile con Python 3.8+)
- Creazione di un **extended codetext** che combina segmenti plain e Unicode
- Utilizzo della **ECI encoding** per rendere correttamente i caratteri russi
- Configurazione del `BarcodeGenerator` per produrre un QR code
- Salvataggio dell'immagine di output in formato PNG
- Suggerimenti, errori comuni e idee per i prossimi passi (come aggiungere loghi o modificare il livello di correzione degli errori)

Non è necessaria alcuna esperienza pregressa con Aspose; basta una configurazione Python di base e la curiosità per i QR code.

---

## Prerequisiti

Prima di immergerci, assicurati di avere:

1. **Python 3.8 o più recente** installato sulla tua macchina.  
2. Un **ambiente virtuale** (opzionale ma consigliato) per mantenere ordinate le dipendenze.  
3. Accesso a **pip** per installare il pacchetto `aspose-barcode`.  
4. Permessi di scrittura su una cartella dove verrà salvato il PNG generato.

Se qualcuno di questi punti ti è sconosciuto, fermati qui e configurali — una volta pronti, il resto è un gioco da ragazzi.

## Passo 1: Installare Aspose.Barcode per Python

Il primo ostacolo è ottenere la libreria. Aspose distribuisce i suoi pacchetti su PyPI, quindi un singolo comando `pip` fa al caso tuo:

```bash
pip install aspose-barcode
```

> **Pro tip:** Se sei all'interno di un ambiente virtuale, manterrai puliti i tuoi site‑packages globali. Se incontri errori di permesso, anteponi `--user` o esegui il comando con `sudo` (anche se quest'ultimo è raramente necessario nei setup moderni).

Dopo che l'installazione è terminata, puoi verificarla con:

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Se la versione viene stampata senza problemi, sei pronto per procedere.

## Passo 2: Creare un'istanza **Extended Codetext Builder**

Aspose.Barcode fornisce la classe `ExtCodetextBuilder` per comporre payload QR complessi. Pensala come un piccolo editor di testo che sa come anteporre i giusti caratteri di controllo per ogni segmento.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Perché usare un builder? Concatenare direttamente byte grezzi è soggetto a errori; il builder garantisce i corretti switch ECI (Extended Channel Interpretation), così il tuo scanner QR può decodificare correttamente ogni lingua.

## Passo 3: Iniziare da zero (Opzionale ma pulito)

Se riutilizzi la stessa istanza del builder, chiamare `clear()` elimina tutti i dati precedenti. È una rete di sicurezza che impedisce a segmenti residui di infiltrarsi nel QR successivo.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Puoi saltare questa riga la prima volta che esegui lo script, ma mantenerla rende il codice idempotente — utile quando incapsuli questa logica in una funzione che potrebbe essere chiamata più volte.

## Passo 4: Aggiungere un segmento Plain (non codificato)

La maggior parte dei QR code inizia con una semplice stringa ASCII — magari un identificatore o un URL. Il metodo `add_plain_codetext` aggiunge esattamente questo, senza alcun marcatore ECI.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

In questo esempio usiamo `"HelloWorld"` come segnaposto. Sostituiscilo con ciò che ti serve — forse un SKU prodotto o un breve messaggio.

## Passo 5: Aggiungere un segmento **ECI‑Encoded** (UTF‑8 = 26)

Ora arriva la parte multilingue. Il valore ECI **26** corrisponde a UTF‑8, lo standard de‑facto per Unicode. Passando `26` insieme a una frase russa, indichiamo allo scanner QR di passare a UTF‑8 prima di leggere i caratteri successivi.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Puoi sostituire `26` con altri valori ECI (ad esempio `27` per ISO‑8859‑1) se ti serve una codifica diversa. Il builder inserirà automaticamente i corretti caratteri di controllo.

## Passo 6: Recuperare il Codetext Esteso combinato

Una volta aggiunti tutti i segmenti, estrai la stringa finale che il generatore QR consumerà. Questa stringa contiene sequenze di controllo invisibili, ma puoi comunque stamparla per il debug.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

L'output della console apparirà confuso (a causa dei byte di controllo incorporati), il che è perfettamente normale. La parte importante è che il builder ha unito correttamente le parti plain e Unicode.

## Passo 7: Configurare il Barcode Generator

Ora passiamo il codetext esteso a `BarcodeGenerator` di Aspose. Imposta la simbologia su `QR` e assegna la stringa combinata a `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Puoi modificare altre proprietà qui — come `resolution`, `error_correction_level` o `foreground_color`. Quelle opzioni sono descritte nella documentazione Aspose, ma per un'immagine di base i valori predefiniti funzionano bene.

## Passo 8: Salvare l'immagine QR Code generata

Infine, scrivi il QR code su disco. Il metodo `save` accetta un percorso file e un formato opzionale; PNG è un valore sicuro di default.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Apri il file `qr_extended.png` con qualsiasi visualizzatore di immagini. Scansionandolo con uno smartphone dovresti vedere due messaggi separati: “HelloWorld” e “Привет”. La maggior parte dei lettori QR moderni gestisce automaticamente lo switch ECI.

## Esempio completo funzionante

Mettendo tutto insieme, ecco lo script completo che puoi copiare‑incollare ed eseguire:

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Output atteso** (console):

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Apri `qr_extended.png` → scansiona → vedrai “HelloWorld” seguito da “Привет”.

## Domande comuni e casi limite

### 1. *E se ho bisogno di più di due segmenti?*

Basta chiamare `add_plain_codetext` o `add_eci_codetext` tutte le volte che desideri. Il builder mantiene l'ordine corretto, così il QR code conterrà ogni segmento nella sequenza in cui li aggiungi.

### 2. *Posso incorporare emoji?*

Sì — le emoji sono semplicemente caratteri Unicode. Usa l'ECI UTF‑8 (valore 26) e passa la stringa emoji, ad esempio `builder.add_eci_codetext(26, "🚀")`. Il QR mostrerà l'emoji razzo su scanner che la supportano.

### 3. *Cosa succede se il QR diventa troppo denso?*

I QR code hanno limiti di versione. Se superi la capacità dati, Aspose aumenterà automaticamente la versione alla successiva dimensione, ma l'immagine potrebbe diventare più grande. Per controllare le dimensioni, puoi abbassare il livello di correzione degli errori:

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Devo preoccuparmi di set di caratteri diversi da UTF‑8?*

Solo se hai sistemi legacy che richiedono una codifica specifica (ad esempio ISO‑8859‑1). In tal caso, sostituisci `26` con il valore ECI appropriato (vedi la tabella ECI di Aspose). Per la maggior parte delle app moderne, UTF‑8 è la scelta più sicura.

### 5. *Come aggiungere un logo al centro?*

Aspose.Barcode supporta `barcode.generator.QRCodeParameters.logo_image`. Carica un'immagine con Pillow (`from PIL import Image`) e assegnala:

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

Il logo verrà sovrapposto mantenendo la scansionabilità (Aspose regola automaticamente le zone quiet).

## Consigli professionali per l'uso in produzione

- **Cache the builder** se generi lo stesso QR più volte; evita di ricostruire la stringa estesa ad ogni esecuzione.  
- **Validate the output** con un test unitario che decodifica il QR (ad es. usando `zxing` o `pyzbar`) per assicurarti che gli switch ECI siano corretti.  
- **Set a deterministic file name** (magari includendo un hash del payload) per evitare di sovrascrivere immagini esistenti.  
- **Mind the licensing**: Aspose.Barcode è software commerciale. La valutazione gratuita funziona per lo sviluppo, ma è necessaria una licenza per il deployment in produzione.

## Prossimi passi e argomenti correlati

Ora che sai **come generare QR code

## Cosa dovresti imparare dopo?

I tutorial seguenti trattano argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}