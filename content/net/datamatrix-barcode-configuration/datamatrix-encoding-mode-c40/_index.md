---
title: DataMatrix Encoding Mode (C40)
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 16
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2023 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class DataMatrixEncodeModeC40 : TwoDBase
    {
		public static void Run()
        {
            string path = GetFolder();
            System.Console.WriteLine("DataMatrixEncodeModeC40:");

            using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
            {
                gen.Parameters.Barcode.XDimension.Pixels = 6;
                //set encode mode to C40
                gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
                gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
            }
        }
	}
}
```
