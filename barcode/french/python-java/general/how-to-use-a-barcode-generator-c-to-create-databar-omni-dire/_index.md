---
category: general
date: 2026-08-22
description: Le tutoriel du générateur de codes‑barres C# montre comment générer des
  fichiers PNG de codes‑barres, créer des codes‑barres DataBar et ajuster la hauteur
  du code‑barres en quelques étapes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: fr
lastmod: 2026-08-22
og_description: Le guide du générateur de codes‑barres C# vous explique comment générer
  des PNG de codes‑barres, créer des codes‑barres DataBar et ajuster efficacement
  la hauteur du code‑barres.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: Générateur de codes-barres C# – créer des codes-barres DataBar et ajuster
  la hauteur
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment utiliser un générateur de codes-barres C# pour créer des codes-barres
  DataBar omnidirectionnels
url: /fr/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un générateur de code‑barres C# pour créer des codes‑barres DataBar Omni‑directionnels

Si vous avez besoin d’un **barcode generator C#** capable de produire des images PNG de haute qualité, ce guide est fait pour vous. Vous apprendrez à générer des fichiers PNG de code‑barres, à créer un code‑barres DataBar Omni‑directionnel et à ajuster la hauteur du code‑barres sans quitter votre IDE.

Générer des codes‑barres de façon programmatique supprime l’étape manuelle d’utilisation d’un éditeur graphique. À la fin de ce tutoriel, vous disposerez de deux fichiers PNG — l’un avec une hauteur de barre de 30 pixels et l’autre avec une hauteur de barre de 60 pixels — prêts à être intégrés dans des factures, des étiquettes ou des systèmes d’inventaire.

**Prérequis**

- .NET 6.0 ou supérieur (le code fonctionne également avec .NET Framework 4.7+)
- Une référence au package NuGet `Aspose.BarCode` (ou toute bibliothèque exposant une API similaire)
- Une connaissance de base du C# et de Visual Studio ou de votre IDE préféré

---

## Étape 1 : Configurer le projet du barcode generator C#

Créer une instance de **barcode generator C#** est la première chose à faire. Le constructeur accepte deux arguments : le type de code‑barres (`EncodeTypes.DatabarOmniDirectional`) et la donnée à encoder. Dans cet exemple, la donnée suit le format d’Identifiant d’Application GS1 pour un GTIN à 14 chiffres.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Pourquoi c’est important :** L’énumération `EncodeTypes.DatabarOmniDirectional` indique à la bibliothèque de rendre un DataBar lisible depuis n’importe quelle direction, ce qui est idéal pour les petites étiquettes de vente au détail.

---

## Étape 2 : Définir la dimension du module (X‑dimension)

La X‑dimension contrôle la largeur d’un seul module du code‑barres. La régler à 2 pixels donne une image nette et lisible tout en maintenant une taille de fichier réduite.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Astuce :** Si vous avez besoin d’un code‑barres plus compact pour un espace limité, réduisez la valeur à 1 pixel, mais testez la lisibilité avec un scanner.

---

## Étape 3 : Générer le premier PNG avec une hauteur de barre de 30 pixels

La hauteur de la barre détermine la taille verticale des barres. Une hauteur de 30 pixels est une valeur par défaut courante pour les étiquettes standards.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Le fichier `DatabarBarHeight30Pixels.png` contient maintenant un **generate barcode PNG** qui peut être utilisé directement dans des pages web ou imprimé à la demande.

---

## Étape 4 : Ajuster la hauteur du code‑barres à 60 pixels et enregistrer un second PNG

Modifier la hauteur de la barre est aussi simple que d’assigner une nouvelle valeur à la même propriété. Cela montre la capacité du générateur à **adjust barcode height**.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Vous avez maintenant `DatabarBarHeight60Pixels.png`, idéal pour les emballages plus grands où le code‑barres doit être scanné à distance.

**Résultat attendu**

- `DatabarBarHeight30Pixels.png` – un code‑barres DataBar Omni‑directionnel compact, 30 px de haut.
- `DatabarBarHeight60Pixels.png` – le même code‑barres, doublé en hauteur pour une meilleure visibilité.

Les deux images sont des fichiers PNG, préservant une qualité sans perte et supportant la transparence si nécessaire.

---

## Comment générer des fichiers PNG de code‑barres dans d’autres formats

Bien que ce tutoriel se concentre sur le PNG, la méthode `Save` accepte d’autres formats tels que `Jpeg`, `Bmp` et `Svg`. Pour **how to generate barcode** dans un autre format, remplacez simplement `BarCodeImageFormat.Png` par la valeur d’énumération souhaitée :

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Choisir le SVG est pratique lorsque vous avez besoin d’une image vectorielle qui s’adapte sans pixellisation.

---

## Pièges courants lors de la **create DataBar barcode** d’images

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code‑barres apparaît flou | X‑dimension trop basse pour la résolution cible | Augmentez `XDimension.Pixels` à 3 ou 4 |
| Le scanner ne lit pas le code | Hauteur de barre trop courte pour l’optique du scanner | Utilisez au minimum 30 pixels ou suivez les spécifications du scanner |
| La chaîne de données est rejetée | Formatage GS1 incorrect | Assurez‑vous que la chaîne commence par le bon Identifiant d’Application, par ex. `(01)` pour GTIN‑14 |

Traiter ces points dès le départ vous fait gagner du temps lors de l’intégration des codes‑barres dans les pipelines de production.

---

## Astuce avancée : Réutiliser le même générateur pour plusieurs codes‑barres

Si vous devez **generate barcode PNG** pour un lot de produits, réutilisez la même instance de `BarcodeGenerator` et ne mettez à jour que la propriété `CodeText` :

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Ce modèle minimise la surcharge de création d’objets et garde votre code concis.

---

## Conclusion

Vous disposez maintenant d’un flux de travail complet **barcode generator C#** qui **creates DataBar barcodes**, **generates barcode PNG** et vous permet de **adjust barcode height** avec un simple changement de propriété. L’exemple couvre tout, de la configuration du projet à la gestion des cas limites, afin que vous puissiez intégrer la création de codes‑barres dans n’importe quelle application .NET en toute confiance.

**Prochaines étapes**

- Explorez d’autres symbologies de code‑barres (`EncodeTypes.QR`, `EncodeTypes.Code128`) pour élargir votre solution.
- Combinez le générateur avec ASP.NET Core pour servir les codes‑barres à la volée via un point d’accès API.
- Expérimentez les options de couleur (`generator.Parameters.Barcode.ForeColor`) pour des besoins de branding.

Bon codage, et que vos scans soient toujours rapides !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}