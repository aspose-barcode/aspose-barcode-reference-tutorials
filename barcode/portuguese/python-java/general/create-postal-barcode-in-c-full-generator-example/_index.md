---
category: general
date: 2026-07-15
description: Crie códigos de barras postais em C# rapidamente. Este exemplo de gerador
  de códigos de barras mostra como exportar o código de barras em formato PNG para
  os códigos Planet e RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: pt
lastmod: 2026-07-15
og_description: Crie um código de barras postal em C# com este guia passo a passo.
  Aprenda o exemplo de gerador de código de barras que permite exportar a imagem do
  código de barras em formato PNG.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Criar Código de Barras Postal em C# – Guia Completo do Gerador
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Criar código de barras postal em C# – Exemplo completo de gerador
url: /pt/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras Postal em C# – Exemplo Completo de Gerador

Já se perguntou como **criar código de barras postal** em um projeto .NET sem vasculhar documentos intermináveis? Você não está sozinho. Seja construindo um sistema de etiquetas de envio ou automatizando postagem em massa, gerar um PNG de código de barras limpo é uma habilidade indispensável. Neste tutorial, vamos percorrer um **exemplo de gerador de código de barras** completo que mostra exatamente como **exportar imagens de código de barras** em **formato PNG de código de barras**.

Vamos cobrir tudo, desde a configuração da pasta de saída até o ajuste da largura do módulo e da altura da barra para os padrões Planet e RM4SCC. Ao final, você terá um aplicativo console pronto‑para‑executar que gera quatro arquivos PNG — dois com altura automática e dois com altura fixa de 100 px. Sem enrolação, apenas uma solução prática que você pode copiar‑colar.

## Pré-requisitos

- .NET 6 SDK ou posterior (o código funciona com .NET Core e .NET Framework)
- Uma IDE ou editor com o qual você se sinta confortável (Visual Studio, VS Code, Rider…)
- O pacote NuGet Aspose.BarCode for .NET (instale via `dotnet add package Aspose.BarCode`)

É isso — sem serviços extras, sem APIs web. Apenas um projeto C# local.

## Criar Código de Barras Postal – Passo a Passo

Abaixo dividimos o processo em cinco etapas claras. Cada etapa tem um cabeçalho **H2** descritivo que inclui a palavra‑chave principal ou secundária, para que você encontre exatamente o que precisa com uma rápida leitura.

### Etapa 1: Preparar o Diretório de Saída

Primeiro de tudo, precisamos de uma pasta onde os arquivos PNG gerados serão armazenados. Definir um caminho fixo funciona para uma demonstração, mas em produção você provavelmente lerá isso a partir de uma configuração.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Dica profissional:** Usar `Path.Combine` torna o código independente do SO, e `Directory.CreateDirectory` pode ser chamado com segurança mesmo se a pasta já existir.

### Etapa 2: Gerar um Código de Barras Planet com Altura Automática

Agora chegamos ao coração da parte **como gerar código de barras planet**. Criamos uma instância `BarcodeGenerator`, definimos a largura do módulo (dimensão X) e deixamos a biblioteca decidir a altura da barra.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

O enum `EncodeTypes.Planet` indica à Aspose que queremos a simbologia Planet, que é comum para serviços postais em muitos países. Como não alteramos `BarHeight`, o gerador escolhe um padrão sensato que mantém o código de barras legível.

### Etapa 3: Gerar um Código de Barras RM4SCC com Altura Automática

RM4SCC é o formato de código de barras postal canadense. O código espelha o exemplo Planet, ilustrando o padrão **exemplo de gerador de código de barras** que você pode reutilizar para qualquer simbologia suportada.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Novamente, contamos com a altura automática, que é perfeita para protótipos rápidos ou quando você deixa a impressora cuidar do dimensionamento.

### Etapa 4: Gerar um Código de Barras Planet com Altura Fixa (100 px)

Às vezes o sistema de envio exige uma altura de barra estrita — talvez a impressora espere exatamente 100 px. Aqui está como **exportar imagem de código de barras** com uma altura forçada.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Definir `BarHeight.Pixels` substitui o cálculo automático. O restante das configurações permanece o mesmo, garantindo consistência visual entre as imagens de altura automática e fixa.

### Etapa 5: Gerar um Código de Barras RM4SCC com Altura Fixa (100 px)

Repetimos a abordagem de altura fixa para RM4SCC. Isso demonstra a flexibilidade do **exemplo de gerador de código de barras**: você pode combinar configurações automáticas e manuais por simbologia.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Listagem Completa do Código Fonte

Juntando tudo, aqui está o programa completo e executável. Copie o bloco abaixo para um novo projeto console e execute **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

Executar este programa cria os seguintes arquivos (todos em **formato PNG de código de barras**):

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Cada imagem é uma representação nítida, preto‑sobre‑branco, pronta para impressão ou processamento adicional.

## Por Que Esta Abordagem Funciona

- **Consistência:** Ao fixar `XDimension.Pixels` em 4 para todos os códigos de barras, você garante a mesma largura de módulo, essencial para scanners que esperam um tamanho de ponto específico.
- **Flexibilidade:** A mesma base de código permite alternar entre altura automática e fixa sem reescrever a lógica do gerador — perfeito para soluções multi‑transportadora.
- **Desempenho:** Gerar um PNG é uma operação leve; a biblioteca Aspose transmite a imagem diretamente para o disco, evitando sobrecarga de memória desnecessária.
- **Portabilidade:** As chamadas `Path.Combine` e `Directory.CreateDirectory` mantêm o código multiplataforma, de modo que a mesma fonte funciona no Windows, Linux e macOS.

## Armadilhas Comuns & Como Evitá‑las

| Problema | Por que acontece | Correção |
|------|----------------|-----|
| Código de barras parece borrado | Uso de uma dimensão X muito baixa (ex.: 1 px) | Aumente `XDimension.Pixels` para pelo menos 3‑4 para códigos de barras postais |
| Scanner rejeita a imagem | Altura da barra muito pequena ou muito grande para a impressora | Use `BarHeight.Pixels` para corresponder às especificações da impressora |
| Arquivo PNG está corrompido | Esquecer de fechar o stream (raro com Aspose) | Deixe o método `Save` lidar com a liberação; evite manipulação manual de streams, a menos que necessário |
| Pasta de saída não encontrada | Caminho codificado aponta para um diretório inexistente | Sempre chame `Directory.CreateDirectory` antes de salvar |

## Expandindo o Exemplo

Agora que você dominou os fundamentos de **criar código de barras postal**, pode querer explorar:

- **Adicionar texto legível por humanos** abaixo do código de barras (`DisplayText` property)
- **Alterar cores** (`ForeColor`, `BackColor`) para branding
- **Processamento em lote** de uma lista CSV de códigos postais (iterar sobre o gerador)
- **Exportar para outros formatos** como SVG ou PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Cada uma dessas extensões segue o mesmo padrão demonstrado neste **exemplo de gerador de código de barras**, permitindo que você experimente sem começar do zero.

## Conclusão

Você

## O Que Você Deve Aprender a Seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar imagem de código de barras C# – Exemplo GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Como criar texto de código estendido para dotcode com Aspose.BarCode para .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Como criar código de barras Aztec com correção de erro em .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}