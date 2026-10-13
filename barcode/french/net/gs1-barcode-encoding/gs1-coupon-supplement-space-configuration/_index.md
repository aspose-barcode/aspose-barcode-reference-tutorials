---
date: 2026-09-28
description: Apprenez comment créer un custom space de barcode pour les coupons GS1
  avec Aspose.BarCode for .NET et améliorer la lisibilité du barcode. Suivez notre
  guide étape par étape.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Configuration de l'espace du GS1 coupon supplement
og_description: Apprenez comment créer un custom space de barcode pour les coupons
  GS1 avec Aspose.BarCode for .NET et améliorer la lisibilité du barcode. Code étape
  par étape et astuces inclus.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Créer un custom space de barcode pour le GS1 coupon supplement – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Comment créer un custom space de barcode pour le GS1 coupon supplement
url: /fr/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuration de l'espace supplémentaire du coupon GS1

Dans ce tutoriel, vous allez **créer un espace personnalisé pour le code-barres** pour l'Espace Supplémentaire du Coupon GS1 en utilisant Aspose.BarCode pour .NET. Ajuster l'espace supplémentaire est essentiel lorsque vous devez **augmenter la lisibilité du code-barres** sur des scanners à basse résolution ou respecter les marges imposées par les détaillants. À la fin de ce guide, vous comprendrez pourquoi l'espace supplémentaire est important, comment le définir par programme, et comment générer des images avec différentes valeurs de pixels.

## Réponses rapides
- **À quoi sert l'espace supplémentaire ?** Il définit la zone blanche (en pixels) entre les données du coupon et le reste du code-barres.  
- **Quel type de code-barres est utilisé ?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Puis-je modifier la taille de l'espace ?** Oui – définissez `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` à n'importe quelle valeur entière.  
- **Ai-je besoin d'une licence pour cette fonctionnalité ?** Une licence temporaire fonctionne pour l'évaluation ; une licence complète est requise pour la production.  
- **Quels formats de sortie sont pris en charge ?** PNG, JPEG, BMP, GIF, TIFF, et plus via `BarCodeImageFormat`.

## Qu'est-ce que l'espace supplémentaire du coupon GS1 ?
L'Espace Supplémentaire du Coupon GS1 est une région blanche définie qui apparaît dans les codes-barres GS1‑Databar de coupons. Les systèmes de détail utilisent cet espace pour améliorer la fiabilité de la lecture et se conformer aux spécifications industrielles qui exigent une marge minimale autour des données supplémentaires.

## Pourquoi configurer l'espace supplémentaire ?
L'espace supplémentaire augmente directement **la lisibilité du code-barres** et vous aide à respecter les directives strictes des détaillants. En ajoutant des pixels supplémentaires, vous réduisez la probabilité d'erreurs de lecture sur les scanners à basse résolution, assurez une numérisation cohérente sur des tailles d'étiquettes diverses, et obtenez une flexibilité visuelle pour équilibrer le code-barres dans une mise en page imprimée.

## Prérequis

Avant de plonger dans la configuration de l'Espace Supplémentaire du Coupon GS1 avec Aspose.BarCode pour .NET, assurez‑vous d'avoir les éléments suivants :

1. **Visual Studio** – L'IDE principal pour le développement .NET.  
2. **Aspose.BarCode for .NET** – Téléchargez la bibliothèque depuis la [documentation Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework ou .NET 5+** – Une connaissance de C# et du runtime .NET est requise.

Maintenant que l'environnement est prêt, passons à l'implémentation.

## Importer les espaces de noms

L'espace de noms `Aspose.BarCode.Generation` contient la classe `BarcodeGenerator` et les paramètres associés.

```csharp
using Aspose.BarCode;
```

## Étape 1 : définir le chemin

Choisissez un dossier où les images générées seront enregistrées. Le chemin doit se terminer par le séparateur de répertoire approprié pour votre système d'exploitation.

```csharp
string path = "Your Directory Path";
```

## Étape 2 : générer la configuration de l'espace supplémentaire du coupon GS1

Le fragment suivant crée un code-barres, définit la dimension X et ajuste l'espace supplémentaire.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

Dans cet exemple, nous :

1. **Créer** une instance `BarcodeGenerator` pour le type `UpcaGs1DatabarCoupon`.  
2. **Définir** la dimension X à 2 pixels, ce qui détermine la largeur de la barre la plus étroite.  
3. **Ajuster** la propriété `SupplementSpace.Pixels` à 30 px, générer une image, puis répéter avec 50 px.  

N'hésitez pas à expérimenter d'autres valeurs de pixels pour correspondre à votre flux d'impression.

## Problèmes courants et astuces

- **Chemin invalide** – Assurez‑vous que la variable `path` se termine par une barre oblique inverse (`\`) ou une barre oblique (`/`) appropriée à votre OS.  
- **Permissions insuffisantes** – Exécutez Visual Studio en tant qu'administrateur ou choisissez un dossier où l'application a les droits d'écriture.  
- **Format de données incorrect** – La chaîne de données doit suivre la syntaxe GS1 (`(8110)` désigne l'identifiant du supplément).

## Pourquoi cela importe pour votre entreprise

Aspose.BarCode prend en charge **plus de 60 symbologies de code‑barres** et peut rendre des images jusqu'à **10 000 × 10 000 pixels** sans épuiser la mémoire. Pour les déploiements de détail à grande échelle, cela signifie que vous pouvez générer des coupons GS1 haute résolution en mode batch tout en maintenant le temps de traitement sous une seconde par image sur du matériel serveur typique.

## Questions fréquemment posées

**Q : Quel est le but de l'Espace Supplémentaire du Coupon GS1 dans les codes‑barres ?**  
R : Il ajoute une marge blanche obligatoire autour des données supplémentaires, améliorant la fiabilité du scanner et respectant les largeurs minimales spécifiées par les détaillants.

**Q : Puis‑je personnaliser la largeur de l'Espace Supplémentaire du Coupon GS1 avec Aspose.BarCode pour .NET ?**  
R : Oui, définissez `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` à n'importe quelle valeur entière ; la bibliothèque applique immédiatement le changement à l'image générée.

**Q : Où puis‑je trouver une documentation supplémentaire et du support pour Aspose.BarCode pour .NET ?**  
R : Consultez la [documentation Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/) et visitez le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pour l'aide de la communauté.

**Q : Aspose.BarCode pour .NET convient‑il aux débutants comme aux développeurs expérimentés ?**  
R : Absolument. L'API offre des méthodes simples pour les tâches rapides et des options avancées pour une génération de code‑barres fine‑tuned.

**Q : Puis‑je obtenir une licence temporaire pour Aspose.BarCode pour .NET afin d'évaluer ses fonctionnalités ?**  
R : Oui, demandez une licence d'essai sur le [site de licence temporaire Aspose](https://purchase.aspose.com/temporary-license/).

## Conclusion

En suivant les étapes ci‑dessus, vous savez maintenant comment **créer un espace personnalisé pour le code‑barres** pour l'Espace Supplémentaire du Coupon GS1, une technique clé pour **augmenter la lisibilité du code‑barres** et satisfaire les normes du commerce de détail. Intégrez le code dans vos solutions de numérisation existantes, expérimentez différentes valeurs de pixels, et explorez les autres types de code‑barres proposés par Aspose.BarCode pour .NET.

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Tutoriels associés

- [Générer un code‑barres Databar Aspose.BarCode avec l'API .NET – Configuration des lignes et colonnes](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Comment générer des codes‑barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}