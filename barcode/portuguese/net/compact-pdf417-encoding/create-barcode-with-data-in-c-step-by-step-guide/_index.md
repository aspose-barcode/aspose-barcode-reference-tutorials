---
category: general
date: 2026-07-27
description: Crie código de barras com dados em C# rapidamente. Aprenda como criar
  código de barras PDF417 em C# usando Aspose.BarCode, definir dimensões e salvar
  como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: pt
lastmod: 2026-07-27
og_description: Crie código de barras com dados em C# usando Aspose.BarCode. Este
  guia mostra como criar um código de barras PDF417 em C# com configurações personalizadas
  e salvar como PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Criar código de barras com dados em C# – Guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Criar código de barras com dados em C# – Guia passo a passo
url: /pt/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras com dados em C# – Guia completo de programação

Já precisou **criar código de barras com dados** em um aplicativo .NET, mas não sabia quais chamadas de API usar? Você não está sozinho. Seja etiquetando inventário, imprimindo ingressos ou incorporando informações em uma leitura móvel, dominar a criação de códigos de barras é uma habilidade útil para qualquer desenvolvedor C#.

Neste tutorial, percorreremos um exemplo prático que mostra como **criar código de barras PDF417 c#** usando a biblioteca Aspose.BarCode, ajustar a largura do módulo, limitar a contagem de colunas e, finalmente, salvar o resultado em um arquivo PNG. Ao final, você terá um programa de console totalmente funcional e pronto para executar, que pode ser inserido em qualquer projeto.

## Pré-requisitos — O que você precisará

- **.NET 6.0** ou posterior (o código também funciona com .NET Framework 4.7+)  
- **Aspose.BarCode for .NET** pacote NuGet (`Install-Package Aspose.BarCode`)  
- Um editor de código ou IDE (Visual Studio, VS Code, Rider – escolha **sua** favorita)  
- Permissão de escrita em uma pasta onde o PNG será salvo  

Nenhum arquivo de configuração extra é necessário; a biblioteca é autônoma.

## Etapa 1: Configurar o projeto e importar namespaces

Primeiro, crie um novo projeto de console (ou abra um existente) e adicione a referência ao Aspose.BarCode.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Por que isso importa:** Importar os namespaces corretos lhe dá acesso ao `BarcodeGenerator` e às configurações relacionadas sem precisar qualificar cada tipo. Também deixa o código mais limpo para manutenção futura.

## Etapa 2: Inicializar o gerador de código de barras com seus dados

Agora realmente **criamos código de barras com dados**. O construtor `BarcodeGenerator` recebe dois argumentos: a simbologia (`EncodeTypes.MicroPdf417`) e a string que você deseja codificar.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Dica:** A simbologia MicroPdf417 é uma versão compacta do PDF417, perfeita quando você precisa de uma imagem menor, mas ainda deseja alta capacidade de dados. A biblioteca lida com Unicode nativamente, então caracteres como “Å” e “©” funcionam perfeitamente.

## Etapa 3: Ajustar a X‑Dimension (largura do módulo)

Se precisar de uma imagem mais nítida e de alta resolução, você pode reduzir a largura do módulo. Definir para **2 pixels** fornece uma grade mais fina sem aumentar muito o tamanho do arquivo.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por que ajustar a X‑Dimension?** Uma X‑dimension menor torna cada barra mais estreita, o que melhora a legibilidade em scanners de alta resolução, mantendo o tamanho geral do código de barras razoável.

## Etapa 4: Limitar as colunas do PDF417 (Opcional, mas comum)

O PDF417 permite especificar o número de colunas. Para MicroPdf417 o máximo é **4**, o que mantém o código de barras curto e largo.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Caso de borda:** Se você definir uma contagem de colunas maior que o máximo permitido, o Aspose a limitará automaticamente, mas a melhor prática é permanecer dentro da faixa documentada para evitar dimensionamento inesperado.

## Etapa 5: Salvar o código de barras como imagem PNG

Finalmente, grave a imagem gerada no disco. O método `Save` recebe o caminho completo e o formato de imagem desejado.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Dica profissional:** PNG preserva os dados de pixel exatos, o que é essencial para códigos de barras. Se precisar de um formato vetorial para dimensionamento, você pode trocar `BarCodeImageFormat.Png` por `BarCodeImageFormat.Svg`.

### Exemplo completo em funcionamento

Juntando tudo, aqui está o programa completo, pronto para copiar e colar:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

Executar este programa produz um arquivo PNG que se parece aproximadamente com isto:

![Código de barras criado com dados em C#](barcode-sample.png "Captura de tela de um código de barras criado com dados em uma aplicação C#")

*A imagem acima é um placeholder—seu código de barras real conterá a string exata “Åspóse.Barcóde©”.*

## Perguntas comuns e casos de borda

| Pergunta | Resposta |
|----------|----------|
| *E se meus dados excederem a capacidade do MicroPdf417?* | Mude para `EncodeTypes.Pdf417` (PDF417 regular) que suporta até 1 800 caracteres. |
| *Posso mudar o formato da imagem para JPEG?* | Sim—substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. Lembre-se de que JPEG é com perdas; pode afetar a confiabilidade do scanner. |
| *Preciso tratar Unicode manualmente?* | Não. Aspose.BarCode codifica automaticamente caracteres Unicode, mas certifique-se de que seu arquivo fonte esteja salvo com codificação UTF‑8. |
| *E se eu precisar de fundo transparente?* | Defina `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` antes de salvar. |
| *Existe uma maneira de gerar o código de barras na memória?* | Chame `generator.GenerateBarCodeImage()` para obter um objeto `System.Drawing.Image` que você pode transmitir diretamente. |

## Recapitulação – O que aprendemos

Demonstramos como **criar código de barras com dados** em C# ao:

1. Inicializar o `BarcodeGenerator` com MicroPdf417 e uma string Unicode.  
2. Ajustar a X‑dimension para resolução mais fina.  
3. Limitar as colunas para manter o código de barras compacto.  
4. Salvar o resultado como um arquivo PNG.  

Todos esses passos juntos respondem à consulta principal “como **criar código de barras PDF417 c#**” ao mesmo tempo que mostram como personalizar parâmetros comuns.

## Próximos passos e tópicos relacionados

- **Adicionar texto legível por humanos** abaixo do código de barras usando `generator.Parameters.Barcode.CodeTextParameters`.  
- **Incorporar o PNG em um PDF** com `Aspose.Pdf` para relatórios imprimíveis.  
- **Gerar outras simbologias** (QR, Code128, DataMatrix) trocando `EncodeTypes`.  
- **Processamento em lote** – percorrer um CSV de IDs de produtos e gerar uma pasta de códigos de barras.  

Sinta-se à vontade para experimentar a contagem de colunas, o nível de correção de erro e os esquemas de cores. Quando estiver confortável, você pode criar soluções de rotulagem completas que se integrem perfeitamente com sistemas de inventário ou bilhetagem.

Feliz codificação, e que suas leituras estejam sempre livres de erros!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras – PDF417 compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Criar imagem de código de barras DotCode – linhas e colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Criar código de barras PNG – Proporção do DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}