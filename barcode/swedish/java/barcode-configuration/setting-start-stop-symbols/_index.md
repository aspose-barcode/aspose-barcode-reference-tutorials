---
date: 2025-12-17
description: Lär dig hur du skapar streckkodsbilder i Java och hur du ställer in symboler
  med Aspose.BarCode. Denna steg‑för‑steg‑guide visar hur du genererar en Codabar‑streckkod
  med anpassade start‑/stopp‑symboler.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Skapa streckkodbild i Java – Ställa in start‑ och stopp‑symboler
url: /sv/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild Java – Ställa in start- och stopp‑symboler

## Introduktion

I den här omfattande handledningen kommer du att **skapa streckkodbild java**‑filer med Aspose.BarCode för Java och lära dig **hur du ställer in symboler** för Codabar‑streckkoder. Oavsett om du bygger ett kassasystem, en logistikapplikation eller någon annan lösning som kräver pålitlig streckkodsgenerering, ger anpassning av start‑ och stopp‑symbolerna dig full kontroll över streckkodens format. Vi går igenom varje steg, förklarar varför varje inställning är viktig och visar hur du producerar en färdig‑att‑använda PNG‑bild.

## Snabba svar
- **Vilket bibliotek skapar streckkodsbilder i Java?** Aspose.BarCode för Java.
- **Kan jag anpassa start‑/stopp‑symboler?** Ja, med `setCodabarStartSymbol` och `setCodabarStopSymbol`.
- **Vilken streckkodstyp används i detta exempel?** CODABAR.
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑testanvändning.
- **Vilket utdataformat genereras?** PNG‑bild sparad till disk.

## Vad är “create barcode image java”?

Att generera en streckkodbild i Java betyder att programatiskt producera en visuell representation (vanligtvis PNG, JPG eller BMP) av en streckkodssymbologi som kan läsas av standardläsare. Aspose.BarCode tillhandahåller ett flytande API som abstraherar de lågnivå‑kodningsdetaljerna, så att du kan fokusera på affärslogiken.

## Varför använda Aspose.BarCode för att generera streckkod med Aspose?

Aspose.BarCode erbjuder:
- **Brett stöd för symbologier** (inklusive CODABAR, QR, DataMatrix osv.).
- **Fin‑granulär kontroll** över utseende, storlek och kodningsalternativ.
- **Plattformsoberoende kompatibilitet** med alla Java‑miljöer.
- **Inga externa beroenden**, vilket gör distributionen enkel.

## Förutsättningar

Innan vi dyker ner, se till att du har:

1. **Java Development Kit (JDK)** – Installera den senaste JDK:n från [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. **Aspose.BarCode för Java‑bibliotek** – Ladda ner det från [nedladdningslänken](https://releases.aspose.com/barcode/java/).

När dessa är på plats kan du **generera streckkodbild java** utan några saknade komponenter.

## Importera paket

I ditt Java‑projekt importerar du de nödvändiga klasserna för att arbeta med Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Steg‑för‑steg guide

### Steg 1: Definiera dokumentkatalogen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den absoluta eller relativa sökvägen där du vill spara streckkodbilden.

### Steg 2: Skapa Barcode Generator‑instans

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Här talar vi om för Aspose.BarCode att använda **CODABAR**‑symbologin och datasträngen `"12345678"`.

### Steg 3: Ställ in Codabar start‑symbol

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

Metoden `setCodabarStartSymbol` låter dig **hur du ställer in symboler** för starttecknet. I detta fall väljer vi `A`.

### Steg 4: Ställ in Codabar stopp‑symbol

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

På samma sätt definierar `setCodabarStopSymbol` stopp‑tecknet. Att använda `D` fullbordar CODABAR‑formatet som krävs av många äldre system.

### Steg 5: Spara den genererade bilden

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

`save`‑anropet skriver streckkoden till en PNG‑fil med namnet **startAndStopSymbols.png** i den katalog du angav tidigare.

### Vanliga fallgropar & tips

- **Felaktig katalogsökväg** – Säkerställ att `dataDir` slutar med en filseparator (`/` eller `\`) eller kombinera med `Paths.get`.
- **Ej stödda start‑/stopp‑symboler** – CODABAR stödjer endast A, B, C, D som start‑/stopp‑symboler. Att använda något annat värde ger ett undantag.
- **Licens ej tillämpad** – I testläge kan den genererade bilden innehålla ett vattenstämpel. Applicera din licens innan du går i produktion.

## Slutsats

Du har nu lärt dig hur du **skapar streckkodbild java**‑filer och exakt **hur du ställer in symboler** för en Codabar‑streckkod med Aspose.BarCode. Denna teknik ger dig flexibiliteten att uppfylla branschspecifika streckkodsspecifikationer samtidigt som din kod förblir ren och underhållbar.

Utforska ytterligare anpassningsalternativ—såsom att ändra färger, lägga till mänskligt läsbar text eller byta till andra symbologier—genom att konsultera den officiella API‑dokumentationen på [dokumentation](https://reference.aspose.com/barcode/java/).

## Vanliga frågor

### Kan jag använda Aspose.BarCode för Java i ett kommersiellt projekt?
Ja, det kan du. För kommersiell användning, överväg att köpa en licens [här](https://purchase.aspose.com/buy).

### Finns det en gratis provversion tillgänglig?
Ja, du kan prova en gratis provversion [här](https://releases.aspose.com/).

### Hur får jag support för Aspose.BarCode för Java?
Besök Aspose.BarCode‑forumet [här](https://forum.aspose.com/c/barcode/13) för support eller frågor.

### Hur skaffar jag en tillfällig licens?
Om det behövs kan du skaffa en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Finns det fler streckkodssymbologier som stöds av Aspose.BarCode för Java?
Ja, Aspose.BarCode stödjer ett brett utbud av streckkodssymbologier. Se dokumentationen för en komplett lista.

**Ytterligare Q&A**

**Q: Vilka bildformat kan jag exportera förutom PNG?**  
A: Aspose.BarCode stödjer PNG, JPEG, BMP, GIF och TIFF. Använd rätt filändelse i `save`‑metoden.

**Q: Kan jag generera streckkodsbilder i minnet utan att skriva till disk?**  
A: Ja, anropa `generator.save(OutputStream)` för att skriva direkt till en ström, vilket är användbart för webb‑svar.

**Q: Fungerar biblioteket på Android?**  
A: Java‑versionen är kompatibel med Android, men du måste inkludera de nödvändiga beroendena manuellt.

---

**Senast uppdaterad:** 2025-12-17  
**Testad med:** Aspose.BarCode för Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}