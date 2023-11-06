---
title: One-Dimensional Code 128 Configuration
linktitle: One-Dimensional Code 128 Configuration
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 10
url: /net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class OneCSCode128 : OneDBase
    {
		public static void Run()
        {
            string path = GetFolder();
            System.Console.WriteLine("OneCSCode128:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
            //do not show checksum
            gen.Parameters.Barcode.ChecksumAlwaysShow = false;
            gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
            //show checksum
            gen.Parameters.Barcode.ChecksumAlwaysShow = true;
            gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
        }
    }
}
```
