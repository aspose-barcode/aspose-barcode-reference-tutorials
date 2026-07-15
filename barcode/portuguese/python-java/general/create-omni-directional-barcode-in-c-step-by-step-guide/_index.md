---
category: general
date: 2026-07-15
description: Crie um código de barras omnidirecional em C# rapidamente com Aspose.BarCode
  – aprenda como gerar código de barras em C# com altura de barra ajustável e dimensão
  X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: pt
lastmod: 2026-07-15
og_description: Crie código de barras omnidirecional em C# com Aspose.BarCode. Domine
  como gerar código de barras em C# ajustando XDimension e BarHeight para resultados
  perfeitos.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: crie código de barras omnidirecional em C# – Guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Criar código de barras omnidirecional em C# – Guia passo a passo
url: /pt/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# criar código de barras omni‑directional em C# – Guia passo a passo

Já se perguntou como gerar um código de barras C# que esteja em conformidade com a simbologia GS1 DataBar Omni‑Directional? Você não está sozinho. Neste tutorial, vamos **criar código de barras omni‑directional** do zero, ajustar a X‑dimension e brincar com a altura das barras — tudo usando a biblioteca Aspose.BarCode.

Vamos percorrer um cenário real: você precisa de um código de barras compacto e de alta densidade para um rótulo de varejo, e deseja controle total sobre seu tamanho visual. Ao final, você terá dois arquivos PNG — um com altura de barra de 30 px e outro com 60 px — prontos para serem inseridos em qualquer fluxo de impressão.

## Pré-requisitos

- .NET 6 (ou qualquer runtime .NET recente) instalado na sua máquina.  
- Visual Studio 2022 ou VS Code — sua IDE favorita serve.  
- Um pacote NuGet gratuito Aspose.BarCode for .NET (`Aspose.BarCode`).

Nenhuma outra dependência é necessária. Se você nunca usou o NuGet antes, basta abrir o Package Manager Console e executar:

```powershell
Install-Package Aspose.BarCode
```

## criar código de barras omni‑directional – Entendendo o básico

A simbologia **GS1 DataBar Omni‑Directional** foi projetada para leitura em qualquer orientação, tornando‑a perfeita para rótulos de borda de prateleira. Quando você chama `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, a biblioteca faz o trabalho pesado: codifica os dados, aplica as regras da simbologia e prepara uma imagem raster.

> **Dica profissional:** Sempre envolva os dados brutos no formato apropriado de Identificador de Aplicação (AI), por exemplo `"(01)12345678901231"` para um GTIN‑14. Isso informa ao scanner o que os dígitos representam.

## Etapa 1 – Configurar o Gerador de Código de Barras (how to generate barcode c#)

Primeiro criamos o objeto gerador. Este é a pedra angular de **how to generate barcode c#** com Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

O valor enum `EncodeTypes.DatabarOmniDirectional` indica ao motor qual simbologia usar. O segundo argumento é a string de dados brutos, já envolvida no AI GTIN.

## Etapa 2 – Ajustar a X‑Dimension (barcode XDimension)

A **barcode XDimension** controla a largura da barra mais fina. Um valor de 2 px é um bom equilíbrio entre legibilidade e compactação para a maioria das impressoras de rótulos.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se precisar de um aspecto mais fino ou mais grosso, basta mudar o número. Lembre‑se: a X‑dimension é a unidade fundamental; todas as outras larguras de barra são múltiplos desse valor.

## Etapa 3 – Criar a Primeira Imagem com Altura de Barra de 30 px (barcode BarHeight)

Agora definimos a **barcode BarHeight** para 30 px e salvamos a imagem. Isso produz um código de barras de tamanho modesto que se encaixa bem em um rótulo padrão.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

O método `Save` grava um arquivo PNG no disco. Você pode trocar por `BarCodeImageFormat.Jpeg` se preferir saída JPEG.

## Etapa 4 – Aumentar a Altura da Barra para 60 px para Rótulos Maiores (barcode BarHeight)

Às vezes, um código de barras maior é necessário — talvez para um rótulo de prateleira que fica mais distante do scanner. Vamos dobrar a altura.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Observe que **não** precisamos recriar o gerador; apenas ajustamos o parâmetro e reutilizamos o mesmo objeto. Isso economiza memória e mantém o código organizado.

## Etapa 5 – Salvar a Segunda Imagem (how to generate barcode c#)

Finalmente, salvamos o segundo PNG. Agora você tem dois arquivos que diferem apenas na altura da barra.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Saída esperada

- `DatabarBarHeight30Pixels.png` – um código de barras omni‑directional de 30 px de altura.  
- `DatabarBarHeight60Pixels.png` – os mesmos dados, mas com um código de barras de 60 px de altura.

Abra os arquivos em qualquer visualizador de imagens; você verá barras nítidas e escaneáveis que respeitam a especificação GS1 DataBar Omni‑Directional.

## Perguntas Frequentes & Casos de Borda

### E se eu precisar de uma X‑dimension diferente?

Basta atribuir um novo valor antes de chamar `Save`. Para impressão ultra‑alta densidade, você pode reduzir para 1 px, mas teste primeiro com seu scanner — alguns dispositivos têm dificuldade com barras menores que 2 px.

### Posso adicionar texto legível por humanos abaixo do código de barras?

Sim. Defina `barcodeGenerator.Parameters.Barcode.CodeText` para uma string e, opcionalmente, ajuste `barcodeGenerator.Parameters.Barcode.CodeLocation` para `BarCodeTextLocation.Below`. Isso é útil em ambientes de varejo onde o GTIN numérico deve ser visível.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### O PNG é o melhor formato para impressão?

PNG é sem perdas, o que preserva as bordas nítidas necessárias para scanners de códigos de barras. Se o seu sistema downstream espera um formato diferente (TIFF, BMP), basta mudar o enum `BarCodeImageFormat`.

## Exemplo Completo em Funcionamento (create omni-directional barcode)

Abaixo está o programa completo, pronto para executar. Copie‑e‑cole em um novo projeto de console e pressione **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Execute o programa, verifique a pasta de saída, e você verá os dois arquivos PNG exatamente como descrito.

## Recapitulação

Mostramos como **how to generate barcode C#** código que cria um **create omni-directional barcode** usando Aspose.BarCode. Ao ajustar a **barcode XDimension** e a **barcode BarHeight**, você obtém controle fino sobre o tamanho visual sem sacrificar a confiabilidade da leitura.

## O que vem a seguir?

- Experimente outras configurações da **GS1 DataBar Omni-Directional**, como `Color` ou `Margin`.  
- Combine múltiplos códigos de barras em uma única tela usando `Graphics` para designs de rótulos complexos.  
- Integre o gerador em uma API web para que sua plataforma de e‑commerce possa gerar códigos de barras sob demanda.

Tem alguma variação que gostaria de compartilhar? Deixe um comentário, e vamos continuar a conversa. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras – Configuração Code 39 com Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Como criar zona silenciosa de código de barras para ITF-14 usando Aspose.BarCode para .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Como criar zona silenciosa de código de barras para Code 16K usando Aspose.BarCode para .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}