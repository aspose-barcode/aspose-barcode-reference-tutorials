---
date: 2026-02-22
description: Apprenez à créer une image de code‑barres en C# avec Aspose.BarCode pour
  .NET et à générer rapidement et efficacement des codes‑barres GS1 DataMatrix.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Créer une image de code‑barres C# – Exemple de GS1 DataMatrix
url: /fr/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemple GS1 DataMatrix

Si vous recherchez un moyen fiable de **create barcode image C#** dans vos applications .NET, Aspose.BarCode for .NET simplifie le processus. Cette bibliothèque puissante prend en charge un large éventail de symbologies, y compris GS1 DataMatrix, et fournit une API claire qui vous permet de vous concentrer sur votre logique métier plutôt que sur les détails bas‑niveau du code‑barres. Dans les quelques minutes qui suivent, nous parcourrons un exemple complet et pratique qui vous montre comment générer un code‑barres GS1 DataMatrix, personnaliser son apparence et l’enregistrer sous forme de fichier image.

## Réponses rapides
- **What does the example generate?** Un code‑barres GS1 DataMatrix contenant des données produit d'exemple.  
- **Which library is used?** Aspose.BarCode for .NET.  
- **Can I change the output format?** Oui, vous pouvez enregistrer au format PNG, JPEG, BMP, etc.  
- **Do I need a license for development?** Un essai gratuit suffit pour les tests ; une licence commerciale est requise pour la production.  
- **Is the code compatible with .NET Core?** Absolument – la même API fonctionne sur .NET Framework et .NET Core/5/6.

## Qu'est‑ce qu'un code‑barres GS1 DataMatrix ?
Un GS1 DataMatrix est un code‑barres bidimensionnel qui encode des informations au niveau du produit (telles que GTIN, numéro de série et identifiants d'application supplémentaires). Il est largement utilisé dans le commerce de détail, la santé et la logistique pour un stockage de données compact et à haute densité.

## Pourquoi utiliser Aspose.BarCode pour créer barcode image C# ?
- **Full‑featured API** – prend en charge les normes GS1, la correction d’erreurs et le contrôle de la taille.  
- **No external dependencies** – bibliothèque .NET pure, facile à intégrer.  
- **Cross‑platform** – fonctionne sous Windows, Linux et macOS.  
- **Extensive documentation** – inclut des exemples comme celui‑ci pour vous aider à démarrer rapidement.

## Prérequis

Avant de plonger dans le tutoriel, assurez‑vous d’avoir les prérequis suivants en place :

1. **Aspose.BarCode for .NET** – Vous devez avoir Aspose.BarCode for .NET installé. Si ce n’est pas déjà fait, vous pouvez [télécharger ici](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – Vous devez disposer d’un environnement de développement .NET installé sur votre système (Visual Studio, VS Code ou tout IDE de votre choix).

Maintenant que les prérequis sont prêts, commençons à générer des codes‑barres GS1 DataMatrix.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms nécessaires pour travailler avec Aspose.BarCode for .NET. Ces espaces de noms vous donnent accès aux fonctionnalités de génération de code‑barres.

```csharp
using Aspose.BarCode;
using System;
```

## Comment créer barcode image C# – Guide étape par étape

### Étape 1 : Configurer le générateur de code‑barres

Pour commencer, créez une instance de `BarcodeGenerator` et spécifiez la symbologie **GS1 DataMatrix** ainsi que les données que vous souhaitez encoder. Dans cet exemple nous encodons la chaîne **"(01)12345678901231(21)ASPOSE(30)9876"**, qui suit le format des Identifiants d’Application GS1.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Astuce :* Remplacez les données d’exemple par vos propres identifiants GS1 pour correspondre à votre catalogue de produits.

### Étape 2 : Personnaliser les propriétés du code‑barres

Vous pouvez ajuster l’apparence du code‑barres à l’aide de l’objet `Parameters`. Ici nous définissons la X‑dimension (la taille du plus petit module) à 8 pixels, et définissons une taille de matrice de 36 colonnes sur 12 lignes. Ajustez ces valeurs pour répondre à vos exigences de lecture.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Pourquoi ajuster la X‑dimension ?* Une X‑dimension plus grande rend le code‑barres plus facile à scanner sur des appareils à basse résolution, tandis qu’une valeur plus petite réduit la taille de l’image.

### Étape 3 : Enregistrer l’image du code‑barres

Enfin, enregistrez le code‑barres généré sur le disque. L’exemple utilise le format PNG, mais vous pouvez choisir parmi JPEG, GIF, BMP et d’autres formats pris en charge par Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Lorsque vous exécutez le code, vous trouverez **Gs1DataMatrixExample.png** dans le dossier spécifié, prêt à être utilisé dans les étiquettes, l’emballage ou les applications numériques.

## Cas d’utilisation courants

- **Retail product labeling** – Encode GTIN, numéros de lot et dates de péremption.  
- **Pharmaceutical tracking** – Répond aux exigences réglementaires avec des données conformes GS1.  
- **Warehouse logistics** – Stocke de façon compacte les informations de localisation et d’inventaire.  

## Dépannage et astuces

- **Incorrect data format** – Assurez‑vous que votre chaîne suit la syntaxe des Identifiants d’Application GS1 ; sinon le code‑barres pourrait ne pas être lisible.  
- **Image size issues** – Si l’image générée apparaît floue, augmentez la valeur `XDimension.Pixels`.  
- **License errors** – Une licence d’essai fonctionne pour l’évaluation, mais une licence complète est requise pour les déploiements en production.

## Questions fréquemment posées

### Qu’est‑ce que le GS1 DataMatrix ?
Le GS1 DataMatrix est une symbologie de code‑barres bidimensionnel utilisée pour encoder des données liées aux produits et à leur identification, notamment dans les secteurs du commerce de détail et de la santé.

### Aspose.BarCode for .NET convient‑il à d’autres types de code‑barres ?
Oui, Aspose.BarCode for .NET prend en charge un large éventail de types de code‑barres, ce qui le rend polyvalent pour différentes applications.

### Puis‑je générer des code‑barres dans d’autres formats d’image que le PNG ?
Oui, Aspose.BarCode for .NET vous permet d’enregistrer les code‑barres générés dans divers formats d’image, tels que JPEG, GIF et BMP, en plus du PNG.

### Ai‑je besoin d’une licence pour utiliser Aspose.BarCode for .NET ?
Oui, une licence valide est requise pour une utilisation commerciale d’Aspose.BarCode for .NET. Vous pouvez obtenir une licence sur le [site Aspose](https://purchase.aspose.com/buy).

### Où puis‑je obtenir du support pour Aspose.BarCode for .NET ?
Vous pouvez trouver des réponses à vos questions et demander de l’aide sur le [forum Aspose.BarCode for .NET](https://forum.aspose.com/c/barcode/13).

## FAQ supplémentaire (optimisée par IA)

**Q : Comment générer un code‑barres DataMatrix en C# sans formatage GS1 ?**  
R : Utilisez `EncodeTypes.DataMatrix` au lieu de `EncodeTypes.GS1DataMatrix` et fournissez la chaîne de données brute au `BarcodeGenerator`.

**Q : Puis‑je changer les couleurs du code‑barres par programmation ?**  
R : Oui, définissez `gen.Parameters.Barcode.ForeColor` et `gen.Parameters.Barcode.BackColor` pour personnaliser les couleurs de premier plan et d’arrière‑plan.

**Q : Est‑il possible d’intégrer le code‑barres généré directement dans un PDF ?**  
R : Absolument – récupérez le code‑barres sous forme de `System.Drawing.Image` et ajoutez‑le à un PDF en utilisant Aspose.PDF ou toute autre bibliothèque PDF.

**Q : Quelles versions de .NET sont prises en charge ?**  
R : Aspose.BarCode for .NET prend en charge .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 et les versions ultérieures.

**Q : Comment améliorer la fiabilité de lecture pour les petites étiquettes ?**  
R : Augmentez la X‑dimension, ajoutez des zones calmes (`gen.Parameters.Barcode.Margin`) et assurez un contraste suffisant entre le code‑barres et l’arrière‑plan.

## Conclusion

Dans ce tutoriel, nous avons exploré comment **create barcode image C#** en utilisant Aspose.BarCode for .NET pour générer un code‑barres GS1 DataMatrix. En quelques lignes de code seulement, vous pouvez intégrer des code‑barres de haute qualité dans vos applications, que vous développiez des solutions de commerce de détail, des systèmes de santé ou des plateformes logistiques. Explorez davantage la bibliothèque pour découvrir d’autres symbologies, des options de rendu avancées et des scénarios d’intégration.

Pour plus d’informations et une documentation détaillée, veuillez consulter la [documentation Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode for .NET (latest version)  
**Author:** Aspose