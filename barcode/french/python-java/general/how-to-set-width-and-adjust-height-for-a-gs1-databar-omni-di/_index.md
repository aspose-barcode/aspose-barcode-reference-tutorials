---
category: general
date: 2026-09-29
description: Comment définir la largeur d’un code‑barres GS1 DataBar omni‑directionnel
  et comment modifier la hauteur en C#. Suivez un guide étape par étape avec le code
  complet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: fr
lastmod: 2026-09-29
og_description: Comment définir la largeur d’un code‑barres GS1 DataBar Omni‑Directionnel
  et comment modifier la hauteur en C#. Découvrez les appels d’API exacts et consultez
  un exemple complet et exécutable.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Comment définir la largeur d’un code‑barres GS1 DataBar – guide C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Comment définir la largeur et ajuster la hauteur d’un code‑barres GS1 DataBar
  Omni‑directionnel en C#
url: /fr/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir la largeur et ajuster la hauteur d'un code‑barres GS1 DataBar Omni‑Directional en C#

Définir la largeur d'un code‑barres GS1 DataBar Omni‑Directional est une tâche fréquente lorsque vous avez besoin d'une taille précise pour les équipements de lecture. Dans ce tutoriel, vous apprendrez également **comment modifier la hauteur** afin que le code‑barres s'adapte parfaitement à votre mise en page. Le guide vous accompagne tout au long du processus complet, de la configuration du projet à un exemple de code entièrement exécutable.

Nous couvrirons :

* Le package NuGet requis et la version .NET.
* Pourquoi la X‑dimension (largeur du module) est importante pour la lisibilité du code‑barres.
* Les appels API exacts pour **comment définir la largeur** et **comment modifier la hauteur**.
* La gestion des cas limites tels que la largeur minimale du module et le rendu haute résolution.
* Un exemple complet, copiable‑collable, qui produit deux fichiers PNG avec des hauteurs de barres différentes.

## Prérequis

| Exigence | Raison |
|------------|--------|
| .NET 6.0 SDK ou version ultérieure | L'exemple utilise les fonctionnalités modernes de C# et fonctionne sous Windows, Linux ou macOS. |
| Visual Studio 2022 (ou tout IDE C#) | Fournit IntelliSense pour l'API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Contient `BarcodeGenerator`, `EncodeTypes` et la prise en charge des formats d'image. Installez avec `dotnet add package Aspose.Barcode`. |
| Permission d'écriture dans un dossier où les fichiers PNG seront enregistrés | Le générateur écrit les images de sortie sur le disque. |

## Comment définir la largeur du code‑barres

L'étape **comment définir la largeur** s'effectue en configurant la propriété `XDimension` des paramètres du code‑barres. `XDimension` représente la largeur du module (le plus petit trait ou espace) en pixels, points ou millimètres. La définir correctement garantit que le code‑barres respecte les spécifications du scanner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Pourquoi la dimension X est importante

* **Tolérance du scanner** – La plupart des scanners attendent une largeur minimale de module ; une valeur trop petite peut entraîner des erreurs de lecture.
* **Résolution d'impression** – Lors d'une impression à 300 dpi, un module de 2 px correspond à ~0,17 mm, ce qui se situe dans la fourchette recommandée pour le GS1 DataBar.
* **Taille de l'image** – Des valeurs de X‑dimension plus élevées augmentent la largeur globale du code‑barres, ce qui peut affecter les contraintes de mise en page.

### Conseils pour des réglages de largeur fiables

* **Ne jamais définir XDimension en dessous de 1 px** – la bibliothèque limitera la valeur, mais le code‑barres résultant risque d'être illisible.
* **Adapter à la DPI cible** – si vous rendez dans un format haute résolution (par ex., TIFF à 600 dpi), augmentez XDimension proportionnellement.
* **Tester avec un scanner réel** – après avoir modifié la largeur, validez le code‑barres sur le dispositif qui le lira.

## Comment modifier la hauteur du code‑barres

Une fois la largeur définie, vous pouvez contrôler la taille verticale avec la propriété `BarHeight`. Le code suivant montre **comment modifier la hauteur** de 30 px à 60 px et enregistrer deux images distinctes.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Comprendre la hauteur des barres

* **Équilibre visuel** – Des barres plus hautes améliorent la lisibilité sur des fonds à faible contraste mais augmentent l'empreinte verticale de l'image.
* **Limites réglementaires** – Certaines normes (par ex., l'étiquetage retail) spécifient une hauteur maximale des barres ; ajustez en conséquence.
* **Ratio d'aspect** – Modifier la hauteur n'affecte pas la largeur du module ; vous pouvez affiner les deux indépendamment.

### Gestion des cas limites pour les ajustements de hauteur

| Situation | Approche recommandée |
|-----------|----------------------|
| Height < 10 px | Augmentez à au moins 10 px ; des barres très courtes peuvent être ignorées par les scanners. |
| Barres très hautes (≥ 100 px) | Vérifiez que le support de sortie (papier, étiquette) peut accueillir l'espace supplémentaire. |
| Besoin d'un redimensionnement proportionnel | Calculez `BarHeight = XDimension * desiredRatio` pour garder la cohérence visuelle. |

## Exemple complet et exécutable

Voici le programme complet qui combine les étapes **comment définir la largeur** et **comment modifier la hauteur**. Copiez le code dans un nouveau projet console, restaurez le package NuGet Aspose.Barcode, puis exécutez-le. Deux fichiers PNG apparaîtront dans le dossier `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Sortie attendue**

L'exécution du programme produit deux fichiers PNG :

* `DatabarBarHeight30Pixels.png` – un code‑barres de 30 px de hauteur, modules de 2 px de largeur.
* `DatabarBarHeight60Pixels.png` – le même code‑barres avec le double de la taille verticale.

Ouvrez l'une ou l'autre image avec n'importe quel visualiseur ; vous verrez un symbole GS1 DataBar Omni‑Directional propre, prêt à être scanné.

## Questions fréquentes

| Question | Réponse |
|----------|--------|
| *Puis‑je utiliser des millimètres au lieu de pixels ?* | Oui. Définissez `generator.Parameters.Barcode.XDimension.Millimeters` et `BarHeight.Millimeters`. La bibliothèque convertit en pixels du dispositif en fonction du DPI de l'image. |
| *Et si j'ai besoin d'un type de code‑barres différent ?* | Remplacez `EncodeTypes.DatabarOmniDirectional` par toute autre valeur `EncodeTypes` (par ex., `EncodeTypes.QR`). Les propriétés de largeur et de hauteur fonctionnent de la même manière. |
| *Existe‑t‑il un moyen de générer du SVG au lieu du PNG ?* | Utilisez `BarCodeImageFormat.Svg` dans l'appel `Save`. Les réglages de largeur/hauteur restent applicables. |
| *Dois‑je appeler `generator.Dispose()` ?* | Le `BarcodeGenerator` implémente `IDisposable`. Dans une application console, vous pouvez le placer dans un bloc `using`, mais pour des exemples courts c'est optionnel. |

## Conclusion

Vous savez maintenant **comment définir la largeur** d'un code‑barres GS1 DataBar Omni‑Directional et **comment modifier la hauteur** en utilisant l'API Aspose.Barcode en C#. L'exemple complet montre comment créer un générateur, configurer `XDimension` et `BarHeight`, puis enregistrer des fichiers PNG avec des tailles verticales différentes.

À partir d'ici, vous pouvez :

* Expérimenter d'autres `EncodeTypes` (par ex., QR, Code128).
* Rendre dans des formats haute résolution comme le TIFF pour l'impression.
* Intégrer le générateur dans une API web qui renvoie des codes‑barres à la volée.

Bon codage, et que vos codes‑barres soient toujours lus correctement !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d'autres fonctionnalités de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}