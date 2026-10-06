---
category: general
date: 2026-10-05
description: Crie PNG de código de barras em C# e aprenda como definir a proporção
  de aspecto 15 para códigos de barras DataBar empilhados omnidirecionais.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: pt
lastmod: 2026-10-05
og_description: Crie PNG de código de barras em C# e descubra como definir a proporção
  de aspecto 15 para códigos de barras DataBar empilhados omnidirecionais em poucos
  passos.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Criar PNG de código de barras em C# – tutorial para definir proporção 15
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Como criar um PNG de código de barras com proporção personalizada em C#
url: /pt/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar barcode PNG com uma proporção de aspecto personalizada em C#

Se você precisa **criar barcode PNG** em C#, este guia mostra **como definir a proporção de aspecto** 15 para um barcode DataBar empilhado omnidirecional. Vamos percorrer cada chamada de API, explicar por que a proporção de aspecto importa e fornecer um exemplo completo e executável que você pode inserir em qualquer projeto .NET.

Gerar uma imagem de barcode é uma necessidade comum para sistemas de inventário, etiquetas de envio e aplicações de ponto de venda no varejo. Ao final deste tutorial você terá um arquivo PNG que atende às especificações visuais exatas exigidas pelo seu parceiro de negócios. Sem ferramentas externas, sem edição manual de imagens — apenas código.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior (o exemplo usa .NET 6, mas funciona com .NET 5+)
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)
* O pacote **Aspose.BarCode for .NET** NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permissão de escrita na pasta onde você deseja salvar o arquivo PNG

Esses requisitos são mínimos; o mesmo código funciona em .NET Core, .NET Framework ou em uma aplicação console.

## Criar barcode PNG com Aspose.BarCode

O primeiro passo é instanciar a classe `BarcodeGenerator` com o tipo de barcode correto. Neste caso usamos `EncodeTypes.DatabarStackedOmniDirectional`, que produz um DataBar empilhado que pode ser lido de qualquer direção.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Por que isso importa:* O construtor recebe dois argumentos — **a simbologia do barcode** e **a string de dados**. O formato DataBar espera um identificador de aplicação GS1, por isso os dados de exemplo começam com `(01)`.

## Como definir a proporção de aspecto para um DataBar empilhado

A largura visual de um DataBar é controlada pela propriedade **aspect ratio**. Uma proporção maior torna as barras mais largas, o que pode melhorar a confiabilidade da leitura em impressoras de baixa resolução.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

O `XDimension` define o tamanho de um único módulo (a menor barra ou espaço). Manter isso em 2 px produz uma imagem nítida e de alta densidade, adequada para a maioria das impressoras de etiquetas.

## Definir proporção de aspecto 15 — walkthrough do código

Agora aplicamos o requisito de **definir proporção de aspecto 15**. Este é o núcleo do tutorial e demonstra a chamada de API exata que você precisa.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Por que 15?* A proporção de aspecto padrão para DataBar empilhado é 12. Aumentá‑la para 15 expande a largura de cada barra em 25 %, o que frequentemente corresponde às especificações de provedores logísticos que exigem um barcode mais largo para leitura mais rápida.

## Salvar o barcode como PNG

Com o gerador configurado, o passo final é gravar a imagem no disco. O método `Save` aceita um caminho de arquivo e um enum de formato de imagem.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

O formato PNG preserva qualidade sem perdas, garantindo que o barcode seja renderizado exatamente como projetado em qualquer tela ou impressora.

## Exemplo completo e saída esperada

Abaixo está o programa completo que você pode copiar para o método `Main` de um aplicativo console. Ele inclui todas as etapas descritas acima, além de uma pequena mensagem de verificação.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Saída esperada**

Executar o programa cria um arquivo chamado `DatabarAspectRatio15.png` contendo um barcode DataBar empilhado claro e largo. Ao abrir o PNG, você deve ver um barcode horizontalmente esticado que ainda cumpre as especificações do GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Texto alternativo da imagem:* **criar barcode PNG mostrando um DataBar empilhado com proporção de aspecto 15**

### Dicas e armadilhas comuns

| Situação | Recomendação |
|-----------|----------------|
| **Imagem está borrada** | Aumente `XDimension.Pixels` para 3 px ou mais, mas mantenha o tamanho total da imagem abaixo de 500 px para evitar arquivos excessivamente grandes. |
| **Leitor não consegue ler o código** | Verifique se a string de dados segue o formato GS1 (prefixo `(01)`). Também, assegure que a resolução da impressora seja de pelo menos 300 dpi. |
| **Precisa de um formato de arquivo diferente** | Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` — a API suporta todos os principais formatos raster. |
| **Executando em uma aplicação web** | Use `generator.Save(Stream, BarCodeImageFormat.Png)` para gravar diretamente na resposta HTTP sem tocar no sistema de arquivos. |

### Expandindo o exemplo

* **Vários barcodes em uma única imagem:** Crie instâncias adicionais de `BarcodeGenerator` e desenhe‑as em um único `Bitmap` usando `Graphics`.  
* **Adicionar texto legível:** Defina `generator.Parameters.Caption.Visible = true` e personalize a fonte via `generator.Parameters.Caption.Font`.  
* **Proporção de aspecto dinâmica:** Obtenha o valor da proporção a partir de um arquivo de configuração ou banco de dados para gerar barcodes com larguras variáveis em tempo real.

## Conclusão

Neste tutorial você aprendeu como **criar barcode PNG** em C# e definir precisamente **a proporção de aspecto** 15 para um barcode DataBar empilhado omnidirecional. O código completo e executável demonstra cada chamada de API necessária, explica por que cada configuração importa e fornece dicas práticas para implantações no mundo real.  

Em seguida, você pode explorar **como definir a proporção de aspecto** para outros tipos de barcode (por exemplo, QR Code ou Code 128) ou integrar o gerador em um serviço ASP .NET Core que retorna imagens de barcode sob demanda. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como criar imagens databar PNG com C# e Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Como criar barcode databar empilhado em C# com Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Personalizar a proporção de aspecto do databar empilhado omnidirecional no .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}