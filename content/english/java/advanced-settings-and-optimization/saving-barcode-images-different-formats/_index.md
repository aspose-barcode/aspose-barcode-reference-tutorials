---
title: Saving Barcode Images to Different Formats in Java
linktitle: Saving Barcode Images to Different Formats
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 13
url: /java/advanced-settings-and-optimization/saving-barcode-images-different-formats/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.utility_features;

import java.io.IOException;

import com.aspose.barcode.*;
import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class SaveBarcodeImagesToDifferentFormats {
	public static void main(String[] args) throws IOException {
		// ExStart: SaveBarcodeImagesToDifferentFormats
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		// Instantiate barcode object, Set the symbology type to code128 and Set the
		// Code text for the barcode
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "1234567");

		// Save the image to your system and set its image format to Jpeg
		bb.save(dataDir + "barcode-image-format.jpg", BarCodeImageFormat.JPEG);
		// ExEnd: SaveBarcodeImagesToDifferentFormats
	}
}

```
