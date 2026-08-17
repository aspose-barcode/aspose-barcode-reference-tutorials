---
date: 2026-08-17
description: Zjistěte, jak vytvořit datamatrix čárový kód aspose pomocí Aspose.BarCode
  pro .NET – ideální pro generování čárových kódů, správu zásob a projekty generátoru
  čárových kódů v C#.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140 Konfigurace
og_description: Vytvořte datamatrix čárový kód aspose pomocí Aspose.BarCode pro .NET
  – rychlé, vysoce výkonné řešení pro správu zásob a projekty čárových kódů v C#.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Vytvořte datamatrix čárový kód aspose pomocí Aspose.BarCode pro .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Jak vytvořit datamatrix čárový kód aspose pomocí Aspose.BarCode
url: /cs/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit datamatrix čárový kód aspose pomocí Aspose.BarCode

V moderním softwaru pro řízení dodavatelského řetězce často potřebujete **vytvořit datamatrix čárový kód aspose** rychle a spolehlivě. Tento tutoriál vás provede generováním symbolu DataMatrix ECC 000‑140 pomocí Aspose.BarCode pro .NET, knihovny, která se stará o těžkou práci kódování, korekce chyb a vykreslování obrázků. Na konci průvodce budete mít připravený úryvek C#, který lze vložit do libovolného .NET projektu pro správu zásob.

## Rychlé odpovědi
- **Jaká je hlavní knihovna?** Aspose.BarCode for .NET  
- **Jaký typ čárového kódu je pokryt?** DataMatrix ECC 000‑140  
- **Jaký jazyk se používá?** C# (C Sharp)  
- **Potřebuji licenci?** A free trial is available; a license is required for production  
- **Typický čas implementace?** About 10‑15 minutes for a basic generator  

## Co je DataMatrix ECC 000‑140?
DataMatrix je dvourozměrný čárový kód, který ukládá velké objemy dat do kompaktního čtverce. Úroveň korekce chyb **ECC 000‑140** dokáže obnovit až 140 % poškozených kódových slov, což je ideální pro drsné skladové prostředí, kde mohou štítky být poškrábány nebo rozmazány.

## Proč zvolit Aspose.BarCode pro .NET?
Aspose.BarCode pro .NET poskytuje komplexní, výkonné API, které zjednodušuje tvorbu čárových kódů napříč mnoha symbologiemi, nabízí vestavěnou korekci chyb, automatické dimenzování a širokou podporu platforem, což z něj činí ideální řešení pro podnikovou správu zásob a označování.

- **Robustní API:** Zpracovává více než 30 symbologií čárových kódů a automaticky aplikuje pravidla kódování.  
- **Cross‑platform:** Běží na Windows, macOS a Linuxu bez nativních závislostí.  
- **Vysoký výkon:** Vygeneruje 200 × 200 pixelový DataMatrix za méně než 50 ms na typickém 2,5 GHz procesoru, což umožňuje vysokou propustnost značení.

## Předpoklady
1. **Visual Studio** – any recent edition (Community, Professional, or Enterprise).  
2. **Aspose.BarCode for .NET** – download it from the [download link](https://releases.aspose.com/barcode/net/). You can also visit [this link](https://releases.aspose.com/) for additional resources.  
3. **A .NET project** – ready to reference the Aspose.BarCode assembly.  

## Importovat jmenné prostory
Ve vašem souboru C# přidejte požadovanou direktivu using, abyste mohli přistupovat ke třídám čárových kódů.

```csharp
using Aspose.BarCode.Generation;
```

**Třída `BarcodeGenerator` je jádrovým motorem Aspose.BarCode pro vytváření obrázků čárových kódů.**  
**Třída `BarcodeGenerator` je jádrovým motorem Aspose.BarCode, který vytváří a konfiguruje obrázky čárových kódů.**  
```csharp
using Aspose.BarCode.Generation;
```

## Případ použití generování čárových kódů pro správu zásob
Představte si, že potřebujete označit tisíce palet v distribučním centru. Generováním DataMatrix ECC 000‑140 čárových kódů můžete vložit ID produktů, čísla šarží a datum expirace do jediného, odolného symbolu, který ruční skenery přečtou okamžitě, čímž snížíte chyby ručního zadávání až o 95 %.

## Jak vytvořit datamatrix čárový kód aspose v C#
Načtěte data, nakonfigurujte generátor a uložte obrázek – vše ve třech stručných krocích. `BarcodeGenerator` automaticky vybere optimální velikost modulu a použije úroveň korekce ECC 140, takže nemusíte sami počítat kontrolní součty, rychle a efektivně.

### Krok 1: definujte výstupní adresář
Vyberte složku, kam bude soubor PNG zapsán. Cesta musí existovat před voláním `Save`.

```csharp
string path = "Your Directory Path";
```

### Krok 2: vytvořte generátor čárového kódu
Instancujte `BarcodeGenerator`, nastavte symbologii na DataMatrix, poskytněte payload a vyberte nejvyšší úroveň korekce chyb.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

V tomto úryvku děláme:
* Vyberte **DataMatrix** jako typ čárového kódu.  
* Poskytněte ukázkovou hodnotu (`"Åspóse.Barcóde©"`).  
* Nastavte **XDimension** pro řízení velikosti modulu (zde 4 pixely).  
* Vyberte nejvyšší úroveň korekce chyb (**ECC 140**).  
* Uložte výstup jako PNG soubor.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Neplatná cesta** | Ensure `path` ends with a directory separator (`\` or `/`) and the folder exists. |
| **Ne podpořené znaky** | DataMatrix supports UTF‑8; avoid control characters and use proper encoding. |
| **Licence nebyla použita** | The `Aspose.BarCode.License` class applies a commercial license to unlock full functionality. Call it before generating any barcode. |

## Často kladené otázky

**Otázka: Mohu používat Aspose.BarCode pro .NET na Linuxových serverech?**  
A: Ano. Knihovna je plně multiplatformní a běží na .NET 5+, .NET 6+ a .NET Core na Linuxu bez dalších závislostí.

**Otázka: Jak knihovna zvládá velké dávky čárových kódů?**  
A: Můžete znovu použít jedinou instanci `BarcodeGenerator` ve smyčce; každé volání `Save` znovu vykreslí obrázek přibližně za 40‑60 ms, což je vhodné pro generování tisíců štítků za minutu.

**Otázka: Musím data kódovat ručně pro ECC 140?**  
A: Ne. Nastavení `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` automaticky použije správný algoritmus korekce chyb.

**Otázka: Je zkušební verze dostačující pro vývoj?**  
A: Bezplatná zkušební verze poskytuje plný přístup ke všem funkcím, včetně ECC 140, ale přidává vodoznak do generovaných obrázků. Pro produkci použijte licenci k odstranění vodoznaku.

**Otázka: Mohu přizpůsobit barvy čárového kódu?**  
A: Určitě. Použijte `generator.Parameters.Barcode.Color` a `generator.Parameters.Barcode.BackColor` pro přizpůsobení vaší značce.

---

**Last Updated:** 2026-08-17  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Související tutoriály

- [Jak generovat DataMatrix čárové kódy (ECC 200) pomocí Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Mistrovské kódování DataMatrix v ASCII pomocí Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Jak číst DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}