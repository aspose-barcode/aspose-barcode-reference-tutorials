---
category: general
date: 2026-07-18
description: Usa extcodetextbuilder di Aspose per creare codici QR che combinano testo
  ASCII semplice e testo russo UTF‑8. Impara la generazione di codici QR con Aspose.Barcode
  in Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: it
lastmod: 2026-07-18
og_description: Usa ExtCodeTextBuilder di Aspose per mescolare frammenti di testo
  semplice e codificati in UTF‑8 in un QR Code. Segui questa guida passo‑passo per
  Aspose.Barcode in Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: Usa extcodetextbuilder aspose – Crea codici QR con testo ECI misto
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Usa ExtCodeTextBuilder Aspose: genera codici QR con testo ECI misto'
url: /it/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# usa extcodetextbuilder aspose – Crea QR Code con Testo ECI Misto

Ti sei mai chiesto come **usare extcodetextbuilder aspose** per incorporare sia caratteri inglesi semplici che caratteri cirillici in un unico QR Code? Non sei solo. Molti sviluppatori si trovano in difficoltà quando devono mescolare dati ASCII e non‑ASCII, soprattutto quando lo scanner di destinazione si aspetta i corretti marcatori ECI (Extended Channel Interpretation).

In questo tutorial percorreremo i passaggi esatti per creare un QR Code che contiene “HELLO123” **e** la parola russa “Привет”, il tutto con l'API Python di Aspose.Barcode. Alla fine avrai uno script pronto all'uso, comprenderai perché ogni chiamata è importante e saprai come modificare il processo per altre lingue o formati di dati.

## Cosa Imparerai

- Come **inizializzare ExtCodetextBuilder** e aggiungere frammenti semplici e codificati ECI.  
- Perché il valore di **ECI encoding** `3` corrisponde a UTF‑8 e come ciò influisce sulla scansione.  
- La sequenza esatta per configurare un **generatore di QR Code** con Aspose.Barcode.  
- Come salvare l'immagine risultante e verificare il contenuto misto.  

**Prerequisiti** – è necessario Python 3.8+, il pacchetto `aspose-barcode` installato (`pip install aspose-barcode`) e una cartella in cui poter scrivere le immagini. Nient'altro.

---

## usa extcodetextbuilder aspose per costruire codetext misto

La prima cosa di cui abbiamo bisogno è un'istanza di `ExtCodetextBuilder`. Pensala come un pattern builder che concatena diverse parti di testo inserendo automaticamente i corretti marcatori ECI dietro le quinte.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Perché è importante:**  
- `add_plain_codetext` mantiene i dati così come sono, perfetto per numeri o lettere inglesi.  
- `add_eci_codetext` inserisce un segmento ECI (`[ECI:3]`) prima della stringa fornita, indicando a qualsiasi lettore compatibile che i byte successivi sono UTF‑8. Senza questo, lo scanner interpreterebbe i byte cirillici come spazzatura.

> **Consiglio:** Se ti serve un set di caratteri diverso, cambia il valore `eci_encoding` secondo la tabella ECI (ad esempio, `26` per ISO‑8859‑1).  

---

## Inizializza la generazione di QR Code con Aspose.Barcode

Ora che abbiamo un `extended_codetext` formattato correttamente, possiamo passarlo al generatore di QR Code. Aspose.Barcode astrae la creazione a basso livello della matrice QR, permettendoti di concentrarti sui dati.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Cosa sta succedendo qui?**  
- `BarcodeGenerator()` crea un nuovo oggetto generatore con impostazioni predefinite (dimensione, risoluzione, ecc.).  
- `set_symbology` indica al motore che vogliamo un QR Code anziché, ad esempio, Code128.  

Se ti serve un livello di correzione errori più alto, puoi chiamare `qr_generator.parameters.barcode.qr_error_level = ...` prima di assegnare il codetext.

---

## Assegna il extended codetext al generatore QR

Con il generatore pronto, il passo successivo è semplicemente fornire la stringa mista che abbiamo costruito in precedenza.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Perché non usare `set_codetext`?**  
`set_codetext` tratta l'input come testo semplice, rimuovendo eventuali marcatori ECI. `set_extended_codetext` conserva i byte grezzi, incluso il segmento ECI, garantendo che lo scanner veda il corretto cambio di lingua.

---

## Salva l'immagine del QR Code e verifica il risultato

Infine, scriviamo il QR Code su disco. Aspose.Barcode supporta PNG, JPEG, BMP e altro; PNG è un valore predefinito sicuro perché preserva i dati lossless.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Ora dovresti avere un file PNG nella posizione specificata. Aprilo con qualsiasi app scanner QR che supporti ECI (la maggior parte degli smartphone moderni lo fa). Scansiona una volta – vedrai “HELLO123”. Scansiona di nuovo (o usa uno scanner che mostri i dati grezzi) – otterrai anche “Привет”. Le due parti appaiono come un unico payload, esattamente come lo abbiamo costruito.

![esempio di QR code use extcodetextbuilder aspose che mostra testo ECI misto](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: esempio di QR code use extcodetextbuilder aspose che mostra testo ECI misto*

---

## Script Completo, Pronto‑da‑Eseguire

Mettiamo tutto insieme, ecco il programma completo che puoi copiare‑incollare in un file chiamato `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Eseguilo con:

```bash
python qr_mixed_eci.py
```

Vedrai un messaggio nella console che conferma la posizione di salvataggio, e il PNG apparirà esattamente dove hai indicato.

---

## Domande Frequenti & Casi Limite

### E se il mio scanner non riconosce la parte cirillica?
Assicurati che l'app di scansione dichiari il supporto ECI. L'hardware più vecchio può ignorare il segmento ECI e trattare i byte come ISO‑8859‑1, risultando in caratteri illeggibili.

### Posso aggiungere più di due frammenti?
Assolutamente. Chiama `add_plain_codetext` o `add_eci_codetext` quante volte serve. Il builder li concatenerà nell'ordine in cui invochi i metodi.

### Come modifico la dimensione del QR Code o il colore di primo piano?
Usa l'oggetto `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### È possibile incorporare dati binari (ad es., un piccolo file) insieme al testo?
Sì. Usa `add_binary_codetext` con un array di byte, e abbinalo a un ECI appropriato se il binario rappresenta un set di caratteri specifico. Il builder gestirà i necessari cambi di modalità.

---

## Conclusione

Ora sai **come usare extcodetextbuilder aspose** per creare QR Code che mescolano senza problemi testo ASCII semplice e testo russo codificato in UTF‑8. Utilizzando `ExtCodetextBuilder`, impostando la corretta **ECI encoding** e passando il risultato a un **generatore di QR Code Aspose.Barcode**, ottieni un'unica immagine conforme agli standard che funziona su scanner moderni.

Da qui, prova a sostituire `eci_encoding=3` con altri identificatori di lingua, o sperimenta con ulteriori frammenti semplici per costruire payload multilingue. Potresti anche esplorare le opzioni `BarCodeImageFormat` per generare SVG o PDF se ti servono grafica vettoriale.

Buona programmazione, e sentiti libero di lasciare un commento se incontri problemi—il tuo feedback aiuta a migliorare ulteriormente queste guide!

## Cosa Dovresti Imparare Dopo?

I seguenti tutorial coprono argomenti strettamente correlati che si basano sulle tecniche dimostrate in questa guida. Ogni risorsa include esempi di codice completi e funzionanti con spiegazioni passo‑passo per aiutarti a padroneggiare funzionalità API aggiuntive ed esplorare approcci di implementazione alternativi nei tuoi progetti.

- [Genera Barcode Java - Imposta Testo Codice usando Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Crea barcode aspose .net - Configurazione Testo Codice DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Codifica Testo Aztec Code con Aspose.BarCode per .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}