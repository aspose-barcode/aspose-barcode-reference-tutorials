---
category: general
date: 2026-10-12
description: Como gerar código de barras em C# rapidamente. Aprenda a criar um código
  de barras vazio e a personalizar a largura das barras para códigos postais claros.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: pt
lastmod: 2026-10-12
og_description: Como gerar código de barras em C# usando Aspose.BarCode. Este guia
  mostra como criar um código de barras vazio e ajustar as dimensões das barras para
  padrões postais.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: Como gerar imagens de código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Como gerar imagens de código de barras em C# com Aspose.BarCode
url: /pt/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar imagens de código de barras em C# com Aspose.BarCode

Se você precisa **gerar códigos de barras** a partir de uma string em uma aplicação .NET, este guia fornece uma solução completa, pronta‑para‑executar. Você verá como gerar códigos de barras padrão Planet e RM4SCC, ajustar a largura das barras para legibilidade e **criar códigos de barras vazios** onde as barras não são preenchidas. O código funciona com a versão mais recente do Aspose.BarCode para .NET (v.24.10) e roda no .NET 6 ou posterior.

Gerar códigos de barras é uma necessidade comum para etiquetas de envio, sistemas de inventário e plataformas de bilhetagem. Ao final deste tutorial você será capaz de produzir códigos de barras preenchidos e vazios programaticamente, sem precisar de ferramentas externas.

## Pré-requisitos

* SDK .NET 6 (ou qualquer versão mais recente do .NET)
* Visual Studio 2022 ou VS Code
* Uma licença válida do Aspose.BarCode para .NET (a avaliação gratuita funciona para testes)
* Familiaridade básica com aplicativos de console C#

Você pode instalar o pacote NuGet Aspose.BarCode com:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar um projeto de console mínimo

Crie um novo projeto de console e adicione as diretivas `using` necessárias. O código a seguir é um exemplo autônomo; copie-o para `Program.cs` e execute-o.

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
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Por que esta etapa é importante

* **Estrutura do projeto** garante que o tutorial seja executável sem configuração extra.
* Os namespaces `using Aspose.BarCode.Generation;` e `using Aspose.BarCode;` expõem a classe `BarcodeGenerator` e os formatos de imagem.
* Criar a pasta de saída programaticamente evita erros de “diretório não encontrado” na primeira execução.

## Etapa 2: Gerar um código de barras Planet preenchido

A primeira chamada a `GeneratePlanetBarcode` passa `filled: true`. Isso produz um código de barras Planet padrão onde cada barra é renderizada como um retângulo sólido e preto.

* **Arquivo resultante:** `PostalPlanetFilledBars.png`
* **Indicação visual:** As barras aparecem pretas, correspondendo às especificações postais para correspondência impressa.

### Saída esperada

Executar o programa criará uma imagem semelhante à abaixo (a imagem real não é exibida aqui, mas você verá um código de barras claro de 6 dígitos ao abrir o arquivo).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Etapa 3: Criar código de barras vazio (Planet com barras não preenchidas)

Para **criar código de barras vazio**, o mesmo método é chamado com `filled: false`. A propriedade `FilledBars` indica ao Aspose.BarCode para desenhar apenas os contornos das barras, deixando o interior transparente.

* **Arquivo resultante:** `PostalPlanetEmptyBars.png`
* **Caso de uso:** Códigos de barras vazios são úteis quando você deseja que o fundo mostre um logotipo ou cor, mantendo a legibilidade do código de barras.

### Saída esperada

O PNG gerado contém apenas os contornos das barras:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Etapa 4: Gerar um código de barras RM4SCC preenchido

RM4SCC é o padrão holandês de código de barras postal. O exemplo usa a mesma X‑dimension (4 pixels) para manter a consistência visual com os códigos de barras Planet.

* **Arquivo resultante:** `PostalRM4SCCFilledBars.png`
* **Por que RM4SCC?** Ele codifica dados numéricos em um formato compacto que muitos serviços postais europeus aceitam.

### Saída esperada

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Dicas práticas e armadilhas comuns

| Dica | Explicação |
|-----|-------------|
| **Dimensão X consistente** | Usar o mesmo valor `XDimension.Pixels` em diferentes simbologias garante uma aparência uniforme nas etiquetas impressas. |
| **Não reutilize a mesma instância do gerador** | Alterar `FilledBars` em um gerador existente pode produzir resultados inesperados; instancie um novo `BarcodeGenerator` para cada código de barras distinto. |
| **Verifique o formato da imagem** | PNG é sem perdas e ideal para códigos de barras; a compressão JPEG pode borrar barras finas, causando falhas na leitura. |
| **Manipulação de licença** | Se você executar o código sem uma licença, as imagens geradas conterão uma marca d'água. Aplique sua licença logo no início de `Main` com `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Segurança de thread** | `BarcodeGenerator` **não** é thread‑safe. Crie instâncias separadas por thread se gerar códigos de barras em paralelo. |

## Casos de borda que você pode encontrar

* **Limites de comprimento de dados** – Códigos de barras Planet aceitam até 6 caracteres numéricos. Fornecer mais caracteres lança uma `ArgumentException`. Valide o comprimento da entrada antes de chamar o gerador.
* **Dados não numéricos** – RM4SCC também espera entrada numérica. Para dados alfanuméricos você precisa de uma simbologia diferente (ex.: Code128). O mesmo padrão de definir `FilledBars` funciona para qualquer tipo de código de barras que o suporte.
* **Impressão em alta resolução** – Se você precisar de códigos de barras maiores que o tamanho na tela, aumente `XDimension.Pixels` (ex.: 8 ou 10) e opcionalmente defina `Resolution` em `generator.Parameters.Image`. Isso mantém as barras nítidas em impressão de 300 dpi.

## Recapitulação do arquivo de código completo

Abaixo está o arquivo de código completo novamente para copiar e colar rapidamente. Ele inclui todas as etapas, comentários e o trecho opcional de licença (comentado).

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
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Conclusão

Agora você sabe **como gerar imagens de código de barras** em C# usando Aspose.BarCode, e pode **criar variantes de código de barras vazios** alternando a propriedade `FilledBars`. O tutorial abordou:

* Configurar um projeto de console e instalar o pacote Aspose.BarCode
* Gerar códigos de barras Planet e RM4SCC preenchidos
* Produzir um código de barras Planet vazio (apenas contorno)
* Ajustar a largura das barras para legibilidade e lidar com armadilhas comuns

Em seguida, explore outras simbologias (Code128, QR, DataMatrix) e experimente cor, tamanho e formatos de imagem. Integrar a geração de códigos de barras em uma API web ou em um serviço Windows segue o mesmo padrão — basta substituir o método `Main` do console pelo ponto de entrada da sua aplicação.

Feliz codificação, e que suas aplicações comecem a escanear!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar imagem de código de barras postal em C# usando Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Como gerar código de barras postal em C# com dimensões personalizadas](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [Como gerar imagem de código de barras com Aspose.BarCode em C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}