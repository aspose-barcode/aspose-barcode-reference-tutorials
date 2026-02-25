---
date: 2026-02-25
description: Lär dig hur du skapar en streckkodbild och sparar den som PNG med Aspose.BarCode
  för .NET – ett komplett Aspose‑streckkodsexempel.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Generera streckkodbild – Code 93 med Aspose.BarCode
url: /sv/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkodbild – Endimensionell Code 93 med Aspose.BarCode

## Introduktion

I dagens digitala era har streckkoder blivit en integrerad del av våra liv och förenklar processer såsom lagerhantering, produktmärkning och försäljningsspårning. **Generering av en streckkodbild** är ofta det första steget för att integrera dessa identifierare i dina applikationer. Aspose.BarCode för .NET erbjuder ett robust, lätt‑använt API som låter dig skapa högkvalitativa Code 93‑streckkoder med bara några rader C#‑kod. Oavsett om du bygger ett lagersystem, en detaljhandelsapp eller ett anpassat rapportverktyg, guidar den här handledningen dig genom ett komplett **aspose barcode‑exempel** som visar hur du genererar, anpassar och **sparar streckkod‑PNG**‑filer.

## Snabba svar
- **Vad täcker handledningen?** Skapa och spara en Code 93‑streckkodbild med kontrollsumme‑hantering.  
- **Vilket bibliotek används?** Aspose.BarCode för .NET (senaste stabila versionen).  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag ändra utdataformatet?** Ja – du kan spara som PNG, JPEG, BMP osv. genom att ändra `BarCodeImageFormat`.  
- **Vad är minimikraven?** .NET Framework 4.6+ eller .NET Core 3.1+ samt Visual Studio.

## Vad är en Code 93‑streckkod?
Code 93 är en högdensitets, alfanumerisk symbologi som stöder hela ASCII‑teckenuppsättningen. Den väljs ofta för sin kompakta storlek och inbyggda kontrollsumma, vilket hjälper till att säkerställa dataintegritet vid skanning.

## Varför generera streckkodsbilder med Aspose.BarCode?
- **Full kontroll** över kodningstyp, kontrollsumma, storlek och bildformat.  
- **Inga externa beroenden** – biblioteket körs på vilken .NET‑plattform som helst.  
- **Utmärkt renderingskvalitet**, lämplig både för skärmvisning och högupplöst utskrift.  
- **Omfattande dokumentation** och ett stort antal exempel som påskyndar utvecklingen.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

1. **Visual Studio** (någon recent version).  
2. **Aspose.BarCode för .NET** installerat – du kan hämta det från den officiella nedladdningssidan.  
3. Grundläggande kunskap om **C#** och .NET‑projektstruktur.

Nu när du är klar, låt oss gå vidare till steg‑för‑steg‑guiden.

## Importera namnrymder

Först, importera de nödvändiga namnrymderna så att du kan komma åt klasserna för streckkodsgenerering.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Steg 1: Ange sökvägen till katalogen

Definiera var den genererade streckkodbilden ska sparas. Ersätt platshållaren med en giltig mapp på din maskin.

```csharp
string path = "Your Directory Path";
```

## Steg 2: Skapa en endimensionell Code 93‑streckkod

Instansiera en `BarcodeGenerator` med typen `Code93Extended` och den data du vill koda.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Steg 3: Aktivera kontrollsumma (valfritt)

Code 93 inkluderar en kontrollsumma som standard. Du kan växla den med egenskapen `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Steg 4: Spara streckkodsbilden (Spara streckkod PNG)

Generera bilden och spara den som en PNG‑fil i den mapp du angav tidigare.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Steg 5: Hantera undantag – Generera utan kontrollsumma

Om du behöver skapa en streckkod **utan** kontrollsumma, måste du hantera eventuella undantag som kan uppstå.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Vanliga problem och lösningar
- **Ogiltig sökväg** – säkerställ att katalogen finns och att applikationen har skrivbehörighet.  
- **Ej stödda tecken** – Code 93 stöder hela ASCII‑uppsättningen, men kontrolltecken kan orsaka fel.  
- **Licens ej angiven** – utan en giltig licens körs biblioteket i utvärderingsläge och kan lägga till ett vattenmärke.

## Vanliga frågor (FAQ)

### Q: Var kan jag hitta dokumentationen för Aspose.BarCode för .NET?
A: Du kan hitta dokumentationen på [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: Hur laddar jag ner Aspose.BarCode för .NET?
A: Du kan ladda ner Aspose.BarCode för .NET från webbplatsen på [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: Finns det en gratis provversion av Aspose.BarCode för .NET?
A: Ja, du kan få en gratis provversion av Aspose.BarCode för .NET från [here](https://releases.aspose.com/).

### Q: Hur kan jag köpa en licens för Aspose.BarCode för .NET?
A: Du kan köpa en licens på köpsidan på [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Var kan jag få support eller ställa frågor om Aspose.BarCode för .NET?
A: Du kan hitta ett community‑forum för support och diskussioner på [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-02-25  
**Testat med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}