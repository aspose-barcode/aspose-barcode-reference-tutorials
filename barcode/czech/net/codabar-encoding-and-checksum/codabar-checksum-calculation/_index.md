---
date: 2026-06-29
description: Naučte se, jak generovat čárový kód Codabar s kontrolním součtem pomocí
  Aspose.BarCode pro .NET. Podrobný návod krok za krokem pokrývající režimy kontrolního
  součtu Mod10 a Mod16.
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Výpočet kontrolního součtu pro Codabar
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generovat čárový kód Codabar s kontrolním součtem (Aspose.BarCode .NET)
url: /cs/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu Codabar s kontrolním součtem (Aspose.BarCode .NET)

Codabar je široce používaná lineární symbologie čárových kódů, využívaná v logistice, knihovnách a zdravotnictví. **Generování čárového kódu Codabar s kontrolním součtem** dramaticky zlepšuje integritu dat tím, že zachytí chyby při přepisu dříve, než způsobí problémy. V tomto tutoriálu se naučíte, jak přidat kontrolní součet při *generování čárového kódu Codabar* pomocí Aspose.BarCode pro .NET, a uvidíte oba režimy kontrolních součtů Mod10 a Mod16 v akci.

## Rychlé odpovědi
- **Co znamená „přidat kontrolní součet“ pro Codabar?** Přidává číslici pro detekci chyb, která ověřuje zakódovaná data.  
- **Jaké režimy kontrolních součtů jsou podporovány?** Mod10 (standard) a Mod16 (vyšší přesnost).  
- **Potřebuji licenci k použití této funkce?** Ano – pro produkční nasazení je vyžadována platná licence Aspose.BarCode pro .NET.  
- **Které verze .NET jsou kompatibilní?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kam se ukládají vygenerované obrázky?** Do složky, kterou určíte v proměnné `path`.

## Jak generovat čárový kód Codabar s kontrolním součtem?

Načtěte svá data, povolte kontrolní součet, vyberte buď `CodabarChecksumMode.Mod10` nebo `CodabarChecksumMode.Mod16` a zavolejte `Save`. Aspose.BarCode provede výpočet a automaticky připojí kontrolní číslici, takže získáte připravený obrázek k nascanování jedním voláním metody. Při ukládání můžete také zadat výstupní složku, název souboru a formát obrázku (např. PNG).

## Proč přidat kontrolní součet k čárovému kódu Codabar?

Přidání kontrolního součtu snižuje chyby jedné znaku až **o 99,9 %** a zachytí většinu transpozic, což je zásadní pro odvětví jako krevní banky, kde může jediná špatná číslice mít vážné následky. Také splňuje regulační požadavky mnoha logistických standardů.

## Požadavky

1. **Aspose.BarCode for .NET** – stáhněte nejnovější verzi [zde](https://releases.aspose.com/barcode/net/).  
2. **Vývojové prostředí C#** – Visual Studio, VS Code nebo jakékoli IDE podporující .NET.

Nyní, když je vše připraveno, projděme si implementaci.

## Importování jmenných prostorů

Třída `BarcodeGenerator` se nachází v jmenném prostoru `Aspose.BarCode.Generation`. Importujte ji na začátku souboru:

`using Aspose.BarCode.Generation;`

## Co je třída BarcodeGenerator?

Třída `BarcodeGenerator` je jádrový objekt Aspose.BarCode, který vytváří, konfiguruje a vykresluje obrázek čárového kódu. Zapouzdřuje všechna nastavení specifická pro čárový kód, jako jsou symbologie, text, velikost a možnosti kontrolního součtu, což vám umožňuje generovat obrázky jediným voláním `Save`. Úpravou její vlastnosti `Parameters` můžete přizpůsobit vzhled, režim kódování a funkce detekce chyb pro jakýkoli podporovaný typ čárového kódu.

## Krok 1: Inicializace generátoru čárových kódů

Vytvořte instanci `BarcodeGenerator`, zadejte symbologii Codabar a poskytněte data, která chcete zakódovat. Nahraďte `"Your Directory Path"` skutečnou složkou, kam chcete obrázky ukládat.

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## Krok 2: Generování čárového kódu Codabar **bez** kontrolního součtu

Pokud starší systém očekává prostý čárový kód, nastavte možnost kontrolního součtu na `Default`. Tím zakážete jakoukoli další číslici.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## Krok 3: Generování čárového kódu Codabar s kontrolním součtem **Mod10**

Povolte kontrolní součet a vyberte algoritmus Mod10, který je nejčastějším režimem pro Codabar.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## Krok 4: Generování čárového kódu Codabar s kontrolním součtem **Mod16**

Pro scénáře vyžadující vyšší detekci chyb přepněte na Mod16. Změna se omezuje na přiřazení jediné vlastnosti.

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

S těmito čtyřmi jednoduchými kroky jste se naučili **jak generovat čárový kód Codabar** s kontrolním součtem a jak přepínat mezi režimy Mod10 a Mod16 pomocí Aspose.BarCode pro .NET.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Vygenerovaný obrázek je prázdný | `path` ukazuje na neexistující složku | Ujistěte se, že adresář existuje, nebo před uložením zavolejte `Directory.CreateDirectory(path)` |
| Kontrolní součet nebyl aplikován | `IsChecksumEnabled` ponechán jako `Default` | Nastavte `IsChecksumEnabled = EnableChecksum.Yes` před uložením |
| Špatný režim kontrolního součtu | Použití nesprávné hodnoty enumu | Použijte `CodabarChecksumMode.Mod10` nebo `CodabarChecksumMode.Mod16` podle potřeby |

## Často kladené otázky

**Q: Mohu použít kontrolní součet Mod16 pro čárové kódy knih v knihovně?**  
**A:** Rozhodně. Mod16 poskytuje silnější detekci chyb, což je výhodné v prostředích s vysokým objemem, jako jsou knihovny.

**Q: Ovlivňuje povolení kontrolního součtu rychlost skenování?**  
**A:** Dodatečná číslice přidává zanedbatelný čas zpracování; většina skenerů ji zvládne bez znatelného zpoždění.

**Q: Jak mohu programově ověřit kontrolní součet?**  
**A:** Po vygenerování čárového kódu přepočítejte kontrolní součet pomocí stejného `CodabarChecksumMode` a porovnejte jej s posledním znakem zakódovaného řetězce.

**Q: Je možné přizpůsobit vzhled kontrolního součtu?**  
**A:** Ano. Použijte nastavení vzhledu `BarcodeGenerator` (např. `BarHeight`, `ForeColor`) k úpravě celého čárového kódu, včetně kontrolní číslice.

**Q: Co když potřebuji v cyklu generovat více čárových kódů?**  
**A:** Vytvořte jedinou instanci `BarcodeGenerator`, pro každou iteraci aktualizujte vlastnost `CodeText` a zavolejte `Save` s unikátním názvem souboru.

Pokud narazíte na jakékoli potíže, komunita Aspose.BarCode je připravena pomoci na [Aspose.BarCode fóru](https://forum.aspose.com/c/barcode/13).

**Poslední aktualizace:** 2026-06-29  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## Související tutoriály

- [Generování čárového kódu Codabar se start/stop znaky v Aspose.BarCode pro .NET](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Komplexní tutoriály a příklady Aspose.BarCode pro .NET](/barcode/net/)
- [Generování DataMatrix čárového kódu – profesionální průvodce s Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}