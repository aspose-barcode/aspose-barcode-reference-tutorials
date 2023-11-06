---
title: DataMatrix Encoding Mode (ASCII)
linktitle: DataMatrix Encoding Mode (ASCII)
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 13
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2023 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class DataMatrixEncodeModeASCII : TwoDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("DataMatrixEncodeModeASCII:");

            using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
            {
                gen.Parameters.Barcode.XDimension.Pixels = 4;
                //set encode mode to ASCII
                gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
                gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
            }
        }
	}
}
```
