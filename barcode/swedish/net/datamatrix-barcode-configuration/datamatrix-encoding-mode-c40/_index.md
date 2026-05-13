---
date: 2026-01-15
description: Lär dig hur du sparar PNG-filer när du använder DataMatrix‑kodningsläge
  (C40) med Aspose.BarCode för .NET – en steg‑för‑steg streckkodstutorial.
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: Hur man sparar PNG med DataMatrix C40 i Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mästar DataMatrix-kodningsläge (C40) med Aspose.BarCode för .NET

## Introduktion

Om du letar efter en tydlig, praktisk guide om **how to save png** filer när du genererar DataMatrix-streckkoder, har du kommit till rätt plats. Oavsett om du bygger ett lagersystem, en fraktetikettgenerator eller någon lösning som kräver kompakta, högdensitetsstreckkoder, kommer behärskning av C40‑kodningsläget ge dig både storlekseffektivitet och pålitlig datarapresentation. I den här handledningen går vi igenom en **step by step barcode**‑skapandeprocess, från förutsättningar till den slutliga PNG‑utmatningen, med Aspose.BarCode för .NET.

## Snabba svar
- **What does “how to save png” refer to?** Saving the generated barcode as a PNG image file.  
- **Which encoding mode is covered?** DataMatrix C40 encoding.  
- **Do I need a license?** A free trial works for testing; a license is required for production.  
- **Can I run this on .NET Core?** Yes, Aspose.BarCode supports .NET Framework and .NET Core.  
- **What file format is produced?** PNG (Portable Network Graphics) image.

## Hur man sparar PNG med DataMatrix C40‑kodning

Att spara streckkoden som en PNG är det sista steget efter att du har konfigurerat generatorn. Metoden `Save` tar filvägen, önskat filnamn och bildformatet (`BarCodeImageFormat.Png`). Detta säkerställer att streckkoden lagras i ett förlustfritt format som fungerar i webbläsare, skrivare och mobila enheter.

## Vad är DataMatrix‑kodningsläge (C40)?

C40 är en effektiv teckenuppsättning för alfanumerisk data, som låter dig packa mer information i en mindre DataMatrix‑symbol. Det är särskilt användbart när du behöver koda text som innehåller bokstäver, siffror och ett begränsat antal specialtecken.

## Varför använda Aspose.BarCode för .NET?

- **Full kontroll** över streckkodsdimensioner, felkorrigering och kodningslägen.  
- **Zero‑dependency**‑generering – inga externa tjänster behövs.  
- **Cross‑platform**‑stöd för .NET Framework, .NET Core och .NET 5/6+.  

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

1. **.NET‑utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stödjer C#.  
2. **Aspose.BarCode för .NET** – installerad via NuGet eller den officiella installationsprogrammet. Se [documentation](https://reference.aspose.com/barcode/net/) för detaljer.  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med namnrymder, klasser och using‑satser.  
4. **Skrivbehörig mapp** – en katalog på din maskin där PNG‑filen kommer att sparas.  

## Importera nödvändiga namnrymder

Lägg till den erforderliga namnrymden högst upp i din C#‑källfil så att du kan komma åt klasserna för streckkodsgenerering:

```csharp
using Aspose.BarCode.Generation;
```

## Steg‑för‑steg streckkodsgenerering

Nedan följer en **step by step barcode**‑genomgång. Varje steg förklaras på enkel svenska, och de ursprungliga kodblocken behålls oförändrade för enkel kopiering.

### Steg 1: Definiera katalogsökvägen
Ange den mapp där PNG‑bilden ska lagras. Ersätt platshållaren med en faktisk sökväg på din maskin.

```csharp
string path = "Your Directory Path";
```

### Steg 2: Ställ in streckkodsgenerering
Skapa en `BarcodeGenerator`‑instans, ange `EncodeTypes.DataMatrix` och ange den data du vill koda.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Steg 3: Anpassa streckkoden
Konfigurera X‑dimensionen (pixelbredden på modulerna) och byt kodningsläget till C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Steg 4: Spara streckkodsbilden
Spara slutligen den genererade streckkoden som en PNG‑fil. Detta är det konkreta svaret på **how to save png** med Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

När du kör programmet hittar du `DataMatrixEncodeModeC40.png` i den mapp du angav, redo att användas i rapporter, etiketter eller webbsidor.

## Vanliga problem & tips

- **Invalid Path** – Säkerställ att katalogen finns och att du har skrivbehörighet; annars kommer `gen.Save` att kasta ett undantag.  
- **Incorrect Encoding Mode** – Om du behöver koda tecken utanför C40‑uppsättningen, byt till `DataMatrixEncodeMode.Auto` eller ett annat lämpligt läge.  
- **Image Size** – Justera `XDimension.Pixels` för att öka eller minska den totala streckkodsstorleken utan att påverka läsbarheten.  

## Vanliga frågor

**Q: Vad är DataMatrix Encoding Mode (C40)?**  
A: C40 är ett kompakt alfanumeriskt kodningsschema för DataMatrix‑symboler, idealiskt för text som innehåller bokstäver, siffror och ett begränsat antal specialtecken.

**Q: Var kan jag hitta Aspose.BarCode för .NET-dokumentationen?**  
A: Du kan hitta dokumentationen [here](https://reference.aspose.com/barcode/net/). Den ger detaljerad vägledning om alla streckkodstyper och kodningsalternativ.

**Q: Är Aspose.BarCode för .NET kompatibel med alla .NET‑versioner?**  
A: Ja, biblioteket stödjer ett brett spektrum av .NET‑versioner, från .NET Framework 4.5+ till .NET 6 och senare.

**Q: Kan jag prova Aspose.BarCode för .NET innan jag köper?**  
A: Ja, du kan utforska en gratis provversion av Aspose.BarCode för .NET genom att besöka [this link](https://releases.aspose.com/). Den låter dig testa bibliotekets funktioner och möjligheter.

**Q: Var kan jag få support för Aspose.BarCode för .NET?**  
A: Du kan hitta en stödjande community och få support för Aspose.BarCode för .NET på [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Slutsats

Genom att följa denna **step by step barcode**‑guide vet du nu exakt **how to save PNG**‑filer som genereras med DataMatrix C40‑kodning med Aspose.BarCode för .NET. Detta tillvägagångssätt ger dig full kontroll över streckkodens utseende, storlek och datarapresentation, vilket gör det enkelt att integrera högkvalitativa streckkoder i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2026-01-15  
**Testat med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}