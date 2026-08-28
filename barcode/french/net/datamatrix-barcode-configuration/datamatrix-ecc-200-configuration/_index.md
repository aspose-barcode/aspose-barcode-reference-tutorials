---
date: 2026-08-02
description: Apprenez à créer un code-barres DataMatrix, générer datamatrix, et explorer
  la high density barcode generation avec Aspose.BarCode pour les projets .NET.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Configuration DataMatrix ECC 200
og_description: Créer un code-barres DataMatrix avec Aspose.BarCode pour .NET. Ce
  tutoriel montre la high density barcode generation, le temporary Aspose license
  setup, et le step‑by‑step C# code.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Créer un code-barres DataMatrix – guide Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Comment créer un code-barres DataMatrix (ECC 200) avec Aspose.BarCode pour
  .NET
url: /fr/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET

## Introduction

Dans ce guide, vous **créerez un code-barres DataMatrix** (ECC 200) en utilisant Aspose.BarCode pour .NET. Que vous construisiez un suivi d’inventaire, un système de point de vente, ou que vous automatisiez des flux de travail de documents, un code-barres à haute densité peut stocker beaucoup de données dans un espace minuscule. Nous passerons en revue chaque étape de configuration, expliquerons pourquoi chaque paramètre est important, et vous fournirons des extraits C# prêts à l’emploi.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour DataMatrix en .NET ?** Aspose.BarCode for .NET  
- **Quel niveau ECC fournit ECC 200 ?** Correction d’erreurs à haute densité pour une lecture robuste.  
- **Ai‑je besoin d’une licence pour exécuter l’exemple ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Puis‑je générer du PNG, JPEG ou TIFF ?** Oui – la méthode `Save` prend en charge plusieurs formats d’image.

## Qu’est‑ce que DataMatrix ECC 200 ?

DataMatrix ECC 200 est un code‑barres bidimensionnel à haute densité qui peut stocker jusqu’à 2 335 caractères alphanumériques ou 1 556 octets de données binaires dans un motif carré ou rectangulaire compact. Il utilise la correction d’erreurs Reed‑Solomon pour récupérer les modules perdus ou endommagés, ce qui le rend idéal pour des applications telles que le marquage de pièces aérospatiales, l’étiquetage pharmaceutique et la logistique où la fiabilité est cruciale.

## Pourquoi utiliser la génération de code‑barres Aspose ?

Aspose.BarCode prend en charge **plus de 30 symbologies**, peut rendre des images jusqu’à 10 000 × 10 000 px sans charger le fichier complet en mémoire, et fournit une sortie déterministe sur Windows, Linux et macOS. Son API vous permet de contrôler chaque paramètre de rendu, ce qui en fait le choix le plus flexible pour les scénarios de **génération de code‑barres ASP.NET**.

## Prérequis

1. **Environnement de développement** – Visual Studio avec le framework .NET approprié installé.  
2. **Aspose.BarCode for .NET** – Téléchargez et installez depuis le site web, [ici](https://releases.aspose.com/barcode/net/).  
3. **Licence** – Obtenez une licence temporaire pour les tests depuis [ici](https://purchase.aspose.com/temporary-license/).  
4. **Bases C#** – Familiarité avec la syntaxe C# et la structure de projet.

Maintenant que les bases sont couvertes, passons à la configuration de DataMatrix ECC 200.

## Importer les espaces de noms

L’espace de noms `Aspose.BarCode.Generation` contient toutes les classes nécessaires à la création de code‑barres. Importez‑le en haut de votre fichier :

```csharp
using Aspose.BarCode.Generation;
```

## Comment créer un code‑barres DataMatrix (ECC 200) étape par étape

Pour générer un code‑barres DataMatrix ECC 200, il suffit de charger les données que vous souhaitez encoder, de configurer quelques paramètres clés sur le `BarcodeGenerator`, puis d’appeler `Save` pour écrire le fichier image. Ce flux en trois étapes gère l’encodage, la correction d’erreurs et la sélection du format de sortie, vous permettant d’intégrer la création de code‑barres dans n’importe quelle application .NET avec un code minimal.

### Étape 1 : Initialiser le générateur de code‑barres

`BarcodeGenerator` est la classe principale d’Aspose.BarCode qui crée et rend les codes‑barres. Elle accepte le type de symbologie et le texte à encoder.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Remplacez `"Your Directory Path"` par le dossier où vous souhaitez enregistrer l’image.

### Étape 2 : Définir XDimension et le type ECC

`XDimension` définit la taille en pixels de chaque module DataMatrix, tandis que `DataMatrixEcc` sélectionne le niveau de correction d’erreurs. ECC 200 offre la capacité de correction la plus élevée pour cette symbologie.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Ajustez la valeur en pixels si vous avez besoin de modules plus grands ou plus petits ; les valeurs typiques sont de 4‑6 px pour l’affichage à l’écran et de 8‑10 px pour les étiquettes imprimées.

### Étape 3 : Générer et enregistrer l’image du code‑barres

La méthode `Save` écrit le code‑barres dans un fichier. Vous pouvez choisir PNG, JPEG ou TIFF en passant la valeur d’énumération `BarCodeImageFormat` correspondante.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff` si votre flux de travail nécessite un format différent.

## Problèmes courants et dépannage

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| Le code‑barres apparaît flou | XDimension trop faible | Augmentez `XDimension.Pixels` à 6‑8 |
| Échec de la lecture sur mobile | Niveau ECC incorrect | Assurez‑vous que `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Fichier non créé | Chaîne de chemin invalide | Utilisez un chemin absolu ou assurez‑vous que le dossier existe |

## Questions fréquemment posées

**Q : Puis‑je utiliser ce code dans une application console .NET Core ?**  
R : Oui, la même API fonctionne dans les projets .NET Core, .NET 5 et .NET 6.

**Q : Comment changer le format de sortie en JPEG ?**  
R : Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` dans l’appel `Save`.

**Q : Est‑il possible d’intégrer le code‑barres directement dans un PDF ?**  
R : Oui – générez d’abord l’image, puis ajoutez‑la à un PDF en utilisant Aspose.PDF ou toute autre bibliothèque PDF.

**Q : Et si je dois encoder des caractères Unicode ?**  
R : DataMatrix prend en charge UTF‑8 ; il suffit de passer la chaîne Unicode au générateur comme indiqué.

**Q : La bibliothèque prend‑elle en charge la génération par lots de plusieurs codes‑barres ?**  
R : Absolument – placez le code de génération dans une boucle et modifiez les données/valeur pour chaque itération.

## Conclusion

Nous avons couvert tout ce dont vous avez besoin pour **créer un code‑barres DataMatrix** (ECC 200) avec Aspose.BarCode pour .NET : des prérequis et importations d’espaces de noms à la configuration de la X‑dimension, la sélection du niveau ECC et l’enregistrement de l’image dans le format de votre choix. Expérimentez avec les nombreuses propriétés supplémentaires—telles que la marge, la couleur d’arrière‑plan et la rotation—pour affiner la sortie selon votre cas d’utilisation spécifique.

Si vous rencontrez des difficultés, la communauté est prête à aider sur le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Bon codage !

---

**Last Updated:** 2026-08-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment générer des codes‑barres DataMatrix ECC 000-140 avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Comment lire les codes‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/)
- [Créer un code‑barres PNG – Ratio d’aspect DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}