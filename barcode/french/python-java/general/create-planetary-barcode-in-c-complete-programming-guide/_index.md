---
category: general
date: 2026-07-30
description: Créez rapidement un code‑barres planétaire avec C#. Apprenez à générer
  un code‑barres planétaire, à définir une hauteur de code‑barres personnalisée et
  à exporter l’image du code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planetary barcode
- generate planet barcode
- custom barcode height
- export barcode image
- customize postal barcode
language: fr
lastmod: 2026-07-30
og_description: Créez un code‑barres planétaire en C# et générez instantanément un
  code‑barres planétaire avec une hauteur personnalisée, puis exportez l’image du
  code‑barres pour tout système postal.
og_image_alt: Screenshot showing a generated planetary barcode saved as a PNG file
og_title: Créer un code‑barres planétaire en C# – Tutoriel complet étape par étape
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  headline: Create planetary barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  name: Create planetary barcode in C# – Complete Programming Guide
  steps:
  - name: 'Example 1: Default planetary barcode (auto height)'
    text: '```csharp using Aspose.Barcode; using Aspose.Barcode.Generation;'
  - name: 'Example 2: Planet barcode with a custom 100‑pixel bar height'
    text: 'Sometimes you need a taller barcode for a specific label printer. Here’s
      how to set a **custom barcode height**:'
  - name: 'Example 3: RM4SCC barcode with a custom 100‑pixel bar height'
    text: 'The Planet format isn’t the only postal symbology you might encounter.
      Let’s **customize postal barcode** for RM4SCC, which is popular in the UK and
      parts of Europe:'
  type: HowTo
tags:
- barcode
- C#
- planetary barcode
title: Créer un code‑barres planétaire en C# – Guide complet de programmation
url: /fr/python-java/general/create-planetary-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres planétaire en C# – Guide de programmation complet

Avez-vous déjà eu besoin de **créer un code-barres planétaire** mais n'étiez pas sûr des propriétés à ajuster ? Vous n'êtes pas seul ; la symbologie Planet peut sembler un peu mystérieuse jusqu'à ce que vous la voyiez en action. Dans ce guide, nous allons **générer des objets de code-barres Planet**, ajuster une **hauteur de code-barres personnalisée**, et enfin **exporter l'image du code-barres** qui fonctionne avec n'importe quel flux de travail postal.

Considérez un code-barres planétaire comme la version du service postal d'un QR code — compact, lisible par machine, et étonnamment flexible. À la fin de ce tutoriel, vous serez capable de **personnaliser les paramètres du code-barres postal** sans fouiller dans d'innombrables documents d'API, et vous disposerez de trois extraits de code prêts à l'emploi que vous pourrez intégrer à votre propre projet.

---

## Prérequis – Ce dont vous avez besoin avant de commencer

| Exigence | Pourquoi c'est important |
|----------|---------------------------|
| .NET 6.0 or later | Runtime moderne, prise en charge complète d'Aspose.Barcode |
| Visual Studio 2022 (or any C# IDE) | Débogage pratique et IntelliSense |
| **Aspose.Barcode for .NET** NuGet package | Fournit `BarcodeGenerator`, `EncodeTypes` et les formats d'image |
| Write access to a folder on disk | Nécessaire pour l'appel `Save` qui **exporter l'image du code-barres** |

Vous pouvez ajouter la bibliothèque via la console du gestionnaire de packages :

```powershell
Install-Package Aspose.Barcode
```

C’est tout — pas de DLL supplémentaires, pas de services externes. Prêt ? Plongeons‑nous.

---

## Créer un code-barres planétaire – Étape par étape

Ci‑dessous, nous passerons en revue trois exemples pratiques :

1. **Code-barres planétaire à hauteur par défaut** (dimension automatique)
2. **Code-barres Planet avec une hauteur de barre personnalisée de 100 pixels**
3. **Code-barres RM4SCC avec une hauteur personnalisée** (vous montre comment **personnaliser le code-barres postal** au‑delà de Planet)

Chaque exemple s'appuie sur le précédent, donc n'hésitez pas à copier‑coller le bloc complet dans une nouvelle application console et à l'exécuter.

### Exemple 1 : Code-barres planétaire par défaut (hauteur automatique)

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a generator for the Planet symbology and supply the data to encode
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Define the module (X) size – 4 pixels per bar
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Render the barcode to a PNG file (this will **export barcode image**)
        gen.Save(@"C:\Barcodes\PostalPlanetAuto.png", BarCodeImageFormat.Png);
    }
}
```

**Que s'est‑il passé ?**  
Le `BarcodeGenerator` est votre point d'entrée ; vous lui indiquez *quoi* (Planet) et *quelle donnée* (`"123456"`). La X‑dimension contrôle la largeur de chaque barre, et comme nous n'avons pas modifié la hauteur, la bibliothèque choisit automatiquement une taille raisonnable selon les normes postales. Lorsque vous exécutez le programme, vous trouverez un PNG nommé **PostalPlanetAuto.png** dans `C:\Barcodes`.

> **Astuce :** Si vous déboguez, ouvrez le PNG avec n'importe quel visualiseur d'images — remarquez comment les barres sont nettes et uniformément espacées. C’est la base d’une opération fiable de **générer le code-barres Planet**.

### Exemple 2 : Code-barres Planet avec une hauteur de barre personnalisée de 100 pixels

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Initialise the generator with the same data
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Override the default bar height to 100 pixels
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Save the customised barcode image
        gen.Save(@"C:\Barcodes\PostalPlanetHeight100.png", BarCodeImageFormat.Png);
    }
}
```

**Pourquoi ajuster la hauteur ?**  
Une barre plus haute peut améliorer la fiabilité du scan sur des imprimantes basse résolution, et certains services postaux demandent explicitement une hauteur minimale. En ajustant `BarHeight.Pixels`, nous conservons le contrôle total sur le poids visuel du symbole tout en continuant à **générer le code-barres Planet** en interne.

### Exemple 3 : Code-barres RM4SCC avec une hauteur personnalisée de 100 pixels

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the RM4SCC symbology
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Specify a 100‑pixel bar height
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Export the barcode to a PNG file
        gen.Save(@"C:\Barcodes\PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
    }
}
```

Remarquez que le code est presque identique à l'Exemple 2 — seule l'énumération `EncodeTypes` change. C’est la beauté d'Aspose.Barcode : vous **personnalisez les formats de code-barres postal** sans devoir apprendre une nouvelle surface d'API.

---

## Comprendre les propriétés clés

| Propriété | Signification | Valeurs typiques |
|-----------|---------------|------------------|
| `XDimension.Pixels` | Largeur d'un module unique (la plus petite barre) | 2‑6 px pour la plupart des imprimantes |
| `BarHeight.Pixels` | Hauteur de la barre la plus haute (en pixels) | 50‑150 px, selon la taille de l'étiquette |
| `EncodeTypes` | Symbologie à générer (Planet, RM4SCC, etc.) | `EncodeTypes.Planet`, `EncodeTypes.RM4SCC` |
| `BarCodeImageFormat` | Format d'image de sortie | `.Png`, `.Jpeg`, `.Bmp` |

Lorsque vous **exportez l'image du code-barres**, la bibliothèque rasterise les données vectorielles dans le format choisi. PNG est sans perte, ce qui le rend parfait pour des étiquettes de haute qualité. Si vous avez besoin d'un fichier plus petit pour le web, passez à `BarCodeImageFormat.Jpeg` et ajustez la compression.

---

## Pièges courants et comment les éviter

* **Largeur de module incorrecte** – Définir `XDimension.Pixels` trop bas peut faire fusionner les barres lors de l'impression. Testez avec une imprimante physique avant la production en masse.  
* **Permissions d'écriture manquantes** – La méthode `Save` lève une exception si le dossier cible n'est pas accessible en écriture. Vérifiez toujours le chemin ou utilisez `Path.GetTempPath()` pour des tests rapides.  
* **Longueur de données incorrecte** – Planet attend une chaîne numérique de 6‑8 chiffres. Fournir des caractères alphabétiques déclenchera une erreur de validation.  
* **Oublier de libérer les ressources** – `BarcodeGenerator` implémente `IDisposable`. Dans un service de longue durée, encapsulez‑le dans un bloc `using` pour libérer les ressources natives.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save...
}
```

---

## Résultat attendu – Ce que vous devriez voir

Après avoir exécuté les trois exemples, le dossier `C:\Barcodes` contiendra :

| Fichier | Description |
|---------|-------------|
| `PostalPlanetAuto.png` | Code-barres Planet à hauteur par défaut (dimension automatique) |
| `PostalPlanetHeight100.png` | Code-barres Planet avec une **hauteur de code-barres personnalisée** de 100 px |
| `PostalRM4SCCHeight100.png` | Code-barres RM4SCC, également **hauteur de code-barres personnalisée** de 100 px |

Ouvrez l'un de ces PNG ; vous remarquerez des barres verticales nettes avec les données numériques encodées en dessous (ou au-dessus, selon la symbologie). Scannez‑les avec une application de lecture de code-barres sur smartphone — si l'application reconnaît « 123456 », vous avez réussi à **créer un code-barres planétaire** et à **exporter l'image du code-barres**.

---

## Aller plus loin – Prochaines étapes et sujets associés

* **Génération par lots** – Parcourez une liste CSV de codes postaux et enregistrez chaque code-barres automatiquement.  
* **Intégration dans les PDF** – Utilisez `PdfDocument` d'Aspose.PDF pour placer le PNG directement sur une étiquette d'expédition.  
* **Dimensionnement dynamique** – Calculez `BarHeight.Pixels` en fonction du DPI de l'étiquette pour garantir des dimensions physiques cohérentes.  
* **Autres symbologies postales** – Explorez `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail` ou `EncodeTypes.Aztec` pour une couverture plus large.  

Si vous êtes curieux des calculs de **hauteur de code-barres personnalisée**, consultez la documentation officielle d'Aspose.Barcode sur *les dimensions des modules* — les formules sont simples et fonctionnent pour toutes les symbologies prises en charge.

---

## Conclusion

Nous avons parcouru un processus complet et pratique pour **créer des images de code-barres planétaire** en C#. En partant d'un générateur simple, nous avons appris comment **générer le code-barres Planet**, appliquer une **hauteur de code-barres personnalisée**, et enfin **exporter l'image du code-barres** qui respecte les normes postales. En ajustant seulement quelques propriétés, vous pouvez également **personnaliser le code-barres postal** pour RM4SCC ou tout autre format pris en charge.

Essayez : modifiez la chaîne de données, expérimentez avec différentes valeurs `XDimension`, ou remplacez le PNG par du JPEG. La bibliothèque est suffisamment flexible pour s'adapter à la plupart des scénarios réels, et vous disposez maintenant d'une base solide sur laquelle construire.

Des questions ou envie de partager vos propres astuces de code-barres ? Laissez un commentaire ci‑dessous, et bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un code-barres hauteur personnalisée – Codes-barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Comment générer un code-barres Aztec avec un rapport d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Créer une image de code-barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}