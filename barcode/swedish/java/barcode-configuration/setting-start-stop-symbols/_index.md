---
date: 2026-02-17
description: Lär dig hur du använder Aspose Barcode Java för att skapa streckkodsbilder,
  ställa in CODABAR:s start- och stopptecken och generera PNG-filer utan vattenstämplar.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – Skapa streckkodsbild med start-/stopp‑symboler
url: /sv/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Skapa streckkodbild med start-/stopp‑symboler

## Introduction

I den här omfattande handledningen kommer du att **create barcode image java** filer med **Aspose Barcode Java** och lära dig **how to set symbols** för Codabar‑streckkoder. Oavsett om du bygger ett kassasystem, en logistikapplikation eller någon lösning som kräver pålitlig streckkodsgenerering, ger anpassning av start‑ och stopp‑symbolerna dig full kontroll över streckkodformatet. Vi går igenom varje steg, förklarar varför varje inställning är viktig och visar hur du producerar en färdig‑att‑använda PNG‑bild—utan provvattenstämpel.

## Quick Answers
- **Vilket bibliotek skapar streckkodsbilder i Java?** Aspose.BarCode for Java.  
- **Kan jag anpassa start-/stopp‑symboler?** Ja, med `setCodabarStartSymbol` och `setCodabarStopSymbol`.  
- **Vilken streckkodstyp används i detta exempel?** CODABAR.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑trial use.  
- **Vilket utdataformat genereras?** PNG image saved to disk.

## What is Aspose Barcode Java?

Aspose Barcode Java är ett kraftfullt, beroende‑fritt bibliotek som låter dig generera ett brett spektrum av streckkodssymbologier programatiskt. Det abstraherar den lågnivå‑kodningslogiken, så att du kan fokusera på affärsregler samtidigt som du säkerställer att resultatet uppfyller branschstandarder.

## Why Use Aspose Barcode Java for Barcode Generation Without Watermark?

- **Ingen vattenstämpel i produktion** – när du applicerar en giltig licens är bilderna rena.  
- **Omfattande symbologistöd** – från klassiska 1D‑koder som CODABAR till 2D‑koder som QR och DataMatrix.  
- **Fin‑granulär kontroll** – du kan ställa in start-/stopp‑symboler, färger, storlekar och till och med generera bilder direkt till strömmar för webbappar.  
- **Plattformsoberoende** – fungerar på alla Java‑runtime‑miljöer, inklusive Android (med manuell beroendehantering).

## Prerequisites

Innan vi dyker ner, se till att du har:

1. **Java Development Kit (JDK)** – Installera den senaste JDK:n från [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Ladda ner den från [download link](https://releases.aspose.com/barcode/java/).

Att ha dessa redo säkerställer att du kan **generate barcode image java** utan några saknade komponenter.

## Import Packages

I ditt Java‑projekt importerar du de nödvändiga klasserna för att arbeta med Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Step‑by‑Step Guide

### Step 1: Define the Document Directory

Ersätt `"Your Document Directory"` med den absoluta eller relativa sökvägen där du vill spara streckkodsbilden. Kom ihåg att avsluta sökvägen med rätt filseparator (`/` eller `\`) eller använd `Paths.get` för plattformsoberoende hantering.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Barcode Generator Instance

Här instruerar vi Aspose.BarCode att använda **CODABAR**‑symbologi och datat strängen `"12345678"`.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Step 3: Set Codabar Start Symbol

`setCodabarStartSymbol`‑metoden låter dig **set barcode symbols** för starttecknet. I detta fall väljer vi `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Step 4: Set Codabar Stop Symbol

På samma sätt definierar `setCodabarStopSymbol` stopptecknet. Genom att använda `D` fullbordas CODABAR‑formatet som krävs av många äldre system.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Step 5: Save the Generated Image

`save`‑anropet skriver streckkoden till en PNG‑fil med namnet **startAndStopSymbols.png** i den katalog du angav tidigare.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Common Pitfalls & Tips

- **Felaktig katalogsökväg** – Se till att `dataDir` slutar med en filseparator (`/` eller `\`) eller sammanfoga med `Paths.get`.  
- **Ej stödda start-/stopp‑symboler** – CODABAR stöder endast `A`, `B`, `C`, `D` som start-/stopp‑symboler. Att använda något annat värde kommer att kasta ett undantag.  
- **Licens ej tillämpad** – I provläge kan den genererade bilden innehålla en vattenstämpel. Applicera din licens innan du distribuerar till produktion för att uppnå **barcode generation without watermark**.

## Frequently Asked Questions

### Can I use Aspose.BarCode for Java in a commercial project?
Ja, det kan du. För kommersiell användning, överväg att köpa en licens [here](https://purchase.aspose.com/buy).

### Is there a free trial available?
Ja, du kan utforska en gratis provversion [here](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode for Java?
Besök Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13) för support eller frågor.

### How do I obtain a temporary license?
Om behövs kan du skaffa en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Are there more barcode symbologies supported by Aspose.BarCode for Java?
Ja, Aspose.BarCode stöder ett brett spektrum av streckkodssymbologier. Se dokumentationen för en komplett lista.

## Additional Q&A (AI‑Friendly)

**Q:** Vilka bildformat kan jag exportera förutom PNG?  
**A:** Aspose.BarCode stöder PNG, JPEG, BMP, GIF och TIFF. Använd rätt filändelse i `save`‑metoden.

**Q:** Kan jag generera streckkodsbilder i minnet utan att skriva till disk?  
**A:** Ja, anropa `generator.save(OutputStream)` för att skriva direkt till en ström, vilket är idealiskt för webb‑svar.

**Q:** Fungerar biblioteket på Android?  
**A:** Java‑versionen är kompatibel med Android, men du måste inkludera de nödvändiga beroendena manuellt.

## Conclusion

Du har nu lärt dig hur du **create barcode image java** filer och exakt **set barcode symbols** för en Codabar‑streckkod med **Aspose Barcode Java**. Denna teknik ger dig flexibiliteten att uppfylla branschspecifika streckkodsspecifikationer samtidigt som din kod förblir ren och underhållbar. Utforska ytterligare anpassningsalternativ—såsom att ändra färger, lägga till mänskligt läsbar text eller byta till andra symbologier—genom att konsultera den officiella API‑dokumentationen på [documentation](https://reference.aspose.com/barcode/java/).

---

**Senast uppdaterad:** 2026-02-17  
**Testad med:** Aspose.BarCode for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}