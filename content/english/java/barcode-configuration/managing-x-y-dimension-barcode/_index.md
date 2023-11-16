---
title: Managing X and Y Dimensions of Barcode in Java
linktitle: Managing X and Y Dimensions of Barcode
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 13
url: /java/barcode-configuration/managing-x-y-dimension-barcode/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode.advanced_features;

import java.io.IOException;


import com.aspose.barcode.generation.BarcodeGenerator;

public class ManageXAndYDimension {

	public static void main(String[] args) throws IOException {
		ManageXAndYDimension.setXDimension();
		ManageXAndYDimension.setYDimension();
	}

	public static void setXDimension() throws IOException {
		// ExStart: setXDimension
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");

		// Set the x-dimension for the bars of the barcode
		generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);

		// Save the Barcode image to file
		generator.save(dataDir + "xDimention.jpg");
		// ExEnd: setXDimension
	}

	public static void setYDimension() throws IOException {
		// ExStart: setYDimension
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.PDF_417, "12345678");

		// Set the Y-Dimension for the bars of the barcode
		generator.getParameters().getBarcode().getBarHeight().setMillimeters(4);

		// Save the Barcode image to file
		generator.save(dataDir + "yDimention.jpg");
		// ExEnd: setYDimension
	}

}

```
