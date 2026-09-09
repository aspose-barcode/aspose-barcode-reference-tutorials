---
date: 2026-04-08
description: Aprenda a ler códigos de barras de PDF em Java usando Aspose.BarCode.
  Este guia também mostra como gerar imagens de código de barras em Java e extrair
  imagens de PDF em Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Reconhecendo códigos de barras de PDF
second_title: Aspose.BarCode Java API
title: Como ler código de barras de PDF em Java usando Aspose.BarCode
url: /pt/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler código de barras de PDF em Java

## Introdução

Bem‑vindo ao nosso guia passo a passo sobre **como ler código de barras de PDF em Java** usando Aspose.BarCode. Os códigos de barras são essenciais para automatizar a captura de dados e, com Aspose.BarCode, você pode detectá‑los perfeitamente dentro de documentos PDF. Neste tutorial, vamos guiá‑lo por tudo o que você precisa — desde a configuração de licenças até a geração de uma imagem de código de barras Java, sua adição a um PDF, a extração de imagens de PDF Java e, finalmente, a leitura do código de barras.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Posso gerar uma imagem de código de barras em Java?** Sim – a classe `BarcodeGenerator` permite criar imagens PNG/JPEG.  
- **Como as imagens são extraídas de um PDF?** Use `PdfExtractor` do Aspose.PDF.  
- **Qual tipo de código de barras é demonstrado?** CODE‑39 (padrão).  
- **Preciso de uma licença?** Uma licença válida do Aspose.BarCode e do Aspose.PDF é necessária para uso em produção.

## Por que usar Aspose.BarCode para Java?
- **Alta precisão** – suporta dezenas de simbologias e funciona em imagens de baixa resolução.  
- **Sem dependências externas** – Java puro, sem bibliotecas nativas.  
- **Integração total com PDF** – combine com Aspose.PDF para ler ou incorporar códigos de barras diretamente em arquivos PDF.

## Pré-requisitos

Antes de mergulhar no código, certifique‑se de que você tem:

1. **Licença Aspose.BarCode para Java** – obtenha uma em [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Licença Aspose.PDF** – necessária para manipulação de PDF; você pode solicitar uma licença [aqui](https://purchase.aspose.com/temporary-license/).  
3. **Biblioteca Aspose.BarCode** – faça o download do JAR mais recente [aqui](https://releases.aspose.com/barcode/java/).  

Agora que você tem os pré‑requisitos necessários, vamos importar os pacotes requeridos e começar a codificar.

## Importar Pacotes

No seu projeto Java, adicione as importações do Aspose.BarCode e Aspose.PDF. Este bloco permanece inalterado em relação ao tutorial original:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Etapa 1: Gerar uma imagem de código de barras Java

Primeiro, criamos uma imagem de código de barras que mais tarde incorporaremos em um PDF. Isso demonstra a capacidade de **gerar imagem de código de barras java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Etapa 2: Criar um PDF e adicionar a imagem do código de barras

Em seguida, criamos um novo documento PDF e inserimos a imagem do código de barras que acabamos de gerar.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Etapa 3: Extrair imagens de PDF Java

Com o PDF pronto, precisamos extrair a imagem incorporada para que o código de barras possa ser lido. Isso usa **extrair imagens de pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Etapa 4: Reconhecer o código de barras a partir das imagens extraídas

Finalmente, enviamos cada imagem extraída para `BarCodeReader` para recuperar o texto codificado.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Repita estas etapas conforme necessário, ajustando nomes de arquivos e caminhos para se adequar à estrutura do seu projeto.

## Problemas Comuns e Soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Nenhum código de barras detectado** | Qualidade da imagem muito baixa ou código de barras muito pequeno. | Aumente a resolução da imagem ao salvar (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` lança uma exceção** | Arquivo PDF não encontrado ou caminho incorreto. | Verifique se `strPdfDoc` aponta para um arquivo existente e se a aplicação tem permissões de leitura. |
| **Licença não aplicada** | Componentes Aspose rodam em modo de avaliação, limitando a saída. | Carregue os arquivos de licença no início do seu programa: `new License().setLicense("Aspose.BarCode.lic");` e de forma semelhante para Aspose.PDF. |

## Perguntas Frequentes (FAQs)

### Q: Posso usar Aspose.BarCode para Java sem licença?
Embora o Aspose.BarCode possa ser usado sem licença, recomenda‑se obter uma para funcionalidade completa e para cumprir os termos de licenciamento.

### Q: Como posso obter uma licença temporária para Aspose.BarCode para Java?
Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Q: Existem limitações nos tipos de código de barras suportados pelo Aspose.BarCode?
Aspose.BarCode suporta uma ampla variedade de tipos de código de barras. Consulte a documentação para obter a lista completa.

### Q: Existe uma versão de avaliação disponível para Aspose.BarCode para Java?
Sim, você pode baixar a versão de avaliação [aqui](https://releases.aspose.com/).

### Q: Onde posso buscar suporte ou fazer perguntas sobre Aspose.BarCode para Java?
Visite o [fórum](https://forum.aspose.com/c/barcode/13) do Aspose.BarCode para suporte e discussões.

## Conclusão

Parabéns! Você aprendeu como **ler código de barras de PDF em Java** usando Aspose.BarCode, como **gerar imagem de código de barras Java**, e como **extrair imagens de PDF Java** para processamento adicional. Sinta‑se à vontade para explorar recursos adicionais, como processamento em lote, manipulação de diferentes simbologias de código de barras ou integração com outros produtos Aspose. Para mais detalhes, consulte a [documentação](https://reference.aspose.com/barcode/java/) oficial.

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}