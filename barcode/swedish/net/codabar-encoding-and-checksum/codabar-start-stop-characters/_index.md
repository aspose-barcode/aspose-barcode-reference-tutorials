---
date: 2026-05-24
description: Lär dig hur du skapar en Codabar-streckkod med start- och stopptecken
  med hjälp av Aspose.BarCode för .NET. Steg‑för‑steg‑handledning för generering av
  streckkoder för utvecklare.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar start-/stopptecken
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Skapa Codabar-streckkod med start-/stopptecken i Aspose.BarCode för .NET
url: /sv/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Codabar-streckkod med start-/stopptecken i Aspose.BarCode för .NET

## Introduktion

I den här handledningen kommer du att **skapa codabar-streckkod**-bilder som inkluderar explicita start-/stopptecken med Aspose.BarCode för .NET. Oavsett om du bygger ett detaljhandelslagerhanteringssystem, en laboratorieprovspårare eller en medicinsk journallösning, förlitar sig Codabars numeriska symbologi på dessa gränssymboler för att garantera pålitlig avläsning. Under de kommande minuterna kommer vi att gå igenom allt från miljöinställning till att spara PNG-filer, så att du kan börja generera Codabar-streckkoder omedelbart.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode for .NET  
- **I vilket format kan jag spara streckkoden?** PNG (`BarCodeImageFormat.Png`)  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra start-/stopptecknen?** Ja – använd `CodabarSymbol.A`, `B`, `C` eller `D`.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Vad är Codabar och varför är start-/stopptecken viktiga?

Codabar är en numerisk streckkodssymbologi som används i stor utsträckning i bibliotek, sjukvård och lagerhantering. Start- och stopptecknen (A‑D eller bindestreck) definierar streckkodens gränser, vilket gör att skannrar kan upptäcka var data börjar och slutar med 99,9 % läsningsnoggrannhet.

## Varför använda Aspose.BarCode för .NET?

Aspose.BarCode stödjer **30+ streckkodssymbologier** och kan generera bilder upp till **10 000 × 10 000 px** utan att ladda hela dokumentet i minnet. Den körs på Windows, Linux och macOS, och är kompatibel med .NET Framework, .NET Core och .NET 5+—vilket ger dig flexibilitet på alla moderna plattformar.

## Förutsättningar

1. **Miljöinställning** – Säkerställ en fungerande .NET‑utvecklingsmiljö. Om du behöver vägledning, se [dokumentationen](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode för .NET‑bibliotek** – Ladda ner och installera biblioteket från den officiella [källan](https://releases.aspose.com/barcode/net/).  
3. **Grundläggande .NET‑kunskap** – Bekantskap med C# och en IDE som Visual Studio, Rider eller VS Code.  
4. **IDE** – Visual Studio, Rider eller Visual Studio Code fungerar alla bra.

Nu när vi har gått igenom förutsättningarna, låt oss dyka ner i den faktiska koden.

## Hur genererar jag en Codabar-streckkod med start-/stopptecken?

Läs in `BarcodeGenerator`, sätt kodningstypen till **Codabar**, och skicka en datasträng som redan innehåller de nödvändiga start-/stopptecknen (t.ex. “-12345-”). Konfigurera sedan X‑Dimension, välj eventuellt ett annat start-/stopptecken, och spara slutligen bilden som PNG. Detta end‑to‑end‑flöde skapar en färdig‑till‑användning streckkod på bara några rader C#.

### Importera namnrymder

`BarcodeGenerator` och relaterade typer finns i namnrymden `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Steg 1: Initiera Barcode‑generatorn

`BarcodeGenerator` är kärnklassen som skapar streckkodsbilder. Den tar symbologitypen och datasträngen som konstruktörsargument.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Proffstips:** Bindestrecket (`-`) är ett av de giltiga start-/stopptecknen för Codabar. Du kan också använda `A`, `B`, `C` eller `D` beroende på din applikations krav.

### Steg 2: Ställ in X‑Dimension (streckkodselementets bredd)

`XDimension` styr bredden på den smalaste stapeln. Större värden förbättrar läsbarheten på lågupplösta skrivare, medan mindre värden sparar utrymme på högdensitetsetiketter.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför det är viktigt:** Att justera `XDimension` hjälper dig att uppfylla scannerspecifikationer som ofta kräver en minsta stapelbredd på 0,25 mm.

### Steg 3: Definiera start‑ och stopptecken

Codabar stödjer fyra start-/stopp‑symboler (A, B, C, D). Nedan finns exempel för varje alternativ. Välj den som matchar specifikationen för det system du integrerar med.

#### Ställer in Start A och Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Ställer in Start B och Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Ställer in Start C och Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Ställer in Start D och Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Du kan upprepa konfigurationen för varje symbol du behöver generera; exemplet nedan sparar fyra separata bilder—en för varje start-/stopp‑par.

### Steg 4: Spara de genererade streckkodsbilderna (PNG)

`Save` skriver streckkoden till en fil. Att använda `BarCodeImageFormat.Png` producerar förlustfria PNG‑bilder som är idealiska för webb‑ och utskriftsbruk.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Varje fil innehåller nu ett **codabar‑streckkodsexempel** med motsvarande start‑/stopp‑symboler.

## Vanliga problem & felsökning

| Symtom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| Strek­kod­en ser förvrängd ut | X‑Dimension för låg för den valda skrivarlösningen | Öka `XDimension.Pixels` (t.ex. till 3 eller 4) |
| Skannern kan inte läsa start-/stopp | Fel start-/stopp‑symbol för mål‑systemet | Verifiera det erforderliga symbolen (A‑D) och ställ in den därefter |
| PNG‑filen är tom eller korrupt | Ogiltig utskrivningssökväg eller otillräckliga skrivbehörigheter | Säkerställ att `path` pekar på en befintlig mapp och att din app har skrivbehörighet |

## Vanliga frågor

**Q1: Vad är Codabar, och varför är start‑ och stopptecken viktiga?**  
A: Codabar är en numerisk streckkodssymbologi som används i lager, bibliotek och sjukvård. Start‑/stopptecken definierar streckkodens gränser, vilket säkerställer att skannrar vet var data börjar och slutar.

**Q2: Kan jag anpassa utseendet på Codabar‑streckkoder med Aspose.BarCode för .NET?**  
A: Ja. Utöver X‑Dimension kan du ändra färger, lägga till marginaler och exportera till PDF eller SVG med samma API.

**Q3: Finns det några begränsningar för Codabar‑streckkoder när det gäller data‑kodning?**  
A: Codabar stödjer främst numerisk data (0‑9) plus ett begränsat antal specialtecken. Det är inte lämpligt för fullständiga alfanumeriska strängar.

**Q4: Är Aspose.BarCode för .NET lämplig för kommersiell användning, och hur kan jag skaffa en licens?**  
A: Ja, den är produktionsklar. Köp en licens på [Aspose's purchase page](https://purchase.aspose.com/buy).

**Q5: Var kan jag få hjälp eller diskutera problem relaterade till Aspose.BarCode för .NET?**  
A: Gå med i gemenskapen på [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13) för hjälp från både Aspose‑ingenjörer och andra utvecklare.

---

**Senast uppdaterad:** 2026-05-24  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Codabar start‑stop‑tecken och kontrollsumma](/barcode/net/codabar-encoding-and-checksum/)
- [Hur man lägger till kontrollsumma till Codabar‑streckkoder med Aspose.BarCode för .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Omfattande handledningar och exempel på Aspose.BarCode för .NET](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}