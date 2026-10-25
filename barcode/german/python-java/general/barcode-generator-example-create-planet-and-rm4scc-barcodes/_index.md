---
category: general
date: 2026-10-24
description: Barcode‑Generator‑Beispiel, das zeigt, wie man einen Planet‑Barcode erstellt
  und die Barcode‑Höhe mit Python einstellt. Folgen Sie der Schritt‑für‑Schritt‑Anleitung.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: de
lastmod: 2026-10-24
og_description: Barcode‑Generator‑Beispiel, das zeigt, wie man einen Planet‑Barcode
  erstellt und die Barcode‑Höhe in Python festlegt. Erhalten Sie eine vollständige,
  ausführbare Lösung.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Barcode-Generator‑Beispiel – Planet‑ und RM4SCC‑Barcodes erstellen
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
title: Barcode‑Generator‑Beispiel – Planet‑ und RM4SCC‑Barcodes mit benutzerdefinierter
  Höhe erstellen
url: /de/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑Generator‑Beispiel – Planet‑ und RM4SCC‑Barcodes mit benutzerdefinierter Höhe erstellen

Wenn Sie nach einem **barcode generator example** suchen, bietet Ihnen dieser Leitfaden eine komplette, sofort einsatzbereite Lösung. Sie sehen **wie man Planet‑Barcode**‑Bilder erstellt, lernen **wie man die Barcode‑Höhe einstellt** und verstehen die kleinen Unterschiede zwischen automatischer und manueller Größenbestimmung.

Das Tutorial führt Sie durch zwei realistische Szenarien: einen Planet‑Barcode, der die Standard‑(Auto‑)Höhe verwendet, und einen RM4SCC‑Barcode, bei dem die Höhe auf 100 px erzwungen wird. Am Ende können Sie PNG‑Dateien für jeden unterstützten Barcode‑Typ mit einer einzigen, konsistenten API erzeugen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* Python 3.8 oder neuer installiert.
* Das `aspose-barcode`‑Paket (oder eine Bibliothek, die `BarcodeGenerator`, `EncodeTypes` und `BarCodeImageFormat` bereitstellt). Installieren Sie es mit  

  ```bash
  pip install aspose-barcode
  ```
* Schreibrechte für einen Ordner, in dem die PNG‑Dateien gespeichert werden.

Weitere Systemabhängigkeiten sind nicht erforderlich.

## Übersicht der Lösung

Der Kern des **barcode generator example** besteht aus drei wiederverwendbaren Schritten:

1. **Instanziieren** Sie einen `BarcodeGenerator` mit dem gewünschten `EncodeTypes`‑Wert und dem Daten‑String.
2. **Konfigurieren** Sie die X‑Dimension (Modulbreite) und, falls nötig, die Barcode‑Höhe.
3. **Speichern** Sie das Bild im PNG‑Format auf der Festplatte.

Beide Beispiele teilen die Schritte 1 und 3; nur Schritt 2 unterscheidet sich, weil der Planet‑Barcode die automatische Höhenberechnung der Bibliothek nutzt, während der RM4SCC‑Barcode **wie man die Barcode‑Höhe einstellt** manuell demonstriert.

Unten finden Sie ein hochrangiges Diagramm, das den Ablauf veranschaulicht:

![Barcode‑Generator‑Beispiel zeigt Planet‑ und RM4SCC‑Barcodes mit unterschiedlichen Höhen.](barcode-example.png)

*Alt‑Text: Barcode‑Generator‑Beispiel zeigt Planet‑ und RM4SCC‑Barcodes mit unterschiedlichen Höhen.*

## Wie man Planet‑Barcode erstellt – automatische Höhe

Der Planet‑Barcode ist Teil der Postfamilie, die von vielen nationalen Postdiensten verwendet wird. In den meisten Fällen lassen Sie das SDK die Höhe bestimmen, wodurch die visuellen Proportionen für unterschiedliche Datenlängen korrekt bleiben.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Warum das funktioniert**

* `EncodeTypes.Planet` weist die Bibliothek an, die Planet‑Symbologie zu verwenden.
* Das Setzen von `x_dimension.pixels` auf 4 gibt jedem Modul eine Breite von 4 px, was ein gängiger Standard für gedruckte Etiketten ist.
* Es wird keine explizite Höhe festgelegt; das SDK berechnet die optimale Höhe basierend auf den Daten und der X‑Dimension, weshalb dies das einfachste **barcode generator example** für Postcodes ist.

**Erwartetes Ergebnis**

Eine 2‑D‑PNG‑Datei namens `PostalPlanetBarHeightAuto.png`, die einen scharfen Planet‑Barcode enthält. Die Höhe beträgt etwa 30 px (abhängig von der Bibliotheksversion) und die Breite entspricht 4 px × Anzahl der Module.

## Wie man die Barcode‑Höhe einstellt – benutzerdefiniertes RM4SCC‑Beispiel

RM4SCC ist ein weiterer Post‑Barcode, der häufig eine feste Höhe erfordert, um zu Etikettenvorlagen zu passen. Dieser Teil des Tutorials zeigt **wie man die Barcode‑Höhe einstellt** auf einen genauen Pixelwert.

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

**Warum das funktioniert**

* `EncodeTypes.RM4SCC` wählt die RM4SCC‑Symbologie.
* Die X‑Dimension bleibt bei 4 px, um die Modulgröße bei beiden Barcodes konsistent zu halten.
* `bar_height.pixels = 100` zwingt den Barcode, exakt 100 px hoch zu sein, und überschreibt die automatische Berechnung. Dies ist die empfohlene Vorgehensweise **wie man die Barcode‑Höhe einstellt**, wenn Ihr Layout eine bestimmte Größe verlangt.

**Erwartetes Ergebnis**

Eine PNG‑Datei namens `PostalRM4SCCBarHeight100Pixels.png`, die einen hohen RM4SCC‑Barcode anzeigt. Die Breite wird weiterhin von der X‑Dimension bestimmt, während die Höhe fest auf 100 px gesetzt ist, was sie für hochauflösende Etikettendrucker geeignet macht.

## Vollständiges Skript – beide Beispiele kombinieren

Wenn Sie ein einzelnes Skript bevorzugen, das beide Bilder erzeugt, kopieren Sie den folgenden Code in `generate_barcodes.py` und führen Sie ihn aus.

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

**Erklärung des Skripts**

* Zwei Hilfsfunktionen halten den Code DRY (Don’t Repeat Yourself) und erleichtern das Erweitern des Skripts für andere Symbologien.
* Die `if __name__ == "__main__":`‑Abfrage ermöglicht es, die Datei als Modul zu importieren, ohne die Generierungslogik auszuführen – praktisch für Unit‑Tests.
* Alle Parameter (Daten‑String, X‑Dimension, Höhe) sind explizit, sodass das Skript als Referenz‑**barcode generator example** für zukünftige Projekte dient.

## Häufige Fragen und Sonderfälle

| Frage | Antwort |
|----------|--------|
| *Was tun, wenn ich eine andere X‑Dimension benötige?* | Ändern Sie `x_dimension.pixels` auf die gewünschte Modulbreite. Größere Werte vergrößern die Gesamtabmessungen des Barcodes proportional. |
| *Kann ich andere Bildformate erzeugen?* | Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpg`, `Bmp` oder `Gif`, je nach Enum der Bibliothek. |
| *Was passiert, wenn der Daten‑String ungültige Zeichen enthält?* | Der Generator wirft eine `ArgumentException`. Validieren Sie die Daten gegen den Zeichensatz der Symbologie, bevor Sie den Konstruktor aufrufen. |
| *Ist es möglich, eine Mindesthöhe festzulegen und gleichzeitig Auto‑Scaling zu nutzen?* | Verwenden Sie `gen.parameters.barcode.bar_height.min_pixels = <value>` (sofern das SDK eine `min_pixels`‑Eigenschaft bereitstellt). Dadurch wird verhindert, dass der Barcode unter eine lesbare Größe schrumpft. |
| *Muss ich den Generator freigeben?* | Die `BarcodeGenerator`‑Klasse implementiert `IDisposable` in .NET; in Python übernimmt der Garbage Collector das, Sie können jedoch `gen.dispose()` aufrufen, wenn Sie viele Instanzen in einer Schleife erzeugen. |

## Tipps für den Produktionseinsatz

* **Pro‑Tipp:** Speichern Sie X‑Dimension und Höhenwerte in einer Konfigurationsdatei, sodass Sie sie ohne Neukompilierung anpassen können.
* **Achten Sie darauf:** Eine zu kleine Höhe für die gewählte Symbologie kann dazu führen, dass Scanner den Barcode nicht lesen können.
* **Leistungshinweis:** Das Erzeugen einer großen Charge von Barcodes ist schneller, wenn Sie eine einzelne `BarcodeGenerator`‑Instanz wiederverwenden und nur die Eigenschaft `code_text` zwischen den Saves ändern.

## Fazit

Dieses **barcode generator example** demonstriert sowohl **wie man Planet‑Barcode**‑Bilder mit automatischer Größenbestimmung erstellt als auch **wie man die Barcode‑Höhe** manuell für RM4SCC‑Codes einstellt. Durch die Schritt‑für‑Schritt‑Anleitung können Sie die Barcode‑Erstellung in jede Python‑Anwendung integrieren, Dimensionen anpassen und PNG‑Dateien erzeugen, die bereit für den Druck oder die digitale Anzeige sind.

### Nächste Schritte

* Erkunden Sie weitere Symbologien wie `EncodeTypes.Postnet` oder `EncodeTypes.Code128` – das gleiche Muster gilt.
* Experimentieren Sie mit **wie man die Barcode‑Höhe einstellt** für QR‑Codes oder DataMatrix‑Symbole; die meisten Bibliotheken bieten eine ähnliche `bar_height`‑Eigenschaft.
* Kombinieren Sie den Generator mit einer PDF‑Bibliothek, um Barcodes direkt in Rechnungen oder Versandetiketten einzubetten.

Passen Sie das Skript gerne an, teilen Sie Ihre Ergebnisse und lassen Sie uns wissen, welche Barcode‑Typen Sie als Nächstes hinzufügen!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man PNG aus einem barcode generator example in Python speichert](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Wie man Planet‑Barcode‑PNG mit Python erstellt](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Wie man einen C#‑Barcode‑Generator verwendet, um einen Planet‑Barcode zu erstellen](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}