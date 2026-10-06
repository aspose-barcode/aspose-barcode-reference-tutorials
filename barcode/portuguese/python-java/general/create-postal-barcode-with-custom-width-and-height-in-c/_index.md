---
category: general
date: 2026-09-16
description: Crie código de barras postal em C# e aprenda como definir a largura e
  alterar a altura do código de barras para uma leitura perfeita.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: pt
lastmod: 2026-09-16
og_description: Crie código de barras postal em C# com este guia passo a passo, mostrando
  como definir a largura e alterar a altura do código de barras para uma leitura postal
  confiável.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Criar código de barras postal com largura e altura personalizadas em C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Criar código de barras postal com largura e altura personalizadas em C#
url: /pt/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras postal com largura e altura personalizadas em C#

Se você precisa **criar imagens de código de barras postal** em C#, este guia mostra como gerar códigos de barras Planet e RM4SCC com dimensões exatas. Ao final das duas primeiras frases você saberá as chamadas de API exatas para **definir largura** e **alterar a altura do código de barras**, permitindo produzir códigos escaneáveis que atendem às especificações dos serviços postais.

Você aprenderá:
* Como instanciar um gerador de código de barras para os formatos Planet e RM4SCC.  
* A propriedade exata para **definir largura** (X‑dimension) em pixels.  
* Como **alterar a altura do código de barras** para um tipo específico de código.  
* Onde os arquivos PNG gerados são salvos e como eles se apresentam.

O único pré‑requisito é uma referência à biblioteca `Aspose.BarCode` (ou similar) que fornece a classe `BarcodeGenerator`. Nenhum pacote NuGet adicional é necessário além do próprio SDK de código de barras.

---

## Criar código de barras postal com dimensões personalizadas

Primeiro, adicione as diretivas `using` necessárias e crie um programa de console simples. O exemplo completo e executável é apresentado após a explicação passo a passo.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Por que isso funciona:**  
* `EncodeTypes.Planet` e `EncodeTypes.RM4SCC` informam ao gerador qual padrão postal seguir.  
* `XDimension.Pixels` controla a **largura** de cada módulo do código de barras (o menor elemento preto/branco).  
* `BarHeight.Pixels` permite **alterar a altura do código de barras** para formatos que não calculam a altura automaticamente, como RM4SCC.

Ao executar o programa são criados dois arquivos PNG no diretório de trabalho do executável:
* `PostalPlanetBarWidth4.png` – um código de barras Planet com largura de módulo de 4 px.  
* `PostalRM4SCCHeight100.png` – um código de barras RM4SCC com largura de 4 px e altura fixa de 100 px.

---

## Como definir a largura para um código de barras postal

A etapa **como definir a largura** é a mesma para todos os formatos postais suportados:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` é um inteiro que representa o tamanho em pixels de um único módulo.  
* Um valor típico para códigos de barras postais é **4 px**, mas você pode aumentá‑lo para impressão de alta resolução.  

**Dica profissional:** Ao imprimir em uma impressora controlada por DPI, multiplique a largura em pixels pelo fator DPI da impressora para manter as dimensões físicas.

---

## Alterar a altura do código de barras para o postal RM4SCC

Somente um subconjunto de simbologias postais (por exemplo, RM4SCC) requer uma altura explícita. Use a propriedade **alterar altura do código de barras**:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` é a altura total da imagem do código de barras, não a altura de um único módulo.  
* Definir `BarHeight` para **100 px** gera um código de barras alto, facilmente legível, que cumpre muitas diretrizes de serviços postais.

**Caso extremo:** Se você definir uma altura muito pequena, o código de barras pode ficar ilegível para os scanners. Sempre teste com uma impressão física antes de implantar em grande escala.

---

## Arquivo fonte completo para copiar‑e‑colar

Abaixo está o programa inteiro que você pode copiar para um novo projeto de console. Nenhum outro código é necessário.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Saída esperada** (console):

```
Both postal barcodes have been saved.
```

E dois arquivos PNG aparecem na pasta de saída, cada um exibindo um código de barras postal claro, pronto para impressão ou incorporação.

---

## Perguntas comuns e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| *E se eu precisar de uma X‑dimension diferente para cada código de barras?* | Crie instâncias separadas de `BarcodeGenerator` e atribua um valor distinto de `XDimension.Pixels` antes de chamar `Save`. |
| *Por que o código de barras Planet ignora `BarHeight`?* | O formato Planet calcula automaticamente a altura a partir da X‑dimension, portanto definir `BarHeight` não tem efeito. |
| *Posso gerar SVG em vez de PNG?* | Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg`. |
| *E se a imagem ficar borrada ao imprimir?* | Aumente a X‑dimension (por exemplo, para 6 px) e gere a imagem em DPI mais alto usando as configurações de `Resolution` no gerador. |

---

## Conclusão

Agora você sabe como **criar imagens de código de barras postal** em C# e definir com precisão a **largura** e **alterar a altura** usando a API `BarcodeGenerator`. O exemplo cobre tanto formatos com dimensionamento automático (Planet) quanto formatos com dimensionamento manual (RM4SCC), proporcionando uma base sólida para qualquer projeto de automação postal.

Em seguida, você pode explorar:
* Adicionar texto legível por humanos abaixo do código de barras (`CodeTextParameters`).  
* Exportar para outros formatos como SVG ou PDF para impressão vetorial.  
* Integrar o gerador em uma API web para servir códigos de barras sob demanda.

Sinta‑se à vontade para experimentar diferentes dimensões, codificações e formatos de saída para adequar ao seu fluxo de trabalho de envio. Boa codificação!


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}