---
title: Configuring Barcode with Segments in Java
linktitle: Configuring Barcode with Segments
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 10
url: /java/barcode-configuration/configuring-barcode-segments/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode.advanced_features;

import java.io.IOException;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class BarcodeWithSegments {

	public static void main(String[] args) throws IOException {
		// TODO Auto-generated method stub
		// ExStart: BarcodeWithSegments

		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.DATABAR_EXPANDED_STACKED,
				"(01)98898765432106(3202)012345(15)991231");

		// Set the column property to define segments per row
		generator.getParameters().getBarcode().getDataBar().setColumns(6);

		// Save the image
		generator.save(dataDir + "6segmets.png");
		// ExEnd: BarcodeWithSegments
	}

}

```