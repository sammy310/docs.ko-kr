---
title: '방법: 비대칭 키를 사용하여 XML 요소 해독'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSA class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: 0456c89987b37840daa1c84342528d11c6da73a4
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822232"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>방법: 비대칭 키를 사용하여 XML 요소 해독

<xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화 및 암호 해독할 수 있습니다.  XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.  XML 암호화 표준에 대 한 자세한 내용은 W3C (World Wide Web 컨소시엄) 권장 사항 [XML 서명 구문 및 처리](https://www.w3.org/TR/xmldsig-core/)를 참조 하십시오.  

> [!NOTE]
> 이 문서의 코드는 Windows에 적용 됩니다.

이 절차의 예제에서는 [방법: 비대칭 키로 Xml 요소 암호화](how-to-encrypt-xml-elements-with-asymmetric-keys.md)에 설명 된 방법을 사용 하 여 암호화 된 xml 요소를 해독 합니다.  <`EncryptedData`> 요소를 찾고 요소를 해독 한 다음 요소를 원래의 일반 텍스트 XML 요소로 바꿉니다.  
  
이 예제에서는 두 키를 사용하여 XML 요소를 암호 해독합니다.  키 컨테이너에서 이전에 생성 된 RSA 개인 키를 검색 한 다음 RSA 키를 사용 하 여 <> 요소의 <> 요소에 저장 된 세션 키의 암호를 해독 `EncryptedKey` `EncryptedData` 합니다.  그런 다음 예제에서는 세션 키를 사용하여 XML 요소를 암호 해독합니다.  
  
이 예제는 여러 애플리케이션이 암호화된 데이터를 공유해야 하거나 애플리케이션이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>비대칭 키를 사용하여 XML 요소를 암호 해독하려면  
  
1. <xref:System.Security.Cryptography.CspParameters> 개체를 만들고 키 컨테이너의 이름을 지정합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 사용하여 컨테이너에서 이전에 생성된 비대칭 키를 검색합니다.  <xref:System.Security.Cryptography.RSACryptoServiceProvider> 생성자에 <xref:System.Security.Cryptography.CspParameters> 개체를 전달하면 키가 자동으로 키 컨테이너에서 검색됩니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. 새 <xref:System.Security.Cryptography.Xml.EncryptedXml> 개체를 만들어 문서를 암호 해독합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. 암호 해독해야 하는 문서 내의 요소와 RSA 키를 연결하는 키/이름 매핑을 추가합니다.  문서를 암호화할 때 사용한 것과 동일한 키 이름을 사용해야 합니다.  이 이름은 1단계에서 지정한, 키 컨테이너에서 키를 식별하는 데 사용되는 이름과 별개입니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. 메서드를 호출 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 하 여 <> 요소의 암호를 해독 `EncryptedData` 합니다.  이 메서드는 RSA 키를 사용하여 세션 키를 암호 해독하고 자동으로 세션 키를 사용하여 XML 요소를 암호 해독합니다.  또한 <`EncryptedData`> 요소를 원래 일반 텍스트로 자동으로 바꿉니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. XML 문서를 저장합니다.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>예제

이 예제에서는 `test.xml`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.  또한 `test.xml` [방법: 비대칭 키로 Xml 요소 암호화](how-to-encrypt-xml-elements-with-asymmetric-keys.md)에 설명 된 기술을 사용 하 여 암호화 된 xml 요소가에 포함 되어 있다고 가정 합니다.  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- .NET Framework를 대상으로 하는 프로젝트에서에 대 한 참조를 포함 `System.Security.dll` 합니다.

- .NET Core 또는 .NET 5를 대상으로 하는 프로젝트에서 NuGet 패키지 [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml)를 설치 합니다.
  
- <xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.  
  
## <a name="net-security"></a>.NET 보안  

대칭 암호화 키를 일반 텍스트로 저장하거나 컴퓨터 간에 일반 텍스트로 대칭 키를 전송하지 마세요.  또한 비대칭 키 쌍의 프라이빗 키를 일반 텍스트로 저장하거나 전송하지 마세요.  대칭 및 비대칭 암호화 키에 대 한 자세한 내용은 [암호화 및 암호 해독을 위한 키 생성](generating-keys-for-encryption-and-decryption.md)을 참조 하세요.  
  
 소스 코드에 직접 키를 포함하지 마세요.  포함 된 키는 [Ildasm.exe (IL 디스어셈블러)](../../framework/tools/ildasm-exe-il-disassembler.md) 를 사용 하거나 메모장과 같은 텍스트 편집기에서 어셈블리를 열어 어셈블리에서 쉽게 읽을 수 있습니다.  
  
 암호화 키를 사용하여 작업이 완료되면 각 바이트를 0으로 설정하거나 관리되는 암호화 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 메서드를 호출하여 메모리에서 지웁니다.  디버거가 메모리에서 암호화 키를 읽거나 메모리 위치가 디스크에 페이징된 경우 하드 드라이브에서 읽을 수 있는 경우도 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [암호화 모델](cryptography-model.md)
- [암호화 서비스](cryptographic-services.md)
- [플랫폼 간 암호화](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [방법: 비대칭 키를 사용하여 XML 요소 암호화](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [ASP.NET Core 데이터 보호](/aspnet/core/security/data-protection/introduction)
