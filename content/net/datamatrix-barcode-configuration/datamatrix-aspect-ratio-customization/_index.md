---
title: DataMatrix Aspect Ratio Customization
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 10
url: /net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2023 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class DataMatrixAspectRatio : TwoDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("DataMatrixAspectRatio:");

            using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
            {
                gen.Parameters.Barcode.XDimension.Pixels = 4;
                //set aspect ratio 1
                gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
                gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);
                //set aspect ratio 0.5
                gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
                gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
            }
        }
    }
}
```
