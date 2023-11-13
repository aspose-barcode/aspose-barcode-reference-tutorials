---
title: Getting All Possible 1D Barcodes from an Image in Java
linktitle: Getting All Possible 1D Barcodes from an Image in Java
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 20
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image-java/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_recognition.advanced_features;

import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.examples.ApplyALicense;
import com.aspose.barcode.examples.Utils;

public class GetAllPossible1DBarcodesFromAnImage {

	public static void main(String[] args) throws Exception {
		ApplyALicense.applyALicense();
		
		// The path to the resource directory.
		String dataDir = Utils.getDataDir(GetAllPossible1DBarcodesFromAnImage.class)
				+ "BarcodeReader/advanced_features/";
		
		// ExStart: GetAllPossible1DBarcodesFromAnImage
		// Initialize the BarCodeReader object
		BarCodeReader reader = new BarCodeReader(dataDir + "MultipleBarcodes.png", DecodeType.CODE_128);

		// Now get all possible barcodes
		int iCount = 0;
		for (BarCodeResult result : reader.readBarCodes()) {
			// Display code text, symbology, detected angle, recognition percentage of the
			// barcode
			System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
					+ " Recognition percentage: " + result.getRegion().getAngle());

			// Display x and y coordinates of barcode detected
			Point[] point = result.getRegion().getPoints();

			System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
			System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
			System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
			System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

			iCount = iCount + 1;
		}
		// ExEnd: GetAllPossible1DBarcodesFromAnImage
	}

}

```
