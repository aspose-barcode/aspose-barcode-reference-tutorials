---
title: GS1 Coupon UPC-A Code 128 Encoding
linktitle: GS1 Coupon UPC-A Code 128 Encoding
second_title: Aspose.BarCode .NET API
description: 
type: docs
weight: 12
url: /net/gs1-barcode-encoding/gs1-coupon-upc-a-code-128-encoding/
---

## Complete Source Code
```csharp
//Copyright(c) 2001-2021 Aspose Pty Ltd.All rights reserved.
//https://github.com/aspose-barcode/Aspose.BarCode-for-.NET
using Aspose.BarCode.Generation;

namespace Aspose.BarCode.Examples.CSharp.BarcodeGeneration
{
    internal class Gs1CouponUpcaCode128 : OneDBase
    {
		public static void Run()
        {
            string path = "Your Directory Path";
            System.Console.WriteLine(" Gs1CouponUpcaCode128:");

            BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1Code128Coupon, "123456789012(8110)ASPOSE");
            gen.Parameters.Barcode.XDimension.Pixels = 2;
            gen.Save($"{path}Gs1CouponUpcaCode128.png", BarCodeImageFormat.Png);
        }
	}
}
```
