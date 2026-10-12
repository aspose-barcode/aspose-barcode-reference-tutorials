---
category: general
date: 2026-09-29
description: Créer un code‑barres Planet en C# avec des barres pleines et vides –
  guide pas à pas utilisant Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: fr
lastmod: 2026-09-29
og_description: Créez rapidement un code‑barcode planétaire en C#. Apprenez à rendre
  les barres remplies, à passer aux barres vides et à ajuster la dimension X avec
  Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Créer un code‑barres planétaire avec des barres pleines et vides – Tutoriel
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Comment créer un code‑barres planétaire avec des barres pleines et vides
url: /fr/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres planet avec des barres remplies et vides

Si vous devez **créer des images de code-barres planet** en C#, ce guide vous montre exactement comment générer les versions à barres remplies et à barres vides. Vous verrez comment définir la largeur des barres (dimension X), basculer la propriété `FilledBars`, et enregistrer les résultats au format PNG — le tout avec la bibliothèque Aspose.Barcode.

La génération de codes-barres postaux est une exigence courante pour les systèmes d'expédition, les applications de listes de diffusion et les tableaux de bord logistiques. À la fin de ce tutoriel, vous disposerez de deux fichiers PNG prêts à l'emploi que vous pourrez intégrer dans des rapports, des e‑mails ou des impressions.

## Pré‑requis

Avant de commencer, assurez‑vous d’avoir :

| Exigence | Pourquoi c'est important |
|----------|---------------------------|
| .NET 6.0 ou version ultérieure | Fournit le runtime pour l'exemple C#. |
| Visual Studio 2022 (ou tout IDE C#) | Vous permet de compiler et d'exécuter le code. |
| **Aspose.Barcode for .NET** package NuGet | Fournit la classe `BarcodeGenerator` et `EncodeTypes.Planet`. Installez‑le avec `dotnet add package Aspose.Barcode`. |
| Permission d'écriture sur un dossier du disque | La méthode `Save` écrit les fichiers PNG vers le chemin que vous spécifiez. |

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console (ou ajoutez le code à un projet existant) et référencez l'espace de noms Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Ces directives `using` vous donnent accès aux classes `BarcodeGenerator`, `EncodeTypes` et aux énumérations de formats d'image nécessaires au tutoriel.

## Étape 2 : Créer un code-barres Planet avec des barres par défaut (remplies)

Le premier code-barres utilise le rendu par défaut de la bibliothèque, qui remplit les barres.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Pourquoi cela fonctionne :**  
`EncodeTypes.Planet` indique à Aspose.Barcode d'utiliser la symbologie **Planet**, un code‑postal utilisé par le United States Postal Service. La propriété `XDimension` contrôle la largeur de chaque barre ; la régler à 4 pixels produit un code‑barres qui s'imprime correctement sur les imprimantes d'étiquettes standards. Par défaut, `FilledBars` vaut `true`, donc les barres apparaissent solides.

## Étape 3 : Créer un code-barres Planet avec des barres vides

Pour générer les mêmes données avec des barres *vides*, il suffit d’inverser le drapeau `FilledBars` tout en conservant les autres paramètres identiques.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Pourquoi c'est important :**  
Certains systèmes de mailing exigent le style **bars‑vides** afin d'améliorer la lisibilité lorsque le code‑barres est imprimé sur des fonds sombres ou lorsqu'un schéma de couleur contrasté est utilisé. En définissant `FilledBars = false`, le générateur ne trace que les contours des barres, laissant l'intérieur transparent.

## Résultat attendu

Après l'exécution du programme, le dossier `C:\Barcodes` (ou le chemin que vous avez choisi) contient deux fichiers PNG :

| Fichier | Description visuelle |
|---------|----------------------|
| `PlanetFilledBars.png` | Les barres sont des rectangles noirs solides sur fond blanc. |
| `PlanetEmptyBars.png`  | Les barres sont des contours noirs ; l'intérieur de chaque barre est transparent (laissent apparaître le fond). |

Les deux images codent la même chaîne numérique `"123456"` et partagent une largeur de barre de 4 pixels, garantissant une apparence cohérente à l'exception du style de remplissage.

## Variations courantes et cas limites

### Modifier la largeur des barres

Si votre imprimante d'étiquettes attend une largeur de barre différente, modifiez la valeur `XDimension.Pixels`. Pour les imprimantes haute résolution, une valeur de **2** ou **3** pixels peut être préférable ; pour les imprimantes basse résolution, **5** ou **6** pixels peuvent améliorer la fiabilité de lecture.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Utiliser un autre format d'image

Aspose.Barcode prend en charge PNG, JPEG, BMP, GIF et TIFF. Remplacez `BarCodeImageFormat.Png` par une autre valeur d'énumération pour correspondre à votre flux de travail en aval.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Générer plusieurs codes-barres dans une boucle

Lorsque vous avez besoin d’un lot de codes‑barres Planet (par ex., pour une liste de diffusion), encapsulez la logique du générateur dans une boucle `foreach` et changez la chaîne de données à chaque itération.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Gestion des entrées invalides

La symbologie Planet n’accepte que des chaînes numériques de **5 à 8** chiffres. Fournir une valeur invalide déclenche une `ArgumentException`. Protégez‑vous avec une simple méthode de validation.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Astuce pro : Vérifier le code‑barres avec un émulateur de scanner

Aspose.Barcode inclut une classe `BarcodeReader` que vous pouvez utiliser pour confirmer que l'image générée se décodera correctement en données d'origine.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Si la sortie affiche `"123456"` pour les deux fichiers, le code‑barres a été généré correctement.

## Conclusion

Vous savez maintenant comment **créer des images de code‑barres planet** en C# avec les styles remplis et vides, contrôler la **XDimension du code‑barres Planet**, et enregistrer les résultats au format PNG à l'aide de la bibliothèque **Aspose.Barcode**. Ajustez la largeur des barres, changez le format d'image ou bouclez sur une collection de valeurs pour répondre à n'importe quel flux de travail de code‑postal.

Ensuite, vous pourriez explorer :

* **Ajouter du texte lisible par l'homme** sous le code‑barres (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Intégrer des codes‑barres dans des documents PDF** avec Aspose.PDF.
* **Générer d'autres symbologies postales** telles que **USPS POSTNET** ou **Intelligent Mail**.

N’hésitez pas à expérimenter avec les paramètres et à intégrer le code dans votre système d'expédition ou de mailing. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un code‑barres Planet en C# – Guide complet étape par étape](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Créer un code‑barres planet en C# – guide complet de programmation](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Générateur de code‑barres C# – créer un code‑barres Planet et exemple RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}