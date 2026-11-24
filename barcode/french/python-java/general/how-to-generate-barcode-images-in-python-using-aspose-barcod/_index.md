---
category: general
date: 2026-11-23
description: Comment générer des images de code‑barres en Python avec Aspose.BarCode.
  Apprenez à créer un code‑barres Planet, à ajuster la dimension X et à produire un
  PNG à barres vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: fr
lastmod: 2026-11-23
og_description: Comment générer un code-barres en Python avec Aspose.BarCode. Ce tutoriel
  vous guide dans la création d’un code-barres Planet avec des barres vides et son
  enregistrement au format PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Comment générer un code‑barres en Python – guide complet
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Comment générer des images de code-barres en Python avec Aspose.BarCode
url: /fr/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des images de code-barres en Python avec Aspose.BarCode

Générer des images de code-barres en Python est simple avec la bibliothèque Aspose.BarCode. Ce guide vous montre étape par étape comment générer un code-barres en utilisant la symbologie Planet, personnaliser la X‑dimension et produire un fichier PNG au style barres vides.

Vous verrez un script complet et exécutable que vous pouvez copier dans votre projet. Le tutoriel couvre également les variantes courantes — comme le passage à une autre symbologie ou à un autre format de sortie — afin que vous puissiez adapter la solution à vos propres besoins.

## Prérequis

* Python 3.8 ou version ultérieure installé.
* Accès à un terminal ou à l’invite de commande.
* Une licence active d’Aspose.BarCode pour Python (l’évaluation gratuite fonctionne pour les tests).
* Familiarité de base avec la gestion des paquets Python (`pip`).

## Étape 1 : Installer le package Aspose.BarCode

Aspose distribue son API Python via PyPI. Installez‑le avec le gestionnaire de paquets standard :

```bash
pip install asposebarcode
```

> **Astuce :** Utilisez un environnement virtuel (`python -m venv venv`) pour garder les dépendances isolées des autres projets.

## Étape 2 : Importer les classes Aspose.BarCode requises

L’instruction d’importation charge le générateur, l’énumération des symbologies et l’énumération des formats d’image.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` crée l’objet code‑barres.
* `EncodeTypes` énumère toutes les symbologies prises en charge — ici nous utiliserons `Planet`.
* `BarCodeImageFormat` définit le type de fichier de sortie (PNG, JPEG, etc.).

## Étape 3 : Créer un générateur de code‑barres pour la symbologie Planet

Instanciez le générateur avec la symbologie souhaitée et les données que vous voulez encoder.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

La symbologie `Planet` produit un motif circulaire idéal pour des usages décoratifs ou de branding.

## Étape 4 : Ajuster la X‑dimension (largeur du module)

La X‑dimension contrôle la largeur de la plus petite barre (module). La régler à 4 pixels donne une image claire et haute résolution.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Modifier la X‑dimension est utile lorsque vous avez besoin d’un code‑barres qui s’adapte bien à l’impression ou à l’affichage à l’écran.

## Étape 5 : Désactiver les barres pleines pour un style barres vides

Un code‑barres à barres vides n’affiche que les contours des barres, ce qui peut être utile pour des applications fortement orientées design.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Lorsque `filled_bars` vaut `False`, le générateur dessine des formes creuses au lieu de formes pleines.

## Étape 6 : Enregistrer l’image du code‑barres au format PNG

Enfin, écrivez le code‑barres sur le disque. PNG est sans perte et largement supporté.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

La méthode `save` crée automatiquement le répertoire cible s’il n’existe pas.

## Exemple complet – un script complet et exécutable

Assembler toutes les pièces vous donne un programme autonome que vous pouvez exécuter immédiatement :

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Sortie attendue :** Après l’exécution du script, `output/PlanetEmptyBars.png` contient une image de 200 × 200 pixels d’un code‑barres Planet avec des barres creuses. Ouvrir le fichier dans n’importe quel visualiseur d’image affichera le motif circulaire avec la valeur numérique encodée à l’intérieur.

## Variantes courantes et cas limites

### Passer à une autre symbologie

Si vous avez besoin d’un QR code, Code 128 ou tout autre format, remplacez `EncodeTypes.Planet` par la valeur d’énumération appropriée :

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Changer le format d’image

Aspose.BarCode prend en charge PNG, JPEG, BMP et TIFF. Pour générer un JPEG à la place :

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Ajuster la taille de l’image sans perdre en qualité

Vous pouvez contrôler les dimensions globales de l’image via la propriété `resolution` ou en mettant à l’échelle conjointement la X‑dimension et la Y‑dimension. Pour des impressions haute résolution, définissez un DPI plus élevé :

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Gestion des chaînes de données longues

La symbologie Planet a une capacité de données limitée (jusqu’à 8 caractères). Si vous essayez d’encoder une chaîne plus longue, le générateur lève une exception. Validez la longueur avant de créer le code‑barres :

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Conseils et pièges

* **Activation de licence :** Pour une utilisation en production, appliquez votre fichier de licence tôt dans le script avec `asposebarcode.License().set_license("Aspose.Total.lic")`. Ignorer cette étape ajoutera un filigrane à l’image de sortie.
* **Sécurité des threads :** Les instances de `BarcodeGenerator` ne sont pas thread‑safe. Créez une instance distincte par thread si vous générez des codes‑barres en parallèle.
* **Performance :** Réutiliser un générateur pour plusieurs valeurs (en appelant `barcode.value = "new data"`) est plus rapide que de créer un nouvel objet à chaque fois.
* **Chemins de fichiers :** Utilisez `os.path.join` pour construire des chemins indépendants de la plateforme, notamment lors du déploiement sous Linux ou macOS.

## Conclusion

Vous savez maintenant comment générer des images de code‑barres en Python avec Aspose.BarCode, personnaliser la X‑dimension, produire un style barres vides et enregistrer le résultat au format PNG. L’exemple complet peut être adapté à d’autres symbologies, formats de sortie et styles visuels, vous offrant une base flexible pour toute fonctionnalité liée aux codes‑barres dans vos applications.

**Prochaines étapes :** Explorez des mots‑clés secondaires supplémentaires tels que *Python barcode generation* en essayant différents encodages, expérimentez les paramètres de compression *barcode image PNG*, ou intégrez les images générées dans un service web avec Flask ou FastAPI. Bon codage !

## Ce que vous devriez apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer un code‑barres Planet PNG avec Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Comment créer une image de code‑barres en Python avec Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [Comment générer une image de QR Code en Python avec Aspose.Barcode – Guide complet](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}