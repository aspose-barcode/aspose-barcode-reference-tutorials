---
date: 2026-01-04
description: Lär dig hur du genererar Codabar‑streckkod med start‑ och stopptecken
  med Aspose.BarCode för .NET. En steg‑för‑steg‑handledning för streckkodsgenerering
  för utvecklare.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Generera Codabar-streckkod med start-/stopptecken i Aspose.BarCode för .NET
url: /sv/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera Codabar-streckkod med start-/stopptecken i Aspose.BarCode för .NET

## Introduktion

Välkommen till den här omfattande guiden om hur du **genererar codabar-streckkod**‑bilder med start‑/stopptecken med hjälp av Aspose.BarCode för .NET. Oavsett om du bygger ett lagerhanteringssystem, en laboratorieprovspårare eller en medicinsk journal‑lösning, är Codabar en pålitlig numerisk symbologi som kräver explicita start‑ och stopp‑symboler för korrekt avläsning. Under de kommande minuterna går vi igenom allt du behöver – från förutsättningar till att spara de slutgiltiga PNG‑filerna – så att du kan börja skapa Codabar‑streckkoder direkt.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode för .NET  
- **Vilket format kan jag spara streckkoden i?** PNG (BarCodeImageFormat.Png)  
- **Behöver jag licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag ändra start‑/stopp‑symbolerna?** Ja – använd CodabarSymbol.A, B, C eller D.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Förutsättningar

Innan vi börjar, låt oss säkerställa att du har allt du behöver för att följa med i den här tutorialen:

1. **Miljöinställning** – Se till att du har en fungerande .NET‑utvecklingsmiljö på din maskin. Om du behöver vägledning, se [dokumentationen](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode för .NET‑bibliotek** – Ladda ner och installera biblioteket från den officiella [källan](httpshttps://releases.aspose.com/barcode/net/).  
3. **Grundläggande .NET‑kunskaper** – Bekantskap med C# och Visual Studio (eller någon annan föredragen IDE) gör stegen smidigare.  
4. **IDE** – Visual Studio, Rider eller Visual Studio Code fungerar alla bra.

Nu när vi har gått igenom förutsättningarna, låt oss dyka ner i själva koden.

## Importera namnrymder

För att komma igång med Aspose.BarCode för .NET, importera den nödvändiga namnrymden:

```csharp
using Aspose.BarCode.Generation;
```

## Så här genererar du codabar‑streckkod – Steg‑för‑steg‑guide

### Steg 1: Initiera Barcode‑generatorn

Skapa en `BarcodeGenerator`‑instans, ange **Codabar** som kodningstyp och ange datasträngen som redan innehåller start‑/stopp‑tecknen (t.ex. “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Proffstips:** Bindestrecket (`-`) är ett av de giltiga start‑/stopp‑symbolerna för Codabar. Du kan också använda A, B, C eller D beroende på ditt programs krav.

### Steg 2: Ställ in X‑dimensionen (streckkodselementets bredd)

X‑dimensionen styr bredden på den smalaste stapeln. Justera den så att den passar din avläsningsmiljö.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför det är viktigt:** En större X‑dimension förbättrar läsbarheten på lågupplösta skrivare, medan ett mindre värde sparar utrymme på högdensitets‑etiketter.

### Steg 3: Definiera start‑ och stopp‑tecken

Codabar stöder fyra start‑/stopp‑symboler (A, B, C, D). Nedan finns exempel för varje alternativ. Välj den som matchar specifikationen för det system du integrerar med.

#### Ställ in Start A och Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Ställ in Start B och Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Ställ in Start C och Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Ställ in Start D och Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Du kan upprepa konfigurationen för varje symbol du behöver generera; exemplet nedan sparar fyra separata bilder – en för varje start‑/stopp‑par.

### Steg 4: Spara de genererade streckkodsbilderna (PNG)

Till sist, skriv streckkoden till PNG‑filer. Detta demonstrerar **save barcode png**‑användningsfallet och ger dig färdiga resurser för testning.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Varje fil innehåller nu ett **codabar‑streckkodsexempel** med motsvarande start‑/stopp‑symboler.

## Vanliga problem & felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-------|
| Streckkoden ser förvrängd ut | X‑dimensionen för låg för den valda skrivarlösningen | Öka `XDimension.Pixels` (t.ex. till 3 eller 4) |
| Skannern kan inte läsa start/stop | Fel start‑/stopp‑symbol för mål‑systemet | Verifiera den krävs symbolen (A‑D) och ställ in den korrekt |
| PNG‑filen är tom eller korrupt | Ogiltig utskrifts‑sökväg eller otillräckliga skrivbehörigheter | Säkerställ att `path` pekar på en befintlig mapp och att appen har skrivbehörighet |

## Vanliga frågor

### Q1: Vad är Codabar, och varför är start‑ och stopp‑tecken viktiga?

A1: Codabar är en numerisk streckkodssymbologi som används flitigt i lager, bibliotek och sjukvård. Start‑ och stopp‑tecken definierar streckkodens gränser, så att skannrar vet var data börjar och slutar.

### Q2: Kan jag anpassa utseendet på Codabar‑streckkoder med Aspose.BarCode för .NET?

A2: Ja. Förutom X‑dimensionen kan du ändra färger, lägga till marginaler och till och med bädda in streckkoden i PDF‑ eller SVG‑format med samma API.

### Q3: Finns det några begränsningar för Codabar‑streckkoder när det gäller datakodning?

A3: Codabar stödjer främst numerisk data (0‑9) och några få specialtecken. Den är inte lämplig för fullständiga alfanumeriska strängar.

### Q4: Är Aspose.BarCode för .NET lämplig för kommersiell användning, och hur får jag en licens?

A4: Ja, den är produktionsklar. Köp en licens på [Asposes köpsida](https://purchase.aspose.com/buy).

### Q5: Var kan jag få hjälp eller diskutera problem relaterade till Aspose.BarCode för .NET?

A5: Gå med i communityn på [Aspose.BarCode för .NET‑supportforumet](https://forum.aspose.com/c/barcode/13) för assistans från både Aspose‑ingenjörer och andra utvecklare.

---

**Senast uppdaterad:** 2026-01-04  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}