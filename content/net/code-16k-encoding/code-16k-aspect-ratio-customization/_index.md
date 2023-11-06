---
title: Code 16K Aspect Ratio Customization
linktitle: Code 16K Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 10
url: /net/code-16k-encoding/code-16k-aspect-ratio-customization/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class Code16KAspectRatio : OneDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine("Code16KAspectRatio:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code16K, "Aspose.Barcode");
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            //set Code 16K aspect ratio 10
            gen.Parameters.Barcode.Code16K.AspectRatio = 10;
            gen.Save($"{path}Code16KAspectRatio10.png", BarCodeImageFormat.Png);
            //set Code 16K aspect ratio 20
            gen.Parameters.Barcode.Code16K.AspectRatio = 20;
            gen.Save($"{path}Code16KAspectRatio20.png", BarCodeImageFormat.Png);
        }
    }
}
```
