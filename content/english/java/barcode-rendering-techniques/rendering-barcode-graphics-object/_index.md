---
title: Rendering Barcode to Graphics Object in Java
linktitle: Rendering Barcode to Graphics Object
second_title: Aspose.BarCode Java API
description: 
type: docs
weight: 10
url: /java/barcode-rendering-techniques/rendering-barcode-graphics-object/
---

## Complete Source Code
```java
package com.aspose.barcode.examples.barcode_image.rendering_features;

import java.awt.Dimension;
import java.awt.Frame;
import java.awt.Graphics;
import java.awt.Image;
import java.awt.MediaTracker;
import java.io.File;
import java.io.IOException;

import javax.imageio.ImageIO;

import com.aspose.barcode.examples.Utils;
import com.aspose.barcode.generation.BarcodeGenerator;
//ExStart: RenderBarcodeToGraphicsObject
public class RenderBarcodeToGraphicsObject {
	public static void main(String[] args) {
		// Create frame instance
		Frame f = new Frame();
		// Set frame size
		f.setSize(300, 300);
		// Create and add barcode instance to frame
		f.add(new MyBarCode());
		// Display frame
		f.setVisible(true);
	}
}

class MyBarCode extends java.awt.Canvas {
	public void paint(Graphics g) {
		// The path to the resource directory.
		String dataDir = "Your Document Directory";
		String fileName = dataDir + "barcode.png";
		
		BarcodeGenerator bb = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
		try {
			bb.save(fileName);
		} catch (IOException e1) {
			// TODO Auto-generated catch block
			e1.printStackTrace();
		}
		
		// Load and Draw the image on applet
		MediaTracker tr = new MediaTracker(this);
		
		File sourceimage = new File(fileName);
		Image image;
		try {
			image = ImageIO.read(sourceimage);
			tr.addImage(image, 0);
			g.drawImage(image, 0, 0, this);
		} catch (IOException e) {
			e.printStackTrace();
		}
	}

	public Dimension getPreferredSize() {
		return new Dimension(300, 300);
	}
}
//ExEnd: RenderBarcodeToGraphicsObject
```