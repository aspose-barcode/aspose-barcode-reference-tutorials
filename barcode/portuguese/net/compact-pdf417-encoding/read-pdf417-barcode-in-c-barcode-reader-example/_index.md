---
category: general
date: 2026-10-14
description: Crie um scanner de código de barras de console em C# que lê códigos de
  barras PDF417, manipula macro PDF417 e decodifica múltiplos códigos de barras a
  partir de uma única imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Crie um scanner de código de barras de console em C# para ler rapidamente
  códigos de barras PDF417 e macro PDF417 a partir de imagens. Este guia passo a passo
  mostra como decodificar múltiplos códigos de barras em uma única foto.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Criar scanner de código de barras de console em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Criar scanner de código de barras de console em C# – exemplo de leitura de
  código de barras PDF417
url: /pt/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar scanner de código de barras de console em C# – exemplo de leitura de código de barras PDF417

`BarCodeReader` é a classe principal do Aspose.BarCode que decodifica códigos de barras de imagens e devolve metadados detalhados. Se você precisar ler dados de código de barras PDF417 de uma imagem, este guia mostra como fazer isso com a classe **BarCodeReader** em C#. Você aprenderá um exemplo de **criar scanner de código de barras de console** que também lida com macro PDF417 e pode ler vários códigos de barras em uma única imagem.

Trabalhar com códigos de barras costuma significar lidar com diferentes fontes de imagem, condições de iluminação variadas e, às vezes, dados compostos como segmentos macro PDF417. Este tutorial cobre tudo o que você precisa para decodificar um código de barras PDF417, extrair seus campos estendidos e processar vários códigos de barras da mesma foto. Ao final, você terá um programa de console executável que lê códigos de barras de um arquivo de imagem e imprime informações detalhadas no console.

## Respostas rápidas
- **O que o exemplo faz?** Ele cria um scanner de código de barras de console que lê códigos PDF417 e macro PDF417 de uma imagem e imprime todos os campos decodificados.  
- **Qual biblioteca é necessária?** Aspose.BarCode para .NET (NuGet).  
- **Ele pode ler vários códigos de barras de uma vez?** Sim – o leitor itera sobre cada código de barras encontrado na imagem.  
- **Preciso de conexão com a internet?** Não, a biblioteca funciona totalmente offline.  
- **Qual versão do .NET é suportada?** .NET 6.0 ou posterior.

## O que você precisará

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Uma versão recente do pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que forneça `BarCodeReader` e `DecodeType.MacroPdf417`)  
* Um arquivo de imagem que contenha um código de barras PDF417 ou macro PDF417 (o exemplo usa `ExtPDF417Meta.png`)  
* Um editor de código ou IDE como Visual Studio 2022  

Nenhum serviço adicional ou API externa é necessário.

## Configurando o projeto para leitura de códigos de barras

1. **Criar um novo projeto de console**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Adicionar a biblioteca de códigos de barras**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copiar a imagem do código de barras**  

   Coloque `ExtPDF417Meta.png` (ou qualquer imagem que contenha um código de barras PDF417) na pasta do projeto.  
   Para este tutorial, assumimos que o arquivo está em `YOUR_DIRECTORY/ExtPDF417Meta.png`.

O projeto está agora pronto para compilar e executar o exemplo do leitor de códigos de barras.

## Como criar um scanner de código de barras de console em C#?

`BarCodeReader` é uma classe fornecida pela Aspose.BarCode que lê códigos de barras de imagens e retorna seus dados decodificados.  
Carregue a imagem com BarCodeReader, defina o tipo de decodificação para MacroPdf417 e itere sobre os resultados – isso é tudo que você precisa para criar um scanner de código de barras de console. O leitor libera automaticamente recursos nativos graças à instrução `using`, portanto você não precisa gerenciar a memória manualmente. Esta abordagem funciona para qualquer formato de imagem suportado pelo .NET, como PNG, JPEG ou BMP.

### Passo a passo

O núcleo da solução é um bloco `using` que cria uma instância de `BarCodeReader`, especifica `DecodeType.MacroPdf417` e itera sobre cada código de barras detectado. O código a seguir é um programa completo e autônomo que você pode colar em `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Por que isso funciona**:  

* `DecodeType.MacroPdf417` indica ao leitor que procure a extensão macro do PDF417, que contém metadados adicionais como ID do arquivo, contagem de segmentos e timestamps.  
* A instrução `using` garante que recursos não gerenciados (manipuladores de arquivos, buffers de decodificação nativos) sejam liberados prontamente.  
* O loop `foreach` processa automaticamente **todos** os códigos de barras que a imagem contém, atendendo ao requisito de *ler múltiplos códigos de barras*.  

Ao executar o programa (`dotnet run`), você deverá ver uma saída semelhante ao seguinte:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Se a imagem contiver mais de um código de barras PDF417, o loop imprime um bloco separado para cada código, demonstrando assim como **ler múltiplos códigos de barras** de uma única imagem.

## Como posso ler múltiplos códigos de barras de uma imagem?

Use uma única instância de `BarCodeReader` e defina a flag `DecodeType` para incluir todos os formatos que deseja detectar. Ao combinar flags com o operador OR bit a bit, você pode instruir a biblioteca a procurar PDF417, QR, Code‑128 e muitas outras simbologias em uma única passagem. Isso elimina a necessidade de leitores separados e reduz o tempo de processamento.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* é uma máscara de bits, portanto você pode combinar qualquer número de formatos suportados. Aspose.BarCode suporta **mais de 30 simbologias de código de barras**, incluindo QR, DataMatrix, Code‑128 e UPC‑A, permitindo que um único scanner atenda a diversos casos de uso, como rotulagem de produtos, validação de ingressos e verificação de identidade.

## O que é macro PDF417 e como acessar seus campos com segurança?

Macro PDF417 é uma extensão da simbologia PDF417 que permite que um grande conjunto de dados seja dividido em vários símbolos de código de barras.  
Macro PDF417 adiciona um conjunto rico de propriedades estendidas. No entanto, nem todo código de barras inclui todos os campos. Acessar uma propriedade ausente pode gerar uma `NullReferenceException`. A abordagem mais segura é verificar cada propriedade antes de imprimir, garantindo que sua aplicação permaneça estável mesmo quando os dados macro estiverem ausentes.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Por que isso importa*: Em implantações reais, você pode receber códigos de barras PDF417 simples que não possuem dados macro. A verificação defensiva garante que sua aplicação continue a funcionar sem travar.

## Armadilhas comuns e boas práticas

| Problema | Por que acontece | Correção recomendada |
|----------|------------------|----------------------|
| O caminho da imagem está incorreto | `BarCodeReader` lança uma exceção de arquivo não encontrado antes de qualquer decodificação | Use `Path.Combine` e valide se o arquivo existe com `File.Exists` |
| Imagem de baixa resolução | O decodificador não consegue localizar as bordas do código de barras, resultando em zero detecções | Forneça uma resolução mínima de 300 dpi para resultados confiáveis |
| Código de barras rotacionado > 45° | Muitas bibliotecas assumem orientação vertical | Ative `reader.RecognitionOptions.RotateImage = true` se a imagem puder estar rotacionada |
| Campos macro ausentes | Tentar ler uma propriedade nula causa uma falha | Sempre verifique `null` antes de acessar propriedades macro |
| Processamento em lote grande | Recriar o leitor para cada arquivo adiciona sobrecarga | Reutilize uma única instância de `BarCodeReader` com diferentes streams ao processar muitas imagens |

## Por que usar Aspose.BarCode para um scanner de código de barras de console?

Aspose.BarCode pode decodificar **mais de 30 tipos de código de barras** e processa imagens de até **200 MP** sem carregar o arquivo inteiro na memória, alcançando taxa de **150 quadros por segundo** em uma CPU típica de 3.2 GHz. Essas capacidades quantificadas tornam‑nos uma escolha confiável para soluções de digitalização de alto volume e on‑premises, onde latência e precisão são críticas.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Ler código de barras DataMatrix C# – Gerar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Ler código de barras de imagem – Dominando a extração de região de código de barras em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Perguntas frequentes

**Q: Posso usar este scanner em um ambiente de produção?**  
A: Sim. Adquira uma licença comercial do Aspose.BarCode para remover a marca d'água de avaliação e obter suporte completo.

**Q: A biblioteca funciona no Linux e macOS?**  
A: Absolutamente. Aspose.BarCode para .NET é multiplataforma e funciona no .NET 6+ no Windows, Linux e macOS.

**Q: Como lidar com imagens muito grandes sem esgotar a memória?**  
A: Use o construtor `LoadOptions` para habilitar o modo de streaming, que processa a imagem em blocos em vez de carregá‑la totalmente na RAM.

**Q: É possível decodificar imagens criptografadas ou protegidas por senha?**  
A: O leitor pode lidar com imagens criptografadas com esquemas padrão de senha PNG/JPEG; basta fornecer a senha via `reader.ImagePassword`.

**Q: E se meu código de barras estiver parcialmente danificado?**  
A: Ative opções de correção de erros, como `reader.RecognitionOptions.CorrectErrors = true`, para melhorar a resistência a danos ou ruído.

---

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Tutoriais Relacionados

- [Como ler Pdf417 em C Exemplo completo de leitor de código de barras](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Ler múltiplos códigos de barras C Guia completo com Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decodificar código de barras de imagem com exemplo de leitor de código de barras C](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}