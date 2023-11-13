---
title: Creating an Image with Exact Barcode Only in Java
linktitle: Creating an Image with Exact Barcode Only
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 12
url: /java/barcode-basics/creating-image-exact-barcode-only/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.technical_articles;

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class CreateAnImageWithExactBarcodeOnly {

	public static void main(String[] args) throws IOException {
		// ExStart: CreateAnImageWithExactBarcodeOnly
		String dataDir = "Your Document Directory";
		// Generate the barcode
		BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128);

		// Set the code text
		generator.getParameters().getBarcode().getCodeTextParameters().setTwoDDisplayText("123456");

		// Get bitmap with exact barcode only
		BufferedImage image = generator.generateBarCodeImage();

		// Saving the buffered image
		File outputfile = new File(dataDir + "custombarcode.png");
		ImageIO.write(image, "png", outputfile);
		// ExEnd: CreateAnImageWithExactBarcodeOnly
	}
}

```