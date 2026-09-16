---
category: general
date: 2026-09-16
description: Créez un code‑barres postal en C# et apprenez à définir la largeur et
  à modifier la hauteur du code‑barres pour une lecture parfaite.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: fr
lastmod: 2026-09-16
og_description: Créez un code‑barres postal en C# avec ce guide pas à pas, montrant
  comment définir la largeur et modifier la hauteur du code‑barres pour un scan postal
  fiable.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Créer un code-barres postal avec une largeur et une hauteur personnalisées
  en C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Créer un code‑barres postal avec une largeur et une hauteur personnalisées
  en C#
url: /fr/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres postal avec largeur et hauteur personnalisées en C#

Si vous devez **créer des images de code‑barres postal** en C#, ce guide vous montre comment générer les codes‑barres Planet et RM4SCC avec des dimensions exactes. Au bout des deux premières phrases, vous connaîtrez les appels d’API précis pour **définir la largeur** et **modifier la hauteur du code‑barres**, afin de produire des codes‑barres lisibles qui respectent les spécifications des services postaux.

Vous apprendrez :
* Comment instancier un générateur de code‑barres pour les formats Planet et RM4SCC.  
* La propriété exacte pour **définir la largeur** (X‑dimension) en pixels.  
* Comment **modifier la hauteur du code‑barres** pour un type de code‑barres spécifique.  
* Où les fichiers PNG générés sont enregistrés et à quoi ils ressemblent.

Le seul prérequis est une référence à la bibliothèque `Aspose.BarCode` (ou similaire) qui fournit la classe `BarcodeGenerator`. Aucun package NuGet supplémentaire n’est requis au‑delà du SDK de code‑barres lui‑même.

---

## Créer un code‑barres postal avec des dimensions personnalisées

Tout d’abord, ajoutez les directives `using` requises et créez un simple programme console. L’exemple complet et exécutable est présenté après l’explication pas à pas.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Pourquoi cela fonctionne :**  
* `EncodeTypes.Planet` et `EncodeTypes.RM4SCC` indiquent au générateur quel standard postal appliquer.  
* `XDimension.Pixels` contrôle la **largeur** de chaque module du code‑barres (l’élément noir/blanc le plus petit).  
* `BarHeight.Pixels` vous permet de **modifier la hauteur du code‑barres** pour les formats qui ne calculent pas automatiquement la hauteur, comme RM4SCC.

L’exécution du programme crée deux fichiers PNG dans le répertoire de travail de l’exécutable :
* `PostalPlanetBarWidth4.png` – un code‑barres Planet avec une largeur de module de 4 px.  
* `PostalRM4SCCHeight100.png` – un code‑barres RM4SCC avec une largeur de 4 px et une hauteur fixe de 100 px.

---

## Comment définir la largeur d’un code‑barres postal

L’étape **comment définir la largeur** est la même pour chaque format postal pris en charge :

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` est un entier représentant la taille en pixels d’un seul module.  
* Une valeur typique pour les codes‑barres postaux est **4 px**, mais vous pouvez l’augmenter pour une impression à plus haute résolution.  

**Astuce :** Lors d’une impression sur une imprimante à DPI contrôlé, multipliez la largeur en pixels par le facteur DPI de l’imprimante afin de conserver les dimensions physiques.

---

## Modifier la hauteur du code‑barres pour le code‑barres postal RM4SCC

Seul un sous‑ensemble de symbologies postales (par ex., RM4SCC) nécessite une hauteur explicite. Utilisez la propriété **modifier la hauteur du code‑barres** :

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` représente la hauteur totale de l’image du code‑barres, pas la hauteur d’un seul module.  
* Définir `BarHeight` à **100 px** produit un code‑barres haut et facilement lisible, conforme à de nombreuses directives des services postaux.

**Cas limite :** Si vous définissez une hauteur trop petite, le code‑barres peut devenir illisible par les scanners. Testez toujours avec une impression physique avant un déploiement en masse.

---

## Fichier source complet pour copier‑coller rapidement

Voici le programme complet que vous pouvez copier dans un nouveau projet console. Aucun autre code n’est nécessaire.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Sortie attendue** (console) :

```
Both postal barcodes have been saved.
```

Et deux fichiers PNG apparaissent dans le dossier de sortie, chacun affichant un code‑barres postal clair, prêt à être imprimé ou intégré.

---

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| *Et si j’ai besoin d’une X‑dimension différente pour chaque code‑barres ?* | Créez des instances séparées de `BarcodeGenerator` et attribuez une valeur distincte à `XDimension.Pixels` avant d’appeler `Save`. |
| *Pourquoi le code‑barres Planet ignore‑t‑il `BarHeight` ?* | Le format Planet calcule automatiquement la hauteur à partir de la X‑dimension, donc la définition de `BarHeight` n’a aucun effet. |
| *Puis‑je générer du SVG au lieu du PNG ?* | Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Svg`. |
| *Que faire si l’image est floue à l’impression ?* | Augmentez la X‑dimension (par ex., à 6 px) et générez l’image à un DPI plus élevé en utilisant les paramètres `Resolution` du générateur. |

---

## Conclusion

Vous savez maintenant comment **créer des images de code‑barres postal** en C# et comment **définir précisément la largeur** et **modifier la hauteur du code‑barres** à l’aide de l’API `BarcodeGenerator`. L’exemple couvre les formats à taille automatique (Planet) et à taille manuelle (RM4SCC), vous offrant une base solide pour tout projet d’automatisation postale.

Ensuite, vous pourriez explorer :
* Ajouter du texte lisible par l’homme sous le code‑barres (`CodeTextParameters`).  
* Exporter vers d’autres formats comme SVG ou PDF pour une impression vectorielle.  
* Intégrer le générateur dans une API web afin de servir les codes‑barres à la demande.

N’hésitez pas à expérimenter avec différentes dimensions, encodages et formats de sortie pour les adapter à votre flux de travail d’envoi de courrier. Bon codage !

## Que devez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}