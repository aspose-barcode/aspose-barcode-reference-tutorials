---
title: Supplementing Data in Java
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 16
url: /java/barcode-configuration/supplementing-data/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode.advanced_features;

import java.io.IOException;


import com.aspose.barcode.generation.BarcodeGenerator;

public class SupplementData {

	public static void main(String[] args) throws IOException {
		// ExStart: SupplementData

		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		// Create instance of BarcodeGenerator, specify codetext and symbology in the
		// constructor
		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.EAN_13, "123456789123");

		// Set the supplement data (5 Digit)
		generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");

		// Set space between the supplemental barcode and main barcode
		generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);

		// Save the Barcode image to file
		generator.save(dataDir + "supplementData.jpg");
		// ExEnd: SupplementData
	}

}

```
