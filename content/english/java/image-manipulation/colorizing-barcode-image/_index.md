---
title: Colorizing Barcode Image in Java
linktitle: Colorizing Barcode Image
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 13
url: /java/image-manipulation/colorizing-barcode-image/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.basic_features;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.awt.*;
import java.io.IOException;

public class ColorizeBarcodeImage {
    public static void main(String[] args) throws IOException {
		//ExStart: ColorizeBarcodeImage
		// The path to the resource directory.
		String dataDir = "Your Document Directory";
		
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128,"1234567");
		
		//Set background color of the barcode
		bb.getParameters().setBackColor(Color.YELLOW);
		
		//Set the foreground color of the barcode
		bb.getParameters().getBarcode().setBarColor(Color.BLUE);
		
		//Set border's color
		bb.getParameters().getBorder().setColor(Color.RED);
		
		//Set the code text's color
		bb.getParameters().getBarcode().getCodeTextParameters().setColor(Color.RED);
		
		// Save the image
		bb.save(dataDir + "colorizeBarcode.png");
		//ExEnd: ColorizeBarcodeImage
    }
}

```
