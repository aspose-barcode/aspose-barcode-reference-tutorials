---
category: general
date: 2026-09-23
description: Lär dig hur du genererar Code 128‑streckkod och sparar streckkodsbilden
  med Aspose.BarCode i Python – steg‑för‑steg‑guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: sv
lastmod: 2026-09-23
og_description: Generera Code 128‑streckkod och spara streckkodbilden med Aspose.BarCode
  i Python. Följ detta kompletta exempel för att skapa, anpassa och exportera streckkoden
  som en PNG‑fil.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Generera Code 128‑streckkod och spara streckkodsbild – Python‑guide
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
title: Hur man genererar Code 128‑streckkod och sparar streckkodsbilden med Aspose.BarCode
url: /sv/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar Code 128 streckkod och sparar streckkodsbild med Aspose.BarCode

Om du behöver **generera Code 128 streckkod** och **spara streckkodsbild** i ett Python‑projekt, visar den här handledningen de exakta stegen. Med Aspose.BarCode:s `ExtCodetextBuilder` kan du bädda in vanlig text och Unicode‑segment i en enda payload, och sedan rendera resultatet som en PNG‑fil.

Du kommer att se ett komplett, körbart skript, en förklaring av varje rad och tips för vanliga fallgropar såsom hantering av ECI‑kodning eller val av rätt utdatamapp. Ingen extern dokumentation krävs—bara kopiera, klistra in och kör.

## Förutsättningar

* Python 3.8+ installerat.
* `aspose.barcode`‑paketet (installera med `pip install aspose-barcode`).
* Skrivbehörighet till den katalog där PNG‑filen kommer att sparas.

Koden fungerar med alla symboler som stöds av Aspose.BarCode, men exemplet fokuserar på **Code 128** eftersom den effektivt kodar alfanumerisk data och stödjer utökade teckenuppsättningar.

## Steg 1: Importera de nödvändiga klasserna

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Varför detta steg?* Att importera klasserna ger dig åtkomst till byggaren för utökad kodtext, skrivar‑objektet som skapar bilden och versions‑hjälparen som kan vara användbar för felsökning av bibliotekuppdateringar.

## Steg 2: Bygg den utökade kodtexten

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

`ExtCodetextBuilder` låter dig blanda vanlig ASCII‑ och Unicode‑data i en enda streckkodspayload. ECI‑byten (Extended Channel Interpretation) `0x03` talar om för skannern att de följande bytena är UTF‑8‑kodade, vilket är nödvändigt för språk som ryska, kinesiska eller arabiska.

## Steg 3: Konfigurera streckkodsskrivaren för Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Genom att sätta `encode_type` till `CODE_128` instrueras skrivaren att rendera en **Code 128 streckkod**. `code_text`‑egenskapen får den utökade strängen som byggdes i föregående steg.

## Steg 4: Spara streckkodsbilden som PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

`save`‑metoden skriver streckkoden till en fil. Genom att använda `BarCodeImageFormat.PNG` säkerställs förlustfri komprimering och bred kompatibilitet med webb‑ och mobilapplikationer.

## Steg 5 (valfritt): Verifiera Aspose.BarCode‑bibliotekets version

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Att känna till den exakta biblioteksversionen hjälper när du behöver rapportera buggar eller jämföra beteende mellan olika versioner.

## Förväntat resultat

Att köra skriptet ger konsolutdata liknande:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Den genererade PNG‑filen (`extended_codetext.png`) ser ut så här:

![Python‑genererad Code 128 streckkod sparad som PNG‑bild](images/code128_extended.png)

*Bilden visar en Code 128 streckkod som kodar både ASCII‑strängen `ABC123` och det ryska ordet “Пример”.*

## Vanliga frågor och hantering av edge‑case

| Fråga | Svar |
|----------|--------|
| **Kan jag använda en annan symbol?** | Ja. Ersätt `BarCodeEncodeMode.CODE_128` med någon annan stödd läge såsom `QR`, `EAN_13` eller `PDF_417`. |
| **Vad händer om min Unicode‑text innehåller emojis?** | Emojis är också UTF‑8‑tecken, så samma `add_eci_codetext`‑anrop fungerar. Säkerställ att den målskannern stödjer den ECI du använder. |
| **Hur ändrar jag bildens storlek?** | Ställ in `writer.x_dimension` och `writer.bar_height` innan du anropar `save`. |
| **Vilken mapp ska jag använda för `output_path`?** | Vilken mapp som helst som Python‑processen kan skriva till. Använd `os.makedirs` med `exist_ok=True` för att skapa den automatiskt. |

## Pro‑tips

* **Undvik att hårdkoda sökvägar.** Använd `os.path.join` och `Path` från `pathlib`‑modulen för plattformsoberoende kompatibilitet.
* **Validera streckkoden.** Efter sparning kan du läsa tillbaka bilden med `barcode.BarCodeReader` för att bekräfta att den kodade texten matchar `extended_codetext`.
* **Prestandatips.** Om du genererar många streckkoder i en loop, återanvänd en enda `BarCodeWriter`‑instans och uppdatera bara `code_text` för varje iteration.

## Slutsats

Du vet nu hur du **genererar Code 128 streckkod** med blandad ASCII‑ och Unicode‑data och **sparar streckkodsbild** som PNG med Aspose.BarCode i Python. Det kompletta skriptet täcker byggandet av utökad kodtext, konfiguration av skrivaren, export av bilden och kontroll av biblioteksversioner.

Från här kan du utforska:

* Lägga till förgrunds‑/bakgrundsfärger (`writer.back_color`, `writer.fore_color`).
* Bädda in streckkoden i PDF‑filer med `Aspose.PDF`.
* Använda `BarCodeReader`‑klassen för att avkoda den sparade bilden och automatiskt verifiera innehållet.

Lycka till med kodningen, och känn dig fri att experimentera med andra symboler och bildformat!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera Code128 streckkod med Aspose.Barcode Python – Fullständig guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Hur man genererar streckkod i Python – komplett steg‑för‑steg‑guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Hur man genererar QR‑kod bild i Python med Aspose.Barcode – Fullständig guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}