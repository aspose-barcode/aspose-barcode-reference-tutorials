---
date: 2026-04-12
description: Lär dig hur du skapar Code128‑streckkod med tomma staplar i Java med
  Aspose.BarCode. Den här guiden visar dig hur du snabbt genererar streckkodsbilder
  i Java.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Generera streckkod med tomma staplar
second_title: Aspose.BarCode Java API
title: Hur man skapar Code128‑streckkod med tomma staplar i Java
url: /sv/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar Code128-streckkod med tomma staplar i Java

## Introduktion

Integrering av streckkodsgenerering i Java‑applikationer är ett vanligt krav, oavsett om du bygger lagerhanteringssystem, biljettplattformar eller kassasystem. Med **Aspose.BarCode for Java** kan du **skapa Code128‑streckkod**‑bilder med bara några rader kod. I den här handledningen går vi igenom stegen för att **generera streckkod Java**‑bilder som har tomma (ej fyllda) staplar, vilket ger dig full kontroll över streckkodens visuella stil.

## Snabba svar
- **Vilket bibliotek?** Aspose.BarCode for Java  
- **Primärt användningsområde?** Skapa Code128‑streckkoder med tomma staplar för anpassade UI‑designer  
- **Förutsättningar?** Java JDK 8+, Aspose.BarCode JAR, skrivbehörighet till en mapp för utdata‑bilden  
- **Typisk implementeringstid?** 5‑10 minuter för ett grundexempel  
- **Kan jag anpassa färger?** Ja – API‑et erbjuder omfattande stilalternativ  

## Vad är en Code128-streckkod?

Code128 är en högdensitets linjär streckkodssymbol som kodar hela ASCII‑teckenuppsättningen. Den används i stor utsträckning inom logistik, frakt och detaljhandel eftersom den kan representera alfanumerisk data kompakt. Som standard renderar Aspose.BarCode Code128‑staplar som solida rektanglar; genom att sätta egenskapen **FilledBars** till `false` blir de tomma (kontur) staplar, vilket är användbart för stilistisk varumärkesprofilering.

## Varför använda Aspose.BarCode för Java?

- **Rik funktionsuppsättning** – stöder över 50 streckkodstyper, inklusive QR, DataMatrix och PDF417.  
- **Inga externa beroenden** – en enda JAR fungerar på alla Java‑runtime.  
- **Finjusterad kontroll** – du kan justera stapelbredd, färger, typsnitt och egenskapen `FilledBars`.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS utan inhemska bibliotek.

## Förutsättningar

Innan du börjar, se till att du har:

1. **Java‑utvecklingsmiljö** – JDK 8 eller senare installerad och `JAVA_HOME` konfigurerad.  
2. **Aspose.BarCode för Java** – ladda ner den senaste JAR‑filen från [download page](https://releases.aspose.com/barcode/java/).  
3. **Dokumentkatalog** – en mapp på din dator där den genererade streckkodsbilden kommer att sparas.

## Importera paket

I ditt Java‑projekt importerar du de klasser du behöver för att arbeta med Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Dessa importeringar ger dig åtkomst till streckkodsgeneratorn, bildformat‑enumerationen och felhantering.

## Steg 1: Ställ in resurskatalogen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den absoluta sökvägen till mappen du skapade i förutsättningarna. Detta är där PNG‑filen kommer att skrivas.

## Steg 2: Skapa en Code128‑streckkodsgenerator‑instans

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Här instansierar vi `BarcodeGenerator` med **CODE_128**‑symbologi och exempeltexten `"TEXT"`. Detta är ett **barcode generator Java‑exempel** som du kan anpassa till vilken sträng du än behöver koda.

## Steg 3: Sätt egenskapen FilledBars till false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Genom att sätta `FilledBars` till `false` kommer den genererade streckkoden att visa tomma staplar istället för solida, vilket ger den visuella effekt vi eftersträvar.

## Steg 4: Spara streckkodsbilden

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

`save`‑metoden skriver streckkoden till den angivna katalogen i PNG‑format. Du kan ändra `BarCodeImageFormat.PNG` till `JPG`, `BMP` eller `TIFF` om en annan bildtyp krävs.

## Vanliga användningsfall

- **Anpassad varumärkesprofilering** – tomma staplar kan överlagras med bakgrundsmönster eller färger.  
- **Utskriftsklara resurser** – generera högupplösta PNG‑filer för inkludering i fakturor eller fraktetiketter.  
- **Dynamisk generering** – skapa streckkoder i realtid i webb‑tjänster eller skrivbordsapplikationer.

## Felsökningstips

- **Ogiltig sökväg** – säkerställ att `dataDir` slutar med en filseparator (`/` eller `\\`) eller sammanfoga med `File.separator`.  
- **Licens krävs** – en provversion fungerar för utvärdering, men en full licens behövs för produktion.  
- **Ej stödda tecken** – Code128 stöder hela ASCII‑uppsättningen; undvik Unicode‑tecken om du inte byter till en annan symbologi.

## Slutsats

Du har nu lärt dig hur du **skapar Code128‑streckkod**‑bilder med tomma staplar med hjälp av Aspose.BarCode för Java. Detta enkla tillvägagångssätt låter dig snabbt generera anpassningsbara streckkodsgrafiker, oavsett om du bygger ett skrivbordsinventeringsverktyg eller ett molnbaserat API.

## Vanliga frågor

### Är Aspose.BarCode kompatibel med alla Java‑utvecklingsmiljöer?
Ja, Aspose.BarCode är utformat för att sömlöst integreras med alla Java‑IDE‑er eller byggsystem, inklusive Maven, Gradle och vanliga JAR‑projekt.

### Kan jag anpassa utseendet på den genererade streckkoden?
Absolut! Förutom `FilledBars` kan du ändra färger, stapelbredd, marginaler och till och med lägga till mänskligt läsbar text med det omfattande API‑et.

### Finns en provversion av Aspose.BarCode tillgänglig?
Ja, du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis provversion [här](https://releases.aspose.com/).

### Hur kan jag få support för Aspose.BarCode?
För frågor eller hjälp, besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Var kan jag hitta detaljerad dokumentation för Aspose.BarCode?
Den omfattande dokumentationen finns tillgänglig [här](https://reference.aspose.com/barcode/java/).

**Ytterligare frågor**

**Q: Hur genererar jag en streckkodsbild i ett annat format, till exempel JPEG?**  
A: Ändra det andra argumentet i `save` till `BarCodeImageFormat.JPEG`.

**Q: Kan jag generera flera streckkoder i en loop?**  
A: Ja – instansiera en ny `BarcodeGenerator` inom din loop eller återanvänd samma instans med en ny `CodeText`.

---

**Senast uppdaterad:** 2026-04-12  
**Testat med:** Aspose.BarCode for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}