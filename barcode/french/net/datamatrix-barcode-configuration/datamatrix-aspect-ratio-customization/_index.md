---
date: 2026-05-30
description: Apprenez à créer un PNG de code-barres avec un ratio d'aspect DataMatrix
  personnalisé en utilisant Aspose.BarCode pour .NET. Guide étape par étape pour la
  génération de codes-barres et la personnalisation de la taille.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Personnalisation du ratio d'aspect DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Créer un PNG de code-barres – Ratio d'aspect DataMatrix – Aspose.BarCode
url: /fr/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code-barres – Ratio d’aspect DataMatrix – Aspose.BarCode

Générer un **barcode PNG** avec un ratio d’aspect DataMatrix personnalisé est une exigence courante lorsque vous devez **créer des fichiers barcode PNG** qui s’adaptent à des contraintes de mise en page spécifiques. Dans ce tutoriel, nous parcourrons les étapes exactes pour **créer des fichiers barcode PNG** en utilisant Aspose.BarCode pour .NET, expliquerons pourquoi vous pourriez vouloir ajuster le ratio d’aspect, et vous montrerons comment affiner la sortie pour votre application.

## Réponses rapides
- **Que contrôle le « ratio d’aspect » ?** Il définit la proportion largeur‑hauteur des modules DataMatrix.  
- **Puis-je exporter en PNG, JPEG ou SVG ?** Oui – la méthode `Save` prend en charge PNG, JPEG, BMP, GIF, TIFF, SVG et PDF.  
- **Ai-je besoin d’une licence pour cette fonctionnalité ?** Un essai gratuit fonctionne pour le développement ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de valeurs de ratio d’aspect sont valides ?** Toute valeur flottante positive ; les valeurs typiques sont 0.5 – 2.0.

## Qu’est‑ce qu’un code‑barres DataMatrix et pourquoi ajuster son ratio d’aspect ?
Un code‑barres DataMatrix est un code matriciel bidimensionnel qui stocke de grandes quantités de données dans un carré compact. Ajuster le **ratio d’aspect** vous permet d’étirer ou de compresser les modules horizontalement, ce qui est utile lorsque vous devez intégrer le code‑barres dans des colonnes étroites ou des étiquettes larges sans compromettre la fiabilité du scan.

## Pourquoi utiliser Aspose.BarCode pour créer un barcode PNG ?
Aspose.BarCode prend en charge **7 formats d’image** — PNG, JPEG, BMP, GIF, TIFF, SVG et PDF — et peut traiter **plus de 50 formats d’entrée et de sortie** en mémoire, gérant des documents de plusieurs centaines de pages sans charger le fichier complet. La bibliothèque offre une API fluide qui vous permet de générer un code‑barres DataMatrix en une seule ligne de code, garantissant un rendu pixel‑parfait et une compatibilité .NET totale.

## Prérequis
Avant de commencer à personnaliser les ratios d’aspect DataMatrix, assurez‑vous que les prérequis suivants sont en place :

1. **Visual Studio** – toute version récente convient.  
2. **Aspose.BarCode for .NET** – téléchargez‑le [ici](https://releases.aspose.com/barcode/net/).  
3. Vous pouvez également explorer les autres versions de produits Aspose [ici](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – votre projet doit cibler une version prise en charge.

## Importer les espaces de noms

Tout d’abord, vous devez importer l’espace de noms nécessaire dans votre projet C# :

`using Aspose.BarCode.Generation;` importe l’espace de noms qui contient les classes de génération de code‑barres.  

```csharp
using Aspose.BarCode.Generation;
```

> **Astuce :** Conservez cette instruction `using` en haut de votre fichier afin que la classe `BarcodeGenerator` soit toujours disponible.

## Comment créer un barcode PNG avec un ratio d’aspect personnalisé ?
Chargez le `BarcodeGenerator`, définissez le type DataMatrix, ajustez la propriété `AspectRatio`, puis appelez `Save`. Ce modèle en une ligne crée un barcode PNG qui respecte le ratio que vous spécifiez, et la bibliothèque gère automatiquement le redimensionnement des modules et les zones calmes.

`BarcodeGenerator` crée une image de code‑barres à partir de la symbologie et des données spécifiées.

### Étape 1 : Configurer votre projet
Créez un nouveau projet console ou Windows Forms dans Visual Studio et ajoutez une référence à la DLL Aspose.BarCode.

### Étape 2 : Initialiser un générateur de code‑barres
Instanciez‑le avec la symbologie DataMatrix et les données que vous souhaitez encoder :

`BarcodeGenerator` crée une image de code‑barres à partir de la symbologie et des données spécifiées.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Cette ligne crée un générateur prêt à produire un code‑barres DataMatrix contenant le texte d’exemple.

### Étape 3 : Personnaliser le ratio d’aspect et enregistrer les fichiers PNG
Vous pouvez maintenant modifier le **ratio d’aspect** et enregistrer chaque version en tant qu’image PNG :

`AspectRatio` définit la proportion largeur‑hauteur des modules DataMatrix.  
`Save` écrit l’image de code‑barres générée dans un fichier au format choisi.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Le premier appel crée un code‑barres à proportion carrée (`AspectRatio = 1`).  
- Le deuxième appel compresse le code‑barres horizontalement (`AspectRatio = 0.5`), produisant une apparence plus large.

Vous avez maintenant deux fichiers **barcode PNG** avec des ratios d’aspect différents, prêts à être utilisés dans des rapports, des étiquettes ou des éléments d’interface utilisateur.

## Problèmes courants & solutions
| Problème | Solution |
|----------|----------|
| **L’image générée est floue** | Augmentez le paramètre `Resolution` avant d’enregistrer (`gen.Parameters.ImageResolution = 300`). |
| **Le code‑barres ne se lit pas** | Assurez‑vous que le ratio d’aspect reste entre 0,5 – 2,0 et conservez une zone calme suffisante (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Erreurs de chemin de fichier** | Utilisez `Path.Combine` pour construire le chemin de sortie et vérifiez que le dossier existe. |

## Questions fréquemment posées

**Q : Puis‑je personnaliser le ratio d’aspect d’autres types de code‑barres avec Aspose.BarCode pour .NET ?**  
R : Oui, de nombreux codes‑barres 2‑D (p. ex., QR, PDF417) prennent en charge les ajustements de ratio d’aspect via leurs objets de paramètres spécifiques.

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.BarCode pour .NET [ici](https://releases.aspose.com/).

**Q : Où puis‑je acheter une licence pour Aspose.BarCode pour .NET ?**  
R : Vous pouvez acheter une licence sur le site d’Aspose [ici](https://purchase.aspose.com/buy).

**Q : Aspose.BarCode pour .NET est‑il compatible avec différentes versions du .NET Framework ?**  
R : Oui, il fonctionne avec .NET Framework 4.x, .NET Core 3.1+ et les dernières versions de .NET.

**Q : Puis‑je générer des code‑barres dans différents formats avec Aspose.BarCode pour .NET ?**  
R : Absolument – PNG, JPEG, BMP, GIF, TIFF, SVG et PDF sont tous pris en charge nativement.

## Conclusion

La personnalisation du **ratio d’aspect** d’un code‑barres DataMatrix et la **création de fichiers barcode PNG** est simple avec Aspose.BarCode pour .NET. En suivant les étapes ci‑dessus, vous pouvez générer des code‑barres parfaitement dimensionnés qui répondent aux exigences exactes de mise en page de votre projet. Explorez des paramètres supplémentaires tels que `Resolution`, `Margin` et `Color` pour affiner davantage la sortie, et envisagez les capacités de `generate datamatrix barcode` lors de la création d’applications conviviales pour le scan dans Visual Studio.

Pour une exploration plus approfondie, consultez la [documentation officielle](https://reference.aspose.com/barcode/net/) ou rejoignez la communauté sur le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-05-30  
**Testé avec :** Aspose.BarCode 24.12 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Générer un code‑barres DataMatrix – Guide pro avec Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Maîtriser le codage DataMatrix en ASCII avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}