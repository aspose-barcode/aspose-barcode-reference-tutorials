---
date: 2026-04-12
description: Naučte se, jak vytvořit čárový kód Code128 s prázdnými pruhy v Javě pomocí
  Aspose.BarCode. Tento průvodce vám ukáže, jak rychle generovat obrázky čárových
  kódů v Javě.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Generování čárového kódu s prázdnými pruhy
second_title: Aspose.BarCode Java API
title: Jak vytvořit čárový kód Code128 s prázdnými pruhy v Javě
url: /cs/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód Code128 s prázdnými pruhy v Javě

## Úvod

Integrace generování čárových kódů do Java aplikací je častým požadavkem, ať už vytváříte systémy správy zásob, platformy pro prodej vstupenek nebo řešení pokladen. S **Aspose.BarCode for Java** můžete **create Code128 barcode** obrázky vytvořit během několika řádků kódu. V tomto tutoriálu projdeme kroky k **generate barcode Java** obrázkům, které obsahují prázdné (nevyplněné) pruhy, což vám poskytne plnou kontrolu nad vizuálním stylem čárového kódu.

## Rychlé odpovědi
- **Which library?** Aspose.BarCode for Java  
- **Primary use case?** Creating Code128 barcodes with empty bars for custom UI designs  
- **Prerequisites?** Java JDK 8+, Aspose.BarCode JAR, write access to a folder for the output image  
- **Typical implementation time?** 5‑10 minutes for a basic example  
- **Can I customize colors?** Yes – the API provides extensive styling options  

## Co je čárový kód Code128?

Code128 je vysoce hustá lineární čárová kódová symbologie, která kóduje celý ASCII znakový soubor. Je široce používána v logistice, přepravě a maloobchodu, protože může kompaktně představovat alfanumerická data. Ve výchozím nastavení Aspose.BarCode vykresluje pruhy Code128 jako plné obdélníky; nastavení vlastnosti **FilledBars** na `false` je převádí na prázdné (obrysové) pruhy, což je užitečné pro stylové značkování.

## Proč používat Aspose.BarCode pro Java?

- **Rich feature set** – podporuje více než 50 typů čárových kódů, včetně QR, DataMatrix a PDF417.  
- **No external dependencies** – jeden JAR funguje na jakémkoli Java runtime.  
- **Fine‑grained control** – můžete upravit šířku pruhu, barvy, písma a vlastnost `FilledBars`.  
- **Cross‑platform** – funguje na Windows, Linuxu a macOS bez nativních knihoven.

## Předpoklady

Před začátkem se ujistěte, že máte:

1. **Java Development Environment** – nainstalovaný JDK 8 nebo novější a nastavená proměnná `JAVA_HOME`.  
2. **Aspose.BarCode for Java** – stáhněte nejnovější JAR ze [stránky ke stažení](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – složka ve vašem počítači, kam bude uložen vygenerovaný obrázek čárového kódu.

## Import balíčků

Ve vašem Java projektu importujte třídy, které budete potřebovat pro práci s Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Tyto importy vám poskytují přístup k generátoru čárových kódů, výčtu formátů obrázků a zpracování výjimek.

## Krok 1: Nastavte adresář zdrojů

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní cestou k složce, kterou jste vytvořili v předchozích předpokladech. Zde bude zapsán soubor PNG.

## Krok 2: Vytvořte instanci generátoru čárového kódu Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Zde vytvoříme instanci `BarcodeGenerator` se symbologií **CODE_128** a ukázkovým textem `"TEXT"`. Jedná se o **barcode generator Java example**, který můžete přizpůsobit libovolnému řetězci, který potřebujete zakódovat.

## Krok 3: Nastavte vlastnost FilledBars na False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Nastavením `FilledBars` na `false` bude vygenerovaný čárový kód zobrazovat prázdné pruhy místo plných, čímž dosáhnete požadovaného vizuálního efektu.

## Krok 4: Uložte obrázek čárového kódu

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Metoda `save` zapíše čárový kód do určeného adresáře ve formátu PNG. Pokud je potřeba jiný typ obrázku, můžete změnit `BarCodeImageFormat.PNG` na `JPG`, `BMP` nebo `TIFF`.

## Běžné případy použití

- **Custom branding** – prázdné pruhy lze překrýt vzory nebo barvami pozadí.  
- **Print‑ready assets** – generujte vysoce rozlišené PNG pro zařazení do faktur nebo přepravních štítků.  
- **Dynamic generation** – vytvářejte čárové kódy za běhu ve webových službách nebo desktopových aplikacích.

## Tipy pro řešení problémů

- **Invalid path** – ujistěte se, že `dataDir` končí souborovým oddělovačem (`/` nebo `\\`) nebo jej spojte pomocí `File.separator`.  
- **License required** – zkušební verze funguje pro hodnocení, ale pro produkci je potřeba plná licence.  
- **Unsupported characters** – Code128 podporuje celý ASCII soubor; vyhněte se Unicode znakům, pokud nepřejdete na jinou symbologii.

## Závěr

Teď jste se naučili, jak **create Code128 barcode** obrázky s prázdnými pruhy pomocí Aspose.BarCode for Java. Tento jednoduchý přístup vám umožní rychle generovat přizpůsobitelné grafiky čárových kódů, ať už vytváříte desktopový nástroj pro inventuru nebo cloud‑based API.

## Často kladené otázky

### Je Aspose.BarCode kompatibilní se všemi vývojovými prostředími Java?

Ano, Aspose.BarCode je navržen tak, aby se bez problémů integroval s jakýmkoli Java IDE nebo systémem pro sestavení, včetně Maven, Gradle a jednoduchých JAR projektů.

### Mohu přizpůsobit vzhled vygenerovaného čárového kódu?

Rozhodně! Kromě `FilledBars` můžete měnit barvy, šířku pruhu, okraje a dokonce přidat lidsky čitelný text pomocí rozsáhlého API.

### Je k dispozici zkušební verze Aspose.BarCode?

Ano, můžete prozkoumat možnosti Aspose.BarCode získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Jak mohu získat podporu pro Aspose.BarCode?

Pro jakékoli dotazy nebo pomoc navštivte [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Kde najdu podrobnou dokumentaci pro Aspose.BarCode?

Komplexní dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

**Další otázky**

**Q: Jak mohu vygenerovat obrázek čárového kódu v jiném formátu, například JPEG?**  
A: Změňte druhý argument metody `save` na `BarCodeImageFormat.JPEG`.

**Q: Mohu generovat více čárových kódů ve smyčce?**  
A: Ano – vytvořte novou instanci `BarcodeGenerator` uvnitř smyčky nebo znovu použijte stejnou instanci s novým `CodeText`.

---

**Poslední aktualizace:** 2026-04-12  
**Testováno s:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}