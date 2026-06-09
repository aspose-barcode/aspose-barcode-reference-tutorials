---
date: 2026-06-09
description: Apprenez à générer un code-barres datamatrix avec Aspose.BarCode pour
  .NET, personnalisez les rapports d'aspect, les modes ECC et le codage datamatrix
  c40 pour une création de code-barres efficace.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: Configuration du code-barres DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Générer le code-barres DataMatrix – Guide Pro avec Aspose.BarCode
url: /fr/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer le code-barres DataMatrix – Guide Pro avec Aspose.BarCode

Bienvenue dans notre série de tutoriels complète sur **generate datamatrix barcode** utilisant Aspose.BarCode pour .NET. Que vous soyez un développeur chevronné ajustant la sortie des codes-barres ou un nouveau venu désireux de comprendre les bases, ce guide vous accompagne à chaque étape — de la configuration de base aux techniques d’encodage avancées — afin que vous puissiez fournir des codes-barres fiables et prêts à être scannés dans n’importe quelle application .NET.

## Réponses rapides
- **Quel est le but principal ?** Créer et personnaliser des codes-barres DataMatrix de manière programmatique.  
- **Quelle bibliothèque est utilisée ?** Aspose.BarCode pour .NET.  
- **Ai-je besoin d’une licence ?** Un essai gratuit est disponible ; une licence commerciale est requise pour la production.  
- **Versions .NET prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Puis-je personnaliser le rapport d’aspect ?** Oui – voir la section « How to customize DataMatrix aspect ratio ».

## Qu’est‑ce que generate datamatrix barcode ?
Un code-barres DataMatrix est une matrice bidimensionnelle de cellules noires et blanches pouvant stocker jusqu’à 2 300 caractères alphanumériques. Avec Aspose.BarCode, vous pouvez **generate datamatrix barcode** des images, PDF ou SVG directement depuis votre code .NET, en contrôlant la taille, le niveau de correction d’erreurs et le mode d’encodage pour répondre à toute norme industrielle.

## Pourquoi utiliser Aspose.BarCode pour DataMatrix ?
Aspose.BarCode rend les symboles DataMatrix jusqu’à **600 dpi** sans pixellisation, garantissant des scans nets sur les imprimantes haute résolution. Il prend en charge **plus de 50 modes ECC et macro** — y compris ECC 000‑140, ECC 200 et Macro 05/06 — vous permettant de choisir le niveau de correction d’erreurs optimal pour la taille de vos données. L’API propose des options d’encodage **ASCII, C40, Text, X12 et Bytes**, vous permettant d’empaqueter les données efficacement. L’intégration ne nécessite qu’un seul package NuGet et aucune bibliothèque native externe.

## Comment personnaliser le rapport d’aspect DataMatrix
La propriété `AspectRatio` de `BarCodeGenerator` contrôle la proportion largeur‑hauteur du symbole DataMatrix généré. `BarCodeGenerator` est la classe principale d’Aspose.BarCode utilisée pour créer des images de code‑barres.  

**Réponse directe :** Définissez `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (ou toute valeur entre 0,5 et 2,0) avant d’appeler `GenerateBarCodeImage()`. La bibliothèque recalcule automatiquement la taille du module pour préserver la fiabilité du scan tout en respectant le rapport demandé.

### Étape par étape
1. **Instancier** `BarCodeGenerator` avec `EncodeTypes.DataMatrix`.  
2. **Ajuster** `AspectRatio` à la valeur souhaitée.  
3. **Générer** l’image et vérifier avec un scanner ou le lecteur intégré d’Aspose.

## Comment générer des codes-barres DataMatrix ECC 000‑140
ECC 000‑140 est idéal pour les courtes chaînes de données où un symbole compact est requis, offrant jusqu’à 140 mots de correction d’erreurs. `DataMatrixEccMode.Ecc000140` sélectionne le schéma de correction d’erreurs ECC 000‑140 pour DataMatrix.  

**Réponse directe :** Utilisez `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` avant le rendu. Cela bascule l’encodeur vers l’algorithme ECC 000‑140, produisant la plus petite matrice possible pour les données fournies tout en offrant une correction d’erreurs robuste.

### Astuce pratique
Lors de l’encodage de données numériques de moins de 20 caractères, ECC 000‑140 produit souvent une matrice 10 × 10, ce qui économise un espace d’étiquette précieux.

## Comment générer des codes-barres DataMatrix ECC 200
ECC 200 est le mode DataMatrix le plus largement adopté, prenant en charge jusqu’à 2 335 caractères alphanumériques et offrant une correction d’erreurs supérieure. `DataMatrixEccMode.Ecc200` sélectionne le schéma de correction d’erreurs ECC 200 pour DataMatrix.  

**Réponse directe :** Définissez `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` et fournissez votre charge utile via `CodeText`. La bibliothèque sélectionne alors automatiquement la taille de matrice optimale.

### Quand privilégier ECC 200
Utilisez ECC 200 pour les chaînes plus longues, les données de type mixte, ou lorsque vous avez besoin de la plus grande résilience contre les dommages — jusqu’à **30 %** du symbole peut être restauré.

## Maîtriser l’encodage DataMatrix en ASCII
Le mode ASCII encode les caractères en utilisant un octet unique par caractère, ce qui le rend le plus efficace en termes d’espace pour le texte brut. `DataMatrixEncodeMode.Ascii` indique au générateur d’utiliser l’encodage ASCII pour le symbole DataMatrix.  

**Réponse directe :** Assignez `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` et définissez `CodeText` sur votre chaîne ASCII. Le moteur empaquette les données sans surcharge supplémentaire, produisant la plus petite matrice possible pour du contenu purement ASCII.

### Scénario d’exemple
Un SKU d’entrepôt composé de lettres majuscules et de chiffres (par ex., « AB1234 ») s’adapte parfaitement au mode ASCII, aboutissant souvent à une matrice 12 × 12.

## Comment générer le mode DataMatrix (Auto)
Le mode Auto permet à Aspose.BarCode d’analyser l’entrée et de choisir automatiquement l’encodage le plus efficace (ASCII, C40, Text, X12 ou Bytes). `DataMatrixEncodeMode.Auto` active cette fonctionnalité de sélection automatique.  

**Réponse directe :** Définissez `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. La bibliothèque évalue la charge utile, sélectionne le mode optimal et rend le code‑barres en une seule étape.

### Avantages
Le mode Auto réduit l’effort de développement et garantit le symbole le plus petit possible pour les données de type mixte, améliorant la vitesse de scan.

## Comment utiliser le mode d’encodage DataMatrix (Bytes)
Le mode Bytes est conçu pour les données binaires, telles que les charges chiffrées ou les fichiers compressés. `DataMatrixEncodeMode.Bytes` indique au générateur de traiter chaque octet comme des données brutes.  

**Réponse directe :** Utilisez `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` et fournissez une chaîne encodée en Base64 comme `CodeText`. L’encodeur traite chaque octet comme des données brutes, préservant la représentation binaire exacte.

### Cas d’utilisation
Intégrer un GUID de 128 bits ou un petit jeton chiffré directement dans un symbole DataMatrix.

## Maîtriser le mode d’encodage DataMatrix (C40)
Le mode C40 compresse les données alphanumériques en majuscules, réalisant jusqu’à **40 %** de réduction de taille comparé à l’ASCII. `DataMatrixEncodeMode.C40` active cet algorithme de compression.  

**Réponse directe :** Définissez `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` et fournissez une chaîne en majuscules (par ex., « HELLO WORLD »). Le moteur empaquette trois caractères en deux mots‑code, réduisant la matrice finale.

### Astuce pro
C40 fonctionne mieux lorsque la charge utile se compose principalement de lettres majuscules, de chiffres et d’espaces. Pour les cas mixtes, envisagez le mode Auto.

## Comment configurer le texte du code DataMatrix
La propriété `CodeText` définit les données exactes stockées dans le code‑barres. Elle peut inclure du texte brut, des chaînes numériques ou même des charges XML. `CodeText` est la propriété de chaîne principale de `BarCodeGenerator` qui contient la charge du code‑barres.  

**Réponse directe :** Assignez `generator.Parameters.Barcode.CodeText = "YourDataHere"` avant le rendu. La propriété accepte toute chaîne UTF‑8 jusqu’à la longueur maximale prise en charge par le mode ECC choisi.

### Astuce avancée
Combinez `CodeText` avec `ExtendedDataMatrix` pour intégrer des métadonnées supplémentaires sans augmenter la taille visible de la matrice.

## Maîtriser la configuration macro DataMatrix
Les modes macro (Macro 05 et Macro 06) vous permettent d’intégrer un symbole DataMatrix secondaire à l’intérieur du principal, utile pour créer des liens vers des sources de données externes. `DataMatrixMacroMode.Macro05` et `DataMatrixMacroMode.Macro06` activent ces fonctionnalités macro.  

**Réponse directe :** Activez le mode macro avec `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (ou `Macro06`) et définissez les propriétés `MacroPdf417` pour la charge secondaire. Le générateur crée un symbole composite que les scanners peuvent interpréter comme deux codes liés.

### Exemple réel
Intégrer une URL dans la partie macro tout en conservant les identifiants produit dans la matrice principale, permettant une intégration fluide du web vers le code‑barres.

*Liste des tutoriels Aspose.BarCode pour .NET*

## Tutoriels de configuration du code‑barres DataMatrix
### [Personnaliser le rapport d’aspect DataMatrix](./datamatrix-aspect-ratio-customization/)
Apprenez à personnaliser les rapports d’aspect des codes‑barres DataMatrix avec Aspose.BarCode pour .NET. Guide étape par étape pour la génération de codes‑barres.

### [Créer des codes‑barres DataMatrix ECC 000‑140](./datamatrix-ecc-000-140-configuration/)
Créez facilement des codes‑barres DataMatrix ECC 000‑140 avec Aspose.BarCode pour .NET. Augmentez l’efficacité de la gestion des stocks et plus encore.

### [Créer des codes‑barres DataMatrix ECC 200](./datamatrix-ecc-200-configuration/)
Apprenez à générer des codes‑barres DataMatrix ECC 200 en .NET avec Aspose.BarCode. Rationalisez les opérations grâce à une création de codes‑barres efficace.

### [Maîtriser l’encodage DataMatrix en ASCII](./datamatrix-encoding-mode-ascii/)
Apprenez à créer des codes‑barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET. Guide étape par étape pour les développeurs.

### [Générer le mode DataMatrix (Auto)](./datamatrix-encoding-mode-auto/)
Apprenez à générer le mode DataMatrix (Auto) avec Aspose.BarCode pour .NET. Ce guide étape par étape couvre tout, des prérequis à la lecture des codes‑barres.

### [Mode d’encodage DataMatrix (Bytes)](./datamatrix-encoding-mode-bytes/)
Apprenez à encoder des données au format DataMatrix en mode Bytes avec Aspose.BarCode pour .NET. Suivez notre guide étape par étape pour la génération et la reconnaissance de codes‑barres.

### [Maîtriser le mode d’encodage DataMatrix (C40)](./datamatrix-encoding-mode-c40/)
Apprenez le mode d’encodage DataMatrix (C40) avec Aspose.BarCode pour .NET. Créez des codes‑barres personnalisés efficacement. Explorez le guide étape par étape.

### [Configurer le texte de code étendu DataMatrix](./datamatrix-extended-code-text-configuration/)
Apprenez à configurer le texte de code étendu DataMatrix avec Aspose.BarCode pour .NET. Générez, reconnaissez et intégrez des codes‑barres dans vos applications .NET.

### [Maîtriser la configuration macro DataMatrix](./datamatrix-macro-configuration/)
Apprenez à configurer les codes‑barres DataMatrix Macro avec Aspose.BarCode pour .NET. Générez, personnalisez et reconnaissez les codes‑barres DataMatrix dans vos applications .NET.

## Questions fréquemment posées

**Q : Comment choisir le mode ECC à utiliser ?**  
R : Choisissez ECC 000‑140 pour les petits ensembles de données avec une correction d’erreurs limitée, ou ECC 200 pour des données plus volumineuses et une fiabilité accrue. Le mode macro ajoute une couche de données supplémentaire pour le lien.

**Q : Puis‑je intégrer du texte personnalisé dans un code‑barres DataMatrix ?**  
R : Oui, définissez la propriété `CodeText` sur votre chaîne personnalisée, puis sélectionnez le mode d’encodage approprié (ASCII, C40, etc.) pour contrôler la taille.

**Q : Existe‑t‑il un moyen de sélectionner automatiquement le meilleur mode d’encodage ?**  
R : Définissez `EncodeMode` sur `Auto` ; Aspose.BarCode évalue la charge utile et choisit automatiquement le mode le plus efficace en termes d’espace.

**Q : Quelles sont les considérations de performance pour de gros lots de codes‑barres ?**  
R : Réutilisez une seule instance de `BarCodeGenerator`, activez le multithreading, et générez des images PNG pour une qualité sans perte ou JPEG pour une taille de fichier réduite. Le traitement de 10 000 symboles se termine généralement en moins de 30 secondes sur un serveur standard à 8 cœurs.

**Q : Aspose.BarCode prend‑il en charge .NET Core et .NET 5/6 ?**  
R : Absolument – la bibliothèque est entièrement compatible avec .NET Framework, .NET Core et les dernières versions de .NET, offrant le même ensemble de fonctionnalités sur toutes les plateformes.

**Dernière mise à jour :** 2026-06-09  
**Testé avec :** Aspose.BarCode 24.12 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Maîtriser l’encodage DataMatrix en ASCII avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Créer un PNG de code‑barres – Rapport d’aspect DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}