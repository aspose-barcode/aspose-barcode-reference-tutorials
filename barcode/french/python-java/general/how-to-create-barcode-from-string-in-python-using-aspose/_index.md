---
category: general
date: 2026-10-15
description: Créez un code‑barres à partir d’une chaîne avec Aspose.Barcode pour Python.
  Apprenez à générer un code‑barres, à définir les dimensions et à l’enregistrer au
  format PNG en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: fr
lastmod: 2026-10-15
og_description: Créer un code‑barres à partir d’une chaîne avec Aspose.Barcode pour
  Python. Ce tutoriel vous montre, étape par étape, comment générer un code‑barres
  postal et l’enregistrer au format PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Créer un code‑barres à partir d’une chaîne en Python – Guide Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Comment créer un code‑barres à partir d’une chaîne en Python avec Aspose
url: /fr/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres à partir d’une chaîne en Python avec Aspose

Si vous devez **créer un code‑barres à partir d’une chaîne** rapidement, Aspose.Barcode pour Python rend cela simple. Dans ce guide, vous verrez exactement **comment générer des images de code‑barres**, ajuster la dimension X et enregistrer le résultat au format PNG — le tout en quelques lignes de code.

Vous obtiendrez également un **exemple complet de générateur de code‑barres** que vous pourrez copier‑coller dans votre propre projet. Aucun script externe ni configuration complexe n’est requis, et le tutoriel fonctionne avec la version actuelle d’Aspose.Barcode 23.10.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- Python 3.8+ installé sur votre machine  
- Une licence active d’Aspose.Barcode pour Python (l’essai gratuit suffit pour l’évaluation)  
- `pip install aspose-barcode` exécuté dans votre environnement virtuel  

Ces éléments garantissent que le code s’exécute sans erreurs d’importation.

## Créer un code‑barres à partir d’une chaîne avec Aspose.Barcode (Python)

La première étape consiste à instancier le `BarcodeGenerator` avec la symbologie souhaitée — dans ce cas le code‑barres postal **Planet** — et la chaîne que vous voulez encoder.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Pourquoi c’est important :**  
`EncodeTypes.Planet` indique à Aspose d’utiliser la symbologie postal Planet, conçue pour le tri du courrier dans de nombreux pays. Le deuxième argument (`"123456"`) est la chaîne brute qui sera encodée dans le code‑barres. Modifier cette valeur vous permet de **créer un code‑barres à partir d’une chaîne** pour n’importe quel code postal ou numéro de suivi dont vous avez besoin.

## Comment générer un code‑barres avec des dimensions personnalisées

La largeur du module d’un code‑barres postal (la dimension X) doit souvent correspondre aux spécifications d’impression. Aspose vous permet de définir la largeur en pixels tout en calculant automatiquement la hauteur.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Pourquoi vous pourriez ajuster cela :**  
Une dimension X plus grande rend les barres plus épaisses, ce qui peut améliorer la fiabilité du scan sur des imprimantes basse résolution. À l’inverse, une valeur plus petite réduit la taille de l’image pour une utilisation web. Cette ligne montre **comment générer des images de code‑barres** qui répondent à des exigences de taille précises.

## Enregistrer l’image du code‑barres

Après avoir configuré le générateur, il suffit d’appeler `save`. La méthode accepte le chemin de sortie et le format d’image souhaité.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Ce que vous obtenez :**  
Un fichier PNG nommé `PostalPlanetAuto.png` contenant le code‑barres Planet qui encode `"123456"`. Vous pouvez ouvrir le fichier avec n’importe quel visualiseur d’images pour vérifier le résultat.

![Capture d’écran d’un code‑barres postal généré et enregistré au format PNG](barcode_example.png){.align-center alt="Capture d’écran d’un code‑barres postal généré et enregistré au format PNG"}

## Exemple complet de générateur de code‑barres

Voici le script complet, prêt à être exécuté, qui inclut toutes les étapes ci‑dessus. Copiez‑le dans un fichier nommé `generate_postal_barcode.py` et lancez `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Résultat attendu

L’exécution du script produit :

```
Barcode saved to PostalPlanetAuto.png
```

…et crée un fichier `PostalPlanetAuto.png` qui ressemble à ceci :

![Code‑barres Planet généré](barcode_example.png){.align-center alt="Code‑barres Planet généré et enregistré au format PNG"}

## Variations courantes et cas limites

| Situation | Ce qu’il faut modifier | Pourquoi |
|-----------|------------------------|----------|
| **Symbologie différente** (p. ex., Code128) | Remplacez `EncodeTypes.Planet` par `EncodeTypes.Code128` | Vous permet de **générer un code‑barres** pour des étiquettes d’inventaire, pas seulement des codes postaux. |
| **Chaînes de données plus longues** | Assurez‑vous que la symbologie choisie supporte la longueur ; pour Planet, vous devez rester sur 6 chiffres. | Évite l’`ValueError` à l’exécution. |
| **Résolution supérieure** | Augmentez `x_dimension.pixels` à 6 ou 8. | Produit des barres plus épaisses pour une impression haute DPI. |
| **Autres formats d’image** | Utilisez `BarCodeImageFormat.JPEG` ou `BarCodeImageFormat.GIF`. | Utile lorsque le PNG ne convient pas à votre flux de travail. |
| **Exécution dans un service web** | Remplacez l’appel `save` du système de fichiers par un flux `BytesIO` et renvoyez les octets. | Permet la génération de code‑barres à la volée dans Flask ou Django. |

**Astuce :** Validez toujours la chaîne d’entrée avant d’appeler `BarcodeGenerator`. Des données invalides (longueur incorrecte, caractères non numériques pour Planet) déclencheront une exception et interrompront votre application.

## Comment générer un code‑barres dans un endpoint Flask (étape optionnelle suivante)

Si vous souhaitez exposer l’**exemple de générateur de code‑barres** en tant qu’API REST, vous pouvez encapsuler la fonction `create_postal_barcode` :

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Cet extrait montre comment **générer un code‑barres** à la demande sans écrire sur le disque, ce qui est pratique pour les micro‑services.

## Conclusion

Vous savez maintenant comment **créer un code‑barres à partir d’une chaîne** en Python avec Aspose.Barcode, comment **générer un code‑barres** avec des dimensions personnalisées, et comment **enregistrer** le résultat au format PNG. L’**exemple complet de générateur de code‑barres** inclut la validation des entrées, la gestion des erreurs et une fonction réutilisable que vous pouvez intégrer dans des applications plus importantes.

Ensuite, explorez d’autres symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) ou intégrez le générateur dans un framework web comme Flask ou Django. Ces étapes approfondiront votre compréhension de la bibliothèque **aspose barcode python** et élargiront les façons dont vous pouvez **générer des images de code‑barres postaux** pour des projets réels.

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}