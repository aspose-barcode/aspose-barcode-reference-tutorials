---
title: Rendering Barcode to Image Instance in Java
linktitle: Rendering Barcode to Image Instance
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 11
url: /java/barcode-rendering-techniques/rendering-barcode-image-instance/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.rendering_features;

import java.awt.Image;

import com.aspose.barcode.generation.BarcodeGenerator;

public class RenderBarcodeToImageInstance {

	public static void main(String[] args) {
		//ExStart: RenderBarcodeToImageInstance
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
		
		// Generate bar code image
		Image image = bb.generateBarCodeImage();
		//ExEnd: RenderBarcodeToImageInstance
	}

}

```
