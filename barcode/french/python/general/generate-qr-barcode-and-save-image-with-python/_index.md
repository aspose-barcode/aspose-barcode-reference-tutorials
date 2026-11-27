---
category: general
date: 2026-11-27
description: Générez un code‑QR en Python avec Aspose.Barcode et apprenez à enregistrer
  rapidement l’image du code‑barres sur le disque.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: fr
lastmod: 2026-11-27
og_description: Générez un code‑QR en Python avec Aspose.Barcode et enregistrez instantanément
  l’image du code‑QR. Suivez l’exemple complet pour créer, personnaliser et stocker
  les codes QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Générer un code‑QR et enregistrer l’image avec Python – guide étape par
  étape
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Générer un code QR et enregistrer l'image avec Python
url: /fr/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres QR et enregistrer l'image avec Python

If you need to **generate QR barcode** in a Python application, this guide shows you how to do it using the Aspose.Barcode library. You will also learn the correct way to **save barcode image** to a local folder, retrieve library version details, and handle extended codetext segments.

Creating QR codes is a common requirement for ticketing systems, mobile payments, and product tracking. By the end of this tutorial you will have a ready‑to‑run script that produces a QR barcode image file and prints version information for debugging or compliance purposes.

## Prérequis

Before you start, make sure you have:

* Python 3.8 ou version plus récente installé.
* Le package `aspose-barcode`. Installez‑le avec `pip install aspose-barcode`.
* Permission d'écriture sur le répertoire où l'image du code‑barres sera stockée.

No additional external services are required; the entire process runs locally.

## Étape 1 : Construire un texte de code étendu avec `ExtCodetextBuilder`

Extended codetext lets you mix plain text and ECI (Extended Channel Interpretation) segments in a single QR code. This is useful when you need to embed characters from different character sets, such as the Euro sign.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Pourquoi cette étape est importante :**  
`ExtCodetextBuilder` assembles the final string that the QR encoder will process. Without building the extended codetext, the barcode would contain only plain ASCII characters and could not represent locale‑specific symbols.

## Étape 2 : Récupérer la chaîne de texte de code étendu combinée

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

La sortie ressemble à :

```
Extended codetext: ABC123[ECI3]€123
```

Le marqueur entre crochets `[ECI3]` indique à l'encodeur QR de passer au jeu de caractères spécifié pour les caractères suivants.

## Étape 3 : Générer le code‑barres QR en utilisant le texte de code étendu

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Explication :**  
`BarcodeGenerator` receives two arguments: the barcode type (`QR`) and the data to encode (`extended_codetext`). The generator prepares all internal structures needed for rendering.

## Étape 4 : Enregistrer l'image du code‑barres généré

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Pourquoi vous devriez utiliser cette approche :**  
Calling `save` directly writes the image to disk using the format inferred from the file extension. The method supports PNG, JPEG, BMP, and TIFF, giving you flexibility for different downstream consumers.

### Vérification de l'image enregistrée

Open the file `output/qr_extended.png` with any image viewer. You should see a QR code that, when scanned, returns the string `ABC123€123`. Most modern mobile QR scanners handle the ECI segment automatically.

## Étape 5 : Interroger les informations de version d'Aspose.BarCode (optionnel mais utile)

Knowing the exact version of the Aspose.BarCode library helps when you need to report bugs or verify compatibility.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Sortie typique :

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Script complet – copier, coller et exécuter

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Running the script produces the QR code image and prints both the extended codetext and version details to the console.

## Variantes courantes et cas limites

| Situation | Ajustement recommandé |
|-----------|------------------------|
| **Jeu de caractères différent** | Change the ECI identifier passed to `add_eci_codetext`. For UTF‑8 use `5`. |
| **Correction d'erreur plus élevée** | Set `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` before calling `save`. |
| **Taille d'image personnalisée** | Use `barcode.parameters.image_width` and `barcode.parameters.image_height` to control pixel dimensions. |
| **Sortie non‑PNG** | Change the file extension in `output_path` to `.jpg` or `.bmp`. The library automatically selects the correct encoder. |

## Conseils pro

* **Créer le dossier de sortie** de façon programmatique s'il n'existe pas :

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Valider le code QR** après génération en le lisant avec `aspose.barcode.BarcodeReader`. Cela garantit que les données encodées correspondent aux attentes, surtout lors de l'utilisation de segments ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Astuce de performance** – réutilisez une seule instance de `BarcodeGenerator` si vous devez générer de nombreux codes QR dans une boucle. Réinitialisez la propriété `code_text` au lieu de créer un nouvel objet à chaque itération.

## Conclusion

You now know how to **generate QR barcode** in Python with Aspose.Barcode, build an extended codetext that mixes plain and ECI segments, and correctly **save barcode image** to disk. The script also shows how to retrieve library version information for troubleshooting.

Les prochaines étapes que vous pourriez explorer incluent :

* Ajouter un logo superposé ou des couleurs personnalisées au code QR.
* Intégrer le code‑barres QR directement dans des PDF avec Aspose.PDF.
* Automatiser la génération par lots pour de grands ensembles de données.

Feel free to experiment with different data payloads, error‑correction levels, and image formats. Happy coding!

## Que devriez‑vous apprendre ensuite ?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Comment générer une image de code QR en Python avec Aspose.Barcode – Guide complet](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Comment générer un code‑barres Code 128 et enregistrer l'image du code‑barres avec Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Comment générer un code‑barres DataMatrix en Python avec Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}