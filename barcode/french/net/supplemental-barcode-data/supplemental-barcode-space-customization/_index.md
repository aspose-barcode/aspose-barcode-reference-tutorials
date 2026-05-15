---
date: 2026-03-05
description: Learn how to generate barcode image, adjust barcode width, and customize
  supplement space with Aspose.BarCode for .NET. Try the free trial today!
linktitle: Supplemental Barcode Space Customization
second_title: Aspose.BarCode .NET API
title: Comment générer une image de code‑barres avec personnalisation de l’espace
  supplémentaire à l’aide d’Aspose.BarCode
url: /fr/net/supplemental-barcode-data/supplemental-barcode-space-customization/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer une image de code-barres avec personnalisation de l'espace supplémentaire à l'aide d'Aspose.BarCode

Dans les environnements de vente au détail et de logistique d'aujourd'hui, où tout évolue rapidement, pouvoir **générer des images de code-barres** qui correspondent exactement aux exigences de mise en page est essentiel. Que vous ayez besoin de **créer des étiquettes de code-barres EAN13** pour une gamme de produits ou d'ajuster finement l'espacement visuel des données supplémentaires, Aspose.BarCode for .NET vous offre un contrôle total. Dans ce tutoriel, nous parcourrons l'ensemble du processus — de la configuration du générateur à **ajuster la largeur du code-barres** et enfin **enregistrer les fichiers PNG du code-barres** — afin que vous puissiez produire des codes-barres parfaitement adaptés en quelques minutes.

## Réponses rapides
- **Que signifie « générer une image de code-barres » ?** Elle crée une représentation raster (PNG, JPEG, etc.) d'un code-barres qui peut être imprimée ou affichée.  
- **Quel type de code-barres est utilisé dans l'exemple ?** EAN13, un format numérique courant pour les produits de détail.  
- **Comment modifier la largeur du code-barres ?** En définissant la propriété X‑Dimension (pixels).  
- **Puis-je contrôler l'espace autour des données supplémentaires ?** Oui, en utilisant la propriété `SupplementSpace` (pixels).  
- **Quel format de fichier est utilisé pour l'enregistrement ?** PNG, via l'énumération `BarCodeImageFormat.Png`.

## Qu'est-ce que la génération d'image de code-barres avec Aspose.BarCode ?
La classe `BarcodeGenerator` d'Aspose.BarCode convertit des données brutes (comme un numéro de produit) en une image de code-barres visuelle. Cette image peut être enregistrée dans divers formats, intégrée dans des documents ou envoyée directement à une imprimante.

## Pourquoi personnaliser l'espace supplémentaire et la X‑Dimension ?
Personnaliser l'**espace supplémentaire** vous permet de respecter des normes de mise en page d'étiquettes spécifiques, tandis que **ajuster la largeur du code-barres** (X‑Dimension) garantit que le code-barres se lit de manière fiable sur différents lecteurs. Ensemble, ils vous offrent la flexibilité nécessaire pour répondre aux exigences de marque, réglementaires et ergonomiques.

## Prérequis

Avant de commencer, assurez‑vous d'avoir les éléments suivants :

### 1. Aspose.BarCode for .NET
Vous devez avoir Aspose.BarCode for .NET installé sur votre système. Vous pouvez trouver le lien de téléchargement [ici](https://releases.aspose.com/barcode/net/). Si vous ne l'avez pas encore, vous pouvez également obtenir une licence temporaire [ici](https://purchase.aspose.com/temporary-license/).

### 2. Votre chemin de répertoire
Créez (ou choisissez) un dossier où les images de code-barres générées seront enregistrées. Remplacez `"Your Directory Path"` dans les exemples de code par le chemin réel sur votre machine.

## Importer les espaces de noms
Tout d'abord, importez l'espace de noms qui contient les classes de génération de code-barres.

```csharp
using Aspose.BarCode.Generation;
```

## Guide étape par étape

### Étape 1 : Créer un générateur de code-barres (Créer un code-barres EAN13)
Instanciez un `BarcodeGenerator`, en spécifiant le type de code-barres (`EncodeTypes.EAN13`) et les données que vous souhaitez encoder.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Étape 2 : Ajuster la largeur du code-barres (Définir la X‑Dimension)
La X‑Dimension contrôle la largeur de chaque module du code-barres. La définir en pixels vous permet de **ajuster la largeur du code-barres** pour correspondre à la taille de votre étiquette.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

### Étape 3 : Ajouter des données supplémentaires
Si votre norme d'étiquetage nécessite des données supplémentaires (par ex., un complément de 5 chiffres pour les livres), affectez‑les en utilisant la propriété `SupplementData`.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Étape 4 : Personnaliser l'espace supplémentaire
Contrôlez l'espacement entre le code-barres principal et la partie supplémentaire en définissant `SupplementSpace`. Dans cet exemple, nous utilisons 20 pixels.

```csharp
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Étape 5 : Enregistrer l'image du code-barres au format PNG (Enregistrer le PNG du code-barres)
Maintenant que le code-barres est entièrement configuré, enregistrez‑le dans le dossier que vous avez préparé. L'image sera un fichier PNG, idéal pour le web et l'impression.

```csharp
gen.Save($"{path}SupplementSpace20Pixels.png", BarCodeImageFormat.Png);
```

### Étape 6 : Expérimenter avec différents espaces supplémentaires
Vous pouvez répéter le processus avec une valeur différente de `SupplementSpace` pour voir comment la mise en page visuelle change. Ici, nous passons à 40 pixels et enregistrons une deuxième image.

```csharp
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 40;
gen.Save($"{path}SupplementSpace40Pixels.png", BarCodeImageFormat.Png);
```

## Problèmes courants et solutions
- **Le code-barres apparaît trop fin ou trop épais :** Réajustez la X‑Dimension (`gen.Parameters.Barcode.XDimension.Pixels`). Les valeurs typiques vont de 1 à 4 pixels.  
- **Les données supplémentaires ne s'affichent pas :** Vérifiez que `SupplementData` est défini *avant* d'enregistrer l'image.  
- **Le fichier n'est pas enregistré :** Assurez‑vous que la variable `path` pointe vers un répertoire valide et que votre application dispose des permissions d'écriture.

## Questions fréquentes

**Q : Où puis‑je trouver la documentation d'Aspose.BarCode for .NET ?**  
R : Vous pouvez accéder à la documentation [ici](https://reference.aspose.com/barcode/net/).

**Q : Existe‑t‑il un essai gratuit disponible pour Aspose.BarCode for .NET ?**  
R : Oui, vous pouvez obtenir un essai gratuit [ici](https://releases.aspose.com/).

**Q : Comment puis‑je acheter une licence pour Aspose.BarCode for .NET ?**  
R : Vous pouvez acheter une licence [ici](https://purchase.aspose.com/buy).

**Q : Quels formats de code-barres sont pris en charge par Aspose.BarCode for .NET ?**  
R : Aspose.BarCode for .NET prend en charge un large éventail de formats de code-barres, y compris EAN, QR, Code39, et plus encore. Vous pouvez trouver la liste complète dans la documentation.

**Q : Puis‑je utiliser Aspose.BarCode for .NET dans mes projets commerciaux ?**  
R : Oui, Aspose.BarCode for .NET convient à la fois aux usages personnels et commerciaux. Vous pouvez acheter une licence pour l'utiliser dans vos projets.

## Conclusion
Vous disposez maintenant d'un guide complet et pratique pour **générer des images de code-barres** avec une X‑Dimension et un espace supplémentaire personnalisés à l'aide d'Aspose.BarCode for .NET. En ajustant la largeur et l'espace supplémentaire, vous pouvez répondre à pratiquement toutes les exigences d'étiquetage — que vous ayez besoin de **créer un code-barres EAN13**, **ajuster la largeur du code-barres**, ou **enregistrer des fichiers PNG du code-barres** pour le web ou l'impression. N'hésitez pas à expérimenter avec d'autres types de code-barres et formats d'image pour étendre cette base.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-05  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose