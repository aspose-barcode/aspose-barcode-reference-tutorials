---
date: 2026-01-04
description: Lär dig hur du lägger till kontrollsumma när du genererar Codabar‑streckkod
  med Aspose.BarCode för .NET. Steg‑för‑steg‑guide som täcker Mod10‑ och Mod16‑kontrollsumma‑lägen.
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: Hur man lägger till kontrollsumma till Codabar-streckkoder med Aspose.BarCode
  för .NET
url: /sv/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så lägger du till kontrollsumma till Codabar‑streckkoder med Aspose.BarCode för .NET

Codabar är en mycket använd linjär streckkodssymbol, särskilt inom logistik, bibliotek och sjukvård. Att lägga till en kontrollsumma till en Codabar‑streckkod förbättrar avsevärt dataintegriteten genom att upptäcka transkriptionsfel innan de blir ett problem. I den här handledningen lär du dig **hur du lägger till kontrollsumma** när du genererar en Codabar‑streckkod med Aspose.BarCode för .NET, och du får se både Mod10‑ och Mod16‑kontrollsumma‑lägen i praktiken.

## Snabba svar
- **Vad betyder “lägga till kontrollsumma” för Codabar?** Det aktiverar fel‑detekterande siffror som validerar den kodade datan.
- **Vilka kontrollsumma‑lägen stöds?** Mod10 (vanligt) och Mod16 (för scenarier med högre noggrannhet).
- **Behöver jag en licens för att använda funktionen?** Ja, en giltig Aspose.BarCode för .NET‑licens krävs för produktionsbruk.
- **Vilka .NET‑versioner är kompatibla?** Biblioteket fungerar med .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Var kan jag hitta de genererade bilderna?** De sparas i den mapp du anger i variabeln `path`.

## Vad betyder “lägga till kontrollsumma” i Codabar?
Att lägga till en kontrollsumma innebär att konfigurera streckkodsgeneratorn så att den beräknar och lägger till en extra siffra (eller siffror) baserat på den data du tillhandahåller. Denna extra information verifieras av skannrar, vilket minskar risken för felaktiga avläsningar.

## Varför generera Codabar‑streckkod med kontrollsumma?
- **Förbättrad pålitlighet:** Upptäcker enkla teckenfel och de flesta transpositionsfel.
- **Efterlevnad:** Vissa branscher (t.ex. blodbanker) kräver streckkoder med kontrollsumma.
- **Flexibilitet:** Aspose.BarCode låter dig växla mellan Mod10 och Mod16 med en enda egenskapsändring.

## Förutsättningar

Innan vi går vidare, se till att du har följande:

1. **Aspose.BarCode för .NET** – ladda ner den senaste versionen från [here](https://releases.aspose.com/barcode/net/).  
2. **C#‑utvecklingsmiljö** – Visual Studio, VS Code eller någon IDE som stödjer .NET‑utveckling.

Nu när allt är på plats, låt oss gå igenom implementeringen.

## Importera namnrymder

Lägg till den nödvändiga namnrymden högst upp i din C#‑fil så att du kan komma åt klasserna för streckkodsgenerering:

```csharp
using Aspose.BarCode.Generation;
```

## Steg 1: Initiera streckkodsgeneratorn

Skapa en `BarcodeGenerator`‑instans, ange Codabar‑symbologi och tillhandahåll den data du vill koda. Kom ihåg att ersätta `"Your Directory Path"` med den faktiska mappen där du vill spara bilderna.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## Steg 2: Generera Codabar‑streckkod **utan** kontrollsumma

Om du behöver en enkel streckkod (utan kontrollsumma), sätt kontrollsummealternativet till `Default`. Detta är användbart för äldre system som inte förväntar sig en kontrollsiffra.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## Steg 3: Generera Codabar‑streckkod med **Mod10**‑kontrollsumma

Aktivera kontrollsumman och välj Mod10‑algoritmen. Detta är det vanligaste kontrollsumma‑läget för Codabar.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## Steg 4: Generera Codabar‑streckkod med **Mod16**‑kontrollsumma

För applikationer som kräver högre fel‑detekteringsförmåga, växla till Mod16. Kodändringen är minimal – uppdatera bara `CodabarChecksumMode`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

Med dessa fyra enkla steg har du lärt dig **hur du lägger till kontrollsumma** till Codabar‑streckkoder och hur du växlar mellan Mod10‑ och Mod16‑lägen med Aspose.BarCode för .NET.

## Vanliga problem och lösningar

| Problem | Orsak | Åtgärd |
|-------|--------|-----|
| Genererad bild är tom | `path` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller använd `Directory.CreateDirectory(path)` innan du sparar |
| Kontrollsumma ej tillämpad | `IsChecksumEnabled` lämnades som `Default` | Sätt `IsChecksumEnabled = EnableChecksum.Yes` innan du sparar |
| Fel kontrollsumma‑läge | Fel enum‑värde används | Använd `CodabarChecksumMode.Mod10` eller `CodabarChecksumMode.Mod16` efter behov |

## Slutsats

I den här guiden har vi gått igenom **hur du lägger till kontrollsumma** när du genererar en Codabar‑streckkod med Aspose.BarCode för .NET, demonstrerat både Mod10‑ och Mod16‑kontrollsumma‑lägen, samt förklarat varför streckkoder med kontrollsumma är avgörande för dataintegritet. Känn dig fri att experimentera med olika datasträngar och utforska det rika urvalet av anpassningsalternativ som Aspose erbjuder.

Om du stöter på några utmaningar är Aspose.BarCode‑communityn redo att hjälpa till på [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

## Vanliga frågor och svar

**Q: Kan jag använda Mod16‑kontrollsumma för bibliotekets bokstreckkoder?**  
A: Absolut. Mod16 ger starkare felupptäckt, vilket är fördelaktigt i högkapacitetsmiljöer som bibliotek.

**Q: Påverkar aktivering av kontrollsumma skanningshastigheten?**  
A: Den extra siffran tillför försumbar bearbetningstid; de flesta skannrar hanterar den utan märkbar fördröjning.

**Q: Hur verifierar jag kontrollsumman programatiskt?**  
A: Efter att ha genererat streckkoden kan du återberäkna kontrollsumman med samma `CodabarChecksumMode` och jämföra den med den sista tecknet i den kodade strängen.

**Q: Är det möjligt att anpassa utseendet på kontrollsiffra?**  
A: Ja. Använd `BarcodeGenerator`‑utseendeinställningarna (t.ex. `BarHeight`, `ForeColor`) för att styla hela streckkoden, inklusive kontrollsiffran.

**Q: Vad gör jag om jag måste generera flera streckkoder i en loop?**  
A: Instansiera en enda `BarcodeGenerator`, uppdatera egenskapen `CodeText` för varje iteration och anropa `Save` med ett unikt filnamn varje gång.

---

**Senast uppdaterad:** 2026-01-04  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}