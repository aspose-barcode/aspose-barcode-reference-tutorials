---
category: general
date: 2026-09-29
description: Toon de productnaam in Python terwijl je de releasedatum afdrukt en versiegegevens
  ophaalt uit de barcodebibliotheek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: nl
lastmod: 2026-09-29
og_description: Geef de productnaam weer in Python en leer hoe je de releasedatum
  afdrukt, de versie ophaalt en de subversie toont met een paar regels code.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Toon productnaam en versie‑informatie in Python
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
title: Productnaam en versie‑informatie weergeven in Python
url: /nl/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Productnaam en versie‑informatie weergeven in Python

Als je de **productnaam** van een bibliotheek moet **weergeven**, laat deze gids je precies zien hoe. Je leert ook hoe je de **release‑datum** kunt **afdrukken**, **hoe je de versie krijgt**, en de **minor‑versie** kunt **tonen** met beknopte Python‑code.

Veel ontwikkelaars integreren barcode‑scan‑ of generatie‑functies en moeten de metadata van de bibliotheek aan gebruikers of logs tonen. Deze tutorial behandelt alles wat nodig is om die informatie betrouwbaar op te halen en weer te geven.

## Wat je zult leren

* Versie‑informatie ophalen uit de `barcode`‑bibliotheek.  
* **Productnaam weergeven** samen met hoofd‑ en minor‑versienummers.  
* **Release‑datum afdrukken** in een menselijk leesbaar formaat.  
* Ontbrekende attributen op een nette manier afhandelen.  

**Voorvereisten**  
* Python 3.8 of nieuwer.  
* Toegang tot het `barcode`‑pakket (installeer met `pip install python-barcode` of de bibliotheek die `BuildVersionInfo` levert).  

---

## Hoe productnaam en versie‑informatie weer te geven in Python

De eerste stap is om de bibliotheek te importeren en de methode aan te roepen die een versie‑info‑object retourneert. Het object bevat attributen zoals `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` en `RELEASE_DATE`.

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

**Waarom dit werkt**  
`BuildVersionInfo()` retourneert een lichtgewicht object waarvan de attributen bij het importeren worden gevuld. Direct toegang tot de attributen voorkomt extra I/O en garandeert dat de weergegeven gegevens overeenkomen met de bibliotheekversie die je code daadwerkelijk gebruikt.

### Verwachte output

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

De exacte waarden hangen af van de geïnstalleerde versie van de barcode‑bibliotheek.

---

## Hoe de versie op te halen uit de barcode‑bibliotheek

Als je alleen de versienummers nodig hebt, kun je het afdrukken van de productnaam overslaan en je richten op de numerieke velden.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*De `PRODUCT_MAJOR`‑ en `PRODUCT_MINOR`‑attributen volgen semantische versiebeheer, waardoor je versies programmatisch kunt vergelijken.*

---

## Hoe de release‑datum af te drukken

De release‑datum wordt opgeslagen als een tekenreeks in `YYYY‑MM‑DD`‑formaat. Om deze in een andere locale weer te geven, converteer je deze eerst naar een `datetime`‑object.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tip:** Valideer altijd de datum‑string vóór het parseren om `ValueError` te voorkomen wanneer de bibliotheek haar formaat wijzigt.

---

## Minor‑versie naast de hoofd‑versie tonen

Soms moet je de minor‑versie apart weergeven, bijvoorbeeld bij het loggen van compatibiliteitswaarschuwingen.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Gebruik de minor‑versie om feature‑flags te activeren:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Ontbrekende attributen afhandelen (edge cases)

Oudere releases van de barcode‑bibliotheek tonen mogelijk niet alle attributen. Wikkel attribuut‑toegang in `getattr` met verstandige standaardwaarden.

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

Dit patroon zorgt ervoor dat je script nooit crasht door een ontbrekend veld, waardoor het robuust is voor CI‑pipelines die tegen meerdere bibliotheekversies kunnen draaien.

---

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige script dat alle best practices combineert: attribuutvalidatie, datumformattering en duidelijke output.

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

Het uitvoeren van dit script op een systeem met de barcode‑bibliotheek geïnstalleerd levert een output op die lijkt op het eerdere voorbeeld, maar nu beschermt het tegen ontbrekende velden en formatteert het de datum netjes.

---

## Conclusie

Je weet nu hoe je **productnaam kunt weergeven**, **release‑datum kunt afdrukken**, **hoe je de versie krijgt**, **hoe je het product kunt afdrukken**, en **minor‑versie kunt tonen** met een eenvoudige Python‑workflow. Het volledige voorbeeld toont betrouwbare attribuut‑toegang, datum‑verwerking en versie‑vergelijking — vaardigheden die je kunt hergebruiken voor elke externe bibliotheek die metadata‑objecten blootlegt.

**Volgende stappen**

* Verken de andere metadata‑methoden van de barcode‑bibliotheek, zoals `BuildCommitInfo()`.  
* Integreer de output in een logging‑framework (bijv. `logging.info`).  
* Vergelijk versies programmatisch om minimale vereiste versies in je applicatie af te dwingen.

Voel je vrij om te experimenteren met verschillende output‑formaten of het script uit te breiden om de informatie naar een bestand te schrijven voor auditdoeleinden. Veel programmeerplezier!  

![Terminaloutput die productnaam en versie‑details toont](image.png "Terminaloutput")

## Wat je hierna zou moeten leren

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [productnaam weergeven met Python barcode‑bibliotheek – stap‑voor‑stap gids](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Hoe de versie van Aspose.Barcode af te drukken (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Hoe een barcode te genereren met Aspose.BarCode in Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}