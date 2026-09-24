---
date: 2026-08-02
description: Guia passo a passo sobre como ler o código de barras DataMatrix C# e
  gerar a imagem do código de barras C# usando Aspose.BarCode for .NET com codificação
  automática.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: Modo de Codificação DataMatrix (Auto)
og_description: Aprenda como ler o código de barras DataMatrix C# e gerá-lo no modo
  automático usando Aspose.BarCode for .NET. Este tutorial cobre a configuração, o
  código e a solução de problemas.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Como ler código de barras DataMatrix C# – Modo automático
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Como ler código de barras DataMatrix C# – Modo automático
url: /pt/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras DataMatrix C# – Modo Auto

No mundo digital de hoje, que se move rapidamente, **como ler datamatrix** de forma rápida e confiável é essencial para rastreamento de inventário, manuseio seguro de documentos e muitos outros cenários empresariais. Este tutorial orienta você a gerar um código de barras DataMatrix no modo *Auto* com Aspose.BarCode para .NET e, em seguida, mostra como ler esse código de volta em C#. Seja seguindo um guia de tutorial de código de barras ou precisando de um exemplo de código pronto para uso, você terminará com uma solução pronta para produção que pode ser inserida em qualquer projeto .NET.

## Respostas Rápidas
- **O que o modo “Auto” faz?** Ele permite que o Aspose.BarCode selecione automaticamente o melhor esquema de codificação para seus dados.  
- **Qual biblioteca é necessária?** Aspose.BarCode para .NET (versão de avaliação gratuita disponível).  
- **Posso ler o código de barras no mesmo aplicativo?** Sim – use `BarCodeReader` com `DecodeType.DataMatrix`.  
- **Preciso de licença para produção?** Uma licença comercial é necessária para uso em produção.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` é a classe do Aspose.BarCode para escanear imagens e recuperar informações de código de barras.

## O que é ler código de barras DataMatrix C#?
Ler um código de barras DataMatrix em C# significa decodificar a matriz bidimensional de módulos pretos e brancos de volta ao texto ou dados originais. Aspose.BarCode abstrai o processamento de imagem de baixo nível, permitindo que você se concentre na lógica de negócios enquanto a biblioteca lida automaticamente com correção de erros, seleção de tamanho de símbolo e suporte a Unicode.

## Por que usar Aspose.BarCode para gerar imagem de código de barras C#?
Aspose.BarCode seleciona automaticamente a codificação ideal, suporta **30+ simbologias de código de barras**, e pode gerar símbolos DataMatrix de até **1558 × 1558 módulos** – muito maiores que a maioria dos concorrentes. Ele funciona em Windows, Linux e macOS sem dependências nativas, oferecendo uma única API multiplataforma tanto para geração quanto para leitura.

## Pré-requisitos

1. **Ambiente .NET** – Instale a versão mais recente do runtime .NET a partir do [.NET website](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode para .NET** – Baixe a biblioteca a partir do [website](https://releases.aspose.com/barcode/net/).  

## Importando Namespaces
O namespace `Aspose.BarCode` contém todas as classes necessárias para criação e leitura de códigos de barras. Importe-o no início do seu arquivo antes de qualquer outro código.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Agora que os namespaces estão definidos, vamos percorrer o código passo a passo.

## Etapa 1: Definir o Caminho do Diretório
Escolha uma pasta onde o PNG gerado (ou qualquer formato suportado) será salvo. Esse caminho pode ser absoluto ou relativo ao seu projeto.

```csharp
string path = "Your Directory Path";
```

Substitua `"Your Directory Path"` pela pasta que preferir. Manter a pasta de saída configurável torna o tutorial reutilizável em diferentes ambientes.

## Etapa 2: Criar um código de barras DataMatrix no modo Auto
`DataMatrixEncodeMode.Auto` indica ao gerador que selecione automaticamente o esquema de codificação ideal para os dados fornecidos.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Sinta-se à vontade para substituir o texto de exemplo por qualquer string que você precise **como gerar datamatrix**. O modo auto mudará automaticamente entre Base‑256, ASCII ou outros esquemas para obter o menor símbolo possível.

## Etapa 3: Ler o código de barras (ler código de barras DataMatrix C#)
`BarCodeReader` é a classe do Aspose.BarCode para escanear imagens e recuperar informações de código de barras. Ele suporta leitura a partir de streams, arquivos e objetos bitmap, tornando‑o ideal para cenários de **ler código de barras a partir de arquivo**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Este trecho decodifica a imagem que acabamos de gerar e imprime o texto original no console, demonstrando um ciclo completo de geração e leitura.

## Problemas Comuns e Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| **Código de barras não detectado** | Resolução da imagem muito baixa | Aumente `XDimension.Pixels` (por exemplo, para 6) |
| **Caracteres corrompidos** | Codificação ECI incorreta | Defina `ECIEncoding` para corresponder aos seus dados (UTF‑8, ASCII, etc.) |
| **Exceção em `ReadBarCodes`** | Bitmap descartado antes da leitura | Mantenha a instância `Bitmap` viva até após a leitura |

## Perguntas Frequentes

**Q: O que é o modo de codificação DataMatrix "Auto"?**  
A: Ele permite que o Aspose.BarCode selecione automaticamente o método de codificação ideal para os dados fornecidos, simplificando o processo de **como gerar datamatrix**.

**Q: Posso personalizar as dimensões do código de barras gerado?**  
A: Sim – ajuste `generator.Parameters.Barcode.XDimension.Pixels` para mudar o tamanho do módulo.

**Q: O Aspose.BarCode para .NET é adequado para uso comercial?**  
A: Absolutamente. Compre uma licença no [website](https://purchase.aspose.com/buy).

**Q: Existe uma versão de avaliação gratuita?**  
A: Sim, você pode explorar o Aspose.BarCode com uma avaliação gratuita neste [link](https://releases.aspose.com/).

**Q: Quais opções de codificação estão disponíveis para códigos de barras DataMatrix?**  
A: O Aspose.BarCode suporta UTF‑8, ASCII e outras codificações ECI; defina o valor desejado via `ECIEncoding`.

## Conclusão

Agora você tem um exemplo completo e pronto para produção que **lê código de barras DataMatrix C#**, gera o código no modo Auto e verifica o resultado — tudo usando Aspose.BarCode para .NET. Experimente diferentes textos, tamanhos e configurações ECI para atender ao seu cenário específico, e consulte a [documentação](https://reference.aspose.com/barcode/net/) oficial para personalizações mais avançadas.

---

**Última atualização:** 2026-08-02  
**Testado com:** Aspose.BarCode 24.12 para .NET  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como ler códigos de barras DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/)
- [Configuração de Structured Append do DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Programação do leitor DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}