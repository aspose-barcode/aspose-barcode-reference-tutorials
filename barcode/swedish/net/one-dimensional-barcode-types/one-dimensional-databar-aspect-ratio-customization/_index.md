---
date: 2026-02-25
description: Lär dig hur du **databar staplad omnidirektionell** anpassar bildförhållandet
  medan du **installerar Aspose.BarCode för .NET**. Precisa streckkoddesign blir enkel.
linktitle: One-Dimensional Databar Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Anpassa staplat omnidirektionellt bildförhållande för databar i .NET
url: /sv/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/
weight: 16
---

 produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Anpassa databar stacked omnidirectional aspect ratio i .NET

I barcodevärlden är precision och anpassning nyckeln till att uppnå önskade resultat. I den här handledningen lär du dig hur du **anpassar databar stacked omnidirectional aspect ratio** med Aspose.BarCode för .NET. Vi delar upp processen i små steg, förklarar varför varje inställning är viktig och visar exakt hur du genererar de slutliga bilderna. Så, låt oss dyka ner!

## Snabba svar
- **Vad kan jag anpassa?** Aspect ratio för en databar stacked omnidirectional‑streckkod.  
- **Vilket bibliotek krävs?** Aspose.BarCode för .NET (installera Aspose.BarCode för .NET).  
- **Hur många pixlar kan jag ange för X‑Dimension?** Ett heltal; exemplet använder 2 pixlar.  
- **Var sparas de genererade bilderna?** Till en mapp du anger via variabeln `path`.  
- **Behöver jag en licens?** En tillfällig licens fungerar för testning; en full licens krävs för produktion.

## Vad är databar stacked omnidirectional?

`databar stacked omnidirectional` är en endimensionell streckkodstyp definierad av GS1‑standarden. Den kodar numerisk data i ett kompakt, högdensitetsformat som kan läsas från vilken riktning som helst, vilket gör den idealisk för små föremål och mobil skanning.

## Varför anpassa aspect ratio?

Att ändra **aspect ratio** låter dig kontrollera den visuella balansen mellan bredd och höjd. Detta är användbart när du behöver en streckkod som passar en specifik etikettstorlek, följer varumärkesriktlinjer eller förbättrar skanningspålitlighet under begränsade utskriftsförhållanden.

## Förutsättningar

Innan vi börjar, se till att du har följande:

### 1. Installera Aspose.BarCode för .NET  
Du kan ladda ner den senaste versionen från den officiella webbplatsen **[here](https://releases.aspose.com/barcode/net/)**. Följ installationsguiden för att lägga till NuGet‑paketet i ditt projekt.

### 2. Skapa ett .NET‑projekt  
En enkel konsol‑ eller Windows‑applikation räcker. Se till att du riktar mot .NET 6+ (eller .NET Framework 4.5+) så att biblioteket fungerar utan extra konfiguration.

### 3. Din katalogsökväg  
Bestäm var du vill att de genererade PNG‑filerna ska sparas och notera den absoluta eller relativa sökvägen.

## Importera namnrymder

Innan du börjar anpassa aspect ratio, importera den erforderliga namnrymden så att du kan komma åt Aspose.BarCode‑klasser.

### Steg 1: Importera Aspose.BarCode‑namnrymden

```csharp
using Aspose.BarCode;
```

Nu är du redo att skapa en streckkodsgenerator.

## databar stacked omnidirectional aspect ratio‑inställningar

### Steg 2: Initiera `BarcodeGenerator`

Vi kommer att skapa en generator för typen **databar stacked omnidirectional** och mata in en exempel‑GS1‑datasträng.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarAspectRatio:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Tips:* Ersätt `"Your Directory Path"` med en riktig mapp, t.ex. `@"C:\Barcodes\"`.

### Steg 3: Ange X‑Dimension‑pixlar

X‑Dimension definierar den smala stapelns bredd. I detta exempel använder vi 2 pixlar, men du kan justera det för att matcha din skrivar‑DPI.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Steg 4: Anpassa DataBar aspect ratio

Nu kommer kärnan i handledningen – att ändra aspect ratio.

#### 4.1 Ange aspect ratio till 15

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 15;
gen.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Streckkoden sparas som **DatabarAspectRatio15.png** med ett relativt högt utseende.

#### 4.2 Ange aspect ratio till 30

```csharp
gen.Parameters.Barcode.DataBar.AspectRatio = 30;
gen.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Att öka förhållandet till **30** gör streckkoden bredare och kortare, vilket kan vara användbart för breda etiketter.

### Steg 5: Verifiera resultatet

Öppna de genererade PNG‑filerna i någon bildvisare. Du bör se två versioner av samma streckkod, var och en med en annan bredd‑till‑höjd‑proportion. Skanna dem med en standardstreckkodsläsare för att bekräfta att de fortfarande är läsbara.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Streckkoden blir suddig | X‑Dimension för låg för skrivar‑DPI | Öka `XDimension.Pixels` (t.ex. till 3 eller 4). |
| Skannern läser inte | Extrem aspect ratio (t.ex. > 50) | Håll förhållandet mellan 10‑40 för pålitlig skanning. |
| Filen sparas inte | Ogiltig `path`‑sträng | Använd `Path.Combine` och säkerställ att mappen finns (`Directory.CreateDirectory`). |

## Vanliga frågor

**Q: Vad är aspect ratio för en streckkod, och varför är den viktig?**  
A: Aspect ratio är bredd‑till‑höjd‑proportionen. Den påverkar hur streckkoden passar på en etikett och kan påverka skanningspålitlighet.

**Q: Kan jag ändra aspect ratio för andra streckkodstyper med Aspose.BarCode för .NET?**  
A: Ja, många endimensionella och tvådimensionella streckkoder har en `AspectRatio`‑egenskap för finjustering.

**Q: Finns det några begränsningar för att ändra aspect ratio?**  
A: Extrema värden kan bryta kodningsstandarderna och göra streckkoden oläslig. Testa med dina målskannrar.

**Q: Var kan jag hitta fler handledningar och exempel för Aspose.BarCode för .NET?**  
A: Utforska den omfattande guiden i den officiella **[documentation](https://reference.aspose.com/barcode/net/)**.

**Q: Hur får jag en tillfällig licens för Aspose.BarCode för .NET?**  
A: Du kan begära en provlicens **[here](https://purchase.aspose.com/temporary-license/)**.

## Slutsats

Du har nu lärt dig hur du **anpassar databar stacked omnidirectional aspect ratio** med Aspose.BarCode för .NET. Genom att justera `XDimension` och `DataBar.AspectRatio` kan du skapa streckkoder som exakt matchar dina etikettdimensioner, förbättrar estetisk konsistens och bibehåller skanningspålitlighet. Experimentera med olika förhållanden, integrera koden i ditt lager‑ eller förpackningsflöde, och njut av den flexibilitet som Aspose erbjuder.

För djupare kunskap, kolla in den fullständiga **[documentation](https://reference.aspose.com/barcode/net/)** eller gå med i communityn på **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Senast uppdaterad:** 2026-02-25  
**Testad med:** Aspose.BarCode 24.12 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}