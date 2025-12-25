---
date: 2025-12-25
description: Aprenda a extrair texto de imagens de códigos de barras, especificamente
  PDF417 com caracteres chineses, usando Aspose.BarCode para Java. Siga nosso guia
  passo a passo sobre como ler os dados do código de barras de forma eficiente.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Extrair Texto de Código de Barras: PDF417 Caracteres Chineses em Java'
url: /pt/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair Texto de Código de Barras: PDF417 com Caracteres Chineses em Java

## Introdução

Integrar o reconhecimento de códigos de barras em aplicações Java é uma habilidade valiosa, especialmente quando você precisa **extrair texto de imagens de código de barras** que contêm dados multilíngues. Neste tutorial, vamos guiá‑lo no uso do Aspose.BarCode para Java para reconhecer códigos de barras PDF417 com caracteres chineses. Ao final, você saberá exatamente como ler os dados do código de barras e decodificá‑los em texto legível.

## Respostas Rápidas
- **Qual biblioteca suporta PDF417 com caracteres chineses?** Aspose.BarCode para Java.  
- **Qual conjunto de caracteres é necessário para a decodificação chinesa?** MS936 (GBK).  
- **Preciso de licença para uso em produção?** Sim, é necessária uma licença comercial.  
- **Posso executar isso em qualquer versão do Java?** Funciona com Java 8 ou superior.  
- **Existe uma versão de avaliação gratuita?** Absolutamente – faça o download no site da Aspose.

## O que é “extrair texto de código de barras”?

Extrair texto de um código de barras significa converter os dados codificados de volta ao seu formato original legível por humanos. Para códigos de barras PDF417 que armazenam caracteres chineses, isso também envolve selecionar a codificação de caracteres correta para que os bytes correspondam aos glifos adequados.

## Por que usar Aspose.BarCode para Java?

Aspose.BarCode oferece suporte robusto a uma ampla variedade de simbologias de código de barras, incluindo PDF417, e lida com conjuntos de caracteres complexos prontamente. Ele abstrai o processamento de imagem de baixo nível, permitindo que você se concentre na lógica de negócios em vez das intricacias da decodificação.

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – recomenda‑se a versão mais recente.  
2. **Aspose.BarCode para Java** – faça o download [aqui](https://releases.aspose.com/barcode/java/).  
3. **Uma imagem de código de barras PDF417** que contenha caracteres chineses (por exemplo, `barcode.png`).

## Importar Pacotes

No seu projeto Java, importe as classes necessárias para trabalhar com Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Etapa 1: Definir o Diretório do Documento

Especifique a pasta onde sua imagem de código de barras está localizada:

```java
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho real na sua máquina.

## Etapa 2: Carregar a Imagem do Código de Barras

Crie uma instância de `BarCodeReader` que aponte para o arquivo PNG e indique ao leitor que procure a simbologia PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Etapa 3: Ler o Código de Barras

Itere pelos resultados de detecção, extraia o array de bytes bruto e decodifique‑o usando o conjunto de caracteres GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Este loop **extrai texto do código de barras** e imprime os caracteres chineses decodificados no console.

## Como ler código de barras com PDF417?

O código acima demonstra **como ler dados de código de barras** passo a passo:

1. **Inicializar** o leitor com o `DecodeType` correto.  
2. **Iterar** sobre cada `BarCodeResult` retornado.  
3. **Converter** os bytes brutos usando o charset apropriado (`MS936` para chinês).  

Se o seu código de barras contiver outros idiomas, basta trocar o charset para o que corresponde aos seus dados.

## Problemas Comuns & Soluções

| Problema | Solução |
|----------|---------|
| Caracteres corrompidos após a decodificação | Verifique se está usando o charset correto (`MS936` para GBK). |
| Nenhum código de barras detectado | Garanta que a qualidade da imagem seja alta e que o código não esteja girado; você pode pré‑processar a imagem se necessário. |
| Vários resultados retornados | PDF417 pode armazenar múltiplos segmentos; itere por todos os resultados conforme mostrado. |

## Perguntas Frequentes (FAQs)

### Posso usar Aspose.BarCode para Java em projetos comerciais?
Sim, você pode usar Aspose.BarCode para Java em projetos comerciais. Para detalhes de licenciamento, visite [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de avaliação gratuita?
Sim, você pode acessar uma avaliação gratuita do Aspose.BarCode para Java [aqui](https://releases.aspose.com/).

### Como posso obter suporte para Aspose.BarCode?
Visite o fórum do Aspose.BarCode [aqui](https://forum.aspose.com/c/barcode/13) para qualquer suporte ou dúvidas.

### Posso obter uma licença temporária para testes?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde encontro a documentação?
A documentação está disponível [aqui](https://reference.aspose.com/barcode/java/).

**Perguntas & Respostas Adicionais**

**P: E se minha imagem de código de barras estiver no formato JPEG?**  
R: O `BarCodeReader` funciona com JPEG, PNG, BMP e outros formatos de imagem comuns—basta mudar a extensão do arquivo conforme necessário.

**P: Posso decodificar códigos de barras a partir de um stream em vez de um arquivo?**  
R: Sim, você pode passar um `InputStream` ao construtor do `BarCodeReader` para decodificação em tempo real.

**P: O Aspose.BarCode suporta outros conjuntos de caracteres?**  
R: Absolutamente. Use `Charset.forName("<seu‑charset>")` para decodificar bytes em UTF‑8, ISO‑8859‑1, etc.

## Conclusão

Agora você aprendeu como **extrair texto de imagens de código de barras**, especificamente códigos de barras PDF417 contendo caracteres chineses, usando Aspose.BarCode para Java. Essa capacidade abre portas para sistemas de inventário multilíngues, automação de documentos e muito mais. Sinta‑se à vontade para experimentar outras simbologias e conjuntos de caracteres para ampliar o alcance da sua aplicação.

---

**Última atualização:** 2025-12-25  
**Testado com:** Aspose.BarCode para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}