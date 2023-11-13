---
title: Recognizing PDF417 Barcode with Chinese Characters in Java
linktitle: Recognizing PDF417 Barcode with Chinese Characters
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 10
url: /java/multilingual-support/recognizing-pdf417-chinese-characters/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.technical_articles;

import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.examples.Utils;

public class RecognizePdf417BarcodeWithChineseCharacters {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		// ExStart: RecognizePdf417BarcodeWithChineseCharacters
		String dataDir = "Your Document Directory";
		// Load barcode image
		BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);

		// Read barcode
		for (BarCodeResult result : reader.readBarCodes()) {
			// Get byte array and decode
			byte[] bytes = result.getCodeBytes();
			ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
			System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
		}
		// ExEnd: RecognizePdf417BarcodeWithChineseCharacters
	}

}

```
