---
date: 2026-05-19
description: Apprenez à créer un code-barres Aztec avec Aspose.BarCode pour .NET,
  à personnaliser les rapports d’aspect, à encoder des octets ou du texte, et à maîtriser
  les modes de symbole.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Encodage du code-barres Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Comment créer un code-barres Aztec avec Aspose.BarCode pour .NET
url: /fr/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Encodage de code-barres Aztec

Êtes-vous prêt à plonger dans le monde de l'encodage de code-barres Aztec et à apprendre comment **créer des codes-barres Aztec** avec Aspose.BarCode for .NET ? Cette bibliothèque vous offre un contrôle total sur la taille, la correction d'erreurs et la représentation des données, ce qui la rend idéale pour tout, du billetterie mobile au suivi d'inventaire.

## Réponses rapides
- **Quelle bibliothèque prend en charge les codes-barres Aztec ?** Aspose.BarCode for .NET  
- **Puis-je modifier le ratio d'aspect ?** Yes, via the `AspectRatio` property  
- **L'encodage au niveau des octets est‑il possible ?** Absolutely – use the `EncodeBytes` method  
- **Quels niveaux de correction d'erreurs sont disponibles ?** Levels 0 to 4 (higher = more redundancy)  
- **Ai‑je besoin d'une licence pour la production ?** Yes, a commercial license removes evaluation limits  

## Qu'est‑ce qu'un code-barres Aztec ?
Un code‑barres Aztec est un code matriciel bidimensionnel qui peut encoder jusqu'à 3 000 caractères numériques ou 2 300 caractères alphanumériques. Il comporte un motif de recherche central, permettant une lecture rapide même lorsque le symbole est imprimé à basse résolution. Comme le motif est situé au centre, le code peut être lu depuis n'importe quelle direction, ce qui le rend très fiable pour les applications mobiles et industrielles.

## Comment personnaliser le ratio d'aspect d'un code-barres Aztec ?
`BarcodeGenerator` est la classe principale utilisée pour créer des codes-barres dans Aspose.BarCode. Définissez la propriété `AspectRatio` sur l'objet `BarcodeGenerator` à la proportion largeur‑hauteur souhaitée, puis générez l'image. Ajuster le ratio d'aspect aide à adapter le code-barres aux espaces UI ou aux mises en page d'étiquettes restreints sans sacrifier la fiabilité du scan, et permet également de respecter les directives de marque ou les exigences spécifiques de l'imprimante.

### Étapes pour personnaliser le ratio d'aspect
1. **Créer une instance de `BarcodeGenerator`** avec `EncodeTypes.Aztec`.  
2. **Attribuer vos données** (texte, octets ou chaîne numérique).  
3. **Définir `AspectRatio`** – par exemple, `1.5` pour une barre plus large.  
4. **Générer l'image** en utilisant `Save` ou `GetBarCodeImage`.  

## Comment encoder des octets bruts dans un code-barres Aztec ?
`EncodeBytes` est une méthode qui accepte un tableau d'octets et le convertit en une matrice Aztec. Passez un tableau d'octets à la méthode `EncodeBytes` de `BarcodeGenerator`. L'API convertit automatiquement les données binaires en une matrice Aztec compacte, en préservant chaque bit. C'est parfait pour intégrer des charges utiles chiffrées, des identifiants binaires ou des fichiers compressés directement dans un code-barres.

### Étapes pour encoder des octets
1. **Préparer le tableau d'octets** (par ex., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instancier `BarcodeGenerator`** avec `EncodeTypes.Aztec`.  
3. **Appeler `EncodeBytes(data)`** pour charger le contenu binaire.  
4. **Rendre le code-barres** avec `Save` ou `GetBarCodeImage`.  

## Comment encoder du texte dans un code-barres Aztec ?
`CodeText` est une propriété qui contient les données en texte clair à encoder. Utilisez la propriété `CodeText` de `BarcodeGenerator` pour fournir les données en texte clair. La bibliothèque sélectionne automatiquement le mode d'encodage optimal (numérique, alphanumérique ou octet) et applique le niveau de correction d'erreurs approprié. Cela facilite l'intégration d'URL, d'ID de produit ou de toute chaîne lisible.

### Étapes pour encoder du texte
1. **Créer le générateur** avec `EncodeTypes.Aztec`.  
2. **Définir `CodeText`** sur la chaîne que vous souhaitez encoder.  
3. **Optionnellement ajuster `ErrorLevel`** pour une plus grande résilience.  
4. **Générer l'image** en utilisant `Save` ou `GetBarCodeImage`.  

## Comment générer des codes-barres Aztec avec différents niveaux de correction d'erreurs ?
`ErrorLevel` est une propriété qui contrôle la quantité de données redondantes ajoutées au code-barres. Ajustez la propriété `ErrorLevel` (0‑4) avant le rendu. Des niveaux plus élevés augmentent la quantité de données redondantes, permettant au code-barres d'être lu même lorsque jusqu'à 30 % du symbole est endommagé. Ceci est crucial pour les environnements difficiles comme l'étiquetage industriel ou la signalisation extérieure.

### Étapes pour définir la correction d'erreurs
1. **Instancier `BarcodeGenerator`** pour Aztec.  
2. **Attribuer vos données** (texte ou octets).  
3. **Définir `ErrorLevel`** – par ex., `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Rendre le code-barres** avec le format de sortie de votre choix.  

## Quels sont les différents modes de symbole Aztec et comment les utiliser ?
`SymbolMode` est un paramètre qui détermine la taille de la matrice et la capacité de données du code Aztec généré. Le mode de symbole Aztec détermine la taille de la matrice et la capacité de données. La bibliothèque propose quatre modes : **Auto**, **FullRange**, **Compact** et **Rune**.

- **Auto** – le générateur sélectionne la plus petite taille possible.  
- **FullRange** – permet la taille maximale de matrice pour des ensembles de données très volumineux.  
- **Compact** – crée un symbole plus petit et plus dense, idéal pour les espaces limités.  
- **Rune** – un mode spécialisé pour encoder des runes Unicode.

Sélectionnez le mode via `Generator.Parameters.Barcode.Aztec.SymbolMode`. Chaque mode équilibre taille, lisibilité et capacité de données, vous permettant d'adapter le code-barres aux contraintes de votre application.

## Tutoriels d'encodage de code-barres Aztec
Ci-dessous les guides détaillés étape par étape qui approfondissent chacun des sujets abordés ci‑dessus. Cliquez sur n'importe quel lien pour explorer les exemples de code complets, les prérequis et les conseils de bonnes pratiques.

### [Personnaliser le ratio d'aspect du code-barres Aztec](./aztec-aspect-ratio-customization/)
Apprenez à personnaliser les ratios d'aspect des codes-barres Aztec en utilisant Aspose.BarCode for .NET. Créez des codes-barres uniques et flexibles pour vos applications .NET.

### [Encodage d'octets Aztec](./aztec-bytes-encoding/)
Apprenez à réaliser l'encodage d'octets Aztec avec Aspose.BarCode for .NET. Guide étape par étape, prérequis et exemples de code inclus.

### [Encodage du texte du code Aztec](./aztec-code-text-encoding/)
Découvrez la puissance de l'encodage du texte du code Aztec avec Aspose.BarCode for .NET. Apprenez à créer et à reconnaître les codes Aztec dans vos applications .NET.

### [Générer des codes-barres Aztec avec correction d'erreurs](./aztec-error-level-example/)
Apprenez à générer des codes-barres Aztec avec différents niveaux de correction d'erreurs en utilisant Aspose.BarCode for .NET. Guide complet pour la création de codes-barres.

### [Maîtriser le mode de symbole Aztec](./aztec-symbol-mode-example/)
Explorez le mode de symbole Aztec dans Aspose.BarCode for .NET et apprenez à générer des codes-barres polyvalents avec facilité. Mettez‑vous en pratique les modes Auto, FullRange, Compact et Rune dans ce tutoriel complet.

## Questions fréquentes

**Q : Quelles versions de .NET sont prises en charge par Aspose.BarCode pour l'encodage Aztec ?**  
A: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6, and later.

**Q : Puis-je créer un code-barres Aztec haute résolution pour l'impression ?**  
A: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image to obtain print‑ready quality.

**Q : Quelle taille de charge de données un code-barres Aztec peut‑il contenir ?**  
A: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800 bytes of raw data in Compact mode.

**Q : Est‑il possible de lire un code-barres Aztec qui a été tourné ?**  
A: Absolutely—Aspose.BarCode’s decoder automatically detects orientation and corrects it during the read operation.

**Q : Ai‑je besoin d’une licence pour le développement et les tests ?**  
A: A free evaluation license is available for testing; a commercial license is required for production deployments.

**Dernière mise à jour :** 2026-05-19  
**Testé avec :** Aspose.BarCode 24.12 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Comment générer un code‑barres Aztec avec un ratio d'aspect personnalisé en utilisant Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Encodage d'octets Aztec avec le générateur de code‑barres .NET](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Comment créer un code‑barres Aztec avec correction d'erreurs en .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}