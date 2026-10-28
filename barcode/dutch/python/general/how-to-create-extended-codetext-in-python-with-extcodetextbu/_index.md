---
category: general
date: 2026-10-28
description: Leer hoe je uitgebreide codetekst maakt in Python met ExtCodetextBuilder.
  Inclusief platte en ECI‑gecodeerde data, stap‑voor‑stap code en best‑practice tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: nl
lastmod: 2026-10-28
og_description: Maak uitgebreide codetekst in Python met ExtCodetextBuilder. Deze
  tutorial toont de verwerking van platte en ECI‑gecodeerde gegevens, volledige uitvoerbare
  code en veelvoorkomende valkuilen.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Maak uitgebreide codetekst in Python – volledige gids
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
title: Hoe maak je uitgebreide codetekst in Python met ExtCodetextBuilder
url: /nl/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je uitgebreide codetekst in Python met ExtCodetextBuilder

Als je **uitgebreide codetekst** moet maken voor barcode‑ of data‑matrix‑toepassingen, laat deze gids je precies zien hoe je dat in Python doet. Je ziet hoe je platte tekst combineert, ECI‑ (Extended Channel Interpretation) secties toevoegt voor Unicode‑tekens, en een enkele, correct geformatteerde string ophaalt die klaar is voor codering.

De tutorial behandelt alles, van het installeren van de vereiste bibliotheek tot het afhandelen van randgevallen zoals niet‑ondersteunde ECI‑waarden. Aan het einde heb je een herbruikbaar patroon dat je in elk project kunt gebruiken dat **uitgebreide codetekst** moet **maken**.

## Wat je zult leren

* De rol van `ExtCodetextBuilder` bij het bouwen van gemengde‑codering strings.  
* Hoe je **plain codetext** en **ECI codetext** toevoegt in één builder‑instantie.  
* Hoe je de uiteindelijke output verifieert en veelvoorkomende valkuilen oplost.  
* Variaties voor andere tekenreeksen (bijv. ISO‑8859‑1, Shift‑JIS).  

### Vereisten

* Python 3.8 of nieuwer.  
* Het `extcodetext`‑pakket (of een vergelijkbare bibliotheek die `ExtCodetextBuilder` biedt). Installeer het met:

```bash
pip install extcodetext
```

* Basiskennis van Unicode en ECI‑waarden – ECI 3 komt overeen met UTF‑8, ECI 4 met ISO‑8859‑1, enz.

> **Pro tip:** Houd een referentietabel met ECI‑nummers bij de hand. Het voorkomt per ongeluk mismatches tussen de gedeclareerde codering en de werkelijke byte‑reeks.

## Begrijpen van ExtCodetextBuilder

`ExtCodetextBuilder` is een kleine utility die meerdere tekstfragmenten aan elkaar plakt terwijl automatisch de benodigde ECI‑markers worden ingevoegd. Een ECI‑marker vertelt de barcode‑encoder welke tekenset moet worden gebruikt voor de volgende bytes. Zonder de marker zouden niet‑ASCII tekens verkeerd worden geïnterpreteerd.

De builder werkt in drie eenvoudige fasen:

1. **Create** de builder‑instantie.  
2. **Append** platte of ECI‑gecodeerde fragmenten.  
3. **Retrieve** de gecombineerde extended‑codetext string.

Hieronder lopen we elke fase door met concrete code.

## Stap 1: Maak een ExtCodetextBuilder‑instantie

De eerste regel maakt het object dat alle fragmenten zal bevatten. Er is op dit moment geen configuratie nodig.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Waarom dit belangrijk is*: Het instantieren van de builder reserveert een interne buffer. Alle daaropvolgende `add_*`‑aanroepen werken op die buffer, waardoor de door jou opgegeven volgorde gegarandeerd wordt.

## Stap 2: Voeg platte (niet‑gecodeerde) data toe

Platte data bestaat uit tekens die tot de standaard tekenset behoren (meestal ASCII). Gebruik `add_plain_codetext` voor dergelijke fragmenten.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Uitleg*: De string `"ABC123"` bevat alleen ASCII‑tekens, dus er is geen ECI‑marker nodig. De methode voegt simpelweg de ruwe bytes toe aan de interne buffer.

## Stap 3: Voeg data toe die voorafgegaan moet worden door een ECI

Wanneer je Unicode‑tekens moet insluiten—zoals Cyrillisch, Japans of emoji—moet je de encoder vertellen welke tekenset te gebruiken. Dit gebeurt met `add_eci_codetext(eci, text)`. Het eerste argument is de numerieke ECI‑waarde; het tweede is de eigenlijke tekst.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Waarom ECI 3*: Volgens de ISO/IEC 18004‑specificatie correspondeert ECI 3 met UTF‑8. Door deze marker in te voegen weet de barcode‑lezer de volgende bytes als UTF‑8 te decoderen, waardoor de Cyrillische tekens behouden blijven.

### Andere coderingen verwerken

Als je ISO‑8859‑1 (West-Europees) nodig hebt, gebruik je `add_eci_codetext(4, "¡Hola!")`. Voor Shift‑JIS (Japans) is de ECI‑waarde 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Controleer altijd of de doel‑barcode‑bibliotheek de gekozen ECI‑waarde ondersteunt; niet‑ondersteunde ECIs zullen coderingsfouten veroorzaken.

## Stap 4: Haal de gecombineerde extended‑codetext string op

Nadat alle fragmenten zijn toegevoegd, roep je `get_extended_codetext()` aan om de uiteindelijke string te verkrijgen. Deze string bevat alle benodigde ECI‑escape‑sequenties.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Verwachte output** (weergegeven als een Python `repr` voor duidelijkheid):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Uitsplitsing*:

* `ABC123` – platte ASCII‑segment.  
* `\x1B\x1D\x03` – de ECI‑escape‑sequentie voor UTF‑8 (ESC GS 0x03).  
* `Привет` – het UTF‑8‑gecodeerde Cyrillische woord.

De exacte escape‑bytes kunnen verschillen afhankelijk van de bibliotheekimplementatie, maar de logische volgorde zal altijd *plain → ECI‑marker → Unicode‑tekst* zijn.

## Volledig uitvoerbaar voorbeeld

Alles samenvoegend, hier is een zelfstandige script die je kunt kopiëren‑plakken in een bestand genaamd `create_extended_codetext.py` en direct kunt uitvoeren.

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

Het uitvoeren van het script print de gecombineerde string, klaar voor elke barcode‑encoder die extended‑codetext invoer accepteert.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|---|---|---|
| `UnicodeEncodeError` when calling `add_eci_codetext` | Het leveren van een string die tekens bevat die niet representabel zijn in de gekozen ECI | Controleer of de ECI overeenkomt met de werkelijke codering van de string (bijv. gebruik ECI 3 voor elke UTF‑8‑tekst). |
| Missing ECI marker in the final output | Per ongeluk `add_plain_codetext` gebruiken voor niet‑ASCII data | Schakel over naar `add_eci_codetext` voor elk teken buiten het ASCII‑bereik. |
| Barcode scanner shows garbled characters | De scanner ondersteunt de geselecteerde ECI‑waarde niet | Kies een universeel ondersteunde ECI (UTF‑8 is breed ondersteund) of val terug op ISO‑8859‑1 als de doeltaal dit toelaat. |
| `get_extended_codetext` returns an empty string | Er zijn geen fragmenten toegevoegd vóór het aanroepen van de methode | Zorg dat er minstens één `add_*`‑aanroep wordt uitgevoerd. |

### Randgeval: Lege strings

Het aanroepen van `add_plain_codetext("")` of `add_eci_codetext(3, "")` is onschadelijk; de builder negeert simpelweg het lege fragment. Herhaalde lege aanroepen kunnen echter leiden tot onnodige ECI‑markers. Bescherm hiertegen door de tekenreekslengte te controleren voordat je toevoegt.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Het patroon uitbreiden voor dynamische data

In real‑world toepassingen bouw je vaak de extended codetext op basis van gebruikersinvoer of een database‑record. Het volgende fragment toont een lus die een lijst van `(type, value)`‑tuples verwerkt, waarbij `type` of `"plain"` of `"eci"` is.

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

Deze aanpak schaalt goed: je kunt de fragmentdefinities lezen uit JSON, CSV of een API zonder de kernlogica van de builder te wijzigen.

## De output testen

Een snelle unit‑test zorgt ervoor dat de builder zich gedraagt zoals verwacht. Met `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Het uitvoeren van `pytest` zou moeten slagen, wat bevestigt dat de ECI‑marker precies op de juiste plaats verschijnt.

## Gerelateerde concepten die je hierna kunt verkennen

* **Barcode‑codering bibliotheken** – bijv. `python-barcode`, `zxing`‑bindings, die de extended codetext‑string direct accepteren.  
* **ECI‑tabelreferentie** – een volledige lijst van numerieke ECI‑waarden wordt gepubliceerd door ISO/IEC 18004 en kan worden opgeslagen als een Python‑dictionary voor opzoeking.  
* **Foutcorrectieniveaus** – bij het genereren van QR‑codes combineer je de extended codetext met de juiste foutcorrectie (L, M, Q, H) voor robuuste scanning.

## Conclusie

Je weet nu hoe je **uitgebreide codetekst** in Python kunt **maken** met `ExtCodetextBuilder`. Het proces is eenvoudig:

1. Instantieer de builder.  
2. Voeg platte en ECI‑gecodeerde fragmenten toe naar behoefte.  
3. Haal de uiteindelijke string op en geef deze aan je barcode‑generator.

Door het bovenstaande patroon te volgen kun je elke mix van ASCII‑ en Unicode‑data verwerken, veelvoorkomende coderingsfouten vermijden, en barcode‑klaar strings produceren die werken met een breed scala aan scanners. Experimenteer met verschillende ECIs, integreer de builder in je datapijplijn, en je hebt een solide basis voor al je extended‑codetext behoeften.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}