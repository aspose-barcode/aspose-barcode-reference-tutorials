---
category: general
date: 2026-08-09
description: Créez un code‑QR en Python avec Aspose.BarCode. Apprenez à générer un
  texte de code étendu, à ajuster l’apparence et à enregistrer l’image — le tout dans
  un seul tutoriel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: fr
lastmod: 2026-08-09
og_description: Créer un code‑QR en Python avec Aspose.BarCode. Ce guide montre comment
  générer un texte de code étendu, définir les paramètres visuels et exporter l’image.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Créer un code‑QR avec Aspose.BarCode en Python – exemple complet de code
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Créer un code‑barres QR avec Aspose.BarCode en Python – guide étape par étape
url: /fr/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres QR avec Aspose.BarCode en Python – guide étape par étape

Si vous devez **créer un code‑barres QR** en Python, ce tutoriel vous guide à travers l’ensemble du processus en utilisant la bibliothèque Aspose.BarCode. Que vous codiez des identifiants de produit, du texte multilingue ou des données personnalisées, vous verrez comment construire un texte de code étendu, ajuster les paramètres visuels et enregistrer l’image finale dans un script unique et exécutable.

L’exemple montre également comment afficher la version de la bibliothèque, ce qui vous aide à vérifier que vous utilisez une version compatible. À la fin de ce guide, vous disposerez d’une image de code‑barres QR prête à l’emploi et d’une compréhension claire de chaque option de configuration.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Python 3.8+ installé.
- Le package `aspose-barcode` (installer via `pip install aspose-barcode`).
- Une connaissance de base de la syntaxe Python.
- Les droits d’écriture sur le répertoire de sortie où le fichier PNG sera enregistré.

> **Astuce :** Utilisez un environnement virtuel pour éviter les conflits de version avec d’autres projets.

## Étape 1 : Vérifier la version de la bibliothèque Aspose.BarCode

Afficher la version de la bibliothèque garantit que vous utilisez une version qui prend en charge le texte de code étendu et l’encodage QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Pourquoi c’est important :**  
Les versions antérieures peuvent ne pas contenir la classe `ExtCodetextBuilder` requise pour les segments mixtes plain et ECI. Confirmer la version évite les erreurs d’exécution ultérieures dans le flux de travail.

## Étape 2 : Construire une chaîne de texte de code étendu

Un texte de code étendu vous permet de combiner des données ASCII simples avec des segments Unicode (ECI), ce qui est essentiel pour les QR codes multilingues.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Pourquoi c’est important :**  
La méthode `add_plain_codetext` stocke les données en ASCII standard, tandis que `add_eci_codetext` préfixe un bloc Unicode avec le désignateur ECI approprié. Cette approche garantit que les scanners QR interprètent correctement le texte japonais, évitant ainsi les caractères corrompus.

### Variantes courantes

- **Segments ECI multiples :** Appelez `add_eci_codetext` plusieurs fois pour mélanger plusieurs langues.
- **Identifiants ECI différents :** Utilisez `27` pour ISO‑8859‑1, `28` pour ISO‑8859‑2, etc., selon l’encodage cible.

## Étape 3 : Générer le code‑barres QR à l’aide du texte de code étendu

Maintenant que nous disposons d’une chaîne correctement formatée, nous pouvons créer le QR code.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Pourquoi c’est important :**  
`EncodeTypes.QR` indique à Aspose.BarCode d’utiliser la symbologie QR. Passer directement `extended_codetext` lie les données mixtes à la matrice QR, préservant à la fois les parties plain et Unicode.

## Étape 4 : Ajuster l’apparence visuelle (optionnel mais recommandé)

Affiner les paramètres visuels du code‑barres améliore la fiabilité du scan et correspond aux directives de votre identité visuelle.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Pourquoi c’est important :**  
- **`x_dimension`** contrôle la taille de chaque module QR ; une taille trop petite peut entraîner des erreurs de lecture sur des appareils à faible résolution.  
- **`border_width`** ajoute une zone silencieuse. Certains scanners exigent au moins une zone silencieuse de 4 modules ; la bibliothèque l’ajoute automatiquement, mais vous pouvez l’augmenter pour plus de sécurité.

### Gestion des cas limites

- **Données à haute densité :** Si les données encodées sont volumineuses, vous devrez peut‑être augmenter `x_dimension` ou choisir un niveau de correction d’erreur supérieur (via `qr_generator.parameters.qr.error_correction_level`).  
- **Arrière‑plan transparent :** Définissez `qr_generator.parameters.barcode.bg_color = Color.Transparent` pour des PNG avec canal alpha.

## Étape 5 : Enregistrer l’image du code‑barres QR

Enfin, écrivez l’image sur le disque dans le format de votre choix.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Pourquoi c’est important :**  
Enregistrer au format PNG préserve une qualité sans perte, idéale pour les QR codes qui nécessitent des bords nets. Si vous avez besoin d’un autre format pour une application web, modifiez simplement l’énumération `BarCodeImageFormat`.

### Vérification du résultat

Ouvrez le fichier enregistré avec n’importe quel visualiseur d’images. Vous devriez voir un QR code qui, lorsqu’il est scanné, renvoie la chaîne combinée :

```
ABC12345
こんにちは
```

La plupart des applications de lecture QR modernes affichent d’abord le segment plain, puis rendent correctement le salut japonais.

---

## Script complet exécutable

Copiez le bloc entier ci‑dessous dans un fichier nommé `create_qr_barcode.py` et exécutez‑le avec `python create_qr_barcode.py`. Ajustez `YOUR_DIRECTORY` vers un dossier accessible en écriture sur votre machine.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

L’exécution de ce script affiche la version, le texte de code étendu et une confirmation que le fichier PNG a été créé.

---

## Conclusion

Vous savez maintenant comment **créer des images de code‑barres QR** en Python avec Aspose.BarCode. Le tutoriel a couvert :

1. Vérification de la version de la bibliothèque.  
2. Construction d’un texte de code étendu avec des segments plain et ECI (Unicode).  
3. Génération du QR code.  
4. Personnalisation des paramètres visuels tels que la taille du module et la largeur de la bordure.  
5. Enregistrement de l’image finale au format PNG.

À partir d’ici, vous pouvez explorer :

- Modifier les niveaux de correction d’erreur (`qr_generator.parameters.qr.error_correction_level`).  
- Ajouter un logo ou une image d’arrière‑plan (`qr_generator.parameters.qr.logo`).  
- Exporter vers d’autres formats comme SVG pour des graphiques web évolutifs.  
- Intégrer le générateur dans un point de terminaison Flask ou Django pour créer des QR codes à la volée.

Expérimentez avec différentes charges utiles et paramètres visuels pour adapter votre application aux exigences de marque et de numérisation. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}