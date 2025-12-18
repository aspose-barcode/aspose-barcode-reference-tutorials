---
date: 2025-12-18
description: Aprenda a criar imagens de código de barras Codabar e veja um exemplo
  de leitor de código de barras Java usando Aspose.BarCode. Gere e reconheça códigos
  de barras sem esforço com este guia passo a passo.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Como criar imagem de código de barras Codabar com checksum em Java
url: /pt/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras codabar com checksum em Java

## Introdução

Neste tutorial, você aprenderá como **criar imagem de código de barras codabar** com checksum em Java usando Aspose.BarCode. Vamos percorrer a geração de um código de barras CodaBar, habilitar o checksum e, em seguida, lê‑lo de volta com um **exemplo de leitor de código de barras java**. Ao final, você terá um trecho de código pronto‑para‑usar que pode inserir em qualquer projeto Java.

## Respostas Rápidas
- **O que o checksum faz?** Ele valida a integridade dos dados do código de barras durante a leitura.  
- **Qual biblioteca é necessária?** Aspose.BarCode for Java.  
- **Preciso de licença para desenvolvimento?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Posso personalizar a aparência do código de barras?** Sim – cor, tamanho e fonte podem ser alterados via parâmetros do gerador.  
- **Isso é compatível com todas as versões do Java?** A biblioteca suporta Java 8 e superiores.

## O que é um código de barras CodaBar?

CodaBar é uma simbologia linear (unidimensional) amplamente usada em bibliotecas, bancos de sangue e varejo. Ela codifica dados numéricos e alguns caracteres especiais, tornando‑a ideal para etiquetas simples e legíveis por máquina. Adicionar um checksum (Mod 10) melhora a precisão da leitura, especialmente em impressões de baixa qualidade.

## Por que usar Aspose.BarCode para Java?

Aspose.BarCode oferece um **exemplo de leitor de código de barras java** que abstrai os detalhes de baixo nível da geração e reconhecimento de códigos de barras. Ele fornece:

* Controle total sobre os modos de checksum.  
* Integração perfeita com IDEs Java.  
* Documentação extensa e suporte.  

## Pré‑requisitos

Antes de começarmos, certifique‑se de que você tem:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.BarCode for Java. Você pode baixá‑la [aqui](https://releases.aspose.com/barcode/java/).  
- Um entendimento básico de programação Java.  

## Importar Pacotes

Em seu projeto Java, importe as classes necessárias para trabalhar com Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia passo a passo

### Passo 1: Configurar o Ambiente

Crie um novo projeto Java e adicione o JAR do Aspose.BarCode ao seu caminho de compilação. Defina uma pasta onde as imagens geradas serão salvas.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Passo 2: Gerar uma imagem de código de barras CodaBar com checksum

Instancie o `BarcodeGenerator`, habilite o checksum, escolha o modo Mod 10 e salve a imagem.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### Passo 3: Exemplo de leitor de código de barras Java – Reconhecer o código de barras

Agora leia o código de barras de volta, ativando a validação de checksum para garantir que os dados estejam corretos.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Executar o código exibirá o texto decodificado, o tipo de simbologia e o checksum calculado, confirmando que o código de barras foi gerado e validado corretamente.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Checksum validation fails** | Verifique se `EnableChecksum` está definido como `YES` e se `CodabarChecksumMode` corresponde ao modo usado durante a geração (Mod 10). |
| **File not found error** | Certifique‑se de que `dataDir` aponta para uma pasta existente e que a imagem gerada (`Codabar_Mod10.png`) está salva lá antes da leitura. |
| **Unsupported Java version** | Use Java 8 ou superior; versões mais antigas podem não ter as APIs necessárias. |

## Perguntas Frequentes

**Q: O Aspose.BarCode é compatível com todas as versões do Java?**  
A: Aspose.BarCode foi projetado para funcionar com Java 8 e versões mais recentes. Consulte a documentação oficial para compatibilidade detalhada.

**Q: Posso personalizar a aparência do código de barras gerado?**  
A: Sim, você pode modificar cores, fontes e o formato da imagem via API de parâmetros do gerador.

**Q: Licenças temporárias estão disponíveis para fins de teste?**  
A: Sim, você pode obter uma licença temporária para Aspose.BarCode [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso encontrar suporte adicional e recursos?**  
A: Visite o [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para suporte da comunidade e discussões.

**Q: Existe um teste gratuito disponível?**  
A: Sim, você pode explorar os recursos do Aspose.BarCode baixando o teste gratuito [aqui](https://releases.aspose.com/).

---

**Última atualização:** 2025-12-18  
**Testado com:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}