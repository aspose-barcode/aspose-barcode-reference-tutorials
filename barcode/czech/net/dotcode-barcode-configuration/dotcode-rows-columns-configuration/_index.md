---
date: 2026-02-04
description: Naučte se, jak vytvořit obrázek čárového kódu DotCode nastavením řádků
  a sloupců pomocí Aspose.BarCode pro .NET.
linktitle: DotCode Rows and Columns Configuration
second_title: Aspose.BarCode .NET API
title: Vytvořit obrázek čárového kódu DotCode – řádky a sloupce (Aspose.BarCode)
url: /cs/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit obrázek čárového kódu DotCode – řádky a sloupce (Aspose.BarCode)

## Úvod

Vítejte ve světě generování čárových kódů s Aspose.BarCode pro .NET! V tomto průvodci **vytvoříte obrázky čárových kódů DotCode** a naučíte se jemně doladit řádky a sloupce tak, aby odpovídaly vašim přesným požadavkům. Ať už budujete systém označování ve zdravotnictví, aplikaci pro sledování logistiky, nebo jen experimentujete s 2D symbologií, zvládnutí této konfigurace vám poskytne přesnou kontrolu nad velikostí čárového kódu a kapacitou dat.

## Rychlé odpovědi
- **Co znamená „vytvořit obrázek čárového kódu DotCode“?** To znamená generovat vizuální soubor PNG/JPEG/atd., který kóduje vaše data pomocí 2‑D symbologie DotCode.  
- **Která knihovna zajišťuje generování?** Aspose.BarCode pro .NET poskytuje jednoduché API pro vytváření vysoce kvalitních obrázků DotCode.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkční použití je vyžadována komerční licence.  
- **Mohu přizpůsobit řádky a sloupce nezávisle?** Ano – můžete nastavit řádky, sloupce, nebo nechat knihovnu, aby je automaticky určila.  
- **Jaké výstupní formáty jsou podporovány?** PNG, JPEG, BMP, GIF, TIFF a další prostřednictvím `BarCodeImageFormat`.

## Co je obrázek čárového kódu DotCode?

DotCode je kompaktní 2‑dimenzionální čárový kód, který ukládá velké množství dat v malé čtvercové nebo obdélníkové oblasti. Je široce používán v sektorech **zdravotnictví** a **farmacie** pro sledování produktů, kódování informací o pacientech a další. Nastavením řádků a sloupců řídíte hustotu čárového kódu a jeho fyzické rozměry.

## Proč konfigurovat řádky a sloupce?

* Umístit čárový kód do omezeného prostoru štítku.  
* Optimalizovat spolehlivost skenování pro konkrétní tiskárny nebo skenery.  
* Vyvážit velikost obrázku vůči kapacitě dat – více řádků/sloupců znamená více dat, ale větší obrázek.  

Nyní, když rozumíte důvodu, pojďme projít **jak vytvořit obrázek čárového kódu DotCode** s vašimi vlastními nastaveními řádků a sloupců.

## Požadavky

1. **.NET vývojové prostředí** – Visual Studio, Rider nebo VS Code s nainstalovaným .NET SDK.  
2. **Aspose.BarCode pro .NET** – Stáhněte jej z oficiálního webu **[zde](https://releases.aspose.com/barcode/net/)**.  
3. **Platná licence** (nebo dočasná zkušební licence) pro produkční generování.  
4. **Základní znalost C#** – budete psát několik krátkých úryvků, ale koncepty jsou jednoduché.

## Importovat jmenné prostory

We only need one namespace for the examples:

```csharp
using Aspose.BarCode.Generation;
```

## Postupný průvodce vytvořením obrázku čárového kódu DotCode

### Krok 1: Nastavte cestu k adresáři

Nejprve rozhodněte, kam budou generované obrázky uloženy. Nahraďte zástupný text skutečnou složkou na vašem počítači.

```csharp
string path = "Your Directory Path";
```

> **Tip:** Použijte `Path.Combine(Environment.CurrentDirectory, "Barcodes")` k vytvoření cesty, která funguje napříč platformami.

### Krok 2: Inicializujte generátor DotCode

Vytvořte instanci `BarcodeGenerator`, zadejte symbologii `EncodeTypes.DotCode` a poskytněte data, která chcete kódovat (např. „Aspose“).

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // All configuration and saving will happen inside this block.
}
```

### Krok 3: Nastavte sloupce DotCode

Pokud chcete pevný počet sloupců, nastavte vlastnost `Columns`. Zde volíme **18 sloupců** a výsledek uložíme jako PNG soubor.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.Columns = 18;
gen.Save($"{path}DotCodeColumns18.png", BarCodeImageFormat.Png);
```

> **Proč XDimension?** Úprava velikosti pixelu mění vizuální hustotu každé tečky, aniž by ovlivnila kódovaná data.

### Krok 4: Nastavte řádky DotCode

Můžete také pevně nastavit počet řádků a nechat knihovnu rozhodnout o počtu sloupců (nastavením `Columns = -1`). Níže uvedený příklad vytvoří čárový kód s **12 řádky**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = -1;
gen.Parameters.Barcode.DotCode.Rows = 12;
gen.Save($"{path}DotCodeRows12.png", BarCodeImageFormat.Png);
```

### Krok 5: Nastavte řádky a sloupce současně

Když potřebujete plnou kontrolu, nastavte obě vlastnosti. Následující úryvek vytvoří čárový kód s **29 sloupci** a **26 řádky**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = 29;
gen.Parameters.Barcode.DotCode.Rows = 26;
gen.Save($"{path}DotCodeRows26Columns29.png", BarCodeImageFormat.Png);
```

> **Častý úskalí:** Nastavení jak řádků, tak sloupců na příliš vysoké hodnoty může vytvořit obrázek, který překročí typické rozměry štítku. Otestujte pomocí náhledu před tiskem.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Čárový kód je rozmazaný | XDimension je příliš nízký | Zvyšte `XDimension.Pixels` (např. 12‑15). |
| Skener nedokáže čárový kód přečíst | Řádky/Sloupce jsou příliš husté pro tiskárnu | Snižte řádky/sloupce nebo použijte tiskárnu s vyšším rozlišením. |
| Obrázek se neuložil | Neplatný řetězec `path` | Ujistěte se, že adresář existuje, nebo zavolejte `Directory.CreateDirectory(path)`. |

## Často kladené otázky

**Q: Jaké je maximální množství dat, které mohu uložit do čárového kódu DotCode?**  
A: Záleží na počtu řádků a sloupců, které nakonfigurujete. Více buněk znamená více dat, ale také větší obrázek.

**Q: Mohu změnit barvy čárového kódu?**  
A: Ano. Použijte `gen.Parameters.Barcode.ForeColor` a `BackColor` k nastavení vlastních barev před uložením.

**Q: Je symbologie DotCode podporována na všech platformách?**  
A: Aspose.BarCode pro .NET funguje na .NET Framework, .NET Core a .NET 5/6+, takže můžete generovat obrázky na Windows, Linuxu nebo macOS.

**Q: Kde najdu kompletní seznam všech parametrů DotCode?**  
A: Oficiální API reference poskytuje podrobnou dokumentaci – viz [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/).

**Q: Jak vygenerovat čárový kód ve webovém API bez zápisu na disk?**  
A: Zavolejte `gen.Save(Stream, BarCodeImageFormat.Png)` a vraťte stream jako výsledek souboru.

## Závěr

Nyní víte, jak **vytvořit obrázky čárových kódů DotCode** a přesně řídit jejich řádky a sloupce pomocí Aspose.BarCode pro .NET. Úpravou vlastností `Rows` a `Columns` můžete přizpůsobit velikost čárového kódu pro jakýkoli štítek nebo balení. Experimentujte s různými rozměry, barvami a výstupními formáty, aby vyhovovaly potřebám vašeho projektu, a prozkoumejte širší sadu funkcí Aspose.BarCode pro ještě větší přizpůsobení.

Pokud narazíte na jakékoli potíže nebo chcete jít hlouběji, podívejte se na oficiální zdroje:

* [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
* [Aspose.BarCode community support](https://forum.aspose.com/c/barcode/13)

---

**Last Updated:** 2026-02-04  
**Testováno s:** Aspose.BarCode for .NET 24.11 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}