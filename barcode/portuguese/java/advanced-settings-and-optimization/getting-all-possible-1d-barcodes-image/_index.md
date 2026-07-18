---
date: 2026-07-18
description: Aprenda como ler códigos de barras 1D em Java com Aspose.BarCode – uma
  biblioteca rápida de decodificação de códigos de barras Java que extrai códigos
  de barras de imagens.
keywords:
- read 1d barcodes java
- java barcode decoding library
- java barcode reader example
lastmod: 2026-07-18
linktitle: ler códigos de barras 1D java
og_description: ler códigos de barras 1D java usando Aspose.BarCode, uma biblioteca
  de decodificação de códigos de barras Java de alto desempenho que lê vários códigos
  de barras de imagens rapidamente.
og_image_alt: 'Developer guide: read 1d barcodes in Java with Aspose.BarCode'
og_title: ler códigos de barras 1D java – Decodificar códigos de barras com Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to read 1D barcodes in Java with Aspose.BarCode – a fast
    Java barcode decoding library that extracts barcodes from images.
  headline: read 1d barcodes java – Decode barcodes with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. A commercial license removes all evaluation limitations and grants
      you full redistribution rights.
    question: Is Aspose.BarCode for Java suitable for commercial projects?
  - answer: Absolutely. Obtain a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/) for development and testing.
    question: Can I test the library without purchasing a license?
  - answer: The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).
    question: Where can I find the full API reference?
  - answer: Post your question on the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      where the community and Aspose engineers can assist you.
    question: How do I get help if I run into a problem?
  - answer: Yes – you can download a trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a free trial download?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- read 1d barcodes java
- Aspose.BarCode
- Java barcode processing
title: ler códigos de barras 1D java – Decodificar códigos de barras com Aspose.BarCode
url: /pt/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ler códigos de barras 1d java com Aspose.BarCode

## Introdução

Neste guia prático, você descobrirá como **ler códigos de barras 1D em Java** usando a poderosa biblioteca **Aspose.BarCode**. Seja para escanear rótulos de produtos, etiquetas de inventário ou qualquer código de barras linear incorporado em uma imagem, este tutorial orienta você em cada passo — desde a configuração do ambiente até a extração de todos os códigos de barras possíveis que a imagem contém. Ao final, você será capaz de **decodificar códigos de barras de imagens** com apenas algumas linhas de código Java.

## Respostas Rápidas
- **O que o Aspose.BarCode faz?** Ele fornece uma biblioteca de códigos de barras completa para Java que pode gerar e decodificar códigos de barras 1D/2D.  
- **Posso ler vários códigos de barras de uma única imagem?** Sim — o método `BarCodeReader.readBarCodes()` retorna todos os símbolos detectados.  
- **Preciso de uma licença para desenvolvimento?** Uma licença temporária funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do Java são suportadas?** Java 8 + (JDK 11 recomendado).  
- **Esta biblioteca é rápida o suficiente para escaneamento em tempo real?** Absolutamente — está otimizada para processamento em lote de alto desempenho.

O método `BarCodeReader.readBarCodes()` escaneia a imagem fornecida e retorna uma coleção de objetos `BarCodeResult` que representam cada código de barras detectado.

## O que é “read 1d barcodes java”?

Ler códigos de barras 1D em Java é o processo de extrair dados de códigos de barras lineares de imagens usando uma biblioteca Java. Envolve analisar uma imagem, localizar os padrões do código de barras e devolver o texto codificado juntamente com metadados como tipo de simbologia e orientação. Aspose.BarCode para Java realiza essa análise automaticamente, lidando com rotação, baixo contraste e uma ampla variedade de simbologias, permitindo que você se concentre em integrar os resultados em sua aplicação.

## Por que escolher Aspose.BarCode para decodificar códigos de barras de imagens?

Aspose.BarCode oferece precisão e velocidade líderes de mercado: pode decodificar mais de 50 + simbologias 1D e 2D em uma única passagem e processa imagens típicas de 300 dpi em menos de 0,2 segundos em um servidor padrão. A API requer apenas algumas chamadas de método, elimina dependências externas e funciona com Java 8 + enquanto suporta processamento em lote de milhares de imagens por minuto. Esses benefícios quantificados a tornam a escolha preferida para escaneamento de códigos de barras em nível empresarial.

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de que você tem o seguinte:

- **Java Development Kit (JDK)** – versão 8 ou mais recente. Baixe-o na página oficial [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – obtenha o JAR mais recente na [Aspose release page](https://releases.aspose.com/barcode/java/).  

Agora que seu ambiente está pronto, vamos começar a programar.

## Importar Namespaces

Adicione as declarações `import` necessárias para que o compilador localize as classes da Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Etapa 1: Inicializar o Objeto BarCodeReader

A classe `BarCodeReader` é o componente central do Aspose.BarCode para escanear imagens e extrair informações de códigos de barras. Crie uma instância de `BarCodeReader` apontando para o seu arquivo de imagem. O parâmetro `DecodeType` indica ao motor quais simbologias procurar; usar `CODE_128` como exemplo funciona para muitos códigos 1D comuns.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Dica profissional:** Se quiser escanear *todos* os tipos 1D suportados, passe `DecodeType.ALL_1D` em vez de uma única simbologia.

## Etapa 2: Ler Todos os Códigos de Barras Possíveis

O objeto `BarCodeResult` representa um único código de barras detectado e fornece propriedades como o texto decodificado, nome da simbologia, ângulo de rotação e coordenadas dos quatro cantos da região do código de barras. Percorra a coleção retornada por `readBarCodes()`. Para cada resultado imprimimos o texto decodificado, nome da simbologia, ângulo de detecção e as quatro coordenadas dos cantos da região do código de barras.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

O loop processa automaticamente cada código de barras encontrado, portanto você não precisa chamar o leitor repetidamente. Após o término do loop, `iCount` contém o número total de códigos de barras detectados.

## Problemas Comuns & Como Corrigi‑los

| Sintoma | Causa Provável | Solução |
|---------|----------------|----------|
| Nenhum código de barras retornado | Imagem muito borrada ou de baixo contraste | Pré‑processar a imagem (aumentar contraste, binarizar) antes de enviá‑la ao leitor. |
| Symbology incorreta relatada | `DecodeType` incorreto usado | Use `DecodeType.ALL_1D` para que o motor auto‑detecte qualquer tipo 1D. |
| Valores de ângulo incorretos | Imagem rotacionada | A API já devolve o ângulo de rotação; você pode girar a imagem de volta, se necessário. |

## Perguntas Frequentes

**Q: O Aspose.BarCode para Java é adequado para projetos comerciais?**  
A: Sim. Uma licença comercial remove todas as limitações de avaliação e concede direitos completos de redistribuição.

**Q: Posso testar a biblioteca sem comprar uma licença?**  
A: Absolutamente. Obtenha uma licença temporária na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) para desenvolvimento e testes.

**Q: Onde posso encontrar a referência completa da API?**  
A: A documentação abrangente está disponível [aqui](https://reference.aspose.com/barcode/java/).

**Q: Como obtenho ajuda se encontrar um problema?**  
A: Publique sua pergunta no [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) onde a comunidade e engenheiros da Aspose podem ajudar.

**Q: Existe um download de avaliação gratuito?**  
A: Sim — você pode baixar uma versão de avaliação na [Aspose releases page](https://releases.aspose.com/).

## Conclusão

Você aprendeu agora como **ler códigos de barras 1D em Java** usando Aspose.BarCode, uma robusta **biblioteca de códigos de barras para Java** que torna a decodificação de códigos de barras de arquivos de imagem simples e confiável. Integre este trecho em suas próprias aplicações para automatizar leituras de inventário, validação de ingressos ou qualquer cenário onde códigos de barras lineares apareçam em imagens.

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.BarCode 24.11 for Java  
**Author:** Aspose

## Tutoriais Relacionados

- [Ler Código de Barras Java: Leitor de Código de Barras de Alto Desempenho para Processamento de Imagem Mais Rápido](/barcode/java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/)
- [Ler Código de Barras de Imagem – Dominando a Extração de Região de Código de Barras em Java com Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/extracting-barcode-region-information/)
- [Aspose.Barcode Java – Obtendo a Qualidade de Reconhecimento de Código de Barras em Percentual](/barcode/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}