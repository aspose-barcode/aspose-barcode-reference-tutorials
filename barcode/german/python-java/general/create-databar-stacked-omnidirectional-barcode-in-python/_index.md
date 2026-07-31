---
category: general
date: 2026-07-30
description: Erstellen Sie einen Databar Stacked Omnidirectional‑Barcode in Python.
  Befolgen Sie diese Schritt‑für‑Schritt‑Anleitung, um das Seitenverhältnis, die XDimension
  zu konfigurieren und das PNG mit einem Python‑Barcode‑Generator zu exportieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: de
lastmod: 2026-07-30
og_description: Erstelle einen Databar Stacked Omnidirectional‑Barcode in Python.
  Dieses Tutorial zeigt, wie man XDimension festlegt, das Seitenverhältnis von DataBar
  anpasst und als PNG mit BarCodeImageFormat speichert.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Databar Stacked Omnidirectional Barcode erstellen – Python‑Tutorial
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Erstelle einen gestapelten omnidirektionalen Databar‑Barcode in Python
url: /de/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar Stacked Omnidirectional Barcode in Python erstellen

Haben Sie jemals **databar stacked omnidirectional**-Barcodes in Python erstellen müssen, wussten aber nicht, wo Sie anfangen sollen? Sie sind nicht allein – viele Entwickler stoßen an diese Hürde, wenn sie das erste Mal mit der Klasse `BarcodeGenerator` arbeiten. Die gute Nachricht ist, dass der gesamte Prozess ziemlich unkompliziert ist, sobald Sie die wichtigsten Eigenschaften verstehen.

In diesem Leitfaden gehen wir Schritt für Schritt durch ein vollständiges, ausführbares Beispiel, das einen **python barcode generator** verwendet, um die XDimension festzulegen, das DataBar‑Seitenverhältnis anzupassen und schließlich zwei PNG‑Dateien zu exportieren. Am Ende haben Sie ein solides Verständnis dafür, wie Sie hochwertige stacked omnidirectional‑Symbole für jedes Inventar‑ oder Logistikprojekt erzeugen.

## Was Sie lernen werden

- Wie man einen **databar stacked omnidirectional**‑Generator mit einer GTIN‑14‑Payload instanziiert.  
- Warum die **XDimension Pixelgröße** für die Scan‑Zuverlässigkeit wichtig ist.  
- Der Einfluss des **DataBar Seitenverhältnisses** auf die Zeilenbreite gegenüber der Höhe.  
- Wie man das Ergebnis als **BarCodeImageFormat PNG**‑Datei speichert.  
- Tipps, wie man dasselbe Generator‑Objekt wiederverwendet, um mehrere Varianten zu erzeugen, ohne zusätzlichen Speicherverbrauch.

### Voraussetzungen

- Python 3.8+ (die von uns verwendete Bibliothek ist reines Python, keine kompilierten Wheels erforderlich).  
- Das Paket `barcode-generator` (Installation über `pip install barcode-generator`).  
- Ein Ordner, in den Sie schreiben können – das Skript legt dort zwei PNG‑Bilder ab.

Wenn Sie mit grundlegenden Python‑Importen und objektorientiertem Code vertraut sind, können Sie loslegen.

## Databar Stacked Omnidirectional Barcode – Überblick über die Schritte

Im Folgenden teilen wir den Arbeitsablauf in sechs handliche Schritte auf. Jeder Schritt ist ein eigenständiger Code‑Abschnitt, den Sie in ein REPL oder eine Skriptdatei kopieren können. Experimentieren Sie gern – das Ändern des Seitenverhältnisses oder der XDimension liefert sofort einen anderen visuellen Stil.

---

## Schritt 1: Databar Stacked Omnidirectional Generator erstellen

Das Erste, was wir tun, ist eine **databar stacked omnidirectional**‑Generator‑Instanz zu erstellen und dabei das passende `EncodeTypes`‑Enum sowie den Daten‑String zu übergeben.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Warum das wichtig ist:** Das Flag `EncodeTypes.DatabarStackedOmniDirectional` weist die Bibliothek an, ein stacked omnidirectional‑Symbol zu erzeugen, das die einzige DataBar‑Variante ist, die bis zu 14 Ziffern kodieren kann und dabei aus jedem Winkel lesbar bleibt.

---

## XDimension Pixelgröße konfigurieren

Die **XDimension Pixelgröße** steuert das kleinste Modul (die dünnste schwarze Linie). Ein Wert von `2` Pixel funktioniert in den meisten Bildschirm‑Anzeige‑Szenarien gut.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro‑Tipp:** Wenn Sie den Barcode bei hoher DPI drucken möchten, erhöhen Sie diesen Wert auf 3 oder 4, um unscharfe Kanten zu vermeiden.

---

## DataBar Seitenverhältnis anpassen (15)

Das **DataBar Seitenverhältnis** bestimmt, wie breit jede Zeile im Vergleich zu ihrer Höhe ist. Ein Seitenverhältnis von `15` erzeugt breitere Zeilen, was viele Scanner für schnelle Bewegungsaufnahmen bevorzugen.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Warum 15?** Die offizielle GS1‑Spezifikation empfiehlt ein Verhältnis zwischen 10 und 20 für stacked omnidirectional‑Symbole. Wir wählen `15` als ausgewogenen Standardwert.

---

## Barcode als PNG mit BarCodeImageFormat exportieren

Jetzt, wo der Generator konfiguriert ist, speichern wir das Bild. Das Enum `BarCodeImageFormat.Png` sorgt für verlustfreie Ausgabe, ideal für nachgelagerte Verarbeitung.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Was Sie sehen werden:** Öffnen Sie das resultierende PNG; Sie sollten einen sauberen, hochkontrastierten Barcode mit relativ breiten Zeilen erkennen.

---

## DataBar Seitenverhältnis auf 30 ändern

Manchmal benötigen Sie höhere statt breiterer Zeilen – etwa um ein schmales Etikett zu füllen. Durch das Wechseln des **DataBar Seitenverhältnisses** zu `30` werden die Zeilen höher.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Randfall:** Sehr hohe Verhältnisse (z. B. > 40) können dazu führen, dass der Barcode typische Etikettenhöhen überschreitet. Testen Sie daher vorher an einem echten Drucker.

---

## Barcode erneut mit neuem Seitenverhältnis exportieren

Abschließend verwenden wir dasselbe `barcode_generator`‑Objekt, um ein zweites PNG zu schreiben. Der Generator muss nicht neu erstellt werden – ändern Sie einfach die Eigenschaft und rufen Sie `Save` erneut auf.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Ergebnis:** Sie haben jetzt zwei PNG‑Dateien – eine mit breiten Zeilen (`AR15`) und eine mit hohen Zeilen (`AR30`). Vergleichen Sie sie nebeneinander, um zu entscheiden, welche für Ihre Scanner‑Konfiguration am besten geeignet ist.

---

## Vollständiges funktionierendes Beispiel

Alles zusammengefügt, hier das komplette Skript, das Sie sofort ausführen können. Ersetzen Sie `YOUR_DIRECTORY` durch einen absoluten Pfad auf Ihrem Rechner.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Erwartete Ausgabe** (in Ihrer Konsole):

```
✅ Two PNG files created – AR15 and AR30
```

Und zwei Bilddateien erscheinen im Zielordner, bereit für Scan‑Tests.

---

## Fazit

Wir haben gerade **databar stacked omnidirectional**‑Barcodes in Python erstellt, die **XDimension Pixelgröße** angepasst, mit zwei verschiedenen **DataBar Seitenverhältnissen** experimentiert und die Ergebnisse als **BarCodeImageFormat PNG**‑Dateien exportiert. Der gesamte Workflow passt in ein paar Zeilen, gibt Ihnen jedoch volle Kontrolle über die visuellen Merkmale, die für Scanner am wichtigsten sind.

Was kommt als Nächstes? Tauschen Sie die Payload gegen eine andere GTIN aus, spielen Sie mit Farben, indem Sie das PNG in ein palettenbasiertes Bild konvertieren, oder erzeugen Sie einen PDF‑Report, der beide PNGs nebeneinander einbettet. Die Klasse `BarcodeGenerator` ist flexibel genug, um all diese Szenarien zu bewältigen – also experimentieren Sie gern.

Haben Sie Fragen zu einem konkreten Anwendungsfall oder stoßen Sie auf einen Fehler? Hinterlassen Sie unten einen Kommentar, ich helfe Ihnen gern weiter. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, damit Sie zusätzliche API‑Funktionen meistern und alternative Implementierungsansätze in Ihren eigenen Projekten erkunden können.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}