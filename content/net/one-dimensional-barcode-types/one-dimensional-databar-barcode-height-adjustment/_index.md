---
title: One-Dimensional Databar Barcode Height Adjustment
linktitle: One-Dimensional Databar Barcode Height Adjustment
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 17
url: /net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class OneDDatabarBarHeight : OneDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("OneDDatabarBarHeight:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            //set barheight 30 pixels
            gen.Parameters.Barcode.BarHeight.Pixels = 30;
            gen.Save($"{path}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            //set barheight 60 pixels
            gen.Parameters.Barcode.BarHeight.Pixels = 60;
            gen.Save($"{path}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        }
    }
}
```
