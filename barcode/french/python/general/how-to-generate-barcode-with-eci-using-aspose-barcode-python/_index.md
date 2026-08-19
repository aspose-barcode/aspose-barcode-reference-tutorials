---
category: general
date: 2026-08-19
description: Comment générer un code‑barres avec ECI en utilisant Aspose.Barcode pour
  Python. Découvrez comment ajouter des données ECI, mélanger du texte brut et enregistrer
  l’image dans un guide clair.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: fr
lastmod: 2026-08-19
og_description: Comment générer un code-barres avec ECI en utilisant Aspose.Barcode
  pour Python. Suivez ce tutoriel pour apprendre comment ajouter des données ECI,
  personnaliser l'apparence et enregistrer le résultat.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Comment générer un code‑barres avec ECI en utilisant Aspose.Barcode Python
  – étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Comment générer un code‑barres avec ECI à l’aide d’Aspose.Barcode Python
url: /fr/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres avec ECI en utilisant Aspose.Barcode Python

Si vous devez savoir **comment générer un code-barres** contenant à la fois des caractères simples et des données encodées en ECI, ce guide montre le processus complet. Vous verrez exactement **comment ajouter des sections eci**, ajuster la taille et écrire l'image sur le disque avec un seul script exécutable.

Le tutoriel couvre :

* Récupérer la version de la bibliothèque Aspose.Barcode (optionnel mais utile pour le débogage).  
* Construire une chaîne de codetext étendue qui mélange des caractères simples et des caractères encodés en ECI.  
* Créer un générateur de code-barres pour une symbologie qui prend en charge le codetext étendu.  
* Personnaliser les dimensions du code-barres et enregistrer le fichier PNG final.

Aucune documentation externe n'est requise ; copiez le code, exécutez-le, et vous obtiendrez une image de code-barres incluant des caractères chinois encodés avec ECI 26 (UTF‑8).

## Prérequis

Avant de commencer, assurez‑vous d'avoir :

* Python 3.8 ou une version plus récente installé.  
* Le package `aspose-barcode` installé (`pip install aspose-barcode`).  
* Permission d'écriture sur le dossier où vous prévoyez d'enregistrer le fichier PNG.

Si vous utilisez un environnement virtuel, activez‑le d'abord pour garder les dépendances isolées.

## Étape 1 : Vérifier la version d'Aspose.Barcode (optionnel)

Connaître la version exacte de la bibliothèque aide lorsque vous devez signaler des bugs ou comparer les fonctionnalités entre les versions.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Pourquoi c'est important* : La sortie de version confirme que le runtime correspond à la documentation que vous suivez. Des versions différentes peuvent prendre en charge des valeurs ECI différentes, c’est donc une vérification rapide.

## Étape 2 : Construire un codetext étendu avec des parties simples et encodées en ECI

Aspose.Barcode fournit `ExtCodetextBuilder` pour concaténer des données simples et des segments encodés en ECI. Dans cet exemple, nous mélangeons une chaîne numérique avec des caractères chinois.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Explication* :  
* `add_plain_codetext` insère des données que la symbologie du code‑barres traite comme des caractères ordinaires.  
* `add_eci_codetext` indique au générateur de préfixer un indicateur ECI (ici **26**, qui correspond à UTF‑8) avant le texte fourni. C’est exactement **comment ajouter des données eci** à un code‑barres.

Vous pouvez appeler `add_eci_codetext` plusieurs fois pour intégrer plusieurs blocs de langues différents. Le constructeur gère automatiquement les séquences d'échappement requises.

## Étape 3 : Choisir une symbologie qui prend en charge le codetext étendu

Tous les types de code‑barres ne peuvent pas stocker des segments ECI. Code 128, QR et Data Matrix sont des choix courants. L'exemple utilise Code 128 car il est largement supporté et fonctionne bien pour des données alphanumériques mixtes.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Pourquoi Code 128 ?* : Il accepte toute la gamme ASCII ainsi que les séquences d'échappement ECI générées par le constructeur, ce qui le rend idéal pour le scénario « comment générer un code‑barres » qui mélange texte simple et texte encodé.

## Étape 4 : Ajuster l'apparence du code‑barres

Vous pouvez contrôler la taille, la hauteur, les marges et de nombreux autres aspects visuels via l'objet `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Conseil* : Si vous prévoyez d'imprimer le code‑barres, augmentez `x_dimension` et `bar_height` proportionnellement pour maintenir la lisibilité à la résolution DPI cible.

## Étape 5 : Enregistrer l'image du code‑barres

Enfin, écrivez l'image générée dans un fichier. Aspose.Barcode prend en charge PNG, JPEG, BMP et de nombreux autres formats.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Assurez‑vous que le dossier `output` existe ou créez‑le avec `os.makedirs("output", exist_ok=True)` avant d'appeler `save`.

### Résultat attendu

Lorsque vous ouvrez `extended_codetext.png`, vous devez voir un code‑barres Code 128 qui encode la chaîne numérique `1234567890` suivie des caractères chinois « 特殊字符 ». Scanner le code‑barres avec un lecteur moderne qui respecte l'ECI renverra la chaîne mixte originale.

![Code‑barres généré avec l'exemple de génération de code‑barres](https://example.com/images/barcode-sample.png){: .align-center alt="Code‑barres généré avec l'exemple de génération de code‑barres"}

## Questions fréquentes et cas particuliers

### Et si j'ai besoin d'un jeu de caractères différent ?

Choisissez la valeur ECI appropriée dans le tableau ISO/IEC 18004. Par exemple, ECI 27 représente ISO‑8859‑1 (Latin‑1). Remplacez l'identifiant numérique dans `add_eci_codetext` en conséquence.

### Puis‑je intégrer plus d'un bloc ECI ?

Oui. Appelez `add_eci_codetext` plusieurs fois. Le constructeur insère les codes de commutation ECI nécessaires entre les blocs, en préservant l'ordre dans lequel vous les ajoutez.

### Le générateur prend‑il en charge les QR codes avec ECI ?

Absolument. Remplacez `barcode.Symbology.CODE_128` par `barcode.Symbology.QR` et ajustez les paramètres spécifiques aux QR (par ex., le niveau de correction d'erreurs) via `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Comment gérer des chaînes de données très longues ?

Pour les codes‑barres linéaires comme Code 128, la longueur maximale est d'environ 80 caractères lorsqu'on utilise le codetext étendu. Si vous dépassez cette limite, envisagez de passer à une symbologie bidimensionnelle telle que QR ou Data Matrix, qui peut stocker des milliers de caractères.

## Script complet et exécutable

Ci‑dessous se trouve le programme complet que vous pouvez copier‑coller dans un fichier nommé `generate_extended_barcode.py` et exécuter directement.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer une image de code‑barres avec personnalisation de l'espace supplémentaire en utilisant Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Comment générer une image de code‑barres en Java avec Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Comment générer un code‑barres DataMatrix avec Aspose.BarCode pour .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}