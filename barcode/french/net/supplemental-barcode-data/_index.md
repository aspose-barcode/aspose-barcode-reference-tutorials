---
date: 2026-03-07
description: Apprenez à créer un code‑barres EAN‑2 et à générer des codes‑barres .NET
  avec Aspose.BarCode pour .NET. Maîtrisez dès aujourd’hui la personnalisation des
  données complémentaires du code‑barres.
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Créer un code‑barres EAN‑2 avec Aspose.BarCode pour .NET
url: /fr/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barcode EAN‑2 avec Aspose.BarCode pour .NET

## Introduction

Si vous êtes un développeur .NET cherchant à **créer un code‑barcode EAN‑2** et à exploiter la puissance des données de code‑barcode supplémentaires, vous êtes au bon endroit. Dans ce guide complet, nous vous accompagnerons pas à pas—de la configuration de base à l’ajustement fin de l’espace autour de vos symboles. Que vous construisiez un nouveau système d’inventaire ou que vous amélioriez une application de point de vente existante, maîtriser ces fonctionnalités rendra vos projets de génération de codes‑barcode .NET plus flexibles et fiables.

## Quick Answers
- **What can I generate?** EAN‑2 and EAN‑5 supplemental barcodes.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How much code is required?** Only a few lines—Aspose.BarCode handles the heavy lifting.  
- **Can I customize spacing?** Yes, you can control X‑dimension and supplement space directly.

## What is supplemental barcode data?

Les données de code‑barcode supplémentaires désignent les petits symboles additionnels (EAN‑2, EAN‑5) qui apparaissent à côté d’un code‑barcode principal, généralement utilisés pour les numéros d’édition, les extensions de prix ou d’autres informations auxiliaires. Aspose.BarCode pour .NET vous permet de générer ces symboles de manière programmatique, en vous offrant un contrôle total sur l’apparence et le positionnement.

## Why use Aspose.BarCode for .NET?

- **Full .NET integration** – works with C#, VB.NET, and F#.  
- **High‑quality rendering** – produces scannable barcodes at any resolution.  
- **Extensive customization** – from symbology type to X‑dimension, quiet zones, and supplement space.  
- **No external dependencies** – pure managed library, easy to deploy.

## Supplemental Barcode Data Configuration

Commençons par explorer la configuration des données de code‑barcode supplémentaires. Aspose.BarCode pour .NET vous offre les outils nécessaires pour générer ces codes sans effort, en vous donnant un contrôle complet sur les codes EAN‑2 et EAN‑5. Mais comment démarrer ?

Tout d’abord, téléchargez et installez Aspose.BarCode pour .NET. Vous pouvez essayer la version d’évaluation gratuite pour tester les fonctionnalités. Une fois installé, suivez notre guide pas à pas, qui vous conduira à travers le processus, afin que vous maîtrisiez la configuration des données de code‑barcode supplémentaires en toute simplicité.

À la fin de cette section, vous disposerez d’une compréhension solide de la création de codes‑barcode EAN‑2 et EAN‑5, vous rendant ainsi plus polyvalent en tant que développeur .NET.

## How to create EAN-2 barcode? (Configuration Steps)

1. **Instantiate the barcode generator** – choose the `BarcodeGenerator` class and set the symbology to `EncodeTypes.EAN13` (or another primary type).  
2. **Enable the supplemental part** – set the `SupplementData` property to the desired numeric string (e.g., `"12"` for an EAN‑2 supplement).  
3. **Adjust visual settings** – optionally modify `XDimension`, `BarHeight`, and `QuietZone` to match your layout requirements.  
4. **Save or render** – call `Save` to write the image to a file or stream.

> *Pro tip:* Keep the supplemental data length exactly 2 digits for EAN‑2 and 5 digits for EAN‑5; otherwise the barcode may become unreadable.

## Supplemental Barcode Space Customization

Dans le monde des codes‑barcode, la personnalisation est essentielle, et c’est là qu’Aspose.BarCode pour .NET excelle. Concentrons‑nous maintenant sur la personnalisation de l’espace des codes‑barcode supplémentaires. Il s’agit de contrôler la X‑Dimension et l’espace de supplément dans vos codes‑barcode.

Encore une fois, commencez par installer Aspose.BarCode pour .NET et profitez de l’essai gratuit. Ensuite, suivez nos instructions pour ajuster l’espace dans vos codes‑barcode. Cette personnalisation peut être extrêmement utile pour diverses applications, de la gestion d’inventaire aux systèmes de point de vente.

La liberté d’adapter vos codes‑barcode à vos besoins spécifiques est une compétence précieuse, et cette section vous assurera d’être parfaitement équipé.

## How to customize supplement space?

- **X‑Dimension** – defines the width of a single module; larger values increase overall barcode size.  
- **Supplement Space** – the gap between the primary barcode and the supplemental part; adjust via the `SupplementSpace` property.  
- **Quiet Zone** – the mandatory blank margin around the entire barcode; keep it at least 10 X‑Dimension units for reliable scanning.

Expérimentez ces paramètres dans un projet de test jusqu’à obtenir l’équilibre visuel requis pour votre matériel de lecture.

## Common Use Cases

| Scenario | Why supplemental data helps |
|----------|------------------------------|
| **Retail price extensions** | EAN‑5 can encode price information directly on the label. |
| **Magazine issue numbers** | EAN‑2 identifies the issue, allowing quick sorting. |
| **Logistics & tracking** | Adding a small supplement to a primary barcode gives extra routing data without expanding label size. |

## Supplemental Barcode Data Tutorials
### [Supplemental Barcode Data Configuration](./supplemental-barcode-data-configuration/)
Generate supplemental barcode data with Aspose.BarCode for .NET. Customize EAN-2 and EAN-5 barcodes effortlessly. Step-by-step guide for .NET developers.
### [Supplemental Barcode Space Customization](./supplemental-barcode-space-customization/)
Customize barcodes easily with Aspose.BarCode for .NET. Control X-Dimension and supplement space. Try the free trial!

## Frequently Asked Questions

**Q: Can I generate both EAN‑2 and EAN‑5 with the same code?**  
A: Yes. Simply change the `SupplementData` length (2 digits for EAN‑2, 5 digits for EAN‑5) and the library will render the correct symbology.

**Q: Do I need to calculate checksum values for the supplement?**  
A: No. Aspose.BarCode automatically computes and appends the required checksum for you.

**Q: Is there a limit to how many barcodes I can generate in a loop?**  
A: The library is optimized for bulk generation; just be mindful of memory usage when handling very large image collections.

**Q: How do I embed the barcode into a PDF or Word document?**  
A: Save the barcode as an image (PNG, JPEG, etc.) and then insert it using your preferred document generation API (e.g., Aspose.PDF or Aspose.Words).

**Q: What if my scanner cannot read the supplemental part?**  
A: Verify that the `SupplementSpace` is at least 2 X‑Dimension units and that the quiet zone meets the scanner’s specifications.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode for .NET 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}