---
date: 2026-02-25
description: Naučte se, jak vygenerovat obrázek čárového kódu a uložit čárový kód
  jako PNG pomocí Aspose.BarCode pro .NET – kompletní příklad Aspose čárového kódu.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Vytvořit obrázek čárového kódu – Code 93 s Aspose.BarCode
url: /cs/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

 sure to preserve markdown formatting.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu – jednorozměrný Code 93 s Aspose.BarCode

## Úvod

V dnešní digitální době se čárové kódy staly nedílnou součástí našeho života a zjednodušují procesy, jako je správa zásob, označování produktů a sledování prodeje na místě. **Generování obrázku čárového kódu** je často prvním krokem při integraci těchto identifikátorů do vašich aplikací. Aspose.BarCode pro .NET poskytuje robustní, snadno použitelný API, který vám umožní vytvořit vysoce kvalitní Code 93 čárové kódy během několika řádků C# kódu. Ať už budujete skladový systém, maloobchodní aplikaci nebo vlastní nástroj pro reportování, tento tutoriál vás provede kompletním **aspose barcode example**, který ukazuje, jak generovat, přizpůsobit a **uložit PNG čárového kódu** soubory.

## Rychlé odpovědi
- **Co tutoriál pokrývá?** Vytvoření a uložení obrázku čárového kódu Code 93 s ošetřením kontrolního součtu.  
- **Která knihovna je použita?** Aspose.BarCode pro .NET (nejnovější stabilní verze).  
- **Potřebuji licenci?** Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.  
- **Mohu změnit výstupní formát?** Ano – můžete uložit jako PNG, JPEG, BMP atd. změnou `BarCodeImageFormat`.  
- **Jaké jsou minimální požadavky?** .NET Framework 4.6+ nebo .NET Core 3.1+ a Visual Studio.

## Co je čárový kód Code 93?
Code 93 je vysoce hustá alfanumerická symbologie, která podporuje celý ASCII znakový soubor. Často se volí pro svou kompaktní velikost a vestavěný kontrolní součet, který pomáhá zajistit integritu dat během skenování.

## Proč generovat obrázky čárových kódů pomocí Aspose.BarCode?
- **Plná kontrola** nad typem kódování, kontrolním součtem, velikostí a formátem obrázku.  
- **Žádné externí závislosti** – knihovna běží na jakékoli .NET platformě.  
- **Vynikající kvalita vykreslování**, vhodná jak pro zobrazení na obrazovce, tak pro tisk ve vysokém rozlišení.  
- **Komplexní dokumentace** a velké množství příkladů, které urychlují vývoj.

## Požadavky

Předtím, než se ponoříme do kódu, ujistěte se, že máte následující:

1. **Visual Studio** (jakékoli nedávné vydání).  
2. **Aspose.BarCode pro .NET** nainstalovaný – můžete jej získat na oficiální stránce ke stažení.  
3. Základní znalost **C#** a struktury .NET projektů.

Nyní, když jste připraveni, přejděme k podrobnému návodu.

## Importovat jmenné prostory

Nejprve importujte požadované jmenné prostory, abyste mohli přistupovat ke třídám pro generování čárových kódů.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Krok 1: Nastavit cestu ke složce

Definujte, kam bude vygenerovaný obrázek čárového kódu uložen. Nahraďte zástupný text platnou složkou na vašem počítači.

```csharp
string path = "Your Directory Path";
```

## Krok 2: Vytvořit jednorozměrný čárový kód Code 93

Vytvořte instanci `BarcodeGenerator` s typem `Code93Extended` a daty, která chcete zakódovat.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Krok 3: Povolit kontrolní součet (volitelné)

Code 93 zahrnuje kontrolní součet ve výchozím nastavení. Můžete jej zapnout nebo vypnout pomocí vlastnosti `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Krok 4: Uložit obrázek čárového kódu (Uložit PNG čárového kódu)

Vygenerujte obrázek a uložte jej jako PNG soubor do složky, kterou jste určili výše.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Krok 5: Ošetření výjimek – Generování bez kontrolního součtu

Pokud potřebujete vytvořit čárový kód **bez** kontrolního součtu, musíte ošetřit možné výjimky, které mohou nastat.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Časté problémy a řešení
- **Neplatná cesta** – ujistěte se, že složka existuje a aplikace má oprávnění k zápisu.  
- **Není podporovaný znak** – Code 93 podporuje celý ASCII soubor, ale řídicí znaky mohou způsobit chyby.  
- **Licence není nastavena** – bez platné licence knihovna běží v režimu hodnocení a může přidat vodoznak.

## Často kladené otázky (FAQ)

### Q: Kde mohu najít dokumentaci pro Aspose.BarCode pro .NET?
A: Dokumentaci najdete na [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: Jak si mohu stáhnout Aspose.BarCode pro .NET?
A: Aspose.BarCode pro .NET můžete stáhnout z webu na adrese [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: Je k dispozici bezplatná zkušební verze pro Aspose.BarCode pro .NET?
A: Ano, bezplatnou zkušební verzi Aspose.BarCode pro .NET získáte [zde](https://releases.aspose.com/).

### Q: Jak mohu zakoupit licenci pro Aspose.BarCode pro .NET?
A: Licenci můžete zakoupit na stránce nákupu na adrese [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Kde mohu získat podporu nebo položit otázky ohledně Aspose.BarCode pro .NET?
A: Komunitní fórum pro podporu a diskuze najdete na [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}