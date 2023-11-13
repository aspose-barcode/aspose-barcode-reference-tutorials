---
title: Adjusting Image Quality for Barcode in Java
linktitle: Adjusting Image Quality for Barcode
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 12
url: /java/image-manipulation/adjusting-image-quality-barcode/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.basic_features;

import java.io.IOException;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class BarcodeImageQuality {
    public static void main(String[] args) throws IOException {
		//ExStart: BarcodeImageQuality
		// The path to the resource directory.
		String dataDir = "Your Document Directory";
		
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128,"1234567");
		
		bb.getParameters().setResolution(400);
		
		// Save the image
		bb.save(dataDir + "barcode-image-quality.jpg");
		//ExEnd: BarcodeImageQuality
    }
}

```