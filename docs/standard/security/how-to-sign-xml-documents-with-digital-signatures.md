---
title: '방법: 디지털 서명으로 XML 문서 서명'
description: 디지털 서명으로 XML 문서에 서명 하는 방법에 대해 알아봅니다. .NET의 System.xml 네임 스페이스에서 클래스를 사용 합니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSACryptoServiceProvider class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: 97bd23182ed54b899b76dbf43e179fe0c94b011d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598569"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a>방법: 디지털 서명으로 XML 문서 서명
<xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 또는 XML 문서의 일부를 디지털 서명으로 서명할 수 있습니다.  XML 디지털 서명(XMLDSIG)을 사용하면 서명된 후 데이터가 변경되지 않았음을 확인할 수 있습니다.  XMLDSIG 표준에 대 한 자세한 내용은 W3C (World Wide Web 컨소시엄) 권장 사항 [XML 서명 구문 및 처리](https://www.w3.org/TR/xmldsig-core/)를 참조 하세요.  
  
 이 절차의 코드 예제에서는 전체 XML 문서를 디지털 서명 하 고 <> 요소의 문서에 서명을 첨부 하는 방법을 보여 줍니다 `Signature` .  이 예제에서는 RSA 서명 키를 만들고, 보안 키 컨테이너에 키를 추가한 다음 키를 사용하여 XML 문서에 디지털 서명합니다.  그런 다음 키를 검색하여 XML 디지털 서명을 확인하거나 다른 XML 문서에 서명하는 데 사용할 수 있습니다.  
  
 이 절차를 사용 하 여 만든 XML 디지털 서명을 확인 하는 방법에 대 한 자세한 내용은 [방법: Xml 문서의 디지털 서명 확인](how-to-verify-the-digital-signatures-of-xml-documents.md)을 참조 하세요.  
  
### <a name="to-digitally-sign-an-xml-document"></a>XML 문서에 디지털 서명하려면  
  
1. <xref:System.Security.Cryptography.CspParameters> 개체를 만들고 키 컨테이너의 이름을 지정합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스를 사용하여 비대칭 키를 생성합니다.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스의 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 자동으로 키 컨테이너에 저장됩니다.  이 키는 XML 문서에 서명하는 데 사용됩니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. 디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.  <xref:System.Xml.XmlDocument> 개체는 암호화할 XML 요소를 포함합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. 새 <xref:System.Security.Cryptography.Xml.SignedXml> 개체를 만들고 <xref:System.Xml.XmlDocument> 개체를 전달합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <xref:System.Security.Cryptography.Xml.SignedXml> 개체에 서명 RSA 키를 추가합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. 서명할 항목을 설명하는 <xref:System.Security.Cryptography.Xml.Reference> 개체를 만듭니다.  전체 문서에 서명하려면 <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> 속성을 `""`로 설정합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> 개체를 <xref:System.Security.Cryptography.Xml.Reference> 개체에 추가합니다.  변환을 통해 검증 도구는 서명자가 사용한 것과 동일한 방식으로 XML 데이터를 나타낼 수 있습니다.  XML 데이터는 다양한 방식으로 표시될 수 있으므로 이 단계는 검증에 중요합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <xref:System.Security.Cryptography.Xml.Reference> 개체를 <xref:System.Security.Cryptography.Xml.SignedXml> 개체에 추가합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> 메서드를 호출하여 서명을 컴퓨팅합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. 시그니처의 XML 표시 (<`Signature`> 요소)를 검색 하 여 새 개체에 저장 <xref:System.Xml.XmlElement> 합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <xref:System.Xml.XmlDocument> 개체에 요소를 추가합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. 문서를 저장합니다.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a>예제  
 이 예제에서는 `test.xml`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.  `test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- 이 예제를 컴파일하려면 `System.Security.dll`에 대한 참조를 포함해야 합니다.  
  
- <xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 비대칭 키 쌍의 프라이빗 키를 일반 텍스트로 저장하거나 전송하지 마세요.  대칭 및 비대칭 암호화 키에 대 한 자세한 내용은 [암호화 및 암호 해독을 위한 키 생성](generating-keys-for-encryption-and-decryption.md)을 참조 하세요.  
  
 소스 코드에 직접 프라이빗 키를 포함하지 마세요.  [Ildasm.exe (IL 디스어셈블러)](../../framework/tools/ildasm-exe-il-disassembler.md) 를 사용 하거나 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 어셈블리에서 포함 된 키를 쉽게 읽을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Security.Cryptography.Xml>
- [방법: XML 문서의 디지털 서명 확인](how-to-verify-the-digital-signatures-of-xml-documents.md)
