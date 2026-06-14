---
date: 2026-06-14
description: Apprenez à créer un code-barres DotCode .NET et à personnaliser son rapport
  d'aspect en utilisant Aspose.BarCode pour .NET.
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: Personnalisation du rapport d'aspect DotCode
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Créer un code-barres DotCode .NET – Personnaliser le rapport d'aspect
url: /fr/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres DotCode .NET – Personnaliser le rapport d’aspect

Si vous devez **créer des solutions de code‑barres DotCode .NET** qui s'adaptent à des espaces restreints ou à des exigences de mise en page spécifiques, Aspose.BarCode pour .NET vous offre un contrôle total. Dans ce tutoriel, nous parcourrons l'ensemble du processus de génération d'un code‑barres DotCode et d'ajustement de son rapport d'aspect afin qu'il apparaisse exactement comme vous le souhaitez sur les emballages, les étiquettes ou les écrans mobiles.  

## Réponses rapides
- **Puis-je générer des codes‑barres DotCode en .NET ?** Oui, Aspose.BarCode prend en charge DotCode dès le départ.  
- **Quelle propriété contrôle la forme ?** La propriété `AspectRatio` de `BarcodeGenerator`.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit suffit pour le développement.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Combien de temps le code met‑il à s’exécuter ?** Moins d’une seconde pour un code‑barres typique de 200 × 200 pixels.

## Quel est l’objectif principal de ce tutoriel ?
La visée du tutoriel est de démontrer comment générer un code‑barres DotCode à l’aide d’Aspose.BarCode pour .NET et comment ajuster son rapport d’aspect afin de répondre à des contraintes de mise en page spécifiques. En suivant les étapes, vous apprendrez à configurer le générateur, modifier les paramètres de taille et exporter l’image dans des formats courants.

## Comment créer un code‑barres DotCode en .NET ?
Pour créer un code‑barres DotCode en .NET, créez une instance de `BarcodeGenerator` avec `EncodeTypes.DotCode` et les données que vous souhaitez encoder. Ensuite, définissez les propriétés X‑Dimension et AspectRatio pour contrôler la taille et la forme, puis appelez la méthode `Save` pour enregistrer l’image dans un fichier au format souhaité.

## Prérequis

1. **Aspose.BarCode for .NET** – téléchargez la bibliothèque depuis le site officiel [ici](https://releases.aspose.com/barcode/net/).  
2. **IDE** – Visual Studio, Rider ou tout éditeur compatible .NET.  
3. **Dossier de sortie** – remplacez « Your Directory Path » dans l’exemple par un vrai dossier sur votre machine.

## Importer les espaces de noms

`Aspose.BarCode.Generation` fournit les classes nécessaires pour générer et configurer des codes‑barres en .NET.  
```csharp
using Aspose.BarCode.Generation;
```

## Étape 1 : Initialiser le générateur de code‑barres

`BarcodeGenerator` est la classe principale qui crée une image de code‑barres à partir de la symbologie et des données spécifiées.  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## Étape 2 : Définir la X‑Dimension (Taille) du code‑barres

`XDimension` définit la largeur d’un module (point) unique en pixels, influençant la taille globale du code‑barres.  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## Étape 3 : Personnaliser le rapport d’aspect

`AspectRatio` définit la proportion hauteur‑largeur de chaque module, vous permettant d’étirer ou de comprimer le code‑barres verticalement.  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## Étape 4 : Enregistrer l’image du code‑barres

`Save` écrit le code‑barres généré dans un fichier au format d’image choisi, tel que PNG ou JPEG.  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Pourquoi utiliser Aspose.BarCode pour la personnalisation DotCode ?
Aspose.BarCode offre un ensemble complet de fonctionnalités pour la génération de DotCode, incluant une sortie haute résolution, une prise en charge étendue des formats et un contrôle fin des dimensions du code‑barres tel que le rapport d’aspect. Il fonctionne sur toutes les principales plateformes .NET, ne nécessite aucune dépendance externe et offre des performances de rendu rapides, ce qui le rend idéal tant pour les applications de bureau que web.

## Cas d’utilisation courants

- **Santé** : Étiquettes d’ID patient compactes qui doivent tenir sur de petits bracelets.  
- **Services postaux** : Étiquettes d’expédition grand format où une hauteur réduite améliore la fiabilité du scan.  
- **Fabrication** : Étiquetage en ligne de pièces où les contraintes d’espace exigent un rapport d’aspect personnalisé.

## Questions fréquemment posées

**Q :** Quel est le rapport d’aspect d’un code‑barres DotCode ?  
**R :** C’est le rapport entre la hauteur et la largeur d’un module ; le modifier change la forme globale du code‑barres.

**Q :** Quels secteurs bénéficient le plus des codes‑barres DotCode ?  
**R :** La santé, les services postaux et la fabrication utilisent fréquemment DotCode pour un encodage compact et à haute densité.

**Q :** Puis‑je personnaliser d’autres paramètres DotCode avec Aspose.BarCode pour .NET ?  
**R :** Absolument. Vous pouvez modifier le niveau de correction d’erreurs, les couleurs de premier plan/arrière‑plan, et même intégrer des logos.

**Q :** Aspose.BarCode convient‑il aux applications .NET web et de bureau ?  
**R :** Oui, la bibliothèque fonctionne parfaitement dans ASP.NET, WPF, WinForms et les applications console.

**Q :** Où puis‑je trouver plus de documentation et d’exemples ?  
**R :** Une référence API détaillée et des exemples de code sont disponibles [ici](https://reference.aspose.com/barcode/net/).

---

**Dernière mise à jour** : 2026-06-14  
**Testé avec** : Aspose.BarCode 24.12 for .NET  
**Auteur** : Aspose

## Tutoriels associés

- [Configuration du texte de code étendu DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Configuration du mode d’ajout structuré DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Créer une image de code‑barres DotCode – lignes & colonnes (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}