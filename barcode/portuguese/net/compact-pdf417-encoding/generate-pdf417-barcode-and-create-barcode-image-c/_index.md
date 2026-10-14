---
category: general
date: 2026-10-08
description: Gere código de barras PDF417 em C# e aprenda como gerar imagens PDF417
  de forma eficiente com Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: pt
lastmod: 2026-10-08
og_description: Gere código de barras PDF417 em C# com um guia passo a passo. Aprenda
  como gerar PDF417 e salvar a imagem do código de barras como PNG.
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: Gerar código de barras PDF417 e criar imagem de código de barras em C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Gerar código de barras PDF417 e criar imagem de código de barras em C#
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras PDF417 e criar imagem de código de barras C#

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este tutorial mostra exatamente como fazer isso. Você verá um exemplo completo e executável que cria um código de barras, personaliza seu layout e salva o resultado como uma imagem PNG.

Gerar um código de barras PDF417 é uma necessidade comum para etiquetas de envio, cartões de embarque e sistemas de inventário. Ao final deste guia, você será capaz de **gerar PDF417** com controle detalhado sobre tamanho e layout, e também aprenderá como **criar imagem de código de barras C#** que podem ser exibidas em uma interface ou enviadas para uma impressora.

## Pré-requisitos

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7.2+)
- Visual Studio 2022 ou qualquer IDE compatível com C#
- Aspose.BarCode for .NET (versão de avaliação gratuita ou licenciada)  
  Instale via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Nenhuma configuração adicional é necessária; a biblioteca lida com a codificação PNG internamente.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e adicione as diretivas `using` necessárias. Este bloco inclui tudo que você precisa para compilar o exemplo.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*Por que esta etapa é importante*: Importar o namespace `Aspose.BarCode.Generation` fornece acesso a `BarcodeGenerator`, `EncodeTypes` e aos objetos de parâmetros usados para personalizar o código de barras.

## Etapa 2: Gerar código de barras PDF417 com o texto desejado

Dentro de `Main`, instancie `BarcodeGenerator` com `EncodeTypes.Pdf417`. O construtor recebe o tipo de código de barras e o texto que você deseja codificar.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*Explicação*: `EncodeTypes.Pdf417` indica à biblioteca que deve produzir a simbologia PDF417. A string `"Layout demo"` torna‑se a carga de dados codificada no código de barras.

## Etapa 3: Ajustar finamente o tamanho do código de barras usando X‑dimension

A X‑dimension controla a largura de um único módulo (o menor quadrado preto/branco). Defini‑la em pixels fornece controle preciso sobre o tamanho final da imagem.

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Por que isso importa*: Uma X‑dimension menor gera um código de barras mais compacto, o que é útil quando há espaço limitado em uma etiqueta ou elemento de UI.

## Etapa 4: Personalizar o layout PDF417 (colunas e linhas)

PDF417 permite especificar o número de colunas e linhas. Ajustar esses valores altera a proporção do código de barras.

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*Explicação*: Com 4 colunas e 9 linhas, o código de barras fica mais alto que largo, correspondendo a muitos formatos de impressão de bilhetes.

## Etapa 5: Salvar o código de barras gerado como imagem PNG

Finalmente, grave o código de barras em um arquivo. O enum `BarCodeImageFormat.Png` garante compressão sem perdas.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*O que acontece aqui*: `Save` cria o arquivo de imagem no disco. Você pode substituir `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se for necessário um formato diferente.

### Exemplo completo em um bloco

Abaixo está o programa completo, pronto para execução. Substitua `YOUR_DIRECTORY` por um caminho de pasta real em sua máquina.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Execute o programa (`dotnet run`) e abra o `LayoutPdf417.png` resultante. Você deverá ver um código de barras PDF417 limpo que codifica o texto *Layout demo*.

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="Código de barras PDF417 gerado salvo como PNG"}

*Saída esperada*: Um arquivo PNG com aproximadamente 150 × 300 pixels (o tamanho varia com a X‑dimension) contendo um código de barras PDF417 legível.

## Variações comuns e casos de borda

| Cenário | Como adaptar o código |
|----------|----------------------|
| **Payload de dados diferente** | Altere o segundo argumento de `BarcodeGenerator` (`"Layout demo"` → qualquer string, até 1 800 caracteres). |
| **Resolução mais alta** | Aumente `XDimension.Pixels` (por exemplo, `4`) ou defina `Resolution` via `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;`. |
| **Fundo transparente** | Use `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`. |
| **Incorporar em um PictureBox do Windows Forms** | Em vez de `Save`, chame `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`. |
| **Tratamento de erros** | Envolva o código de geração em um bloco `try…catch` para capturar `BarCodeException` para caracteres não suportados. |

## Dicas profissionais

- **Validar o código de barras**: Após salvar, você pode carregar o PNG com um SDK de scanner de códigos de barras para garantir que os dados correspondam à string original.
- **Desempenho**: Reutilizar uma única instância de `BarcodeGenerator` para vários códigos de barras reduz a sobrecarga de alocação.
- **Segurança**: Se os dados codificados contiverem informações sensíveis, considere criptografá‑los antes de passá‑los ao gerador.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# e **criar arquivos de imagem de código de barras C#** que atendem a requisitos de layout personalizados. O exemplo completo demonstra a inicialização do gerador, o ajuste de tamanho e layout, e a gravação do resultado como PNG. A partir daqui, você pode explorar recursos adicionais como personalização de cores, incorporação de logotipos ou geração em lote de múltiplos códigos de barras para impressão em massa.

---

*Próximos passos*:  
- Experimente outras simbologias (Code128, QR) usando a mesma classe `BarcodeGenerator`.  
- Aprenda a ler códigos de barras PDF417 com o `BarCodeReader` da Aspose.BarCode.  
- Integre o PNG gerado nas visualizações ASP.NET Core MVC para renderização de códigos de barras em tempo real.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como salvar código de barras e gerar PDF417 com Aspose em C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Como gerar código de barras PDF417 em C# com dimensões personalizadas](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}