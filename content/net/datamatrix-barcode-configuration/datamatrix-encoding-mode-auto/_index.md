---
title: DataMatrix Encoding Mode (Auto)
linktitle: DataMatrix Encoding Mode (Auto)
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 14
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2023 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class DataMatrixEncodeModeAuto : TwoDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("DataMatrixEncodeModeAuto:");

            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
            {
                generator.Parameters.Barcode.XDimension.Pixels = 4;
                //set encode mode to Auto
                generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
                generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
                Bitmap bitmap = generator.GenerateBarCodeImage();
                using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
                {
                    reader.ReadBarCodes();
                    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
                }
            }
        }
	}
}
```
