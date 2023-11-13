---
title: Detecting Barcode Orientation in Java
linktitle: Detecting Barcode Orientation in Java
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 13
url: /java/barcode-basics/detecting-barcode-orientation-java/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.technical_articles;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

public class DetectOrientation {

	public static void main(String[] args) {
		// ExStart: DetectOrientation
		// Instantiate BarCodeReader object
		BarCodeReader reader = new BarCodeReader("rotatedbarcode.jpg", DecodeType.CODE_128);
		// read Code128 bar code
		for (BarCodeResult result : reader.readBarCodes()) {
			// detect bar code orientation
			System.out.println("Rotaion Angle: " +  result.getRegion().getAngle());
		}
		// ExEnd: DetectOrientation
	}

}

```
