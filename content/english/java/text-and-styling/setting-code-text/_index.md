---
title: Setting Code Text in Java
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 13
url: /java/text-and-styling/setting-code-text/
---

## Complete Source Code
```java
//////////////////////////////////////////////////////////////////////////
// Copyright 2001-2015 Aspose Pty Ltd. All Rights Reserved.
//
// This file is part of Aspose.BarCode. The source code in this file
// is only intended as a supplement to the documentation, and is provided
// "as is", without warranty of any kind, either expressed or implied.
//////////////////////////////////////////////////////////////////////////

package com.aspose.barcode.examples.barcode.basic_features;

import java.io.IOException;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;

public class SetCodeText {
	public static void main(String[] args) throws IOException {
		// ExStart: SetCodeText
		// The path to the resource directory.
		String dataDir = "Your Document Directory";

		// Create instance of BarcodeGenerator, specify codetext and symbology in the
		// constructor
		BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");

		// Set the width of the bars to 0.5 millimeter
		generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);

		// Save the barcode image to file
		generator.save(dataDir + "setCodeText.jpg");
		// ExEnd: SetCodeText
	}
}

```
