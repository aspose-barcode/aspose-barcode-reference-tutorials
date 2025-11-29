---
date: 2025-11-29
description: Aprenda a ler códigos de barras 1D em Java com Aspose.BarCode – decodifique
  códigos de barras de imagens rapidamente usando uma biblioteca robusta de códigos
  de barras para Java.
language: pt
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Como ler códigos de barras 1D em Java usando Aspose.BarCode
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ler códigos de barras 1d java com Aspose.BarCode

## Introdução

Neste guia prático você descobrirá como **ler códigos de barras 1D em Java** usando a poderosa biblioteca **Aspose.BarCode**. Seja para escanear rótulos de produtos, etiquetas de estoque ou qualquer código de barras linear incorporado em uma imagem, este tutorial o conduzirá por todas as etapas — desde a configuração do ambiente até a extração de todos os códigos de barras possíveis que a imagem contém. Ao final, você será capaz de **decodificar códigos de barras de arquivos de imagem** com apenas algumas linhas de código Java.

## Respostas rápidas
- **O que a Aspose.BarCode faz?** Ela fornece uma biblioteca completa de códigos de barras para Java que pode gerar e decodificar códigos de barras 1D/2D.  
- **Posso ler vários códigos de barras de uma única imagem?** Sim — o método `BarCodeReader.readBarCodes()` retorna todos os símbolos detectados.  
- **Preciso de licença para desenvolvimento?** Uma licença temporária funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do Java são suportadas?** Java 8 + (JDK 11 recomendado).  
- **Esta biblioteca é rápida o suficiente para escaneamento em tempo real?** Absolutamente — ela é otimizada para processamento em lote de alto desempenho.

## O que é “read 1d barcodes java”?

Ler códigos de barras 1D em Java significa usar uma **biblioteca de códigos de barras para Java** para analisar uma imagem, localizar padrões de códigos de barras lineares e devolver o texto codificado juntamente com metadados como tipo de simbologia e orientação. Aspose.BarCode abstrai o trabalho pesado de processamento de imagem, permitindo que você se concentre na lógica de negócios.

## Por que escolher Aspose.BarCode para decodificar códigos de barras de imagem?

- **Amplo suporte a simbologias** — mais de 50 tipos 1D e 2D.  
- **Detecção precisa** — funciona mesmo com códigos de baixa contraste ou rotacionados.  
- **API simples** — poucas chamadas de método fornecem todos os resultados.  
- **Sem dependências externas** — puro Java, fácil de incorporar em qualquer projeto.  

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você possui o seguinte:

- **Java Development Kit (JDK)** — versão 8 ou superior. Baixe-o na página oficial do [Oracle JDK](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** — obtenha o JAR mais recente na [página de lançamentos da Aspose](https://releases.aspose.com/barcode/java/).  

Com o ambiente pronto, vamos começar a programar.

## Importar namespaces

Adicione as instruções `import` necessárias para que o compilador localize as classes da Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Etapa 1: Inicializar o objeto BarCodeReader

Crie uma instância de `BarCodeReader` apontando para o seu arquivo de imagem. O parâmetro `DecodeType` informa ao motor quais simbologias procurar; usar `CODE_128` como exemplo funciona para muitos códigos 1D comuns.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Dica profissional:** Se quiser escanear *todos* os tipos 1D suportados, passe `DecodeType.ALL_1D` em vez de uma única simbologia.

## Etapa 2: Ler todos os códigos de barras possíveis

Itere sobre a coleção retornada por `readBarCodes()`. Para cada `BarCodeResult` imprimimos o texto decodificado, o nome da simbologia, o ângulo de detecção e as coordenadas dos quatro cantos da região do código de barras.

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

O loop processa automaticamente cada código de barras encontrado, portanto não é necessário chamar o leitor repetidamente. Ao final do loop, `iCount` contém o número total de códigos de barras detectados.

## Problemas comuns e como corrigi‑los

| Sintoma | Causa provável | Solução |
|---------|----------------|----------|
| Nenhum código de barras retornado | Imagem muito borrada ou de baixo contraste | Pré‑processar a imagem (aumentar contraste, binarizar) antes de enviá‑la ao leitor. |
| Tipo de simbologia incorreto | `DecodeType` usado está errado | Use `DecodeType.ALL_1D` para que o motor detecte automaticamente qualquer tipo 1D. |
| Valores de ângulo incorretos | Imagem rotacionada | A API já devolve o ângulo de rotação; você pode girar a imagem de volta, se necessário. |

## Perguntas frequentes

**P: A Aspose.BarCode para Java é adequada para projetos comerciais?**  
R: Sim. Uma licença comercial remove todas as limitações de avaliação e concede direitos completos de redistribuição.

**P: Posso testar a biblioteca sem comprar uma licença?**  
R: Absolutamente. Obtenha uma licença temporária na [página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/) para desenvolvimento e testes.

**P: Onde encontro a referência completa da API?**  
R: A documentação abrangente está disponível [aqui](https://reference.aspose.com/barcode/java/).

**P: Como obtenho ajuda se encontrar um problema?**  
R: Publique sua dúvida no [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), onde a comunidade e os engenheiros da Aspose podem auxiliá‑lo.

**P: Existe um download de avaliação gratuito?**  
R: Sim — você pode baixar a versão de avaliação na [página de lançamentos da Aspose](https://releases.aspose.com/).

## Conclusão

Agora você aprendeu a **ler códigos de barras 1D em Java** usando Aspose.BarCode, uma robusta **biblioteca de códigos de barras para Java** que torna a decodificação de códigos de barras de arquivos de imagem simples e confiável. Integre este trecho ao seu próprio aplicativo para automatizar leituras de estoque, validação de ingressos ou qualquer cenário onde códigos de barras lineares apareçam em imagens.

---

**Última atualização:** 2025-11-29  
**Testado com:** Aspose.BarCode 24.11 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}