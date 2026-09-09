---
category: general
date: 2026-07-18
description: Verwenden Sie extcodetextbuilder von Aspose, um QR‑Codes zu erzeugen,
  die einfachen ASCII‑ und UTF‑8‑russischen Text kombinieren. Lernen Sie die QR‑Code‑Generierung
  mit Aspose.Barcode in Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: de
lastmod: 2026-07-18
og_description: Verwenden Sie extcodetextbuilder; Aspose ermöglicht das Mischen von
  Klartext‑ und UTF‑8‑kodierten Fragmenten in einem QR‑Code. Folgen Sie dieser Schritt‑für‑Schritt‑Anleitung
  für Aspose.Barcode in Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: extcodetextbuilder aspose verwenden – QR‑Codes mit gemischtem ECI‑Text erstellen
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
title: 'Verwenden Sie extcodetextbuilder Aspose: QR-Codes mit gemischtem ECI-Text
  generieren'
url: /de/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# extcodetextbuilder aspose verwenden – QR-Codes mit gemischtem ECI-Text erstellen

Haben Sie sich jemals gefragt, wie man **extcodetextbuilder aspose** verwendet, um sowohl einfachen englischen Text als auch kyrillische Zeichen in einen einzigen QR-Code einzubetten? Sie sind nicht allein. Viele Entwickler stoßen auf Probleme, wenn sie ASCII‑ und Nicht‑ASCII‑Daten mischen müssen, insbesondere wenn der Zielscanner korrekte ECI‑Marker (Extended Channel Interpretation) erwartet.  

In diesem Tutorial führen wir Sie Schritt für Schritt durch die Erstellung eines QR-Codes, der „HELLO123“ **und** das russische Wort „Привет“ enthält, und das alles mit der Python‑API von Aspose.Barcode. Am Ende haben Sie ein sofort ausführbares Skript, verstehen, warum jeder Aufruf wichtig ist, und wissen, wie Sie den Prozess für andere Sprachen oder Datenformate anpassen können.

## Was Sie lernen werden

- Wie man **ExtCodetextBuilder** initialisiert und einfache sowie ECI‑kodierte Fragmente hinzufügt.  
- Warum der **ECI‑Kodierungs**‑Wert `3` UTF‑8 entspricht und wie sich das auf das Scannen auswirkt.  
- Die genaue Reihenfolge, um einen **QR‑Code‑Generator** mit Aspose.Barcode einzurichten.  
- Wie man das resultierende Bild speichert und den gemischten Inhalt überprüft.  

**Voraussetzungen** – Sie benötigen Python 3.8+, das `aspose-barcode`‑Paket installiert (`pip install aspose-barcode`) und einen Ordner, in den Sie Bilder schreiben können. Sonst nichts.

---

## extcodetextbuilder aspose verwenden, um gemischten Codetext zu erstellen

Das erste, was wir benötigen, ist eine Instanz von `ExtCodetextBuilder`. Betrachten Sie sie als ein Builder‑Muster, das verschiedene Textteile aneinanderreiht und dabei automatisch die richtigen ECI‑Marker im Hintergrund einfügt.

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

**Warum das wichtig ist:**  
- `add_plain_codetext` behält die Daten unverändert bei, was perfekt für Zahlen oder englische Buchstaben ist.  
- `add_eci_codetext` fügt vor dem übergebenen String ein ECI‑Segment (`[ECI:3]`) ein und teilt jedem konformen Leser mit, dass die folgenden Bytes UTF‑8 sind. Ohne dies würde der Scanner die kyrillischen Bytes als Kauderwelsch interpretieren.

> **Pro Tipp:** Wenn Sie einen anderen Zeichensatz benötigen, ändern Sie den Wert `eci_encoding` gemäß der ECI‑Tabelle (z. B. `26` für ISO‑8859‑1).  

---

## QR‑Code‑Generierung mit Aspose.Barcode initialisieren

Da wir nun einen korrekt formatierten `extended_codetext` haben, können wir ihn an den QR‑Code‑Generator übergeben. Aspose.Barcode abstrahiert die Low‑Level‑Erstellung der QR‑Matrix, sodass Sie sich auf die Daten konzentrieren können.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Was passiert hier?**  
- `BarcodeGenerator()` erstellt ein neues Generator‑Objekt mit Standardeinstellungen (Größe, Auflösung usw.).  
- `set_symbology` teilt der Engine mit, dass wir einen QR‑Code statt z. B. Code128 wollen.  

Wenn Sie ein höheres Fehlerkorrektur‑Level benötigen, können Sie vor dem Zuweisen des Codetextes `qr_generator.parameters.barcode.qr_error_level = ...` aufrufen.

---

## Den erweiterten Codetext dem QR‑Generator zuweisen

Nachdem der Generator bereit ist, besteht der nächste Schritt einfach darin, den zuvor erstellten gemischten String zu übergeben.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Warum nicht `set_codetext` verwenden?**  
`set_codetext` behandelt die Eingabe als Klartext und entfernt alle ECI‑Marker. `set_extended_codetext` bewahrt die Rohbytes, einschließlich des ECI‑Segments, und stellt sicher, dass der Scanner den korrekten Sprachwechsel erkennt.

---

## QR‑Code‑Bild speichern und Ergebnis überprüfen

Abschließend schreiben wir den QR‑Code auf die Festplatte. Aspose.Barcode unterstützt PNG, JPEG, BMP und weitere Formate; PNG ist ein sicheres Standardformat, da es verlustfreie Daten bewahrt.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Sie sollten jetzt eine PNG‑Datei am angegebenen Ort haben. Öffnen Sie sie mit einer beliebigen QR‑Scanner‑App, die ECI unterstützt (die meisten modernen Smartphones tun das). Einmal scannen – Sie sehen „HELLO123“. Noch einmal scannen (oder einen Scanner verwenden, der Rohdaten anzeigt) – Sie erhalten ebenfalls „Привет“. Die beiden Teile erscheinen als ein einziger Payload, genau wie wir ihn erstellt haben.

![Beispiel für use extcodetextbuilder aspose QR-Code, das gemischten ECI‑Text zeigt](YOUR_DIRECTORY/qr_extended.png)

*Bild‑Alt‑Text: Beispiel für use extcodetextbuilder aspose QR-Code, das gemischten ECI‑Text zeigt*

---

## Vollständiges, sofort ausführbares Skript

Wenn wir alles zusammenfügen, hier das komplette Programm, das Sie in eine Datei namens `qr_mixed_eci.py` kopieren können:

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

Führen Sie es aus mit:

```bash
python qr_mixed_eci.py
```

Sie sehen eine Konsolennachricht, die den Speicherort bestätigt, und die PNG‑Datei erscheint genau dort, wo Sie sie abgelegt haben.

---

## Häufige Fragen & Sonderfälle

### Was, wenn mein Scanner den kyrillischen Teil nicht erkennt?

Stellen Sie sicher, dass die Scan‑App ECI‑Unterstützung anbietet. Ältere Hardware könnte das ECI‑Segment ignorieren und die Bytes als ISO‑8859‑1 behandeln, was zu fehlerhaften Zeichen führt.

### Kann ich mehr als zwei Fragmente hinzufügen?

Auf jeden Fall. Rufen Sie `add_plain_codetext` oder `add_eci_codetext` so oft auf, wie Sie benötigen. Der Builder verkettet sie in der Reihenfolge, in der Sie die Methoden aufrufen.

### Wie ändere ich die QR‑Code‑Größe oder die Vordergrundfarbe?

Verwenden Sie das Objekt `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Gibt es eine Möglichkeit, Binärdaten (z. B. eine kleine Datei) zusammen mit Text einzubetten?

Ja. Verwenden Sie `add_binary_codetext` mit einem Byte‑Array und kombinieren Sie es mit einem passenden ECI, falls das Binärmaterial einen bestimmten Zeichensatz darstellt. Der Builder übernimmt die erforderlichen Moduswechsel.

---

## Fazit

Sie wissen jetzt **wie man extcodetextbuilder aspose** verwendet, um QR‑Codes zu erstellen, die nahtlos einfachen ASCII‑ und UTF‑8‑kodierten russischen Text kombinieren. Durch die Nutzung von `ExtCodetextBuilder`, das Setzen der korrekten **ECI‑Kodierung** und das Übergeben des Ergebnisses an einen **Aspose.Barcode QR‑Code‑Generator** erhalten Sie ein einzelnes, standardkonformes Bild, das auf modernen Scannern funktioniert.  

Ab hier können Sie `eci_encoding=3` durch andere Sprachkennungen ersetzen oder mit zusätzlichen Klartext‑Fragmenten experimentieren, um mehrsprachige Payloads zu erstellen. Sie können auch die Optionen von `BarCodeImageFormat` erkunden, um SVG oder PDF auszugeben, falls Sie Vektorgrafiken benötigen.  

Viel Spaß beim Coden und hinterlassen Sie gerne einen Kommentar, falls Sie auf Probleme stoßen – Ihr Feedback hilft, diese Anleitungen noch besser zu machen!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Barcode in Java generieren – Code‑Text setzen mit Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Barcode in .NET (Aspose) erstellen – DataMatrix‑Code‑Text konfigurieren](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec‑Code‑Textkodierung mit Aspose.BarCode für .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}