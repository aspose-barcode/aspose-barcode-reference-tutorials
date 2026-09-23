---
date: 2026-06-14
description: Lär dig hur du skapar DotCode-streckkod .NET och anpassar bildförhållandet
  med hjälp av Aspose.BarCode för .NET.
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: Anpassning av bildförhållande för DotCode
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Skapa DotCode-streckkod .NET – Anpassa bildförhållandet
url: /sv/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa DotCode-streckkod .NET – Anpassa bildförhållandet

Om du behöver **skapa DotCode-streckkod .NET**‑lösningar som passar trånga utrymmen eller specifika layoutkrav, ger Aspose.BarCode för .NET dig full kontroll. I den här handledningen går vi igenom hela processen för att generera en DotCode-streckkod och justera dess bildförhållande så att den ser exakt ut som du vill på förpackningar, etiketter eller mobila skärmar.  

## Snabba svar
- **Kan jag generera DotCode-streckkoder i .NET?** Ja, Aspose.BarCode stöder DotCode direkt ur lådan.  
- **Vilken egenskap styr formen?** `AspectRatio`‑egenskapen i `BarcodeGenerator`.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provversion fungerar för utveckling.  
- **Stödda .NET-versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Hur lång tid tar det för koden att köras?** Mindre än en sekund för en typisk 200 × 200‑pixel streckkod.

## Vad är huvudmålet med den här handledningen?
Handledningen syftar till att demonstrera hur man genererar en DotCode-streckkod med Aspose.BarCode för .NET och hur man justerar dess bildförhållande för att passa specifika layoutbegränsningar. Genom att följa stegen kommer du att lära dig att konfigurera generatorn, ändra storleksparametrar och exportera bilden i vanliga format.

## Hur skapar man DotCode-streckkod .net?
För att skapa en DotCode-streckkod i .NET, instansiera en `BarcodeGenerator` med `EncodeTypes.DotCode` och den data du vill koda. Ställ sedan in X‑Dimension‑ och AspectRatio‑egenskaperna för att kontrollera storlek och form, och anropa slutligen `Save`‑metoden för att skriva bilden till en fil i önskat format.

## Förutsättningar

1. **Aspose.BarCode for .NET** – ladda ner biblioteket från den officiella webbplatsen [här](https://releases.aspose.com/barcode/net/).  
2. **IDE** – Visual Studio, Rider eller någon .NET‑kompatibel redigerare.  
3. **Utdatamapp** – ersätt “Your Directory Path” i exemplet med en riktig mapp på din dator.

## Importera namnrymder

`Aspose.BarCode.Generation` tillhandahåller de klasser som behövs för att generera och konfigurera streckkoder i .NET.  
```csharp
using Aspose.BarCode.Generation;
```

## Steg 1: Initiera streckkodsgeneratorn

`BarcodeGenerator` är huvudklassen som skapar en streckkodsbild baserad på den angivna symboliken och data.  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## Steg 2: Ställ in X‑Dimension (storlek) för streckkoden

`XDimension` definierar bredden på en enskild modul (punkt) i pixlar, vilket påverkar den totala storleken på streckkoden.  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## Steg 3: Anpassa bildförhållandet

`AspectRatio` anger höjd‑till‑bredd‑förhållandet för varje modul, vilket låter dig sträcka eller komprimera streckkoden vertikalt.  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## Steg 4: Spara streckkodsbilden

`Save` skriver den genererade streckkoden till en fil i det valda bildformatet, till exempel PNG eller JPEG.  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Varför använda Aspose.BarCode för DotCode-anpassning?
Aspose.BarCode erbjuder ett omfattande urval av funktioner för DotCode-generering, inklusive högupplöst output, omfattande formatstöd och finjusterad kontroll över streckkodsdimensioner såsom bildförhållande. Det körs på alla större .NET-plattformar, kräver inga externa beroenden och levererar snabb renderingsprestanda, vilket gör det idealiskt för både skrivbords- och webbapplikationer.

## Vanliga användningsområden

- **Healthcare**: Kompakta patient‑ID‑taggar som måste få plats på små handledsband.  
- **Postal Services**: Bredformatsskicksetiketter där en lägre höjd förbättrar skanningspålitligheten.  
- **Manufacturing**: Inline‑märkning av delar där utrymmesbegränsningar kräver ett anpassat bildförhållande.

## Vanliga frågor

**Q:** Vad är bildförhållandet för en DotCode-streckkod?  
**A:** Det är förhållandet mellan en moduls höjd och dess bredd; att justera det förändrar streckkodens övergripande form.

**Q:** Vilka branscher drar mest nytta av DotCode-streckkoder?  
**A:** Healthcare, postal services och manufacturing använder ofta DotCode för kompakt, högdensitetsdatakodning.

**Q:** Kan jag anpassa andra DotCode‑parametrar med Aspose.BarCode för .NET?  
**A:** Absolut. Du kan ändra felkorrigeringsnivå, förgrunds‑/bakgrundsfärger och till och med bädda in logotyper.

**Q:** Är Aspose.BarCode lämplig för både webb- och skrivbords‑.NET‑applikationer?  
**A:** Ja, biblioteket fungerar sömlöst i ASP.NET, WPF, WinForms och konsolprogram.

**Q:** Var kan jag hitta mer dokumentation och exempel?  
**A:** Detaljerad API‑referens och kodexempel finns [här](https://reference.aspose.com/barcode/net/).

---

**Senast uppdaterad:** 2026-06-14  
**Testad med:** Aspose.BarCode 24.12 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [DotCode utökad kodtextkonfiguration med Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [DotCode strukturerat tilläggsläge konfiguration med Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Skapa DotCode-streckkod bild – rader & kolumner (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}