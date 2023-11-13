---
title: Configuring Barcode Orientation in Java
linktitle: Configuring Barcode Orientation
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 16
url: /java/advanced-settings-and-optimization/configuring-barcode-orientation/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_recognition.advanced_features;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.examples.ApplyALicense;
import com.aspose.barcode.examples.Utils;

public class BarcodeOrientation {

	public static void main(String[] args) throws Exception {
		ApplyALicense.applyALicense();
		// ExStart: BarcodeOrientation
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		// Read code39 barcode from image
		String image = dataDir + "code39Extended.jpg";
		BarCodeReader reader = new BarCodeReader(image, DecodeType.CODE_39_STANDARD);

		// Barcode orientation is detected automatically

		// Try to recognize all possible barcodes in the image
		for (BarCodeResult result : reader.readBarCodes()) {
			System.out.println("BarCode CodeText: " + result.getCodeText());
			System.out.println("BarCode CodeType: " + result.getCodeTypeName());
		}
		// ExEnd: BarcodeOrientation
	}

}

```
