---
date: 2026-01-12
description: Lär dig hur du skapar en streckkod‑PNG med ett anpassat DataMatrix‑aspektförhållande
  med Aspose.BarCode för .NET. Steg‑för‑steg‑guide för streckkodsgenerering och storleksanpassning.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Skapa streckkod PNG – DataMatrix bildförhållande – Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod PNG – DataMatrix-aspektförhållande – Aspose.BarCode

Att generera en **barcode PNG** med ett anpassat DataMatrix-aspektförhållande är ett vanligt krav när du behöver att streckkoden ska passa specifika layoutbegränsningar. I den här handledningen går vi igenom de exakta stegen för att **skapa barcode PNG**-filer med Aspose.BarCode för .NET, förklarar varför du kan vilja justera aspektförhållandet och visar hur du finjusterar resultatet för din applikation.

## Snabba svar
- **Vad styr “aspect ratio”?** Den definierar bredd‑till‑höjd‑förhållandet för DataMatrix-modulerna.  
- **Kan jag exportera PNG, JPEG eller SVG?** Ja – `Save`-metoden stöder PNG, JPEG, BMP, GIF och mer.  
- **Behöver jag en licens för den här funktionen?** En gratis provversion fungerar för utveckling; en full licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Hur många aspect‑ratio‑värden är giltiga?** Alla positiva flyttal; typiska värden är 0.5 – 2.0.

## Vad är en DataMatrix-streckkod och varför justera dess aspektförhållande?
DataMatrix är en tvådimensionell matrisstreckkod som lagrar stora mängder data på liten yta. Att justera **aspect ratio** låter dig sträcka eller komprimera modulerna horisontellt, vilket kan vara användbart för att passa streckkoden i smala kolumner eller breda etiketter utan att offra läsbarheten.

## Förutsättningar

Innan vi börjar anpassa DataMatrix-aspektförhållanden, se till att du har följande förutsättningar på plats:

1. **Visual Studio** – vilken som helst nyare version fungerar.  
2. **Aspose.BarCode for .NET** – ladda ner den [här](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – ditt projekt måste rikta in sig på en stödd version.

## Importera namnrymder

Först måste du importera den nödvändiga namnrymden i ditt C#-projekt:

```csharp
using Aspose.BarCode.Generation;
```

> **Proffstips:** Behåll detta `using`-uttalande högst upp i filen så att `BarcodeGenerator`-klassen alltid är tillgänglig.

## Steg‑för‑steg‑guide

### Steg 1: Ställ in ditt projekt
Skapa ett nytt konsol‑ eller Windows Forms‑projekt i Visual Studio och lägg till en referens till Aspose.BarCode‑DLL.

### Steg 2: Initiera en Barcode Generator
Instansiera en `BarcodeGenerator` med DataMatrix‑typen och den data du vill koda:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Denna rad skapar en generator som är redo att producera en DataMatrix‑streckkod som innehåller exempeltexten.

### Steg 3: Anpassa aspektförhållande och spara PNG‑filer
Nu kan du ändra **aspect ratio** och spara varje version som en PNG‑bild:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Det första anropet skapar en kvadratiskt proportionerad streckkod (`AspectRatio = 1`).  
- Det andra anropet komprimerar streckkoden horisontellt (`AspectRatio = 0.5`), vilket ger ett bredare utseende.

Du har nu två **barcode PNG**‑filer med olika aspektförhållanden redo att användas i rapporter, etiketter eller UI‑element.

## Vanliga problem & lösningar
| Problem | Lösning |
|-------|----------|
| **Genererad bild är suddig** | Öka `Resolution`-parametern innan du sparar (`gen.Parameters.ImageResolution = 300`). |
| **Streckkoden läses inte** | Se till att aspektförhållandet ligger inom 0.5 – 2.0 och behåll tillräcklig tyst zon (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Fel i filsökväg** | Använd `Path.Combine` för att bygga utdata‑sökvägen och verifiera att mappen finns. |

## Vanliga frågor

**Q: Kan jag anpassa aspektförhållandet för andra streckkodstyper med Aspose.BarCode för .NET?**  
A: Ja, många 2‑D‑streckkoder (t.ex. QR, PDF417) stödjer justering av aspektförhållande via sina specifika parameterobjekt.

**Q: Finns det en gratis provversion av Aspose.BarCode för .NET?**  
A: Ja, du kan komma åt en gratis provversion av Aspose.BarCode för .NET [här](https://releases.aspose.com/).

**Q: Var kan jag köpa en licens för Aspose.BarCode för .NET?**  
A: Du kan köpa en licens på Aspose‑webbplatsen [här](https://purchase.aspose.com/buy).

**Q: Är Aspose.BarCode för .NET kompatibel med olika .NET Framework‑versioner?**  
A: Ja, den fungerar med .NET Framework 4.x, .NET Core 3.1+ och de senaste .NET‑utgåvorna.

**Q: Kan jag generera streckkoder i olika format med Aspose.BarCode för .NET?**  
A: Absolut – PNG, JPEG, BMP, GIF, TIFF, SVG och PDF stöds alla direkt.

## Slutsats

Att anpassa **aspect ratio** för en DataMatrix‑streckkod och **skapa barcode PNG**‑filer är enkelt med Aspose.BarCode för .NET. Genom att följa stegen ovan kan du generera perfekt dimensionerade streckkoder som uppfyller ditt projekts exakta layoutkrav. Utforska andra parametrar som `Resolution`, `Margin` och `Color` för att ytterligare skräddarsy resultatet.

För djupare utforskning, kolla in den officiella [dokumentationen](https://reference.aspose.com/barcode/net/) eller gå med i communityn på [Aspose.BarCode‑forumet](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-01-12  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}