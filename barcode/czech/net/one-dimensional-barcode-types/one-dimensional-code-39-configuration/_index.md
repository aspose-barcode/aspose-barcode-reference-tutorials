---
date: 2026-02-25
description: Naučte se, jak generovat obrázky čárových kódů pomocí Aspose.BarCode
  pro .NET. Tento krok‑za‑krokem průvodce ukazuje, jak generovat čárové kódy Code 39
  s kontrolním součtem i bez něj.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Jak generovat čárový kód – konfigurace Code 39 s Aspose.BarCode
url: /cs/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

 "What the code does" -> "Co kód dělá"

Translate bullet points.

Translate "Common Issues and Solutions" etc.

Translate table headers: Issue, Why it Happens, Fix -> "Problém", "Proč se to děje", "Řešení"

Translate rows.

Translate FAQs.

Translate Q/A.

Translate Additional FAQs.

Translate Conclusion.

Translate "Last Updated", "Tested With", "Author".

Make sure not to translate code placeholders.

Also keep markdown formatting.

Let's produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jednorozměrná konfigurace Code 39

## Úvod

V tomto tutoriálu se naučíte **jak generovat obrázky čárových kódů**, konkrétně jednorozměrné čárové kódy Code 39, pomocí Aspose.BarCode pro .NET. Čárové kódy hrají klíčovou roli v moderních podnicích, od sledování zásob po umožnění rychlého a přesného získávání dat. Aspose.BarCode pro .NET je výkonná knihovna, která zjednodušuje generování a přizpůsobení čárových kódů v .NET aplikacích. Tento krok‑za‑krokem průvodce rozděluje proces na snadno stravitelné části, což zajišťuje, že i vývojáři noví v generování čárových kódů mohou postupovat bez problémů.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.BarCode pro .NET  
- **Mohu vytvořit čárový kód s kontrolním součtem?** Ano – nastavte `IsChecksumEnabled = EnableChecksum.Yes`  
- **Je kontrolní součet povinný?** Ne – můžete generovat čárový kód bez kontrolního součtu jeho vypnutím  
- **Jaký formát obrázku se používá v příkladech?** PNG (`BarCodeImageFormat.Png`)  
- **Potřebuji licenci pro vývoj?** Dočasná licence je k dispozici pro hodnocení  

## Co je generování čárových kódů s Aspose.BarCode?
Generování čárových kódů je proces převodu textových nebo číselných dat do strojově čitelného vizuálního vzoru. Aspose.BarCode pro .NET podporuje desítky symbologií, včetně Code 39, a umožňuje vám řídit vše od velikosti a barvy po výpočet kontrolního součtu.

## Proč použít Code 39 a možnosti kontrolního součtu?
Code 39 je široce používán v logistice a výrobě, protože kóduje alfanumerická data bez speciálních znaků. Přidání kontrolního součtu (nebo jeho vynechání) vám umožní vyvážit detekci chyb s jednoduchostí – ideální pro štítky zásob, přepravní štítky nebo jednoduché pokladní systémy.

## Předpoklady

Než se pustíme do práce, ujistěte se, že máte následující:

1. **Vývojové prostředí .NET** – základní znalost .NET frameworku a IDE, jako je Visual Studio. Pokud jste v .NET noví, začněte s oficiální dokumentací: [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode pro .NET** – stáhněte a nainstalujte knihovnu. Dokumentace a ke stažení jsou k dispozici zde: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) a [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/).

Nyní, když jsme pokryli předpoklady, přejděme k hlavním krokům tvorby jednorozměrných Code 39 čárových kódů.

## Jak generovat čárový kód: Importovat jmenné prostory
Pro práci s Aspose.BarCode pro .NET importujte potřebné jmenné prostory do svého projektu. Přidání těchto `using` příkazů vám poskytne přístup ke třídám pro generování čárových kódů.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Jak generovat Code 39 čárový kód (s kontrolním součtem a bez něj)

Níže vytvoříme dva čárové kódy: jeden **bez kontrolního součtu** a jeden **s kontrolním součtem**. Kód je identický, kromě příznaku `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**Co kód dělá**

1. **Vytvoří** instanci `BarcodeGenerator` s `EncodeTypes.Code39Extended` a řetězcem dat `"CODE"`.  
2. **Přepne** `IsChecksumEnabled`, aby určil, zda se přidá číslice kontrolního součtu.  
3. **Uloží** každý čárový kód jako PNG soubor do určené složky.

Nyní máte dva připravené obrázky čárových kódů: `OneCSCode39WithoutChecksum.png` a `OneCSCode39WithChecksum.png`.

## Časté problémy a řešení
| Problém | Proč se to děje | Řešení |
|-------|----------------|-----|
| **Souborová cesta nebyla nalezena** | Proměnná `path` ukazuje na neexistující složku. | Ujistěte se, že adresář existuje, nebo použijte `Directory.CreateDirectory(path)`. |
| **Neplatné znaky v datech** | Code 39 podporuje pouze alfanumerické znaky a několik speciálních symbolů. | Použijte rozšířený Code 39 (`Code39Extended`), který podporuje celý ASCII set, jak je ukázáno výše. |
| **Chyba kontrolního součtu** | Zapomenutí nastavit `IsChecksumEnabled`, když je vyžadován. | Explicitně nastavte příznak na `EnableChecksum.Yes` nebo `No` podle vašeho scénáře. |

## Často kladené otázky (FAQ):

### Q: Mohu použít Aspose.BarCode pro .NET s jinými programovacími jazyky?
A: Aspose.BarCode je primárně navržen pro .NET, ale Aspose nabízí knihovny čárových kódů i pro jiné platformy.

### Q: Existují licenční možnosti pro Aspose.BarCode pro .NET?
A: Ano, můžete prozkoumat licenční možnosti a požádat o dočasnou licenci na webu Aspose: [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### Q: Je Aspose.BarCode pro .NET vhodný pro webové aplikace?
A: Ano, Aspose.BarCode pro .NET lze použít ve webových aplikacích, což jej činí vhodným pro širokou škálu vývojových projektů.

### Q: Mohu přizpůsobit vzhled generovaných čárových kódů?
A: Rozhodně, můžete přizpůsobit různé aspekty čárového kódu, včetně velikosti, barev a fontů.

### Q: Kde mohu získat podporu nebo klást otázky o Aspose.BarCode pro .NET?
A: Odpovědi na vaše otázky a podporu najdete na fóru Aspose.BarCode: [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## Další často kladené otázky

**Q: Jaký je rozdíl mezi čárovým kódem s kontrolním součtem a bez něj?**  
A: Kontrolní součet přidává extra číslici, která pomáhá odhalit chyby při přepisování. Používejte jej, když je integrita dat kritická.

**Q: Jak velký může být vygenerovaný PNG?**  
A: Velikost se řídí pomocí `gen.Parameters.ImageWidth/Height`. Tyto vlastnosti upravte před voláním `Save`.

**Q: Mohu generovat čárové kódy v jiných formátech obrázků?**  
A: Ano, Aspose.BarCode podporuje JPEG, BMP, GIF, TIFF a další – stačí změnit výčet `BarCodeImageFormat`.

**Q: Existuje způsob, jak generovat čárové kódy ve webové aplikaci bez zápisu na disk?**  
A: Můžete uložit do `MemoryStream` a přímo vrátit pole bajtů klientovi.

## Závěr
Dodržením těchto jednoduchých kroků můžete **generovat obrázky čárových kódů** v .NET s plnou kontrolou nad zpracováním kontrolního součtu, formátem obrázku a vizuálním stylem. Ať už spravujete zásoby, zpracováváte objednávky nebo budujete webový portál s podporou čárových kódů, Aspose.BarCode pro .NET poskytuje spolehlivé a vývojářsky přívětivé řešení.

---

**Poslední aktualizace:** 2026-02-25  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}