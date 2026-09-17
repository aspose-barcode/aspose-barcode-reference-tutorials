---
date: 2026-03-07
description: Lär dig hur du skapar endimensionella databar GS1‑kodade streckkoder
  i .NET med Aspose.BarCode. Den här guiden visar hur du ställer in GS1, konfigurerar
  streckkodsgeneratorn och snabbt genererar streckkoder.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Skapa endimensionell Databar GS1‑kodning med Aspose.BarCode
url: /sv/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa endimensionell Databar GS1‑kodning med Aspose.BarCode

I den här handledningen kommer du **att skapa endimensionella databar**‑streckkoder som följer GS1‑standarden, med hjälp av Aspose.BarCode‑biblioteket för .NET. Oavsett om du behöver strikt GS1‑validering eller en mer flexibel streckkod, går vi igenom varje steg – från installation av biblioteket till hantering av kodningsundantag – så att du kan generera pålitliga streckkoder i dina egna applikationer.

## Snabba svar
- **Vad betyder “skapa endimensionell databar”?** Det betyder att generera en linjär (1‑D) streckkod från Databar‑familjen, ofta använd inom detaljhandel och logistik.  
- **Hur ställer jag in GS1‑validering?** Sätt `IsAllowOnlyGS1Encoding` till `true` på `DataBar`‑parametrarna.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Var kan jag ladda ner biblioteket?** Från den officiella Aspose‑utgivningssidan (se förutsättningar).

## Vad är “skapa endimensionell databar”?
En endimensionell Databar (även känd som RSS) är en kompakt linjär streckkod som kan koda numerisk data, datum eller AI‑strängar (Application Identifier). När den kombineras med GS1‑kodning följer streckkoden en globalt erkänd datastruktur, vilket gör den idealisk för detaljhandel, sjukvård och leveranskedjor.

## Varför använda Aspose.BarCode för .NET?
Aspose.BarCode erbjuder ett flytande API, full GS1‑support och möjlighet att finjustera varje visuellt aspekt av streckkoden. Det eliminerar gissningsarbetet kring låg‑nivå‑kodning och låter dig fokusera på affärslogik.

## Förutsättningar

1. **Aspose.BarCode för .NET** – ladda ner och installera det från [here](https://releases.aspose.com/barcode/net/).  
2. **Din katalogsökväg** – ersätt `"Your Directory Path"` i exemplen med en mapp där du har skrivbehörighet.

## Importera namnrymder

Lägg till de nödvändiga `using`‑satserna högst upp i din C#‑fil:

```csharp
using Aspose.BarCode;
using System;
```

## Steg 1: Initiera Barcode‑generatorn

Skapa en `BarcodeGenerator`‑instans och ange Databar Expanded‑symbologi:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Steg 2: Så här ställer du in GS1 – Generera en streckkod med strikt GS1‑validering

Aktivera endast GS1‑kodning, tilldela en GS1‑kompatibel kodtext och spara bilden:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Steg 3: Barcode‑generering med Aspose – Variabel kodning (utan GS1‑kontroll)

Om du behöver en streckkod som **inte** upprätthåller GS1‑regler, stäng av kontrollen:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Steg 4: Barcode‑generatorns GS1‑kontroll – Hantera ett undantag

När `IsAllowOnlyGS1Encoding` är `true` men kodtexten inte är GS1‑kompatibel, kastar Aspose ett undantag. Följande mönster visar hur du fångar och loggar det:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Vanliga fallgropar & tips
- **Fallgrop:** Att ange en icke‑GS1‑sträng medan GS1‑kontrollen är aktiverad avbryter streckkodsgenereringen.  
- **Proffstips:** Validera dina AI‑strängar innan du tilldelar dem till `CodeText` för att undvika körningsfel.  
- **Tips:** Använd absoluta sökvägar eller `Path.Combine` för att bygga filnamn på ett säkert sätt över plattformar.

## Slutsats

Du vet nu hur du **skapar endimensionella databar**‑streckkoder med GS1‑kodning, hur du växlar GS1‑kontrollen och hur du hanterar relaterade undantag – allt med Aspose.BarCode för .NET. Utforska gärna ytterligare stilalternativ som streckkodsstorlek, färg och marginaler via `Parameters.Barcode`‑objektet.

Om du stöter på problem är den officiella dokumentationen och community‑forumet utmärkta resurser:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Vanliga frågor

### 1. Vad är GS1‑kodning i streckkoder?
GS1‑kodning är ett standardiserat sätt att strukturera data (t.ex. produktidentifierare) i en streckkod, vilket säkerställer interoperabilitet mellan återförsäljare, tillverkare och logistikleverantörer.

### 2. Kan jag anpassa utseendet på de genererade streckkoderna?
Ja. Aspose.BarCode låter dig justera storlek, färger, marginaler och till och med lägga till mänskligt läsbar text via `Parameters.Barcode`‑inställningarna.

### 3. Var kan jag hitta ytterligare resurser och dokumentation för Aspose.BarCode?
Du hittar omfattande dokumentation och exempel på [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). Det är en värdefull källa för lärande och felsökning.

### 4. Finns det en provversion av Aspose.BarCode?
Ja, du kan få en gratis provversion av Aspose.BarCode för .NET från [here](https://releases.aspose.com/).

### 5. Hur kan jag köpa en licens för Aspose.BarCode för .NET?
För att köpa en licens för Aspose.BarCode för .NET, besök [purchase page](https://purchase.aspose.com/buy) på Aspose‑webbplatsen.

---

**Senast uppdaterad:** 2026-03-07  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}