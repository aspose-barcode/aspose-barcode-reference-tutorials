---
title: Saving Barcode Image to Streams in Java
linktitle: Saving Barcode Image to Streams in Java
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 14
url: /java/advanced-settings-and-optimization/saving-barcode-image-streams-java/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.utility_features;

import java.io.ByteArrayOutputStream;
import java.io.IOException;

import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;

public class SaveBarcodeImageToStreams {

	public static void main(String[] args) throws IOException {
		// ExStart: SaveBarcodeImageToStreams
		BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "123456");
		ByteArrayOutputStream outStream = new ByteArrayOutputStream();
		generator.save(outStream, BarCodeImageFormat.JPEG);
		// ExEnd: SaveBarcodeImageToStreams
	}
}

```
