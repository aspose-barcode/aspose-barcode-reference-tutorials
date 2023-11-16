---
title: Configuring Wide-Narrow Ratio in Java
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 17
url: /java/barcode-configuration/configuring-wide-narrow-ratio/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode.advanced_features;

import java.io.IOException;


import com.aspose.barcode.generation.BarcodeGenerator;

public class WideNarrowRatio {

	public static void main(String[] args) throws IOException {
		// ExStart: WideNarrowRatio
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		// Instantiate barcode object
		// Create instance of BarcodeGenerator, specify codetext and symbology in the
		// constructor
		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");

		// Set the wide to narrow ratio for the barcode
		generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);

		// Save the image to disk in PNG format
		generator.save(dataDir + "wideNarrowRatio.png");
		// ExEnd: WideNarrowRatio
	}

}

```
