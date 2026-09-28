---
category: general
date: 2026-08-22
description: Como gerar código de barras em C# usando Aspose.BarCode. Aprenda a criar
  imagem de código de barras em C# passo a passo, desativar o componente 2‑D e salvar
  arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: pt
lastmod: 2026-08-22
og_description: Como gerar código de barras em C# com Aspose.BarCode. Este tutorial
  mostra como criar imagem de código de barras em C# usando DataBar Expanded, alternar
  o componente 2‑D e salvar arquivos PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Como gerar código de barras em C# – guia completo para criar imagem de código
  de barras em C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Como gerar código de barras em C# – criar imagem de código de barras em C#
  com DataBar Expanded
url: /pt/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras em C# – criar imagem de código de barras c# com DataBar Expanded

Gerar código de barras em C# é uma necessidade frequente quando você precisa incorporar dados legíveis por máquina em suas aplicações. Este guia mostra como criar **barcode image c#** usando a biblioteca Aspose.BarCode, desativar o componente composto 2‑D e salvar o resultado como arquivos PNG.

Você verá um programa completo e executável, uma explicação de cada opção de configuração e dicas para personalizar a saída. Nenhuma documentação externa é necessária — apenas o código abaixo e um ambiente de desenvolvimento .NET.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* Pacote NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

A biblioteca fornece a classe `BarcodeGenerator` usada ao longo deste tutorial.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo aplicativo de console e importe os namespaces necessários:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

O namespace `Aspose.BarCode.Generation` contém todas as classes necessárias para configurar e renderizar códigos de barras.

## Etapa 2: Inicializar o gerador de código de barras DataBar Expanded

A primeira linha funcional cria um `BarcodeGenerator` para a simbologia **DataBar Expanded** e fornece a string de dados bruta. A string de dados segue o formato do Identificador de Aplicação GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Criar o gerador aloca a tela interna de bitmap, permitindo que você ajuste tamanho e aparência antes da renderização.

## Etapa 3: Definir a largura do módulo (X‑dimension)

A X‑dimension controla a largura do menor elemento do código de barras. Defini‑la em pixels oferece controle preciso sobre o tamanho final da imagem.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Um valor de `2` pixels funciona bem para exibição em tela; aumente‑o para impressões de alta resolução.

## Etapa 4: Desativar o componente composto 2‑D

DataBar Expanded pode incluir opcionalmente um componente 2‑D que transporta informações adicionais. Para gerar um código de barras **sem** esse componente, defina a flag como `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Desativar o componente reduz a complexidade visual e produz um arquivo PNG menor.

## Etapa 5: Salvar a imagem do código de barras sem o componente 2‑D

Escolha um diretório de saída e grave a imagem no disco. O enum `BarCodeImageFormat.Png` garante um arquivo PNG sem perdas.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Após esta chamada, `Databar2DComponentDisabled.png` contém um código DataBar Expanded limpo.

## Etapa 6: Ativar o componente composto 2‑D

Se precisar da camada de dados extra, reative a flag. A mesma instância do gerador pode ser reutilizada, evitando a criação de um segundo objeto.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Etapa 7: Salvar a imagem do código de barras com o componente 2‑D ativado

Renderize a segunda imagem usando as mesmas configurações, exceto pela flag 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Agora `Databar2DComponentEnabled.png` mostra o código de barras com o padrão 2‑D adicional.

## Código‑fonte completo

Copie todo o trecho abaixo para `Program.cs` e execute o projeto. O programa cria ambos os arquivos PNG na pasta que você especificar.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Saída esperada

Ao executar o programa, ele imprime:

```
Barcode images generated successfully.
```

e cria dois arquivos:

* `Databar2DComponentDisabled.png` – código de barras sem o componente 2‑D  
* `Databar2DComponentEnabled.png` – código de barras com o componente 2‑D  

Abra os PNGs em qualquer visualizador de imagens para verificar a diferença visual.

## Variações comuns e casos de borda

| Situação | Ajuste |
|-----------|------------|
| **Simbologia diferente** | Substitua `EncodeTypes.DatabarExpanded` por outro valor, por exemplo, `EncodeTypes.Code128`. |
| **Resolução maior** | Aumente `XDimension.Pixels` para 4 ou 5, ou defina `Resolution` em `barcodeGenerator.Parameters.Image`. |
| **Outros formatos de imagem** | Use `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` ou `BarCodeImageFormat.Svg`. |
| **Execução em aplicação web** | Transmita os bytes da imagem diretamente na resposta HTTP em vez de salvar no disco. |
| **Gerenciamento de memória** | Envolva o gerador em um bloco `using` se você estiver direcionando o .NET Framework para garantir que recursos não gerenciados sejam liberados. |

## Dicas avançadas

* **Reutilizar o gerador** – Alterar apenas a flag 2‑D evita reinstanciar o objeto, economizando ciclos de CPU.  
* **Validar os dados** – Dados GS1 devem seguir exatamente o comprimento e as regras de checksum; entrada inválida lança `ArgumentException`.  
* **Processamento em lote** – Percorra uma coleção de strings de dados, alterne a flag 2‑D conforme necessário e salve cada imagem com um nome de arquivo exclusivo.  

## Conclusão

Agora você sabe como gerar código de barras em C# e criar **barcode image c#** com controle total sobre o componente composto 2‑D. O exemplo demonstra a inicialização do gerador, a configuração da X‑dimension, a alternância do componente e a gravação de arquivos PNG. A partir daqui, você pode explorar outras simbologias, incorporar as imagens em PDFs ou integrar a geração de códigos de barras em serviços ASP.NET Core.

--- 

*Próximos passos*: experimente gerar códigos QR, teste diferentes resoluções de imagem ou incorpore os PNGs gerados em um PDF usando Aspose.PDF. Essas extensões se baseiam na mesma API `BarcodeGenerator` e mantêm seu fluxo de trabalho consistente.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Como gerar e ajustar a altura do código de barras para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}