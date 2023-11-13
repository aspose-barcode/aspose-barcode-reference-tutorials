---
title: Setting Margins for Barcode Image in Java
linktitle: Setting Margins for Barcode Image
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 11
url: /java/image-manipulation/setting-margins-barcode-image/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.basic_features;

import java.io.IOException;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class BarcodeImageMargins {
    
	public static void main(String[] args) throws IOException {
		//ExStart: BarcodeImageMargins
		// The path to the resource directory.
		String dataDir = "Your Document Directory";
		
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "1234567");
		
		//Set border margins for Top, Right, Left and Bottom
		bb.getParameters().getBarcode().getPadding().getTop().setPixels(2f);
		bb.getParameters().getBarcode().getPadding().getRight().setPixels(2f);
		bb.getParameters().getBarcode().getPadding().getLeft().setPixels(2f);
		bb.getParameters().getBarcode().getPadding().getBottom().setPixels(2f);
		
		// Save the image
		bb.save(dataDir + "barcode-image-margins.jpg");
		//ExEnd: BarcodeImageMargins
    }
}

```
