---
category: general
date: 2026-11-20
description: Créez rapidement une image de code‑barres postal en C#. Apprenez à générer
  des codes‑barres Planet et RM4SCC avec des styles de barres personnalisables.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: fr
lastmod: 2026-11-20
og_description: Créer une image de code‑barres postal en C# avec Aspose.BarCode. Ce
  tutoriel montre comment générer un code‑barres Planet, personnaliser les styles
  de barres et produire des images RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Créer une image de code‑barres postal en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Créer une image de code-barres postal et générer un code-barres planétaire
url: /fr/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code‑barres postal et générer un code‑barres Planet

Créez une image de code‑barres postal en C# en utilisant la bibliothèque Aspose.BarCode. Si vous devez générer des codes‑barres Planet ou RM4SCC pour des applications d’envoi, ce tutoriel fournit une solution complète, prête à l’emploi.

La génération de codes‑barres pour les services postaux nécessite souvent des dimensions précises et la possibilité de basculer entre des styles de barres remplies et vides. Ce guide vous accompagne dans la configuration du dossier de sortie, la création de codes‑barres Planet remplis et vides, ainsi que la production d’un code‑barres RM4SCC avec les mêmes paramètres visuels. À la fin, vous disposerez de quatre fichiers PNG utilisables directement dans votre flux de travail d’envoi.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C# de votre choix)  
* Le package NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Aucune configuration supplémentaire n’est requise ; le code utilise uniquement la police par défaut et l’encodeur PNG.

## Créer une image de code‑barres postal – aperçu

Le cœur du processus est la classe `BarcodeGenerator`. Elle accepte une valeur `EncodeTypes` qui détermine la symbologie du code‑barres (par exemple, `EncodeTypes.Planet` pour un code‑barres Planet). Après avoir configuré le générateur, vous appelez `Save` pour écrire le fichier image.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Texte alternatif : Exemple de création d’image de code‑barres postal montrant des barres remplies et vides.*

## Étape 1 : Configurer le dossier de sortie

Définissez d’abord un dossier où les fichiers PNG seront enregistrés. L’utilisation d’un chemin absolu ou relatif fonctionne de la même façon ; assurez‑vous simplement que le dossier existe ou laissez le code le créer.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Créer le dossier par programme évite les `DirectoryNotFoundException` lorsque le tutoriel s’exécute sur une machine fraîche.

## Étape 2 : Générer un code‑barres Planet avec des barres remplies

Un code‑barres Planet à barres remplies est le style visuel par défaut. Le code suivant crée le code‑barres, définit la dimension X à 4 pixels (une taille courante pour les applications postales) et enregistre l’image.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
* `EncodeTypes.Planet` indique au générateur d’utiliser la symbologie Planet, qui est requise par de nombreux services postaux.  
* `XDimension.Pixels` contrôle la largeur de chaque barre ; 4 px donnent une image nette et lisible sans taille de fichier excessive.  
* La méthode `Save` sélectionne automatiquement l’encodeur PNG en fonction de l’énumération `BarCodeImageFormat`.

## Étape 3 : Générer un code‑barres Planet avec des barres vides

Certaines spécifications postales préfèrent des barres vides (blanches) sur un fond sombre. Vous pouvez obtenir cet effet en réglant `FilledBars` sur `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Astuce :** Lorsque `FilledBars` est `false`, le générateur peint les barres avec la couleur d’arrière‑plan (blanc par défaut) et les espaces avec la couleur de premier plan (noir). Si vous avez besoin d’un autre jeu de couleurs, ajustez `Parameters.Barcode.ForeColor` et `BackColor`.

## Étape 4 : Générer un code‑barres RM4SCC avec des barres remplies

RM4SCC est une autre symbologie postale utilisée au Royaume‑Uni. Les étapes de création reflètent l’exemple Planet ; seule la valeur `EncodeTypes` change.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Ce à quoi s’attendre :** Le PNG résultant affiche un code‑barres RM4SCC compact conforme aux directives postales britanniques. La taille de l’image sera similaire à celle des codes‑barres Planet car la dimension X est identique.

## Étape 5 : Vérifier les images générées

Après l’exécution du programme, ouvrez les quatre fichiers dans le dossier `Barcodes`. Vous devriez voir :

* `PostalPlanetFilledBars.png` – barres sombres sur fond clair  
* `PostalPlanetEmptyBars.png` – barres claires sur fond sombre (inverse)  
* `PostalRM4SCCFilledBars.png` – motif RM4SCC standard  

Si une image semble déformée, vérifiez les points suivants :

* **Dimension X** – trop petite (< 2 px) peut provoquer du flou ; trop grande (> 10 px) peut dépasser les limites de taille d’étiquette.  
* **Chaîne de données** – la valeur `"123456"` doit respecter les exigences de longueur de la symbologie choisie (Planet attend 6 chiffres, RM4SCC attend également 6 chiffres).  
* **Permissions du dossier** – assurez‑vous que l’application a les droits d’écriture sur le répertoire de sortie.

## Variantes courantes et cas limites

| Scénario | Ajustement |
|----------|------------|
| **Données de code‑barres différentes** | Remplacez `"123456"` par n’importe quelle chaîne numérique valide. Pour Planet, la longueur doit être exactement de 6 chiffres ; RM4SCC nécessite également 6 chiffres. |
| **Couleurs personnalisées** | Définissez `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` et `BackColor = System.Drawing.Color.LightYellow;`. |
| **Résolution supérieure** | Augmentez `XDimension.Pixels` à 6 ou 8 pour des impressions plus grandes. |
| **Autres formats d’image** | Utilisez `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` dans l’appel `Save`. |
| **Génération par lots** | Parcourez une collection de chaînes et appelez la même logique de générateur à l’intérieur de la boucle, en réutilisant le chemin `outputFolder`. |

## Exemple complet, exécutable

Copiez le code ci‑dessous dans un nouveau projet console C#. Il se compile avec .NET 6.0 et produit automatiquement les quatre images de code‑barres.



## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}