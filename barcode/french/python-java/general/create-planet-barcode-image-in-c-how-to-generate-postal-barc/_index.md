---
category: general
date: 2026-07-15
description: Créez rapidement une image de code‑barres Planet avec C#. Apprenez à
  générer un code‑barres postal et à enregistrer l’image du code‑barres au format
  PNG à l’aide d’Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate postal barcode
- how to save barcode image
language: fr
lastmod: 2026-07-15
og_description: Créer une image de code-barres Planet en C#. Ce guide explique comment
  générer un code-barres postal et comment enregistrer l'image du code-barres avec
  des exemples de code clairs.
og_image_alt: Screenshot showing a generated Planet barcode image saved as PNG
og_title: Créer une image de code-barres Planet en C# – Guide rapide des codes-barres
  postaux
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  headline: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  type: TechArticle
- description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  name: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  steps:
  - name: Why This Structure Works
    text: '- **Separate generators**: We instantiate two `BarcodeGenerator` objects
      because the `FilledBars` property is immutable once an image is rendered. Keeping
      them independent avoids side‑effects. - **X‑dimension choice**: A value of 4
      pixels balances readability and file size. If you need a higher‑reso'
  - name: Changing the Data Payload
    text: 'The `EncodeTypes.Planet` symbology expects numeric data up to 16 digits.
      To encode a different tracking number, just replace `"123456"` with your actual
      string:'
  - name: Adjusting Image Format
    text: If you need a JPEG for web delivery, swap `BarCodeImageFormat.Png` with
      `BarCodeImageFormat.Jpeg`. Remember JPEG introduces compression artifacts—avoid
      it for high‑precision scanning.
  - name: Handling Errors Gracefully
    text: 'When dealing with user‑supplied data, wrap the generation in a try‑catch
      block:'
  type: HowTo
- questions:
  - answer: Yes. Aspose.BarCode supports .NET Framework 4.5 and higher. Just change
      the target framework in your `.csproj` file.
    question: Does this work with .NET Framework 4.5?
  - answer: Replace `EncodeTypes.Planet` with any other enum value (e.g., `EncodeTypes.Code128`).
      The rest of the code stays the same.
    question: What if I need a different barcode symbology?
  - answer: 'Absolutely. Use `generator.Parameters.Barcode.BarColor = Color.Blue;`
      before saving. ## Conclusion You now know **how to create planet barcode image**
      in C#, **how to generate postal barcode** with the Aspose.BarCode library, and
      **how to save barcode image** as PNG files. The full example covered i'
    question: Can I change the bar color?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Créer une image de code-barres Planet en C# – Comment générer un code-barres
  postal
url: /fr/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres Planet en C# – Comment générer un code-barres postal

Vous avez déjà eu besoin de **créer une image de code-barres Planet** dans un projet .NET mais vous ne saviez pas par où commencer ? Vous n'êtes pas seul. Dans ce guide, nous allons parcourir **comment générer un code-barres postal** en utilisant Aspose.BarCode, puis montrer **comment enregistrer l'image du code-barres** sur le disque au format PNG.  

Imaginez que vous construisez un système d'envoi qui imprime des étiquettes postales à la volée—disposer d'un générateur de code-barres fiable vous fait gagner des heures de travail manuel. À la fin de ce tutoriel, vous disposerez d'une application console prête à l'emploi qui génère deux fichiers PNG : l'un avec des barres remplies et l'autre avec seulement les contours.

## Prérequis

Avant de plonger dans le code, assurez-vous d'avoir :

- SDK .NET 6 (ou toute version récente de .NET) installé.
- Visual Studio 2022 ou VS Code avec les extensions C#.
- Le package NuGet **Aspose.BarCode for .NET**. Vous pouvez l'ajouter via la CLI :

```bash
dotnet add package Aspose.BarCode
```

Aucune autre dépendance externe n'est requise.

## Étape 1 : Configurer la structure du projet

Tout d'abord, créez un nouveau projet console et ajoutez la bibliothèque de code-barres.

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Le dossier contient maintenant un fichier `Program.cs` où nous placerons toute notre logique.

## Étape 2 : Écrire le code complet – Créer une image de code-barres Planet

Ci-dessous se trouve le programme complet et autonome. Copiez‑collez‑le dans `Program.cs` (en écrasant le squelette généré par `dotnet new`).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Namespace and class are optional in a top‑level program (C# 9+), but we keep them for clarity.
namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Create a Planet barcode generator with the desired data.
            // -----------------------------------------------------------------
            // The "Planet" symbology is used by many postal services for
            // tracking and sorting. Here we encode a simple numeric string.
            var generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // ---------------------------------------------------------------
            // 2️⃣  Set the X‑dimension (width of a single bar) to 4 pixels.
            // ---------------------------------------------------------------
            // XDimension controls the visual density of the barcode.
            // 4 px is a common default that works well on most printers.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 3️⃣  Save the barcode using the default *filled‑bars* appearance.
            // ---------------------------------------------------------------
            // BarCodeImageFormat.Png ensures a lossless image, perfect for
            // later processing or printing.
            string filledPath = "PlanetFilledBars.png";
            generator.Save(filledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Filled bars saved to {filledPath}");

            // -----------------------------------------------------------------
            // 4️⃣  Create another generator for the same data to show empty bars.
            // -----------------------------------------------------------------
            var emptyBarsGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyBarsGenerator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 5️⃣  Disable filled bars so only the outlines are drawn.
            // ---------------------------------------------------------------
            emptyBarsGenerator.Parameters.Barcode.FilledBars = false;

            // ---------------------------------------------------------------
            // 6️⃣  Save the barcode with empty bars.
            // ---------------------------------------------------------------
            string emptyPath = "PlanetEmptyBars.png";
            emptyBarsGenerator.Save(emptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Empty bars saved to {emptyPath}");

            // -----------------------------------------------------------------
            // 7️⃣  Quick verification – open the files if you’re on Windows.
            // -----------------------------------------------------------------
            // This is optional but handy when you run the demo locally.
            if (OperatingSystem.IsWindows())
            {
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = filledPath,
                    UseShellExecute = true
                });
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = emptyPath,
                    UseShellExecute = true
                });
            }
        }
    }
}
```

### Pourquoi cette structure fonctionne

- **Générateurs séparés** : Nous instancions deux objets `BarcodeGenerator` car la propriété `FilledBars` est immuable une fois l'image rendue. Les garder indépendants évite les effets secondaires.
- **Choix de la X‑dimension** : Une valeur de 4 pixels équilibre lisibilité et taille du fichier. Si vous avez besoin d'une impression à plus haute résolution, augmentez-la à 6 ou 8.
- **Enregistrement au format PNG** : PNG préserve les bords nets du code-barres, ce qui est crucial pour les scanners optiques utilisés par les services postaux.

## Étape 3 : Exécuter la démonstration et vérifier la sortie

Compilez et exécutez le programme :

```bash
dotnet run
```

Vous devriez voir des messages dans la console confirmant que les deux fichiers ont été enregistrés. Dans le dossier du projet, vous trouverez maintenant :

- `PlanetFilledBars.png` – un code-barres à barres pleines.
- `PlanetEmptyBars.png` – uniquement les contours des barres.

Voici une représentation visuelle de l'apparence de la version remplie (l'image est uniquement à titre d'illustration ; votre sortie réelle peut différer légèrement selon les paramètres DPI).

![exemple de création d'image de code-barres Planet montrant un PNG d'un code-barres Planet avec des barres remplies](https://example.com/planet-filled.png)

## Étape 4 : Ajuster le code-barres – Variations courantes

### Modifier la charge de données

La symbologie `EncodeTypes.Planet` attend des données numériques jusqu'à 16 chiffres. Pour encoder un numéro de suivi différent, remplacez simplement `"123456"` par votre chaîne réelle :

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Planet, "9876543210123456");
```

### Ajuster le format d'image

Si vous avez besoin d'un JPEG pour la diffusion web, remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. N'oubliez pas que le JPEG introduit des artefacts de compression—évitez-le pour les scans haute précision.

### Gérer les erreurs de manière élégante

Lors du traitement de données fournies par l'utilisateur, encapsulez la génération dans un bloc try‑catch :

```csharp
try
{
    generator.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

Cela garantit que votre application ne plante pas en cas d'entrée invalide.

## Étape 5 : Intégration dans une application plus grande

Dans un système d'envoi réel, vous généreriez probablement le code-barres à la volée et l'intégreriez dans un PDF ou un modèle d'étiquette. Voici un petit extrait montrant comment obtenir le code-barres sous forme de `byte[]` pour un traitement ultérieur :

```csharp
using System.IO;

// Generate the image in memory
using (MemoryStream ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    byte[] barcodeBytes = ms.ToArray();

    // Pass barcodeBytes to a PDF library, send over a network, etc.
}
```

Vous pouvez maintenant injecter le tableau d'octets dans iTextSharp, QuestPDF ou tout autre générateur de documents sans toucher au système de fichiers.

## Questions fréquemment posées (FAQ)

**Q : Cette solution fonctionne‑t‑elle avec .NET Framework 4.5 ?**  
R : Oui. Aspose.BarCode prend en charge .NET Framework 4.5 et supérieur. Il suffit de changer le framework cible dans votre fichier `.csproj`.

**Q : Et si j’ai besoin d’une symbologie de code‑barres différente ?**  
R : Remplacez `EncodeTypes.Planet` par toute autre valeur d’énumération (par ex., `EncodeTypes.Code128`). Le reste du code reste identique.

**Q : Puis‑je changer la couleur des barres ?**  
R : Absolument. Utilisez `generator.Parameters.Barcode.BarColor = Color.Blue;` avant l’enregistrement.

## Conclusion

Vous savez maintenant **comment créer une image de code‑barres Planet** en C#, **comment générer un code‑barres postal** avec la bibliothèque Aspose.BarCode, et **comment enregistrer l’image du code‑barres** au format PNG. L’exemple complet couvrait l’initialisation, le réglage de la X‑dimension, le basculement des barres remplies, et l’enregistrement sur le disque—plus quelques astuces utiles pour l’intégration en situation réelle.

Prêt pour l’étape suivante ? Essayez d’intégrer le PNG généré dans une étiquette PDF, expérimentez différentes couleurs, ou passez à un format d’image à plus haute résolution. Le ciel est la limite lorsque vous combinez la génération de code‑barres avec les outils .NET modernes.

Si vous avez rencontré des problèmes ou avez des idées d’extensions, laissez un commentaire ci‑dessous. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment enregistrer un PNG en utilisant DataMatrix C40 avec Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Comment créer une zone silencieuse de code‑barres pour Code 16K avec Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Générer une image de code‑barres – Code 93 avec Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}