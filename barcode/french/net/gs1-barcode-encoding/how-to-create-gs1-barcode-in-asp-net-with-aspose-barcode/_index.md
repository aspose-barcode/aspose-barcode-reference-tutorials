---
category: general
date: 2026-10-24
description: Apprenez à créer un code‑barres GS1 en ASP.NET avec Aspose.BarCode. Guide
  étape par étape pour générer un code‑barres à partir d’une chaîne et le rendre au
  format PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: fr
lastmod: 2026-10-24
og_description: Comment créer un code‑barres GS1 dans ASP.NET en utilisant Aspose.BarCode.
  Suivez ce tutoriel pour générer un code‑barres à partir d’une chaîne, configurer
  les paramètres visuels et enregistrer des fichiers PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Comment créer un code‑barres GS1 en ASP.NET – guide complet d’Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Comment créer un code‑barres GS1 dans ASP.NET avec Aspose.BarCode
url: /fr/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres GS1 dans ASP.NET avec Aspose.BarCode

Si vous avez besoin de **comment créer un code‑barres GS1** dans une application ASP.NET, ce guide vous montre les étapes exactes. Vous verrez comment générer un code‑barres à partir d’une chaîne, configurer l’apparence visuelle et enregistrer le résultat sous forme d’image PNG.

La création de codes‑barres GS1 ne nécessite pas de logique d’encodage personnalisée. En utilisant Aspose.BarCode, vous obtenez une solution fiable, conforme aux normes, qui fonctionne sur .NET 6+ et les frameworks antérieurs. Ce tutoriel couvre tout, de la configuration du projet à la vérification du résultat, afin que vous puissiez copier le code directement dans votre propre projet web.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Visual Studio 2022 (ou tout IDE supportant .NET)
* .NET 6 SDK (ou .NET Framework 4.7.2 et supérieur)
* Connaissances de base en ASP.NET Core ou ASP.NET Framework
* Une licence Aspose.BarCode (l’évaluation gratuite suffit pour les tests)

Aucune bibliothèque tierce supplémentaire n’est requise car Aspose.BarCode gère tout l’encodage et le rendu en interne.

## Étape 1 : Créer un nouveau projet ASP.NET

Ouvrez Visual Studio et créez une **ASP.NET Core Web App** (choisissez le modèle *Empty*). Pour un projet Web Forms classique, le même code fonctionne dans un fichier code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

L’exécution du projet doit afficher *GS1 barcode generator is ready.* dans le navigateur. Cela confirme que l’hôte web est opérationnel.

## Étape 2 : Installer Aspose.BarCode via NuGet

Ouvrez la **Package Manager Console** et exécutez :

```powershell
Install-Package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode.Generation`, qui contient la classe `BarcodeGenerator` que vous utiliserez pour **generate barcode from string**. La commande NuGet met également à jour le fichier projet avec la référence requise.

## Étape 3 : Générer un code‑barres simple à partir d’une chaîne

Pour illustrer l’utilisation de base, créez une méthode d’assistance qui renvoie un tableau d’octets PNG. Cette méthode peut être appelée depuis un contrôleur, une page Razor ou tout point d’accès.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Vous pouvez maintenant appeler `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` depuis n’importe quel point d’accès et écrire les octets résultants dans la réponse HTTP. Cela démontre le modèle **barcode generator asp.net** pour des chaînes arbitraires.

## Étape 4 : How to create GS1 barcode – Exemple Micro PDF417

Les codes‑barres GS1 intègrent des identifiants d’application (AI) qui transmettent des informations produit. Aspose.BarCode prend en charge la variante compatible GS1 du Micro PDF417, idéale pour une représentation compacte des données.

### 4.1 Préparer la chaîne de données GS1

Les données GS1 doivent être entourées de parenthèses avec le code AI. Pour un identifiant produit (01) et un numéro de lot (10), la chaîne ressemble à :

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Les parenthèses font partie de la norme ; Aspose.BarCode les analyse automatiquement.

### 4.2 Construire le générateur GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Exposer le générateur via un point d’accès ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Visiter `https://localhost:5001/gs1barcode` diffuse maintenant le PNG généré. L’image respecte la spécification GS1, et le fichier est également stocké sur le disque pour une utilisation ultérieure.

## Étape 5 : Rendu d’autres types de code‑barres

La même approche **create barcode with aspose** fonctionne pour d’autres symbologies. Voici un exemple rapide qui crée un QR code à partir d’une URL :

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Vous pouvez remplacer `EncodeTypes.QR` par `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` ou tout autre type supporté. Les paramètres visuels (`XDimension`, `Resolution`, `Color`) sont configurables via l’objet `Parameters`.

## Étape 6 : Pièges courants et conseils de bonnes pratiques

| Problème | Pourquoi cela se produit | Comment l’éviter |
|----------|--------------------------|------------------|
| **Mise en forme AI incorrecte** | Parenthèses manquantes ou longueur AI erronée entraînent des erreurs d’encodage. | Construisez toujours la chaîne GS1 exactement comme le spécifie la norme. Utilisez une méthode d’assistance pour concaténer les AI. |
| **Trop de colonnes** | Micro PDF417 ne supporte que 1‑4 colonnes ; définir 5 génère une exception. | Validez la valeur des colonnes avant l’affectation : `if (columns < 1 || columns > 4) throw …` |
| **Résolution d’image trop faible** | Des valeurs `XDimension` faibles peuvent rendre le code‑barres illisible à l’impression. | Pour des codes‑barres prêts à imprimer, augmentez `Resolution` (par ex., `generator.Parameters.Image.Resolution = 300`). |
| **Problèmes de chemin de fichier sous Linux** | Les barres obliques inverses codées en dur échouent sur les hôtes non Windows. | Utilisez `Path.Combine` pour construire les chemins de fichiers ; il gère les séparateurs spécifiques à l’OS. |
| **Licence non appliquée** | L’évaluation gratuite ajoute un filigrane après 30 jours. | Appliquez votre licence dès le départ : `new License().SetLicense("Aspose.BarCode.lic");` |

## Étape 7 : Vérifier le code‑barres généré

Après avoir exécuté le point d’accès, ouvrez le PNG dans n’importe quel visualiseur d’images. Pour confirmer que les données GS1 sont correctement encodées, vous pouvez utiliser un scanner mobile gratuit qui prend en charge le GS1 Micro PDF417 (de nombreuses applications de lecture de codes‑barres listent cette symbologie). Scannez l’image ; l’application doit renvoyer :

```
(01)12345678901234
(10)ABCD
```

Si le scanner signale une erreur, revérifiez la mise en forme des AI et le nombre de colonnes.

## Conclusion

Vous savez maintenant **comment créer un code‑barres GS1** dans un environnement ASP.NET en utilisant Aspose.BarCode. Le tutoriel a couvert :

* Configuration d’un projet ASP.NET et installation du package NuGet Aspose.BarCode.  
* Utilisation de **generate barcode from string** pour des codes‑barres génériques.  
* Implémentation de **create barcode with aspose** pour produire une image Micro PDF417 compatible GS1.  
* Enregistrement de l’image sur disque et diffusion via un point d’accès HTTP.  

À partir d’ici, vous pouvez explorer d’autres symbologies GS1 (par ex., GS1 DataMatrix) ou intégrer le générateur dans un flux de travail de traitement de commandes plus vaste. Expérimentez avec différentes valeurs de `XDimension`, couleurs et niveaux de correction d’erreur pour correspondre à votre identité visuelle et à votre environnement de numérisation.

Bon codage, et laissez vos applications parler le langage universel des codes‑barres !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to create code 128 barcode with GS1 using Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}