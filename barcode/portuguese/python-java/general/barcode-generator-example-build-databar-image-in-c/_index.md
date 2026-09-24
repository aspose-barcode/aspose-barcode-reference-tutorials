---
category: general
date: 2026-07-18
description: Exemplo de gerador de código de barras mostrando como definir dimensões
  e gerar uma imagem de código de barras DataBar Stacked Omni‑Directional em C#. Aprenda
  rapidamente os tipos de codificação de código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: pt
lastmod: 2026-07-18
og_description: O exemplo de gerador de código de barras orienta você sobre como definir
  dimensões, escolher tipos de codificação de código de barras e criar projetos de
  imagem de código de barras em C# com o mínimo de código.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Exemplo de Gerador de Código de Barras – Criação Rápida de Imagem DataBar
  em C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Exemplo de Gerador de Código de Barras – Criar Imagem DataBar em C#
url: /pt/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exemplo de Gerador de Código de Barras – Criar Imagem DataBar em C#

Já precisou de um **exemplo de gerador de código de barras** que realmente imprima um código de barras do mundo real sem fazer você perder a cabeça? Você não está sozinho. A maioria dos desenvolvedores bate em um muro quando tenta descobrir **como definir dimensões** para um código de barras DataBar Stacked Omni‑Directional, especialmente quando a documentação está enterrada sob camadas de jargão.

Neste tutorial vamos percorrer um programa C# completo, pronto‑para‑executar, que mostra **como gerar imagens databar**, escolhe os **tipos de codificação de código de barras** corretos e, finalmente, **cria arquivos de imagem de código de barras c#** que você pode inserir em qualquer projeto. Sem enrolação — apenas o código que você pode copiar‑colar, mais o raciocínio por trás de cada linha.

## O que Você Precisa

- **.NET 6** (ou qualquer versão recente do .NET) – a API que usamos tem alvo .NET Standard, então funciona também no .NET Framework.  
- **Aspose.BarCode for .NET** – a biblioteca que fornece `BarcodeGenerator`. Você pode obtê‑la no NuGet com `Install-Package Aspose.BarCode`.  
- Um **IDE C#** – Visual Studio, Rider ou VS Code servem.  
- Uma pasta no disco onde os arquivos PNG serão salvos (o código cria `DatabarAspectRatio15.png` e `DatabarAspectRatio30.png`).

Tudo pronto? Ótimo — vamos começar.

## Exemplo de Gerador de Código de Barras – Inicializar o Gerador

Primeiro passo: precisamos de uma instância de `BarcodeGenerator` configurada para a simbologia **DataBar Stacked Omni‑Directional**. Este é o **tipo de codificação de código de barras** com o qual vamos trabalhar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Por que isso importa:** `EncodeTypes.DatabarStackedOmniDirectional` indica ao Aspose exatamente qual simbologia renderizar. Se você escolher o tipo errado, o scanner não reconhecerá o código de barras, não importa o quão bonito a imagem esteja.

## Como Definir Dimensões para o Código de Barras

A legibilidade de um código de barras depende da sua **X‑dimension** (a largura da barra mais estreita). Na maioria dos casos, um valor de 2 pixels funciona bem, mas você pode ajustá‑lo conforme sua impressora ou tela.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dica de especialista:** Se algum dia você se perguntar **como definir dimensões** para outra família de códigos de barras, a mesma cadeia de propriedades (`Parameters.Barcode.XDimension`) se aplica — basta mudar o valor de `Pixels`.

## Como Gerar Código de Barras DataBar Stacked Omni‑Directional

Agora que o gerador está pronto, vamos brincar com a propriedade **aspect ratio**. Ela controla a relação altura‑largura do DataBar, permitindo que você produza um símbolo curto e quadrado ou um alto e estreito.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **O que está acontecendo?** `AspectRatio = 15` indica ao motor que as barras devem ser 15 vezes mais altas que largas. O PNG resultante é salvo ao lado do seu executável.

## Criar Imagem de Código de Barras C# – Alterando a Proporção

Vamos provar a flexibilidade trocando a proporção para 30 e salvando um segundo arquivo.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Ao executar o programa, você terá dois arquivos PNG:

| Arquivo | Proporção | Tamanho Aproximado |
|---------|-----------|--------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Abra-os em qualquer visualizador de imagens — você deverá ver símbolos DataBar limpos e legíveis.

## Visão Geral dos Tipos de Codificação de Código de Barras (Opcional, mas Útil)

Se você tem curiosidade sobre outros **tipos de codificação de código de barras** suportados pelo Aspose, aqui está um cheat‑sheet rápido:

| Enum EncodeTypes | Descrição |
|------------------|-----------|
| `EncodeTypes.Code128` | Alfanumérico de alta densidade |
| `EncodeTypes.QR` | Código matricial 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar para varejo |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Nosso foco** – compacto, omnidirecional |

Conhecer o enum correto economiza muito tempo de tentativa‑e‑erro quando você troca de projeto.

## Armadilhas Comuns & Como Evitá‑las

- **Pacote NuGet ausente** – O código não compila sem `Aspose.BarCode`. Execute `dotnet add package Aspose.BarCode` primeiro.  
- **Caminho de arquivo errado** – Se usar um caminho absoluto, verifique as barras invertidas (`\\`) no Windows. Caminhos relativos (como mostrado) mantêm a portabilidade.  
- **Proporção extrema** – Proporções acima de 50 podem deixar o código de barras alto demais para scanners típicos. Mantenha entre 15‑30 para a maioria dos casos de uso.

## Código Fonte Completo (Pronto para Copiar e Colar)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Execute o programa (`dotnet run` ou pressione **F5** no Visual Studio) e você verá a mensagem no console confirmando que os arquivos foram gravados no disco.

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Exemplo de saída do gerador de código de barras mostrando DataBar com proporção 15"}

## Conclusão

Acabamos de concluir um **exemplo de gerador de código de barras** que demonstra **como definir dimensões**, escolhe os **tipos de codificação de código de barras** corretos e, finalmente, **cria arquivos de imagem de código de barras c#** que você pode incorporar em qualquer lugar. O código é pequeno, os conceitos são claros como cristal, e agora você tem uma base sólida para expandir a solução — talvez adicionando legendas de texto, girando a imagem ou mudando para outra simbologia.

### Próximos Passos?

- Experimente **diferentes X‑dimensions** para ver como a tolerância do scanner muda.  
- Teste outros **EncodeTypes** como `Code128` ou `QR` para ampliar seu conjunto de ferramentas.  
- Automatize a geração em lote: faça um loop sobre um CSV de IDs de produto e gere um PNG para cada um.

Se encontrar algum problema, deixe um comentário abaixo ou consulte a documentação do Aspose.BarCode — ela está repleta de exemplos que complementam o que abordamos aqui.

Feliz codificação, e que seus códigos de barras sempre sejam lidos na primeira tentativa!

## O que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}