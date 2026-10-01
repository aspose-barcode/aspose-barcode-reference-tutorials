---
category: general
date: 2026-08-15
description: Como definir parâmetros de código de barras em C# e gerar imagens de
  código de barras. Aprenda passo a passo a criar código de barras Databar e salvar
  arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: pt
lastmod: 2026-08-15
og_description: Como definir o código de barras em C# com Aspose.Barcode e gerar a
  imagem do código de barras em C#. Siga este guia para criar um código de barras
  Databar e salvar arquivos PNG.
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: Como definir código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Como definir código de barras – guia completo em C#
url: /pt/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir código de barras – guia completo em C#

Se você está procurando **como definir código de barras** parâmetros em um projeto .NET, este tutorial mostra as etapas exatas que você precisa. Você aprenderá **como gerar código de barras** imagens, criar um código de barras Databar e controlar a altura das barras pixel por pixel — tudo com código C# limpo e pronto para produção.

Neste guia você:

* Instalar o pacote NuGet necessário.  
* Criar um código de barras Databar Omnidirecional (a parte “criar código de barras Databar”).  
* Ajustar a X‑dimension e a altura da barra para demonstrar **como definir código de barras** dimensões.  
* Salvar o resultado como arquivos PNG, cobrindo o cenário **gerar imagem de código de barras C#**.

O código funciona com a versão mais recente do Aspose.Barcode para .NET (v 24.12 na data de escrita) e roda em .NET 6 ou posterior.

---

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6 SDK (ou qualquer versão posterior).  
* Uma IDE como Visual Studio 2022 ou VS Code.  
* Acesso à internet para baixar o pacote NuGet Aspose.Barcode.

Nenhuma biblioteca de terceiros adicional é necessária.

---

## Passo 1: Instalar Aspose.Barcode para .NET

A maneira mais confiável de **gerar código de barras** imagens em C# é usar Aspose.Barcode. Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente ao seu arquivo de projeto, garantindo que você tenha a classe `BarcodeGenerator` e a enumeração `EncodeTypes`.

*Dica de especialista:* Mantenha o pacote atualizado (`dotnet list package --outdated`) para aproveitar correções de bugs e novas simbologias de código de barras.

---

## Passo 2: Criar um código de barras Databar (criar código de barras Databar)

Databar Omnidirecional é ideal para varejo e logística porque pode codificar um valor GTIN‑14 mais dados adicionais. O código a seguir cria o objeto do código de barras:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Por que isso importa:* O enum `EncodeTypes.DatabarOmniDirectional` indica à biblioteca que deve usar a simbologia Databar, enquanto a string `"(01)12345678901231"` segue o formato do Identificador de Aplicação GS1 para um GTIN de 14 dígitos.

---

## Passo 3: Definir parâmetros comuns – X‑dimension e altura base

A maioria dos leitores de código de barras espera uma X‑dimension mínima (a largura da barra mais estreita). Definir para 2 pixels fornece uma imagem compacta, porém legível.

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Você pode ajustar a altura da barra posteriormente sem recriar o gerador — este é o núcleo de **como definir código de barras** atributos após a instanciação.

---

## Passo 4: Definir a primeira altura da barra e salvar a imagem (gerar imagem de código de barras C#)

Agora demonstramos a primeira parte de **como definir código de barras** altura. A altura da barra controla o comprimento visual de cada barra; um valor de 30 pixels gera um código de barras curto, enquanto 60 pixels cria uma versão mais alta.

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Após a execução, `DatabarBarHeight30Pixels.png` contém um código de barras Databar com barra de 30 pixels de altura. Abra o arquivo em qualquer visualizador de imagens para verificar o resultado.

---

## Passo 5: Alterar a altura da barra e salvar uma segunda imagem

Para ilustrar que **como definir código de barras** valores pode ser alterado em tempo real, modificamos a altura da barra para 60 pixels e gravamos um segundo arquivo.

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG mostrando os mesmos dados Databar, mas com alturas visuais diferentes. Isso é útil quando você precisa de um código de barras maior para etiquetas impressas ou menor para exibição em tela.

---

## Passo 6: Exemplo completo e executável

Juntando tudo, aqui está um programa de console autocontido que executa todas as etapas descritas acima. Copie o código para um novo arquivo `Program.cs`, substitua `YOUR_DIRECTORY` por um caminho de pasta real e execute-o.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**Saída esperada**

Quando você executar o programa, o console imprime:

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

E a pasta `C:\Barcodes` (ou o caminho que você forneceu) contém os dois arquivos PNG. Ambas as imagens exibem um código de barras Databar Omnidirecional válido que pode ser lido por leitores GS1 padrão.

---

## Perguntas frequentes

**Isso funciona com outros formatos de imagem?**  
Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp`, `Gif` ou `Tiff` para gerar o tipo de arquivo correspondente.

**Posso mudar a cor de primeiro plano?**  
Defina `generator.Parameters.Barcode.ForeColor` para qualquer valor `System.Drawing.Color`, por exemplo, `Color.Blue`.

**E se eu precisar de uma simbologia diferente?**  
Passe um valor diferente de `EncodeTypes` ao construtor, como `EncodeTypes.Code128` para um código de barras linear ou `EncodeTypes.QR` para um código matricial.

**Existe uma maneira de incorporar o código de barras em um PDF?**  
Aspose.Barcode fornece a classe `PdfGenerator`. Após gerar a imagem, você pode adicioná‑la a uma página PDF usando Aspose.PDF.

---

## Melhores práticas para geração de códigos de barras em C#

* **Reutilize a instância `BarcodeGenerator`** quando precisar apenas ajustar dimensões — isso evita alocações de memória desnecessárias.  
* **Dispose o gerador** (`generator.Dispose()`) após terminar para liberar recursos nativos prontamente.  
* **Valide os dados de entrada** (por exemplo, comprimento do GTIN) antes de criar o código de barras para evitar exceções em tempo de execução.  
* **Teste com um scanner físico** após alterar X‑dimension ou altura da barra; valores extremos podem afetar a legibilidade.  
* **Mantenha a pasta de saída gravável** para a conta que executa; caso contrário, `Save` lançará uma `UnauthorizedAccessException`.

---

## Conclusão

Agora você sabe **como definir código de barras** propriedades como X‑dimension e altura da barra, **como gerar código de barras** imagens em C#, e as etapas exatas para **criar código de barras Databar** arquivos com Aspose.Barcode. Seguindo o exemplo completo, você pode gerar múltiplos arquivos PNG com diferentes características visuais, atendendo ao requisito **gerar imagem de código de barras C#** para qualquer aplicação .NET.

Em seguida, explore tópicos relacionados como **como gerar código de barras** em massa, incorporar códigos de barras em PDFs ou mudar para outras simbologias como QR ou Code 128. Experimente os parâmetros mostrados aqui para ajustar finamente a aparência do código de barras ao seu ambiente de leitura específico. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como gerar código de barras – Configuração Code 39 com Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}