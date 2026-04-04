---
date: 2026-02-20
description: Lär dig hur du ändrar kantlinjen på ITF-14‑streckkoder med Aspose.BarCode
  för .NET. Denna guide täcker streckkodsgenerering med C# och ger praktiska exempel.
linktitle: ITF-14 Barcode Border Type Generation
second_title: Aspose.BarCode .NET API
title: Hur man ändrar kant – Generering av ITF-14 streckkodskanttyp
url: /sv/net/itf-14-barcode-customization/itf-14-barcode-border-type-generation/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ändrar kant – ITF-14 streckkod kanttypgenerering

I den här handledningen kommer du att upptäcka **hur man ändrar kant** för ITF-14 streckkoder med Aspose.BarCode för .NET. Oavsett om du bygger ett förpacknings‑etiketteringssystem eller behöver uppfylla specifika utskriftsstandarder är kontroll av kanttypen avgörande. Vi går igenom ett komplett, körbart exempel som visar **streckkodsgenerering med C#**, så att du kan generera ITF-14 streckkoder exakt på det sätt du behöver dem.

## Snabba svar
- **Vad påverkar “border type”?** Den bestämmer om streckkoden ritas utan kant, med en enkel stapel, en yttre stapel, en ram eller en ram med en yttre stapel.  
- **Vilket bibliotek används?** Aspose.BarCode for .NET.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag köra detta på .NET Core?** Ja, API:et är kompatibelt med .NET Core, .NET 5+ och .NET 6+.  
- **Hur många kodrader?** Mindre än 20 rader för att generera alla fem kantvarianter.

## Vad betyder “how to change border” i samband med ITF-14 streckkoder?
Att ändra kanten betyder att välja ett av `ITF14BorderType`‑alternativen (`None`, `Bar`, `BarOut`, `Frame`, `FrameOut`). Varje alternativ ändrar den visuella inramningen av streckkoden, vilket kan vara viktigt för skannerns läsbarhet och estetiska krav.

## Varför använda Aspose.BarCode för streckkodsgenerering med C#?
Aspose.BarCode erbjuder ett omfattande urval av anpassningsfunktioner—färger, storlekar, typsnitt och de kanttyper vi kommer att utforska—samtidigt som API:et är enkelt. Detta gör det idealiskt för utvecklare som behöver **generate ITF-14 barcode**‑bilder snabbt och pålitligt.

## Förutsättningar

Innan du börjar, se till att du har:

1. **Aspose.BarCode for .NET** – ladda ner det från den [website](https://releases.aspose.com/barcode/net/).  
2. En .NET‑utvecklingsmiljö (Visual Studio, Rider eller VS Code).  
3. Grundläggande kunskap om **C#**‑syntax.  
4. En giltig mappväg där de genererade PNG‑filerna sparas – ersätt `"Your Directory Path"` i koden med din egen plats.

## Importera namnrymder

Först, importera den nödvändiga namnrymden:

```csharp
using Aspose.BarCode;
```

## Steg‑för‑steg‑guide

### Steg 1: Skapa en `BarcodeGenerator`‑instans (generera itf-14 streckkod)

Vi börjar med att initiera generatorn med ITF‑14‑symbologin och data som ska kodas:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.ITF14, "12345678901231");
```

### Steg 2: Ställ in X‑Dimension (styr stapelbredden)

X‑Dimension definierar bredden på varje streckkodsstapel. Ett värde på 2 pixlar fungerar bra för de flesta etikettprinterar:

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Steg 3: Generera ITF‑14 streckkoder med olika kanttyper

Nedan följer fem **ITF‑14 streckkodsexempel** som illustrerar **how to change border**. Varje kodsnutt återanvänder samma `BarcodeGenerator`‑instans och byter bara `ItfBorderType`‑egenskapen.

#### ITF Border Type: None  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.None;
gen.Save($"{path}ITF14BorderNone.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: Bar  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.Bar;
gen.Save($"{path}ITF14BorderBar.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: BarOut  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.BarOut;
gen.Save($"{path}ITF14BorderBarOut.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: Frame  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.Frame;
gen.Save($"{path}ITF14BorderFrame.png", BarCodeImageFormat.Png);
```

#### ITF Border Type: FrameOut  

```csharp
gen.Parameters.Barcode.ITF.ItfBorderType = ITF14BorderType.FrameOut;
gen.Save($"{path}ITF14BorderFrameOut.png", BarCodeImageFormat.Png);
```

Varje `Save`‑anrop skriver en PNG‑bild till den katalog du angav, vilket ger dig en visuell referens för varje kantalternativ.

## Vanliga problem & tips

- **Path formatting** – Säkerställ att `path`‑variabeln slutar med ett bakstreck (`\`) på Windows eller ett snedstreck (`/`) på Linux/macOS.  
- **License exception** – Om du kör koden utan licens visas ett litet vattenstämpel på de genererade bilderna.  
- **Scanner compatibility** – Vissa skannrar ignorerar den yttre kanten; testa med din hårdvara för att avgöra vilken kanttyp som fungerar bäst.  
- **Pro tip:** Du kan kedja flera egenskapsändringar (färg, text osv.) innan du anropar `Save` för att skapa helt anpassade streckkoder i ett enda steg.

## Vanliga frågor

### Vad används ITF-14 streckkod för?
ITF-14 streckkoder används främst för produktförpackning och märkning inom detaljhandeln. De kodar information såsom produktens GTIN (Global Trade Item Number) och finns vanligtvis på kartonger och pallar.

### Kan jag anpassa utseendet på ITF-14 streckkoder med Aspose.BarCode?
Ja, Aspose.BarCode erbjuder omfattande anpassningsalternativ, inklusive möjlighet att ändra streckkodens kanttyp, färg och många andra visuella aspekter.

### Är Aspose.BarCode kompatibel med andra .NET‑ramverk?
Ja, Aspose.BarCode för .NET är kompatibel med olika .NET‑ramverk, inklusive .NET Core och .NET Standard, utöver det traditionella .NET Framework.

### Var kan jag hitta omfattande dokumentation för Aspose.BarCode för .NET?
Du kan hänvisa till dokumentationen [here](https://reference.aspose.com/barcode/net/) för detaljerad information och exempel på hur du använder Aspose.BarCode.

### Finns det en gratis provversion av Aspose.BarCode tillgänglig?
Ja, du kan få åtkomst till en gratis provversion av Aspose.BarCode för .NET från [here](https://releases.aspose.com/).

Om du har några frågor eller stöter på problem under implementeringen, tveka inte att kontakta Aspose.BarCode‑gemenskapen på deras [support forum](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-02-20  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}