---
category: general
date: 2026-10-28
description: Scopri come creare codetext esteso in Python usando ExtCodetextBuilder.
  Include dati in chiaro e codificati ECI, codice passo‑passo e consigli sulle migliori
  pratiche.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: it
lastmod: 2026-10-28
og_description: Crea codetext esteso in Python con ExtCodetextBuilder. Questo tutorial
  mostra la gestione dei dati plain e codificati ECI, codice completo eseguibile e
  le insidie più comuni.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Crea codetext esteso in Python – guida completa
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Come creare codetext esteso in Python con ExtCodetextBuilder
url: /it/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come creare codetext esteso in Python con ExtCodetextBuilder

Se hai bisogno di **creare codetext esteso** per applicazioni barcode o data‑matrix, questa guida ti mostra esattamente come farlo in Python. Vedrai come combinare testo semplice, aggiungere sezioni ECI (Extended Channel Interpretation) per caratteri Unicode e recuperare una singola stringa formattata correttamente pronta per la codifica.

Il tutorial copre tutto, dall’installazione della libreria necessaria alla gestione di casi limite come valori ECI non supportati. Alla fine avrai un modello riutilizzabile da inserire in qualsiasi progetto che deve **creare codetext esteso**.

## Cosa imparerai

* Il ruolo di `ExtCodetextBuilder` nella costruzione di stringhe a codifica mista.  
* Come **aggiungere codetext semplice** e **aggiungere codetext ECI** in un’unica istanza del builder.  
* Come verificare l’output finale e risolvere i problemi più comuni.  
* Varianti per altri set di caratteri (ad es., ISO‑8859‑1, Shift‑JIS).  

### Prerequisiti

* Python 3.8 o successivo.  
* Il pacchetto `extcodetext` (o una libreria simile che fornisce `ExtCodetextBuilder`). Installalo con:

```bash
pip install extcodetext
```

* Familiarità di base con Unicode e valori ECI – ECI 3 corrisponde a UTF‑8, ECI 4 a ISO‑8859‑1, ecc.

> **Suggerimento professionale:** Tieni a portata di mano una tabella di riferimento dei numeri ECI. Evita così corrispondenze accidentali tra la codifica dichiarata e la sequenza di byte reale.

## Comprendere ExtCodetextBuilder

`ExtCodetextBuilder` è una piccola utility che concatena più frammenti di testo inserendo automaticamente i marcatori ECI richiesti. Un marcatore ECI indica al codificatore barcode a valle quale set di caratteri utilizzare per i byte seguenti. Senza il marcatore, i caratteri non‑ASCII verrebbero interpretati in modo errato.

Il builder funziona in tre fasi semplici:

1. **Create** l’istanza del builder.  
2. **Append** frammenti semplici o codificati con ECI.  
3. **Retrieve** la stringa codetext estesa combinata.

Di seguito esaminiamo ogni fase con codice concreto.

## Passo 1: Crea un’istanza di ExtCodetextBuilder

La prima riga costruisce l’oggetto che conterrà tutti i frammenti. Non è necessaria alcuna configurazione a questo punto.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Perché è importante*: L’instanziazione del builder alloca un buffer interno. Tutte le successive chiamate `add_*` operano su quel buffer, garantendo l’ordine specificato.

## Passo 2: Aggiungi dati semplici (non codificati)

I dati semplici consistono in caratteri che appartengono al set di caratteri predefinito (di solito ASCII). Usa `add_plain_codetext` per questi frammenti.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Spiegazione*: La stringa `"ABC123"` contiene solo caratteri ASCII, quindi non è necessario alcun marcatore ECI. Il metodo aggiunge semplicemente i byte grezzi al buffer interno.

## Passo 3: Aggiungi dati che devono essere preceduti da un ECI

Quando devi incorporare caratteri Unicode—come cirillico, giapponese o emoji—devi indicare al codificatore quale charset usare. Questo si fa con `add_eci_codetext(eci, text)`. Il primo argomento è il valore numerico ECI; il secondo è il testo effettivo.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Perché ECI 3*: Secondo la specifica ISO/IEC 18004, ECI 3 mappa a UTF‑8. Inserendo questo marcatore, il lettore barcode sa di decodificare i byte seguenti come UTF‑8, preservando i caratteri cirillici.

### Gestire altre codifiche

Se ti serve ISO‑8859‑1 (Europa occidentale) useresti `add_eci_codetext(4, "¡Hola!")`. Per Shift‑JIS (giapponese) il valore ECI è 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Verifica sempre che la libreria barcode di destinazione supporti il valore ECI scelto; ECI non supportati provocheranno errori di codifica.

## Passo 4: Recupera la stringa codetext estesa combinata

Dopo aver aggiunto tutti i frammenti, chiama `get_extended_codetext()` per ottenere la stringa finale. Questa stringa include eventuali sequenze di escape ECI necessarie.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Output previsto** (visualizzato come `repr` Python per chiarezza):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Dettaglio*:

* `ABC123` – segmento ASCII semplice.  
* `\x1B\x1D\x03` – sequenza di escape ECI per UTF‑8 (ESC GS 0x03).  
* `Привет` – parola cirillica codificata in UTF‑8.

I byte di escape esatti possono variare a seconda dell’implementazione della libreria, ma l’ordine logico sarà sempre *plain → marcatore ECI → testo Unicode*.

## Esempio completo eseguibile

Mettendo tutto insieme, ecco uno script autonomo che puoi copiare‑incollare in un file chiamato `create_extended_codetext.py` ed eseguire subito.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Eseguendo lo script stampa la stringa combinata, pronta per qualsiasi codificatore barcode che accetti un input di codetext esteso.

## Problemi comuni e come evitarli

| Sintomo | Probabile causa | Correzione |
|---|---|---|
| `UnicodeEncodeError` quando si chiama `add_eci_codetext` | Si fornisce una stringa contenente caratteri non rappresentabili nell’ECI scelto | Verifica che l’ECI corrisponda alla reale codifica della stringa (es., usa ECI 3 per qualsiasi testo UTF‑8). |
| Marcatore ECI mancante nell’output finale | Uso accidentale di `add_plain_codetext` per dati non‑ASCII | Passa a `add_eci_codetext` per qualsiasi carattere fuori dall’intervallo ASCII. |
| Lo scanner barcode mostra caratteri illeggibili | Lo scanner non supporta il valore ECI selezionato | Scegli un ECI universalmente supportato (UTF‑8 è ampiamente supportato) o ricorri a ISO‑8859‑1 se la lingua di destinazione lo consente. |
| `get_extended_codetext` restituisce una stringa vuota | Nessun frammento è stato aggiunto prima della chiamata | Assicurati di eseguire almeno una chiamata `add_*`. |

### Caso limite: stringhe vuote

Chiamare `add_plain_codetext("")` o `add_eci_codetext(3, "")` è innocuo; il builder semplicemente ignora il frammento vuoto. Tuttavia, chiamate vuote ripetute possono generare marcatori ECI inutili. Evita ciò controllando la lunghezza della stringa prima di aggiungerla.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Estendere il pattern per dati dinamici

Nelle applicazioni reali spesso si costruisce il codetext esteso a partire da input utente o da un record di database. Il frammento seguente mostra un ciclo che elabora una lista di tuple `(type, value)`, dove `type` è `"plain"` o `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Questo approccio scala agevolmente: puoi leggere le definizioni dei frammenti da JSON, CSV o da un’API senza modificare la logica di costruzione centrale.

## Testare l’output

Un rapido test unitario garantisce che il builder si comporti come previsto. Usando `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

L’esecuzione di `pytest` dovrebbe passare, confermando che il marcatore ECI appare esattamente dove dovrebbe.

## Concetti correlati da esplorare

* **Librerie di codifica barcode** – ad es., `python-barcode`, binding `zxing`, che accettano direttamente la stringa di codetext esteso.  
* **Riferimento tabella ECI** – un elenco completo dei valori numerici ECI è pubblicato da ISO/IEC 18004 e può essere memorizzato come dizionario Python per il lookup.  
* **Livelli di correzione errori** – quando generi QR code, combina il codetext esteso con il livello di correzione appropriato (L, M, Q, H) per una scansione robusta.

## Conclusione

Ora sai come **creare codetext esteso** in Python usando `ExtCodetextBuilder`. Il processo è semplice:

1. Istanzia il builder.  
2. Aggiungi frammenti semplici e codificati con ECI secondo necessità.  
3. Recupera la stringa finale e passala al tuo generatore barcode.

Seguendo il pattern sopra potrai gestire qualsiasi combinazione di dati ASCII e Unicode, evitare errori di codifica comuni e produrre stringhe pronte per il barcode che funzionano su un’ampia gamma di scanner. Sperimenta con diversi ECI, integra il builder nella tua pipeline dati e avrai una solida base per tutte le tue esigenze di codetext esteso.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}