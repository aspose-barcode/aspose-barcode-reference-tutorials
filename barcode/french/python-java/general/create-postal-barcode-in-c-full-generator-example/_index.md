---
category: general
date: 2026-07-15
description: Créez rapidement un code‑barres postal en C#. Cet exemple de générateur
  de code‑barres montre comment exporter le code‑barres au format PNG pour les codes‑barres
  Planet et RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: fr
lastmod: 2026-07-15
og_description: Créez un code‑barres postal en C# avec ce guide étape par étape. Découvrez
  l’exemple de générateur de code‑barres qui vous permet d’exporter l’image du code‑barres
  au format PNG.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Créer un code-barres postal en C# – Guide complet du générateur
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Créer un code-barres postal en C# – Exemple complet de générateur
url: /fr/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres postal en C# – Exemple complet de générateur

Vous vous êtes déjà demandé comment **créer un code-barres postal** dans un projet .NET sans fouiller dans d'innombrables documents ? Vous n'êtes pas seul. Que vous construisiez un système d'étiquettes d'envoi ou que vous automatisiez l'affranchissement en masse, générer un PNG de code-barres net est une compétence indispensable. Dans ce tutoriel, nous parcourrons un **exemple complet de générateur de code-barres** qui montre exactement comment **exporter des images de code-barres** au **format PNG de code-barres**.

Nous couvrirons tout, de la configuration du dossier de sortie à l'ajustement de la largeur du module et de la hauteur des barres pour les normes Planet et RM4SCC. À la fin, vous disposerez d’une application console prête à l’emploi qui génère quatre fichiers PNG — deux avec hauteur automatique et deux avec une hauteur fixe de 100 px. Pas de superflu, juste une solution pratique que vous pouvez copier‑coller.

## Prérequis

- SDK .NET 6 ou ultérieur (le code fonctionne avec .NET Core et .NET Framework)
- Un IDE ou éditeur avec lequel vous êtes à l'aise (Visual Studio, VS Code, Rider…)
- Le package NuGet Aspose.BarCode pour .NET (installer via `dotnet add package Aspose.BarCode`)

C’est tout — pas de services supplémentaires, pas d’API web. Juste un projet C# local.

## Créer un code-barres postal – Étape par étape

Ci-dessous, nous décomposons le processus en cinq étapes claires. Chaque étape possède un en‑tête descriptif **H2** qui inclut le mot‑clé principal ou secondaire, afin que vous trouviez exactement ce dont vous avez besoin d’un simple coup d’œil.

### Étape 1 : Préparer le répertoire de sortie

Tout d’abord, nous avons besoin d’un dossier où les fichiers PNG générés seront stockés. Codifier en dur un chemin fonctionne pour une démonstration, mais en production vous le liriez probablement depuis la configuration.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Astuce :** Utiliser `Path.Combine` rend le code indépendant du système d’exploitation, et `Directory.CreateDirectory` peut être appelé en toute sécurité même si le dossier existe déjà.

### Étape 2 : Générer un code-barres Planet avec hauteur automatique

Nous arrivons maintenant au cœur de la partie **comment générer un code-barres planet**. Nous créons une instance de `BarcodeGenerator`, définissons la largeur du module (dimension X), et laissons la bibliothèque déterminer la hauteur des barres.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

L’énumération `EncodeTypes.Planet` indique à Aspose que nous voulons la symbologie Planet, courante pour les services postaux de nombreux pays. Comme nous n’avons pas modifié `BarHeight`, le générateur choisit une valeur par défaut raisonnable qui garde le code-barres lisible.

### Étape 3 : Générer un code-barres RM4SCC avec hauteur automatique

RM4SCC est le format de code-barres postal canadien. Le code reflète l’exemple Planet, ce qui illustre le modèle **exemple de générateur de code-barres** que vous pouvez réutiliser pour toute symbologie prise en charge.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Encore une fois, nous nous appuyons sur la hauteur automatique, ce qui est parfait pour des prototypes rapides ou lorsque vous laissez l’imprimante gérer le redimensionnement.

### Étape 4 : Générer un code-barres Planet avec hauteur fixe (100 px)

Parfois, le système d’envoi exige une hauteur de barre stricte—peut‑être que l’imprimante attend exactement 100 px. Voici comment **exporter une image de code-barres** avec une hauteur imposée.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Définir `BarHeight.Pixels` remplace le calcul automatique. Le reste des paramètres reste identique, assurant une cohérence visuelle entre les images à hauteur automatique et à hauteur fixe.

### Étape 5 : Générer un code-barres RM4SCC avec hauteur fixe (100 px)

Nous répétons l’approche à hauteur fixe pour RM4SCC. Cela montre la flexibilité de l’**exemple de générateur de code-barres** : vous pouvez combiner paramètres automatiques et manuels selon la symbologie.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Liste complète du code source

En rassemblant le tout, voici le programme complet et exécutable. Copiez le bloc ci‑dessous dans un nouveau projet console et cliquez sur **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

L’exécution de ce programme crée les fichiers suivants (tous au **format PNG de code-barres**) :

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Chaque image est une représentation nette, noir‑sur‑blanc, prête à être imprimée ou traitée davantage.

## Pourquoi cette approche fonctionne

- **Cohérence :** En fixant `XDimension.Pixels` à 4 pour tous les codes‑barres, vous garantissez la même largeur de module, ce qui est essentiel pour les scanners qui attendent une taille de point spécifique.
- **Flexibilité :** La même base de code vous permet de basculer entre hauteur automatique et hauteur fixe sans réécrire la logique du générateur—parfait pour les solutions multi‑transporteurs.
- **Performance :** Générer un PNG est une opération légère ; la bibliothèque Aspose transmet l’image directement sur le disque, évitant un surcoût mémoire inutile.
- **Portabilité :** Les appels `Path.Combine` et `Directory.CreateDirectory` maintiennent le code multiplateforme, de sorte que la même source fonctionne sous Windows, Linux et macOS.

## Pièges courants & comment les éviter

| Problème | Pourquoi cela se produit | Solution |
|------|----------------|-----|
| Le code‑barres apparaît flou | Utilisation d’une dimension X très faible (p. ex., 1 px) | Augmenter `XDimension.Pixels` à au moins 3‑4 pour les codes‑barres postaux |
| Le scanner rejette l’image | Hauteur de barre trop petite ou trop grande pour l’imprimante | Utiliser `BarHeight.Pixels` pour correspondre aux spécifications de l’imprimante |
| Le fichier PNG est corrompu | Oublier de fermer le flux (rare avec Aspose) | Laisser la méthode `Save` gérer la libération; éviter la gestion manuelle du flux sauf si nécessaire |
| Dossier de sortie introuvable | Chemin codé en dur pointe vers un répertoire inexistant | Toujours appeler `Directory.CreateDirectory` avant d’enregistrer |

## Étendre l’exemple

Maintenant que vous avez maîtrisé les bases de **créer un code-barres postal**, vous pourriez vouloir explorer :

- **Ajouter du texte lisible par l’homme** sous le code‑barres (`DisplayText` property)
- **Changer les couleurs** (`ForeColor`, `BackColor`) pour le branding
- **Traitement par lots** d’une liste CSV de codes postaux (boucle sur le générateur)
- **Exporter vers d’autres formats** comme SVG ou PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Chacune de ces extensions suit le même modèle démontré dans cet **exemple de générateur de code‑barres**, vous permettant d’expérimenter sans repartir de zéro.

## Conclusion

Vous

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres C# – Exemple GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Comment créer un texte de code étendu dotcode avec Aspose.BarCode pour .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Comment créer un code‑barres Aztec avec correction d’erreur en .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}