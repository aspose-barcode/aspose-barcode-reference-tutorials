---
category: general
date: 2026-08-03
description: Créez rapidement un PNG de code-barres avec ce guide. Apprenez à générer
  une image de code-barres en utilisant Aspose.BarCode et à créer un code-barres Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode image
- generate planet barcode
- Python barcode generation
- Aspose.BarCode tutorial
language: fr
lastmod: 2026-08-03
og_description: Créez un PNG de code‑barres instantanément. Ce tutoriel montre comment
  générer une image de code‑barres et créer un code‑barres planétaire avec Aspose.BarCode.
og_image_alt: Example of a Planet barcode saved as a PNG image
og_title: Créer un code‑barres PNG en Python – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  headline: Create barcode PNG in Python – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  name: Create barcode PNG in Python – step‑by‑step guide
  steps:
  - name: 1. Install the Aspose.BarCode package
    text: 'Aspose provides a pure‑Python package that wraps its .NET core engine.
      Install it with `pip`:'
  - name: 2. Import required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 3. Create a barcode generator for the Planet symbology
    text: '```python # Step 1: Create a barcode generator for the Planet symbology
      with the desired data barcode_generator = BarcodeGenerator(EncodeTypes.Planet,
      "123456") ```'
  - name: 4. Set the X dimension (module width) in pixels
    text: '```python # Step 2: Set the X dimension (module width) in pixels barcode_generator.parameters.barcode.x_dimension.pixels
      = 4 ```'
  - name: 5. Define a manual bar height in pixels
    text: '```python # Step 3: Define a manual bar height in pixels barcode_generator.parameters.barcode.bar_height.pixels
      = 100 ```'
  - name: 6. Save the generated barcode as a PNG image
    text: '```python # Step 4: Save the generated barcode as a PNG image output_path
      = "output/PlanetBarHeight100.png" barcode_generator.save(output_path, BarCodeImageFormat.Png)
      print(f"Barcode saved to {output_path}") ```'
  - name: 7. Verify the output (optional)
    text: '```python from PIL import Image'
  - name: ' ## What Should You Learn Next?


      The following tutorials cover closely related topics that build on the techniques
      demonstrated in this guide. Each resource includes complete working code examples
      with step-by-step explanations to help you master additional API features and
      explore alternative implementation approaches in your own projects.

      - [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
      - [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
      - [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

      {{< /blocks/products/pf/tutorial-page-section >}}'
    text: '{{< /blocks/products/pf/main-container >}} {{< /blocks/products/pf/main-wrap-class
      >}} {{< blocks/products/products-backtop-button >}}'
  type: HowTo
tags:
- barcode
- PNG
- Python
- Aspose
title: Créer un PNG de code‑barres en Python – guide étape par étape
url: /fr/python-java/general/create-barcode-png-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code-barres en Python – guide étape par étape

Si vous avez besoin de **créer des fichiers PNG de code-barres** à partir de votre application Python, ce tutoriel vous montre exactement comment faire. Nous parcourrons **comment générer une image de code-barres** en utilisant Aspose.BarCode et plus spécifiquement **générer un code-barres Planet** avec des dimensions personnalisées.

Vous apprendrez comment installer la bibliothèque, configurer la symbologie Planet, ajuster les paramètres de taille et enregistrer le résultat sous forme de PNG de haute qualité. Le guide suppose des connaissances de base en Python et une version récente de Python 3 (3.8 ou plus récente). Aucune expérience préalable des normes de code-barres n’est requise.

---

## Comment créer un PNG de code-barres avec Aspose.BarCode

Cette section contient les étapes essentielles nécessaires pour **créer un PNG de code-barres**. Chaque étape comprend un extrait de code, une explication de son importance et des conseils pratiques que vous pouvez appliquer immédiatement.

### 1. Installer le package Aspose.BarCode

Aspose fournit un package pure‑Python qui encapsule son moteur .NET core. Installez‑le avec `pip` :

```bash
pip install aspose-barcode
```

*Pourquoi cette étape est importante :* Le package fournit la classe `BarcodeGenerator` utilisée tout au long de l’exemple. L’installer globalement garantit que l’interpréteur peut localiser l’assembly au moment de l’exécution.

### 2. Importer les classes requises

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

*Conseil :* Importez uniquement les symboles dont vous avez besoin ; cela garde l’espace de noms propre et accélère le chargement du module.

### 3. Créer un générateur de code-barres pour la symbologie Planet

```python
# Step 1: Create a barcode generator for the Planet symbology with the desired data
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

*Pourquoi c’est important :* `EncodeTypes.Planet` indique au moteur d’utiliser la norme de code-barres Planet, tandis que le deuxième argument fournit les données à encoder. Modifier la symbologie (par ex., `EncodeTypes.Code128`) produirait un motif visuel complètement différent.

### 4. Définir la dimension X (largeur du module) en pixels

```python
# Step 2: Set the X dimension (module width) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

*Explication :* La dimension X contrôle la largeur de la barre étroite. Une valeur de 4 pixels donne un code-barres modérément dense qui reste lisible sur la plupart des appareils.

### 5. Définir une hauteur de barre manuelle en pixels

```python
# Step 3: Define a manual bar height in pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

*Pourquoi vous pourriez ajuster cela :* Certains imprimantes de détail nécessitent des barres plus hautes pour un scan fiable. La hauteur par défaut est généralement de 50 px ; l’augmenter à 100 px améliore la lisibilité sans augmenter de façon spectaculaire la taille du fichier.

### 6. Enregistrer le code-barres généré en tant qu’image PNG

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "output/PlanetBarHeight100.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

*Résultat :* Un fichier PNG nommé **PlanetBarHeight100.png** apparaît dans le dossier `output`. PNG est sans perte, ce qui le rend idéal pour l’impression et l’intégration dans les pages web.

### 7. Vérifier la sortie (optionnel)

```python
from PIL import Image

with Image.open(output_path) as img:
    img.show()   # Opens the default image viewer
    print(f"Image size: {img.size} (width, height)")
```

*Conseil :* Visualiser l’image confirme que les dimensions correspondent aux paramètres que vous avez définis. Si le code-barres apparaît déformé, revérifiez la dimension X ou les réglages de hauteur de barre.

---

## Comment générer une image de code-barres au format PNG (paramètres alternatifs)

Si vous avez besoin d’un format d’image différent ou souhaitez intégrer le code-barres dans un PDF ultérieurement, vous pouvez modifier l’énumération `BarCodeImageFormat` :

```python
# Save as JPEG instead of PNG
barcode_generator.save("output/PlanetBar.jpeg", BarCodeImageFormat.Jpeg)

# Save as BMP for legacy Windows applications
barcode_generator.save("output/PlanetBar.bmp", BarCodeImageFormat.Bmp)
```

*Pourquoi c’est important :* PNG préserve chaque pixel, ce qui est crucial pour les codes-barres à fort contraste. JPEG introduit des artefacts de compression qui peuvent gêner le scan, tandis que BMP offre une compatibilité avec les outils plus anciens.

## Générer un code-barres Planet avec des couleurs personnalisées (avancé)

Au-delà de la taille, vous pouvez personnaliser les couleurs de premier plan et d’arrière‑plan :

```python
from aspose.barcode import Color

# Set foreground to dark blue and background to light gray
barcode_generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
barcode_generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

barcode_generator.save("output/PlanetColored.png", BarCodeImageFormat.Png)
```

*Conseil pratique :* Les paires de couleurs à fort contraste (sombre sur clair) maximisent la fiabilité du scanner. Évitez d’utiliser des teintes similaires pour le premier plan et l’arrière‑plan.

## Pièges courants et comment les éviter

| Symptom | Cause | Fix |
|---------|-------|-----|
| Le code-barres ne se lit pas | Dimension X trop petite (≤ 2 px) | Augmenter `x_dimension.pixels` à au moins 3 px |
| L’image apparaît floue | PNG enregistré à faible DPI | Utiliser `barcode_generator.save(..., BarCodeImageFormat.Png, 300)` pour spécifier 300 DPI (si supporté) |
| Exception `ImportError` | Aspose.BarCode non installé | Exécuter `pip install aspose-barcode` dans le même environnement que votre script |
| Symbologie incorrecte | Utilisé `EncodeTypes.Code128` au lieu de `EncodeTypes.Planet` | Remplacer par `EncodeTypes.Planet` lors de la création du générateur |

## Récapitulatif de la solution complète

Voici le script complet et exécutable qui **crée un PNG de code-barres** du début à la fin :

```python
# full_example.py
# -------------------------------------------------
# Demonstrates how to generate a Planet barcode PNG
# -------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create generator with Planet symbology
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# 2️⃣ Configure dimensions
generator.parameters.barcode.x_dimension.pixels = 4          # module width
generator.parameters.barcode.bar_height.pixels = 100        # bar height

# 3️⃣ Optional: set colors (uncomment to use)
# from aspose.barcode import Color
# generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
# generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

# 4️⃣ Save as PNG
png_path = os.path.join(output_dir, "PlanetBarHeight100.png")
generator.save(png_path, BarCodeImageFormat.Png)

print(f"✅ Barcode PNG created at: {png_path}")

# 5️⃣ Verify (opens the image on most OSes)
try:
    from PIL import Image
    with Image.open(png_path) as img:
        img.show()
        print(f"Image size: {img.size}")
except Exception as e:
    print(f"Verification step skipped: {e}")
```

L’exécution de ce script produit un **PNG de code-barres Planet** net que vous pouvez intégrer dans du HTML, joindre à des e‑mails ou imprimer sur des étiquettes de produit.

## Prochaines étapes et sujets associés

* **Intégrer avec Flask ou Django** – servir le PNG généré directement depuis un point de terminaison web.  
* **Génération par lots** – parcourir une liste d’identifiants de produit pour créer un dossier de fichiers PNG de code-barres.  
* **Combiner avec la génération de PDF** – utiliser `aspose-pdf` pour placer le PNG dans une facture ou une étiquette d’expédition.  
* **Explorer d’autres symbologies** – remplacer `EncodeTypes.Planet` par `EncodeTypes.QR`, `EncodeTypes.DataMatrix` ou `EncodeTypes.Code128` pour répondre à différents besoins métier.

En maîtrisant les étapes ci‑dessus, vous savez maintenant **comment générer une image de code-barres** de façon programmatique et pouvez étendre le modèle à toute norme de code-barres prise en charge par Aspose.BarCode.

---

###

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}