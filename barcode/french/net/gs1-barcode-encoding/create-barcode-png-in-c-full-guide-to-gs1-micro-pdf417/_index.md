---
category: general
date: 2026-08-12
description: Créez rapidement un PNG de code‑barres en C# avec Aspose.BarCode. Apprenez
  à générer un code‑barres PDF417 en C# et maîtrisez l’utilisation du générateur de
  code‑barres en un seul tutoriel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: fr
lastmod: 2026-08-12
og_description: Créer un PNG de code-barres en C# avec Aspose.BarCode. Ce tutoriel
  vous montre comment générer un code-barres PDF417 en C# et utiliser efficacement
  le générateur de code-barres.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Créer un PNG de code‑barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Créer un PNG de code‑barres en C# – guide complet du GS1 Micro PDF417
url: /fr/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code-barres en C# – guide complet du GS1 Micro PDF417

Si vous devez **créer un PNG de code-barres** dans une application .NET, ce guide vous montre exactement comment procéder. Vous apprendrez à générer un code-barres PDF417 en C# et à voir les modèles d'**utilisation du générateur de code-barres** qui fonctionnent en production.

Générer une image de code-barres est une exigence courante pour les systèmes d'inventaire, les étiquettes d'expédition et les plateformes de billetterie. À la fin de ce tutoriel, vous disposerez d'un programme console autonome qui écrit un fichier PNG contenant un code-barres GS1 Micro PDF417, prêt pour le traitement en aval.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* .NET 6.0 SDK ou version ultérieure installé (le code fonctionne également avec .NET Framework 4.7.2+).
* Une version récente du package NuGet **Aspose.BarCode for .NET**. Installez‑le avec  
  `dotnet add package Aspose.BarCode`.
* Familiarité de base avec les projets console C#.
* Permission d'écriture sur le dossier où le PNG sera enregistré.

Ces exigences maintiennent l'exemple léger tout en reflétant une configuration réelle.

## Étape 1 : Configurer le projet C#

Créez un nouveau projet console et ajoutez la référence Aspose.BarCode :

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

Le CLI `dotnet` crée un fichier `Program.cs` et restaure le package NuGet. Cette étape est essentielle pour l'**utilisation du générateur de code-barres** car la bibliothèque contient la classe `BarcodeGenerator` que nous allons employer.

## Étape 2 : Écrire le code complet de génération du code-barres

Remplacez le contenu de `Program.cs` par le code suivant. Il contient chaque ligne nécessaire pour **créer un PNG de code-barres** du début à la fin.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante

| Ligne | Raison |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Sélectionne la variante PDF417 spécifique requise pour les applications GS1. |
| Data string `"(01)12345678901231(10)ABC123"` | Démontre la syntaxe GS1 AI pour un GTIN (01) et un numéro de lot (10). |
| `XDimension.Pixels = 2` | Contrôle la taille physique du code-barres ; une valeur par défaut courante pour l'affichage à l'écran. |
| `ImageResolution = 300` | Augmente le DPI, garantissant que le PNG reste net lors de l'impression. |
| `BackgroundColor = Transparent` | Rend le PNG compatible avec les superpositions pour la composition d'interface. |
| `Save(..., BarCodeImageFormat.Png)` | Enregistre le code-barres au format PNG, ce qui satisfait l'objectif de **créer un PNG de code-barres**. |

## Étape 3 : Exécuter le programme et vérifier la sortie

Exécutez l'application console :

```bash
dotnet run
```

Vous devriez voir le message de confirmation et trouver `output.png` dans le dossier du projet. L'ouverture du fichier affichera un code-barres GS1 Micro PDF417 qui encode les données d'exemple.

![create barcode PNG example](barcode-example.png)

*Alt text: exemple de création de PNG de code-barres montrant un code GS1 Micro PDF417.*

### Résultat visuel attendu

Le PNG contient un code-barres rectangulaire avec des modules noirs espacés uniformément. Le scanner le lisant avec un lecteur compatible GS1 renvoie la chaîne `(01)12345678901231(10)ABC123`, confirmant que **générer un code-barres PDF417 C#** a réussi.

## Étape 4 : Explorer les variantes courantes

### Modifier la symbologie

Si vous avez besoin d'un PDF417 standard au lieu de la version micro, remplacez le type d'encodage :

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Ajuster le format d'image

Aspose.BarCode prend en charge de nombreux formats. Pour créer un JPEG à la place :

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Enregistrement dans un flux (utile pour les API web)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Ces extraits illustrent une **utilisation du générateur de code-barres** flexible au‑delà du scénario de sauvegarde de fichier de base.

## Astuces et pièges

* **Valider la longueur des données** – le GS1 Micro PDF417 a une capacité maximale de données ; la dépasser déclenche une exception. Utilisez `generator.Parameters.Barcode.IsValidData(data)` pour vérifier au préalable.
* **Éviter les valeurs XDimension trop petites** – des valeurs inférieures à 1 pixel peuvent produire des codes-barres illisibles sur des appareils à basse résolution.
* **Définir `QuietZone`** si vous intégrez le PNG dans un graphique plus grand ; la zone silencieuse par défaut assure que les scanners peuvent localiser les motifs de début/fin.
* **Sécurité des threads** – les instances de `BarcodeGenerator` ne sont pas thread‑safe. Créez un nouveau générateur par requête dans un service web.

## Conclusion

Vous savez maintenant comment **créer des fichiers PNG de code-barres** en C# avec Aspose.BarCode, comment **générer un code-barres PDF417 C#** avec la variante GS1 Micro, et les modèles essentiels pour une **utilisation efficace du générateur de code-barres**. L'exemple complet et exécutable peut être intégré à n'importe quel projet .NET, et vous pouvez l'étendre avec différentes symbologies, formats d'image ou sorties en flux.

### Et après ?

* Explorer l'**intégration du lecteur de code-barres** pour vérifier automatiquement les images générées.
* Expérimenter avec des **couleurs personnalisées** et l'**intégration de logo** pour des codes-barres adaptés à la marque.
* Examiner la documentation d'Aspose.BarCode pour les paramètres avancés de correction d'erreurs et la génération de PDF417 multi‑pages.

Bon codage, et laissez vos applications parler le langage des machines avec des PNG de code-barres nets et fiables !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment enregistrer un PNG en utilisant DataMatrix C40 avec Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Comment générer un code-barres – Configuration Code 39 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}