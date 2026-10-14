---
category: general
date: 2026-10-02
description: Créer un code‑barres à partir du texte en C# avec Aspose.BarCode. Apprenez
  à générer un code‑barres PDF417 et découvrez comment le générer en mode compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: fr
lastmod: 2026-10-02
og_description: Créer un code‑barres à partir de texte en C# avec Aspose.BarCode.
  Ce guide montre comment générer un code‑barres PDF417 et comment le générer en mode
  compact.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Créer un code‑barres à partir de texte en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Comment créer un code‑barres à partir de texte en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres à partir de texte en C# avec Aspose.BarCode

Si vous devez **créer un code‑barres à partir de texte** dans une application .NET, ce guide vous accompagne pas à pas. Vous verrez un exemple prêt à l’exécution qui **génère un code‑barres PDF417** et qui répond également à la question **comment générer un code‑barres PDF417** dans une mise en page compacte.

Générer un code‑barres par programme élimine les étapes manuelles et garantit la cohérence entre tous les documents. À la fin de ce tutoriel, vous disposerez d’un fichier PNG contenant un code‑barres PDF417 que vous pourrez intégrer dans des factures, des billets ou des cartes d’identité.

## Ce dont vous aurez besoin

- SDK .NET 6.0 ou version ultérieure (le code fonctionne également avec .NET Framework 4.7.2+)
- Visual Studio 2022 ou tout éditeur supportant C#
- Une licence NuGet pour **Aspose.BarCode for .NET** (une version d’essai gratuite suffit pour les tests)

> **Astuce pro :** Ajoutez le package NuGet via la CLI pour garder le projet propre :  
> `dotnet add package Aspose.BarCode`

## Étape 1 : Configurer un projet console

Créez une nouvelle application console et référencez la bibliothèque Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

La commande `dotnet new console` génère un fichier `Program.cs` que nous remplacerons par l’exemple complet ci‑dessous.

## Étape 2 : Comment créer un code‑barres à partir de texte – code principal

Ouvrez `Program.cs` et remplacez son contenu par le code suivant. Chaque ligne est commentée pour expliquer son utilité.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Pourquoi chaque paramètre est important

| Paramètre | Objectif |
|-----------|----------|
| `EncodeTypes.Pdf417` | Sélectionne la symbologie PDF417, capable de stocker de grandes quantités de données dans une matrice bidimensionnelle. |
| `XDimension.Pixels = 2` | Contrôle la largeur de chaque module ; une valeur de 2 pixels équilibre lisibilité et taille du fichier. |
| `Pdf417.Columns = 3` | Réduit le nombre de colonnes, rendant le code‑barres plus compact sans perdre de données. |
| `Pdf417.Truncate = true` | Active le mode compact, supprimant les remplissages inutiles et raccourcissant le code‑barres. |
| `BarCodeImageFormat.Png` | PNG conserve une qualité sans perte, idéale pour un traitement ultérieur ou l’impression. |

## Étape 3 : Générer le code‑barres PDF417 – exécuter l’exemple

Compilez et lancez le projet :

```bash
dotnet run
```

Lorsque l’exécution se termine, vous verrez :

```
Barcode saved to CompactPdf417.png
```

Ouvrez `CompactPdf417.png` pour visualiser le résultat. L’image contient un code‑barres PDF417 qui encode la chaîne **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Texte alternatif : création de code‑barres à partir de texte – code‑barres PDF417 enregistré en PNG*

## Étape 4 : Comment générer un code‑barres PDF417 avec correction d’erreur personnalisée (facultatif)

Si votre environnement de numérisation est bruyant, vous pouvez augmenter le niveau de correction d’erreur :

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Augmenter le niveau d’erreur rend le code‑barres plus grand mais améliore sa résistance aux dommages.

## Étape 5 : Pièges courants et gestion des cas limites

1. **Caractères invalides** – PDF417 prend en charge Unicode, mais certains lecteurs plus anciens peuvent rejeter les symboles non‑ASCII. Testez avec le matériel cible.
2. **Permissions du chemin de fichier** – Assurez‑vous que le répertoire d’écriture est accessible ; sinon `Save` lèvera une `UnauthorizedAccessException`.
3. **Taille de l’image** – Des valeurs très élevées de `XDimension` produisent de gros fichiers PNG. Gardez la taille en pixels entre 1 et 4 pour la plupart des scénarios d’affichage à l’écran.

## Récapitulatif

Vous savez maintenant comment **créer un code‑barres à partir de texte** en C# avec Aspose.BarCode, comment **générer un code‑barres PDF417** avec une mise en page compacte, et les étapes exactes pour **comment générer un code‑barres PDF417** avec des paramètres personnalisés. Le code complet et exécutable ci‑dessus peut être copié dans n’importe quel projet .NET et adapté à d’autres entrées texte ou formats de sortie (par ex., JPEG, BMP).

## Étapes suivantes

- Explorez d’autres symbologies telles que QR Code ou Code128 en modifiant `EncodeTypes`.
- Intégrez le PNG généré dans un PDF à l’aide d’Aspose.PDF pour une création de document de bout en bout.
- Expérimentez avec `generator.Parameters.Barcode.Pdf417.Rows` pour contrôler la densité verticale.

N’hésitez pas à modifier l’exemple, à intégrer le code‑barres dans vos propres applications et à partager vos résultats avec la communauté. Bon codage !

## Quoi apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos projets.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}