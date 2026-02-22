---
date: 2026-02-22
description: Lär dig hur du skapar anpassad streckkodshöjd i .NET med Aspose.BarCode,
  justera höjden på endimensionella streckkoder snabbt och exakt.
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: Skapa streckkod med anpassad höjd – Endimensionella streckkoder
url: /sv/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa anpassad höjd för streckkod – Endimensionella streckkoder

När du behöver **create barcode custom height** i en .NET-applikation, ger Aspose.BarCode for .NET dig full kontroll över det visuella utseendet på endimensionella streckkoder. Oavsett om du bygger lageretiketter, kassa‑kvitton eller fraktsedlar, gör möjligheten att finjustera streckkodens höjd att skanningen blir optimal och utseendet polerat. I den här steg‑för‑steg‑guiden går vi igenom allt du behöver veta för att justera höjden på en endimensionell streckkod med Aspose.BarCode for .NET.

## Snabba svar
- **Vad betyder “barcode custom height”?** Det är den pixel‑baserade vertikala storleken på en 1‑D streckkodssymbol.  
- **Vilken egenskap styr höjden?** `Parameters.Barcode.BarHeight.Pixels`.  
- **Kan jag generera flera höjder i ett körning?** Ja – ändra bara egenskapen och anropa `Save()` igen.  
- **Vilka bildformat stöds?** PNG, JPEG, TIFF, BMP, GIF, och fler.  
- **Behöver jag en licens för att justera höjden?** Nej, funktionen fungerar i gratis‑versionen; en licens krävs för produktionsanvändning.

## Vad är “create barcode custom height”?
Att skapa en streckkod med en anpassad höjd innebär att ange det exakta pixelvärdet för den vertikala dimensionen av streckkodens staplar. Detta är användbart när du har strikta layoutkrav, behöver matcha befintligt tryckt material eller vill förbättra skannerns läsbarhet på olika medier.

## Varför använda Aspose.BarCode for .NET?
- **Rich API** – Justera storlek, färg, text och mer med enkla egenskapsinställningar.  
- **Cross‑platform** – Fungerar med .NET Framework, .NET Core och .NET 5/6+.  
- **No external dependencies** – Genererar bilder utan att behöva extra bibliotek.  
- **High‑quality rendering** – Garantiar skannbara streckkoder även vid anpassade dimensioner.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

- En utvecklingsmiljö med .NET Framework eller .NET Core.  
- Aspose.BarCode for .NET installerat. Du kan ladda ner det från webbplatsen [here](https://releases.aspose.com/barcode/net/).  
- En kodredigerare du föredrar.

Nu när vi har förutsättningarna klara, låt oss dyka in i processen för att justera höjden på en endimensionell streckkod.

## Importera namnrymder

Först måste du importera de nödvändiga namnrymderna till ditt projekt. Dessa namnrymder är nödvändiga för att arbeta med Aspose.BarCode for .NET. Så här gör du:

```csharp
using Aspose.BarCode.Generation;
```

## Steg 1: Ange katalogsökvägen

Börja med att definiera katalogsökvägen där du vill spara dina genererade streckkodsbilder. Ersätt `"Your Directory Path"` med den faktiska sökvägen på ditt system.

```csharp
string path = "Your Directory Path";
```

## Steg 2: Skapa Barcode Generator

Skapa nu en instans av klassen `BarcodeGenerator`. Du kan ange streckkodstypen (i detta fall använder vi `Code128`) och streckkodsvärdet (i detta exempel, `"ASPOSE"`).

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## Steg 3: Justera streckkodens höjd

I detta steg kommer du att sätta streckkodens höjd med egenskapen `BarHeight`. Som exempel kommer vi att justera höjden till 40 pixlar och 80 pixlar och spara två streckkodsbilder därefter. Detta visar hur enkelt det är att **create barcode custom height** värden i farten.

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Streckkoden blir för tunn efter höjdändring | Bredden justerades inte proportionellt | Använd `Parameters.Barcode.XDimension` för att ändra stapelbredden om det behövs. |
| Bilden sparas inte | Ogiltig sökväg eller saknade skrivbehörigheter | Verifiera att `path` slutar med ett bakstreck och att mappen finns. |
| Genererad streckkod kan inte skannas | Höjden är för låg/hög för skannern | Testa med en vanlig skanner; håll höjden mellan 30‑100 px för de flesta 1‑D-koder. |

## Vanliga frågor

**Q: Vilka streckkodstyper stöds av Aspose.BarCode for .NET?**  
A: Aspose.BarCode for .NET stöder ett brett spektrum av streckkodstyper, inklusive Code128, QR Code, DataMatrix och många fler. Du kan hitta en omfattande lista i dokumentationen.

**Q: Kan jag också justera bredden på en endimensionell streckkod?**  
A: Ja, du kan justera bredden på en endimensionell streckkod med Aspose.BarCode for .NET. Processen är liknande justeringen av höjden, och du har full kontroll över streckkodens dimensioner.

**Q: Finns det en gratis provversion av Aspose.BarCode for .NET?**  
A: Ja, du kan prova Aspose.BarCode for .NET med en gratis provversion. Du kan ladda ner den från [here](https://releases.aspose.com/).

**Q: Kan jag generera streckkoder i olika bildformat?**  
A: Ja, Aspose.BarCode for .NET stöder olika bildformat, inklusive PNG, JPEG och TIFF. Du kan välja det format som bäst passar ditt programs krav.

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.BarCode for .NET?**  
A: Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/barcode/net/) för djupgående information om hur du använder Aspose.BarCode i dina .NET-projekt.

## Slutsats

I den här handledningen har vi gått igenom processen för att **create barcode custom height** för endimensionella streckkoder med Aspose.BarCode for .NET. Genom att justera egenskapen `BarHeight` kan du generera streckkodsbilder som exakt matchar dina layoutkrav, oavsett om du behöver en kompakt etikett eller en stor, högsynlig kod.

Om du stöter på problem eller har ytterligare frågor, tveka inte att kontakta Aspose‑gemenskapen via deras [support forum](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-02-22  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}