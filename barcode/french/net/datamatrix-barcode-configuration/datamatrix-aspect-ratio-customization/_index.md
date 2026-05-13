---
date: 2026-01-12
description: Apprenez à créer un PNG de code‑barres avec un rapport d’aspect DataMatrix
  personnalisé à l’aide d’Aspose.BarCode pour .NET. Guide étape par étape pour la
  génération de code‑barres et la personnalisation de la taille.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Créer un PNG de code-barres – Ratio d’aspect DataMatrix – Aspose.BarCode
url: /fr/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code‑barres – Rapport d’aspect DataMatrix – Aspose.BarCode

Générer un **barcode PNG** avec un rapport d’aspect DataMatrix personnalisé est une exigence courante lorsque vous devez adapter le code‑res à des contraintes de mise en page spécifiques. Dans ce tutoriel, nous parcourrons les étapes exactes pour **créer des fichiers barcode PNG** à l’aide d’Aspose.BarCode pour .NET, expliquerons pourquoi vous pourriez vouloir ajuster le rapport d’aspect, et vous montrerons comment affiner la sortie pour votre application.

## Réponses rapides
- **Que contrôle le « rapport d’aspect » ?** Il définit la proportion largeur‑hauteur des modules DataMatrix.  
- **Puis‑je exporter en PNG, JPEG ou SVG ?** Oui – la méthode `Save` prend en charge PNG, JPEG, BMP, GIF, et plus.  
- **Ai‑je besoin d’une licence pour cette fonctionnalité ?** Un essai gratuit suffit pour le développement ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de valeurs de rapport d’aspect sont valides ?** Toute valeur flottante positive ; les valeurs typiques sont 0,5 – 2,0.

## Qu’est‑ce qu’un code‑barres DataMatrix et pourquoi ajuster son rapport d’aspect ?
DataMatrix est un code‑barres matriciel bidimensionnel qui stocke de grandes quantités de données dans un petit espace. Ajuster le **rapport d’aspect** vous permet d’étirer ou de compresser les modules horizontalement, ce qui peut être utile pour faire tenir le code‑barres dans des colonnes étroites ou des étiquettes larges sans sacrifier la lisibilité.

## Prérequis

Avant de commencer à personnaliser les rapports d’aspect DataMatrix, assurez‑vous d’avoir les prérequis suivants :

1. **Visual Studio** – n’importe quelle version récente convient.  
2. **Aspose.BarCode for .NET** – téléchargez‑le [ici](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – votre projet doit cibler une version prise en charge.

## Importer les espaces de noms

Tout d’abord, vous devez importer l’espace de noms nécessaire dans votre projet C# :

```csharp
using Aspose.BarCode.Generation;
```

> **Astuce :** Conservez cette instruction `using` en haut de votre fichier afin que la classe `BarcodeGenerator` soit toujours disponible.

## Guide étape par étape

### Étape 1 : Configurer votre projet
Créez un nouveau projet console ou Windows Forms dans Visual Studio et ajoutez une référence à la DLL Aspose.BarCode.

### Étape 2 : Initialiser un générateur de code‑barres
Instanciez un `BarcodeGenerator` avec le type DataMatrix et les données que vous souhaitez encoder :

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Cette ligne crée un générateur prêt à produire un code‑barres DataMatrix contenant le texte d’exemple.

### Étape 3 : Personnaliser le rapport d’aspect et enregistrer les fichiers PNG
Vous pouvez maintenant modifier le **rapport d’aspect** et enregistrer chaque version sous forme d’image PNG :

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Le premier appel crée un code‑barres à proportions carrées (`AspectRatio = 1`).  
- Le deuxième appel compresse le code‑barres horizontalement (`AspectRatio = 0.5`), produisant une apparence plus large.

Vous disposez maintenant de deux fichiers **barcode PNG** avec des rapports d’aspect différents, prêts à être utilisés dans des rapports, des étiquettes ou des éléments d’interface utilisateur.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **L'image générée est floue** | Augmentez le paramètre `Resolution` avant l’enregistrement (`gen.Parameters.ImageResolution = 300`). |
| **Le code‑barres ne se lit pas** | Assurez‑vous que le rapport d’aspect reste entre 0,5 – 2,0 et maintenez une zone calme suffisante (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Erreurs de chemin de fichier** | Utilisez `Path.Combine` pour construire le chemin de sortie et vérifiez que le dossier existe. |

## Questions fréquemment posées

**Q : Puis‑je personnaliser le rapport d’aspect d’autres types de code‑barres avec Aspose.BarCode pour .NET ?**  
R : Oui, de nombreux codes‑barres 2‑D (par ex., QR, PDF417) prennent en charge les ajustements de rapport d’aspect via leurs objets de paramètres spécifiques.

**Q : Existe‑t‑il un essai gratuit d’Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez accéder à un essai gratuit d’Aspose.BarCode pour .NET [ici](https://releases.aspose.com/).

**Q : Où puis‑je acheter une licence pour Aspose.BarCode pour .NET ?**  
R : Vous pouvez acheter une licence sur le site d’Aspose [ici](https://purchase.aspose.com/buy).

**Q : Aspose.BarCode pour .NET est‑il compatible avec différentes versions du .NET Framework ?**  
R : Oui, il fonctionne avec .NET Framework 4.x, .NET Core 3.1+ et les dernières versions de .NET.

**Q : Puis‑je générer des codes‑barres dans différents formats avec Aspose.BarCode pour .NET ?**  
R : Absolument – PNG, JPEG, BMP, GIF, TIFF, SVG et PDF sont tous pris en charge dès le départ.

## Conclusion

Personnaliser le **rapport d’aspect** d’un code‑barres DataMatrix et **créer des fichiers barcode PNG** est simple avec Aspose.BarCode pour .NET. En suivant les étapes ci‑dessus, vous pouvez générer des codes‑barres parfaitement dimensionnés qui répondent aux exigences de mise en page de votre projet. Explorez d’autres paramètres tels que `Resolution`, `Margin` et `Color` pour affiner davantage la sortie.

Pour aller plus loin, consultez la [documentation officielle](https://reference.aspose.com/barcode/net/) ou rejoignez la communauté sur le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-01-12  
**Testé avec:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}