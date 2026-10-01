---
category: general
date: 2026-08-12
description: Comment générer rapidement un code‑barres avec Python. Apprenez à créer
  un code‑barres à partir de données et à exporter l’image du code‑barres avec une
  seule bibliothèque.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: fr
lastmod: 2026-08-12
og_description: Comment générer un code‑barres en Python avec Aspose.BarCode. Suivez
  ce guide pour créer un code‑barres à partir de données et exporter l’image du code‑barres
  au format PNG.
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: Comment générer un code-barres en Python – guide rapide et fiable
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: Comment générer un code‑barres en Python – guide complet étape par étape
url: /fr/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code-barres en Python – guide complet étape par étape

Si vous avez besoin de **how to generate barcode** dans une application Python, ce tutoriel vous montre le code exact dont vous avez besoin. Vous apprendrez à **create barcode from data**, ajuster son apparence, et **export barcode image** en fichier PNG — le tout en moins de dix lignes de code.

Générer un code-barres peut sembler être une préoccupation distincte du reste de votre logique métier, mais avec une seule bibliothèque vous pouvez garder le processus intégré à votre base de code existante. Dans les sections suivantes, vous verrez un exemple complet et exécutable, comprendrez pourquoi chaque ligne est importante, et découvrirez des variantes courantes telles que la modification de la largeur du module ou le dessin d'un code-barres uniquement en contour.

## Comment générer un code-barres avec la bibliothèque Aspose.BarCode

La bibliothèque Aspose.BarCode pour Python (via .NET) fournit une API simple pour de nombreuses symbologies, y compris le code-barres Planet utilisé dans ce guide. Avant de commencer, assurez-vous que le paquet est installé :

```bash
pip install aspose-barcode
```

> **Astuce :** Utilisez un environnement virtuel pour éviter les conflits de version avec d’autres projets.

### 1. Importer les classes requises

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Ces importations vous donnent accès à la classe générateur, à l’énumération des types de code-barres, et à l’énumération des formats d’image utilisée lors de l’enregistrement du résultat.

### 2. Créer un code-barres à partir de données

La première étape consiste à **create barcode from data**. Le constructeur `BarcodeGenerator` prend la symbologie et la chaîne brute que vous souhaitez encoder.

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

La valeur `EncodeTypes.Planet` sélectionne le code-barres Planet, tandis que `"123456"` est la charge utile qui apparaîtra dans l’image finale.

### 3. Ajuster la dimension X (largeur du module)

La dimension X contrôle la largeur de chaque module du code-barres (la barre fine). La régler à 4 pixels donne une image claire et lisible sans rendre le fichier trop volumineux.

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **Pourquoi c’est important :** Une dimension X plus grande améliore la fiabilité du scan sur les imprimantes basse résolution, tandis qu’une valeur plus petite réduit la taille du fichier pour une utilisation web.

### 4. Exporter l’image du code-barres (style rempli)

Vous pouvez maintenant **export barcode image** en utilisant la méthode `save`. L’exemple enregistre un fichier PNG, mais vous pouvez choisir JPEG, BMP ou TIFF en modifiant l’énumération `BarCodeImageFormat`.

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

Le fichier `PlanetFilled.png` contient un code-barres Planet entièrement rempli, prêt à être imprimé ou intégré dans un PDF.

### 5. Créer un second générateur pour un code-barres uniquement en contour

Si vous avez besoin d’une version en contour (barres vides), vous devez créer un nouveau générateur car le drapeau `filled_bars` ne peut pas être modifié après l’enregistrement de l’image.

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. Appliquer le même réglage de dimension X

Lorsque vous créez un second générateur, vous devez répéter tous les réglages visuels que vous souhaitez conserver de façon cohérente.

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. Désactiver les barres remplies pour un code-barres en contour

Définir `filled_bars` à `False` indique au rendu de ne dessiner que les contours de chaque module, produisant une image plus légère qui peut être utile à des fins de conception.

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. Exporter l’image du code-barres en contour

Enfin, **export barcode image** à nouveau, cette fois en enregistrant la version en contour.

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

Vous avez maintenant deux fichiers PNG : un avec des barres solides (`PlanetFilled.png`) et un avec uniquement les contours (`PlanetEmpty.png`).

## Exporter l’image du code-barres dans d’autres formats (optionnel)

La méthode `save` prend en charge plusieurs formats. Pour exporter en JPEG avec une qualité de 90 % :

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

Si vous avez besoin d’un arrière-plan transparent pour le web, choisissez PNG avec un canal alpha :

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## Variantes courantes et cas limites

| Scénario | Modification requise | Extrait de code |
|----------|----------------------|-----------------|
| **Different symbology** (e.g., QR) | Use a different `EncodeTypes` value | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **Custom foreground color** | Set `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **Higher resolution** | Increase DPI via `image_width` and `image_height` | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **Large data strings** | Ensure data length fits the symbology spec | Validate length before creating the generator |

> **Attention :** Fournir des données qui dépassent la longueur maximale pour la symbologie choisie déclenche une exception d’exécution. Validez toujours la longueur de la chaîne ou capturez `ArgumentException`.

## Exemple complet et exécutable

Voici le script complet que vous pouvez copier‑coller dans un fichier nommé `generate_planet_barcode.py`. Ajustez `YOUR_DIRECTORY` vers un dossier qui existe sur votre machine.

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

L’exécution de ce script produit deux fichiers PNG dans le répertoire spécifié. Vérifiez le résultat en ouvrant les images avec n’importe quel visualiseur d’images ; les deux doivent afficher un code-barres Planet encodant la chaîne `123456`.

## Conclusion

Vous savez maintenant **how to generate barcode** en Python avec Aspose.BarCode, comment **create barcode from data**, et comment **export barcode image** à la fois en styles remplis et en contour. Le même modèle s’applique à d’autres symbologies, formats d’image et personnalisations visuelles, vous offrant une base flexible pour toute fonctionnalité liée aux codes-barres dans votre application.

### Prochaines étapes

* Explorez d’autres symbologies telles que QR, Code‑128 ou DataMatrix en remplaçant `EncodeTypes.Planet` par la valeur souhaitée.  
* Intégrez les fichiers PNG générés dans des rapports PDF en utilisant des bibliothèques comme `ReportLab` ou `PyPDF2`.  
* Expérimentez avec des valeurs dynamiques de dimension X pour adapter la taille du code-barres en fonction de la résolution d’écran ou du DPI de l’imprimante.

Bonne programmation, et n’hésitez pas à adapter l’exemple pour répondre aux exigences de votre propre projet !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer une image de code-barres en Java avec Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Comment générer un code-barres Java – Guide complet de configuration](/barcode/english/java/barcode-configuration/)
- [Comment créer des images de code128 en Java avec Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}