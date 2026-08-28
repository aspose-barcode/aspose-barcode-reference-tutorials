---
category: general
date: 2026-08-19
description: Aprenda a gerar código de barras postal em C# usando Aspere.BarCode.
  Este guia passo a passo mostra como gerar código de barras nos formatos Planet e
  RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: pt
lastmod: 2026-08-19
og_description: Gere código de barras postal em C# com Aspose.BarCode. Siga este guia
  para aprender como gerar código de barras para Planet e RM4SCC com dimensões personalizadas.
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: Gerar código de barras postal em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: Como gerar código de barras postal em C# com Aspose.BarCode
url: /pt/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras postal em C# com Aspose.BarCode

Se você precisa **gerar código de barras postal** para aplicações de envio, este guia mostra exatamente como gerar o código de barras usando a biblioteca Aspose.BarCode. Você verá um exemplo completo e executável que cria tanto um código de barras Planet (altura calculada automaticamente) quanto um código de barras RM4SCC com altura de barra explícita.

Gerar código de barras postal é uma necessidade comum para softwares de logística, impressoras de etiquetas automáticas e sistemas de mala direta em massa. Ao final deste tutorial você será capaz de integrar a geração de códigos de barras em qualquer projeto .NET, personalizar a dimensão X e controlar a altura da barra quando o formato padrão permite.

**O que você aprenderá**

* Como configurar o Aspose.BarCode em um projeto C#.  
* Como gerar códigos de barras Planet e RM4SCC.  
* Como ajustar a dimensão X (largura do módulo) e a altura da barra.  
* Como salvar o resultado como imagem PNG.  

Nenhum serviço externo é necessário — tudo roda localmente após você referenciar o pacote NuGet Aspose.BarCode.

## Pré-requisitos

* .NET 6.0 SDK ou superior (o código também funciona com .NET Framework 4.7+).  
* Visual Studio 2022, Visual Studio Code ou qualquer IDE C# de sua preferência.  
* Pacote Aspose.BarCode for .NET – instale via NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Gerar código de barras postal com Aspose.BarCode

As seções a seguir orientam passo a passo, desde a criação dos objetos geradores até a gravação dos arquivos PNG finais.

### Etapa 1: Criar um código de barras Planet (altura automática)

Planet é um código de barras postal usado em muitos países para triagem de correspondência. Quando você cria um código de barras Planet, a biblioteca determina automaticamente a altura ideal da barra com base nos dados codificados.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**Por que isso funciona** – `EncodeTypes.Planet` indica ao Aspose.BarCode que use a simbologia Planet. A propriedade `XDimension` controla a largura da menor barra (o módulo). Como o Planet não exige uma altura fixa, a biblioteca calcula uma altura adequada automaticamente, simplificando o código.

### Etapa 2: Criar um código de barras RM4SCC com altura explícita

RM4SCC é outra simbologia postal que frequentemente requer uma altura de barra específica para compatibilidade com scanners. O código abaixo mostra como definir essa altura manualmente.

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Por que definir a altura** – Alguns scanners postais esperam uma altura mínima de barra. Ao atribuir `BarHeight.Pixels = 100`, você garante que a imagem gerada atenda a esses requisitos. A dimensão X permanece consistente com o código Planet, de modo que ambas as imagens compartilhem a mesma densidade visual.

### Etapa 3: Verificar a saída

Após executar o programa, abra os dois arquivos PNG localizados em `YOUR_DIRECTORY`. Você deverá ver dois códigos de barras distintos:

* `PostalPlanetBarHeightNone.png` – um código Planet com altura calculada automaticamente.  
* `PostalRM4SCCBarHeight100Pixels.png` – um código RM4SCC com altura de barra de 100 pixels.

Ambas as imagens podem ser enviadas diretamente para impressoras de etiquetas ou exibidas em uma aplicação web.

![Imagem gerada de código de barras postal usando Aspose.BarCode](generated-postal-barcode.png)

*Texto alternativo da imagem:* **Imagem gerada de código de barras postal** usando Aspose.BarCode (demonstrando como gerar código de barras postal).

## Como gerar código de barras com dimensões personalizadas (avançado)

Se precisar ajustar outros parâmetros — como margens, posicionamento de texto ou cor — o Aspose.BarCode oferece um rico objeto `Parameters`. A seguir, um exemplo rápido que adiciona um fundo branco e desabilita o texto legível por humanos.

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**Quando usar isso** – Desabilitar o texto legível por humanos é comum em triagens automatizadas onde apenas o padrão legível por máquina importa. Definir uma cor de fundo garante que o código de barras imprima corretamente em mídia transparente.

## Armadilhas comuns e dicas de especialista

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| O código de barras parece esticado | A dimensão X é muito grande em relação ao tamanho da imagem | Mantenha `XDimension.Pixels` entre 2 e 5 para a maioria dos códigos postais |
| O scanner rejeita a imagem | A altura da barra está abaixo do mínimo exigido pelo serviço postal | Use `BarHeight.Pixels` ≥ 80 para RM4SCC, salvo especificação em contrário |
| O tamanho do arquivo PNG é grande | A resolução da imagem está maior que o necessário | Salve como PNG‑8 (`BarCodeImageFormat.Png8`) ou reduza as dimensões em pixels |

**Dica de especialista:** Sempre teste o código de barras gerado com um scanner real antes de colocar em produção. Pequenas diferenças visuais podem afetar a legibilidade.

## Código-fonte completo

Copie todo o bloco abaixo para uma nova aplicação console (`Program.cs`). Ajuste os caminhos de saída para uma pasta onde seu processo tenha permissão de gravação.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

Executar o programa exibe *“Barcodes generated successfully.”* e cria os dois arquivos PNG no diretório de trabalho do executável.

## Conclusão

Agora você sabe como **gerar código de barras postal** em C# com Aspose.BarCode, cobrindo tanto códigos Planet de altura automática quanto códigos RM4SCC de altura fixa. O guia também mostrou **como gerar código de barras** com dimensão X personalizada, altura de barra e opções visuais, proporcionando uma base sólida para qualquer projeto de automação de correspondência.

Próximos passos que você pode explorar:

* Integrar os PNGs gerados em uma fatura PDF usando Aspose.PDF.  
* Alterar o formato de saída para SVG para gráficos vetoriais escaláveis.  
* Usar a classe `BarcodeReader` para verificar os dados codificados programaticamente.

Sinta-se à vontade para experimentar diferentes simbologias (por exemplo, `EncodeTypes.Postnet`) e compartilhar seus resultados com a comunidade. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}