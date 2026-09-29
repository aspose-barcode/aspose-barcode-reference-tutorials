---
category: general
date: 2026-08-22
description: Comment générer rapidement un code‑barres et apprendre à modifier la
  taille du code‑barres lors de l’exportation de l’image du code‑barres au format
  PNG en utilisant Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: fr
lastmod: 2026-08-22
og_description: Comment générer un code‑barres en C# et modifier facilement la taille
  du code‑barres avant d’exporter l’image du code‑barres au format PNG. Suivez ce
  guide complet.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Comment générer des images de code-barres avec une taille personnalisée
  en C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment générer des images de code‑barres avec une taille personnalisée en
  C#
url: /fr/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des images de code‑barres avec une taille personnalisée en C#

Si vous avez besoin de **comment générer un code‑barres** pour l’automatisation postale, le suivi d’inventaire ou les billets d’événement, ce guide vous montre une solution complète, prête à l’emploi en C#. Vous apprendrez également **comment modifier la taille du code‑barres** et **exporter l’image du code‑barres** au format PNG sans quitter votre IDE.

Nous utiliserons la bibliothèque Aspose.BarCode car elle prend en charge la symbologie OneCode, vous permet de contrôler les dimensions pixel par pixel, et gère l’exportation d’image avec un seul appel de méthode. À la fin du tutoriel, vous disposerez de quatre fichiers PNG—chacun représentant un code‑barres OneCode avec un nombre différent de chiffres.

## Pré‑requis

- .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.6+)
- Visual Studio 2022 (ou tout éditeur C# de votre choix)
- Une référence NuGet à **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Familiarité de base avec la syntaxe C#

> **Astuce pro :** Si vous évaluez la bibliothèque, Aspose propose un essai gratuit de 30 jours incluant toutes les fonctionnalités de code‑barres.

## Étape 1 : Configurer un projet console minimal

Créez une nouvelle application console et ajoutez le package Aspose.BarCode :

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Le fichier `Program.cs` généré contiendra toute la logique de génération de code‑barres.

## Étape 2 : Comment générer un code‑barres – créer une méthode réutilisable

Voici une méthode autonome qui reçoit la chaîne de données, le nom de fichier souhaité, et des paramètres de taille optionnels. Cette méthode illustre le **comment générer un code‑barres** de base.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Pourquoi cette méthode est importante

- **Encapsulation :** Tous les paramètres liés à la taille sont regroupés en un seul endroit, ce qui rend trivial l’appel de la méthode avec différentes dimensions.
- **Réutilisabilité :** Vous pouvez réutiliser la même méthode pour n’importe quelle longueur de chaîne OneCode, ce qui est essentiel car OneCode accepte uniquement 20‑31 chiffres.
- **Clarté :** Les commentaires étiquetés avec des emojis guident le lecteur à travers les trois phases logiques—initialisation, changement de taille et exportation.

## Étape 3 : Modifier la taille du code‑barres pour différentes exigences

Parfois, un scanner attend un code‑barres plus haut, ou une mise en page d’impression nécessite un module plus étroit. La propriété `XDimension.Pixels` contrôle la largeur d’un seul module du code‑barres, tandis que `BarHeight.Pixels` définit la hauteur globale.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Points clés lors du changement de taille :**

- **Dimension X minimale :** 1 pixel est techniquement autorisé, mais la plupart des scanners ont besoin d’au moins 2 pixels pour une lecture fiable.
- **Hauteur maximale :** Il n’y a pas de limite stricte, mais des codes‑barres très hauts peuvent dépasser la zone imprimable sur les étiquettes standards.
- **Ratio d’aspect :** Conservez un ratio hauteur‑largeur‑module équilibré (≈12‑15 × largeur du module) pour éviter les distorsions.

## Étape 4 : Exporter l’image du code‑barres dans d’autres formats (facultatif)

La méthode `Save` accepte plusieurs valeurs `BarCodeImageFormat` : `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Si vous avez besoin d’un format vectoriel sans perte, vous pouvez exporter en `Svg` à la place.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Exporter en PNG est le choix le plus courant car il préserve des bords nets et est largement supporté par les navigateurs web et les flux d’impression.

## Résultat attendu

L’exécution du programme crée quatre fichiers PNG dans le dossier du projet :

- `PostalOneCodeBarcode20Digits.png` – code‑barres OneCode à 20 chiffres
- `PostalOneCodeBarcode25Digits.png` – code‑barres OneCode à 25 chiffres
- `PostalOneCodeBarcode29Digits.png` – code‑barres OneCode à 29 chiffres
- `PostalOneCodeBarcode31Digits.png` – code‑barres OneCode à 31 chiffres

Chaque image ressemblera à l’exemple ci‑dessous (le graphique réel dépend des données numériques que vous avez fournies).

![How to generate barcode example](https://example.com/placeholder.png "How to generate barcode example")

*Le texte alternatif de l’image inclut le mot‑clé principal pour l’accessibilité et le SEO.*

## Questions fréquentes et cas limites

| Question | Réponse |
|----------|--------|
| **Que faire si la chaîne de données est plus courte que 20 chiffres ?** | OneCode nécessite un minimum de 20 chiffres. Complétez la chaîne avec des zéros en tête ou utilisez une autre symbologie (par ex., Code128). |
| **Puis‑je générer des codes‑barres dans un environnement multi‑thread ?** | Oui. `BarcodeGenerator` n’est pas thread‑safe, donc créez un générateur séparé par thread. |
| **Comment définir une couleur d’arrière‑plan ?** | Utilisez `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` avant d’appeler `Save`. |
| **Existe‑t‑il un moyen d’intégrer l’image directement dans une page HTML ?** | Enregistrez l’image dans un `MemoryStream`, convertissez‑la en Base64, puis intégrez‑la avec `<img src="data:image/png;base64,..." />`. |

## Conclusion

Vous savez maintenant **comment générer un code‑barres** en C# avec Aspose.BarCode, **comment modifier la taille du code‑barres** en ajustant la dimension X et la hauteur des barres, et **comment exporter l’image du code‑barres** au format PNG (ou autre). La méthode réutilisable `GenerateOneCode` vous permet de créer n’importe quel code‑barres OneCode entre 20 et 31 chiffres avec une seule ligne de code.

À partir d’ici, vous pourriez :

- Expérimenter d’autres symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Intégrer le générateur dans une API web qui renvoie des images de code‑barres à la demande.
- Combiner la sortie PNG avec une bibliothèque PDF pour intégrer les codes‑barres dans les étiquettes d’expédition.

Bon codage, et n’hésitez pas à partager vos propres variantes dans les commentaires !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer des codes‑barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/english/net/datamatrix-barcode-configuration/)
- [Comment générer un code‑barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment générer et ajuster la hauteur du code‑barres pour One‑Dimensional Databar avec Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}