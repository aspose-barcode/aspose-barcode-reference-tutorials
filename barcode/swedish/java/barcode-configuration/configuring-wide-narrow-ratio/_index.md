---
date: 2026-02-12
description: Lär dig hur du skapar code128‑streckkod med ett anpassat brett‑smalt‑förhållande
  i Java med Aspose.BarCode och genererar streckkod‑PNG‑bilder effektivt. Följ vår
  steg‑för‑steg‑guide.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Hur man skapar CODE_128-streckkod med bredd‑tunn förhållande i Java
url: /sv/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du CODE_128 streckkod med Wide‑Narrow Ratio i Java

## Introduktion

Om du behöver **create code128 barcode** med precisa visuella proportioner är justering av wide‑narrow ratio nyckeln. I den här handledningen går vi igenom en **step‑by‑step barcode**‑skapandeprocess med Aspose.BarCode för Java, visar hur du konfigurerar förhållandet, **generate barcode PNG**‑bilder och **save barcode image** till disk. Oavsett om du bygger lageretiketter, fraktsedlar eller någon applikation som kräver en anpassad CODE_128 streckkod, hittar du allt du behöver här.

## Snabba svar
- **What is the wide‑narrow ratio?** Den styr den relativa bredden på de breda staplarna jämfört med de smala staplarna i en streckkod.  
- **Which symbology supports ratio adjustment?** De flesta 1‑D‑symbologier, inklusive CODE_128, låter dig ange ett eget förhållande.  
- **Do I need a license?** En gratis provversion finns tillgänglig, men en kommersiell licens krävs för produktionsbruk.  
- **Can I generate a barcode image in PNG format?** Ja—använd `generator.save(...)` för att generate barcode PNG‑bilder.  
- **Is the code compatible with Java 8+?** Absolut; Aspose.BarCode fungerar med alla moderna Java‑versioner.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.BarCode för Java‑biblioteket. Ladda ner det från [download link](https://releases.aspose.com/barcode/java/).

## Importera paket

För att börja, importera den väsentliga Aspose.BarCode‑klassen till ditt projekt.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Vad är wide‑narrow ratio och varför justera det?

Wide‑narrow ratio bestämmer hur tjocka de “bredare” staplarna ser ut jämfört med de “smalare”. Att justera detta förhållande kan förbättra läsbarheten för skannrar, uppfylla specifika utskriftsstandarder eller helt enkelt matcha ett varumärkes visuella stil.

## Så skapar du code128 streckkod med wide‑narrow ratio i Java

Nedan följer en **step‑by‑step barcode**‑guide som går igenom varje steg i processen.

### Steg 1: Ange dokumentkatalog

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Se till att katalogen finns och att du har skrivrättigheter; detta är där filen för **save barcode image** kommer att placeras.

### Steg 2: Instansiera Barcode‑objekt

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Här **create code128 barcode** genom att skicka `EncodeTypes.CODE_128` till konstruktorn.

### Steg 3: Ställ in Wide‑Narrow Ratio

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

`setWideNarrowRatio`‑metoden låter dig finjustera det visuella avståndet. Ett värde på `3.0f` betyder att den breda stapeln är tre gånger så bred som en smal stapel.

### Steg 4: Spara bild till disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Genom att anropa `save` kommer **generate barcode image** och lagras som en PNG‑fil, vilket slutför steget **save barcode image**.

## Varför justera wide‑narrow ratio?

- **Scanner Compatibility:** Vissa skannrar föredrar ett förhållande mellan 2.0 och 3.0 för optimal läshastighet.  
- **Print Quality:** Att justera förhållandet kan kompensera för skrivarens DPI‑begränsningar och förhindra förvrängda staplar.  
- **Brand Consistency:** Vissa företag vill ha streckkoder som visuellt matchar företagets färger eller designriktlinjer.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Barcode looks distorted | Ratio too high/low for the printer | Adjust the value passed to `setWideNarrowRatio` (e.g., 2.0‑2.5). |
| File not created | Invalid `dataDir` path or insufficient permissions | Verify the directory path and ensure the application has write access. |
| Scanner cannot read barcode | Ratio outside recommended range for the symbology | Use standard ratios (2.0‑3.0) or test with the target scanner. |

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode med andra Java‑ramverk?**  
A: Ja, Aspose.BarCode är designat för att fungera sömlöst med Spring, Java EE, Android och andra Java‑miljöer.

**Q: Hur kan jag generera streckkoder med olika symbologier?**  
A: Ändra helt enkelt symbologitypen i `BarcodeGenerator`‑konstruktorn, till exempel `EncodeTypes.QR` för QR‑koder.

**Q: Finns det en provversion av Aspose.BarCode?**  
A: Ja, du kan komma åt den kostnadsfria provversionen [här](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.BarCode?**  
A: Se dokumentationen [här](https://reference.aspose.com/barcode/java/).

**Q: Hur får jag support för Aspose.BarCode?**  
A: Besök Aspose.BarCode‑forumet [här](https://forum.aspose.com/c/barcode/13) för support och community‑diskussioner.

---

**Senast uppdaterad:** 2026-02-12  
**Testad med:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}