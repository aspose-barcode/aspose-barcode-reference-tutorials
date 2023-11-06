---
title: One-Dimensional Databar 2D Component Configuration
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 15
url: /net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class OneDDatabar2DComponent : OneDBase
    {
		public static void Run()
        {
            string path = GetFolder();
            System.Console.WriteLine("OneDDatabar2DComponent:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            //disable 2D component flag
            gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
            //enable 2D component flag
            gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
        }
    }
}
```
