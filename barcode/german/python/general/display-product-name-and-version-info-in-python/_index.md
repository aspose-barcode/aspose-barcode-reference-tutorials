---
category: general
date: 2026-09-29
description: Produktnamen in Python anzeigen, während das Veröffentlichungsdatum ausgegeben
  und Versionsdetails aus der Barcode‑Bibliothek abgerufen werden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: de
lastmod: 2026-09-29
og_description: Produktnamen in Python anzeigen und lernen, wie man das Veröffentlichungsdatum
  ausgibt, die Version abruft und die Nebenversionsnummer mit wenigen Codezeilen anzeigt.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Produktname und Versionsinformationen in Python anzeigen
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
title: Produktnamen und Versionsinformationen in Python anzeigen
url: /de/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Produktnamen und Versionsinformationen in Python anzeigen

Wenn Sie den **Produktnamen** einer Bibliothek anzeigen müssen, zeigt Ihnen diese Anleitung genau, wie das geht. Sie lernen außerdem, **das Veröffentlichungsdatum auszugeben**, **wie man die Version ermittelt** und **die Nebenversionsnummer anzuzeigen**, und das mit kompaktem Python‑Code.

Viele Entwickler integrieren Barcode‑Scanning‑ oder Generierungsfunktionen und müssen die Metadaten der Bibliothek den Benutzern oder in Logs zur Verfügung stellen. Dieses Tutorial behandelt alles, was nötig ist, um diese Informationen zuverlässig abzurufen und darzustellen.

## Was Sie lernen werden

* Versioninformationen aus der `barcode`‑Bibliothek abrufen.  
* **Produktnamen** zusammen mit Haupt‑ und Nebenversionsnummern anzeigen.  
* **Veröffentlichungsdatum** in einem menschenlesbaren Format ausgeben.  
* Fehlende Attribute elegant behandeln.  

**Voraussetzungen**  
* Python 3.8 oder neuer.  
* Zugriff auf das `barcode`‑Paket (Installation mit `pip install python-barcode` oder die Bibliothek, die `BuildVersionInfo` bereitstellt).  

---

## So zeigen Sie Produktnamen und Versionsinformationen in Python an

Der erste Schritt besteht darin, die Bibliothek zu importieren und die Methode aufzurufen, die ein Versions‑Info‑Objekt zurückgibt. Das Objekt enthält Attribute wie `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` und `RELEASE_DATE`.

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

**Warum das funktioniert**  
`BuildVersionInfo()` gibt ein leichtgewichtiges Objekt zurück, dessen Attribute beim Import gefüllt werden. Der direkte Zugriff auf die Attribute vermeidet zusätzlichen I/O und stellt sicher, dass die angezeigten Daten mit der Bibliotheksversion übereinstimmen, die Ihr Code tatsächlich verwendet.

### Erwartete Ausgabe

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Die genauen Werte hängen von der installierten Version der barcode‑Bibliothek ab.

---

## So erhalten Sie die Version aus der barcode‑Bibliothek

Wenn Sie nur die Versionsnummern benötigen, können Sie das Ausgeben des Produktnamens überspringen und sich auf die numerischen Felder konzentrieren.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Die Attribute `PRODUCT_MAJOR` und `PRODUCT_MINOR` folgen der semantischen Versionierung, sodass Sie Versionen programmgesteuert vergleichen können.*

---

## So geben Sie das Veröffentlichungsdatum aus

Das Veröffentlichungsdatum wird als Zeichenkette im Format `YYYY‑MM‑DD` gespeichert. Um es in einer anderen Locale darzustellen, konvertieren Sie es zunächst in ein `datetime`‑Objekt.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tipp:** Validieren Sie immer die Datumszeichenkette, bevor Sie sie parsen, um `ValueError` zu vermeiden, falls die Bibliothek ihr Format ändert.

---

## Nebenversionsnummer zusammen mit der Hauptversionsnummer anzeigen

Manchmal müssen Sie die Nebenversionsnummer separat anzeigen, zum Beispiel beim Protokollieren von Kompatibilitätswarnungen.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro‑Tipp:** Verwenden Sie die Nebenversionsnummer, um Feature‑Flags auszulösen:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Umgang mit fehlenden Attributen (Randfälle)

Ältere Versionen der barcode‑Bibliothek stellen möglicherweise nicht alle Attribute bereit. Wickeln Sie den Attributzugriff in `getattr` mit sinnvollen Standardwerten ein.

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

Dieses Muster stellt sicher, dass Ihr Skript nie wegen eines fehlenden Feldes abstürzt, und macht es robust für CI‑Pipelines, die gegen mehrere Bibliotheksversionen laufen können.

---

## Vollständiges, ausführbares Beispiel

Unten finden Sie das vollständige Skript, das alle bewährten Verfahren kombiniert: Attributvalidierung, Datumsformatierung und klare Ausgabe.

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

Wenn Sie dieses Skript auf einem System mit installierter barcode‑Bibliothek ausführen, erhalten Sie eine Ausgabe, die der vorherigen Beispielausgabe ähnelt, jedoch jetzt vor fehlenden Feldern schützt und das Datum ansprechend formatiert.

---

## Fazit

Sie wissen jetzt, wie Sie **Produktnamen anzeigen**, **Veröffentlichungsdatum ausgeben**, **die Version ermitteln**, **das Produkt ausgeben** und **die Nebenversionsnummer anzeigen** können, und das mit einem einfachen Python‑Workflow. Das vollständige Beispiel demonstriert zuverlässigen Attributzugriff, Datumshandhabung und Versionsvergleich – Fähigkeiten, die Sie für jede Drittanbieter‑Bibliothek, die Metadaten‑Objekte bereitstellt, wiederverwenden können.

**Nächste Schritte**

* Untersuchen Sie weitere Metadaten‑Methoden der barcode‑Bibliothek, wie `BuildCommitInfo()`.  
* Integrieren Sie die Ausgabe in ein Logging‑Framework (z. B. `logging.info`).  
* Vergleichen Sie Versionen programmgesteuert, um Mindestversionsanforderungen in Ihrer Anwendung durchzusetzen.

Fühlen Sie sich frei, mit verschiedenen Ausgabeformaten zu experimentieren oder das Skript zu erweitern, um die Informationen zu Audit‑Zwecken in eine Datei zu schreiben. Viel Spaß beim Coden!  

![Terminalausgabe, die Produktnamen und Versionsdetails zeigt](image.png "Terminalausgabe")


## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Produktnamen mit der Python‑Barcode‑Bibliothek anzeigen – Schritt‑für‑Schritt‑Anleitung](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Wie man die Version von Aspose.Barcode (Python) ausgibt](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Wie man einen Barcode mit Aspose.BarCode in Python erzeugt](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}