---
date: 2026-02-22
description: Apprenez à créer une hauteur personnalisée de code‑barres en .NET avec
  Aspose.BarCode, et à ajuster rapidement et précisément la hauteur des codes‑barres
  unidimensionnels.
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: Créer une hauteur personnalisée de code-barres – Codes-barres unidimensionnels
url: /fr/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une hauteur personnalisée de code-barres – Codes-barres unidimensionnels

Lorsque vous devez **create barcode custom height** dans une application .NET, Aspose.BarCode for .NET vous offre un contrôle total sur l'apparence visuelle des codes-barres unidimensionnels. Que vous créiez des étiquettes d'inventaire, des reçus de point de vente ou des étiquettes d'expédition, pouvoir ajuster finement la hauteur du code-barres garantit des performances de lecture optimales et un rendu soigné. Dans ce guide pas à pas, nous passerons en revue tout ce que vous devez savoir pour ajuster la hauteur d'un code-barres unidimensionnel à l'aide d'Aspose.BarCode for .NET.

## Réponses rapides
- **What does “barcode custom height” mean?** C’est la taille verticale du symbole 1‑D exprimée en pixels.  
- **Which property controls height?** `Parameters.Barcode.BarHeight.Pixels`.  
- **Can I generate multiple heights in one run?** Oui – il suffit de modifier la propriété et d’appeler à nouveau `Save()`.  
- **Supported image formats?** PNG, JPEG, TIFF, BMP, GIF, et plus encore.  
- **Do I need a license for height adjustment?** Non, la fonctionnalité fonctionne dans la version d’essai gratuite ; une licence est requise pour une utilisation en production.

## Qu’est‑ce que “create barcode custom height” ?
Créer un code‑barres avec une hauteur personnalisée signifie spécifier la valeur exacte en pixels pour la dimension verticale des barres du code‑barres. Cela est utile lorsque vous avez des exigences de mise en page strictes, que vous devez correspondre à des documents imprimés existants ou que vous souhaitez améliorer la lisibilité du scanner sur différents supports.

## Pourquoi utiliser Aspose.BarCode for .NET ?
- **Rich API** – Ajustez la taille, la couleur, le texte, etc., avec des paramètres simples.  
- **Cross‑platform** – Fonctionne avec .NET Framework, .NET Core et .NET 5/6+.  
- **No external dependencies** – Génère des images sans nécessiter de bibliothèques supplémentaires.  
- **High‑quality rendering** – Garantit des codes‑barres lisibles même avec des dimensions personnalisées.

## Prérequis

Avant de commencer, assurez‑vous d’avoir les prérequis suivants :

- Un environnement de développement avec .NET Framework ou .NET Core.  
- Aspose.BarCode for .NET installé. Vous pouvez le télécharger depuis le site web [ici](https://releases.aspose.com/barcode/net/).  
- Un éditeur de code de votre choix.

Maintenant que les prérequis sont couverts, plongeons dans le processus d’ajustement de la hauteur d’un code‑barres unidimensionnel.

## Importer les espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre projet. Ces espaces de noms sont essentiels pour travailler avec Aspose.BarCode for .NET. Voici comment procéder :

```csharp
using Aspose.BarCode.Generation;
```

## Étape 1 : Définir le chemin du répertoire

Commencez par définir le chemin du répertoire où vous souhaitez enregistrer les images de code‑barres générées. Remplacez `"Your Directory Path"` par le chemin réel sur votre système.

```csharp
string path = "Your Directory Path";
```

## Étape 2 : Créer le générateur de code‑barres

Ensuite, créez une instance de la classe `BarcodeGenerator`. Vous pouvez spécifier le type de code‑barres (dans ce cas, nous utiliserons `Code128`) et la valeur du code‑barres (dans cet exemple, `"ASPOSE"`).

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## Étape 3 : Ajuster la hauteur du code‑barres

Dans cette étape, vous définirez la hauteur du code‑barres à l’aide de la propriété `BarHeight`. À titre d’exemple, nous ajusterons la hauteur à 40 pixels puis à 80 pixels et enregistrerons deux images de code‑barres en conséquence. Cela montre à quel point il est simple de **create barcode custom height** dynamiquement.

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Le code‑barres apparaît trop fin après le changement de hauteur | Largeur non ajustée proportionnellement | Utilisez `Parameters.Barcode.XDimension` pour modifier la largeur des barres si nécessaire. |
| Image non enregistrée | Chemin invalide ou permissions d'écriture manquantes | Vérifiez que `path` se termine par une barre oblique inverse et que le dossier existe. |
| Le code‑barres généré ne peut pas être scanné | Hauteur trop basse/élevée pour le scanner | Testez avec un scanner typique ; maintenez la hauteur entre 30‑100 px pour la plupart des codes 1‑D. |

## Questions fréquentes

**Q : Quels types de code‑barres sont pris en charge par Aspose.BarCode for .NET ?**  
R : Aspose.BarCode for .NET prend en charge un large éventail de types de code‑barres, y compris Code128, QR Code, DataMatrix, et bien d’autres. Vous trouverez une liste complète dans la documentation.

**Q : Puis‑je également ajuster la largeur d’un code‑barres unidimensionnel ?**  
R : Oui, vous pouvez ajuster la largeur d’un code‑barres unidimensionnel avec Aspose.BarCode for .NET. Le processus est similaire à celui de l’ajustement de la hauteur, et vous avez un contrôle total sur les dimensions du code‑barres.

**Q : Existe‑t‑il une version d’essai gratuite d’Aspose.BarCode for .NET ?**  
R : Oui, vous pouvez explorer Aspose.BarCode for .NET avec une version d’essai gratuite. Vous pouvez le télécharger depuis [ici](https://releases.aspose.com/).

**Q : Puis‑je générer des code‑barres dans différents formats d’image ?**  
R : Oui, Aspose.BarCode for .NET prend en charge divers formats d’image, notamment PNG, JPEG et TIFF. Vous pouvez choisir le format qui convient le mieux aux exigences de votre application.

**Q : Où puis‑je trouver la documentation détaillée d’Aspose.BarCode for .NET ?**  
R : Vous pouvez consulter la documentation [ici](https://reference.aspose.com/barcode/net/) pour obtenir des informations approfondies sur l’utilisation d’Aspose.BarCode dans vos projets .NET.

## Conclusion

Dans ce tutoriel, nous avons parcouru le processus de **create barcode custom height** pour les codes‑barres unidimensionnels à l’aide d’Aspose.BarCode for .NET. En modifiant la propriété `BarHeight`, vous pouvez générer des images de code‑barres qui correspondent parfaitement à vos exigences de mise en page, que vous ayez besoin d’une étiquette compacte ou d’un code de grande visibilité.

Si vous rencontrez des difficultés ou avez des questions supplémentaires, n’hésitez pas à contacter la communauté Aspose via leur [forum d’assistance](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}