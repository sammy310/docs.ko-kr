---
description: '자세한 정보: 방법: x.509 인증서를 사용 하 여 XML 요소 암호 해독'
title: '방법: X.509 인증서로 XML 요소 해독'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 40006ca1d3e76dbbc0899c0c22090b27c2cfb0de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792377"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="55d1e-103">방법: X.509 인증서로 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="55d1e-103">How to: Decrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="55d1e-104"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화 및 암호 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="55d1e-105">XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-105">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="55d1e-106">XML 암호화 표준에 대 한 자세한 내용은에 있는 XML 암호화에 대 한 World Wide Web 컨소시엄 (W3C) 사양을 참조 하십시오 <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="55d1e-106">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="55d1e-107">이 예제에서는 [방법: X.509 인증서를 사용 하 여 Xml 요소 암호화](how-to-encrypt-xml-elements-with-x-509-certificates.md)에 설명 된 메서드를 사용 하 여 암호화 된 xml 요소의 암호를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-107">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="55d1e-108"><`EncryptedData`> 요소를 찾고 요소를 해독 한 다음 요소를 원래의 일반 텍스트 XML 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-108">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="55d1e-109">이 절차의 코드 예제에서는 현재 사용자 계정의 로컬 인증서 저장소에 있는 X.509 인증서를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-109">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="55d1e-110">이 예제에서는 메서드를 사용 하 여 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> x.509 인증서를 자동으로 검색 하 고 `EncryptedKey` <> 요소의 <> 요소에 저장 된 세션 키의 암호를 해독 `EncryptedData` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-110">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="55d1e-111"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드는 자동으로 세션 키를 사용하여 XML 요소를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-111">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="55d1e-112">이 예제는 여러 애플리케이션이 암호화된 데이터를 공유해야 하거나 애플리케이션이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-112">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="55d1e-113">X.509 인증서로 XML 요소를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="55d1e-113">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="55d1e-114">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="55d1e-115"><xref:System.Xml.XmlDocument> 개체는 암호 해독할 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-115">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="55d1e-116"><xref:System.Xml.XmlDocument> 개체를 생성자에 전달하여 새 <xref:System.Security.Cryptography.Xml.EncryptedXml>개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="55d1e-117"><xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 메서드를 사용하여 XML 문서를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-117">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="55d1e-118"><xref:System.Xml.XmlDocument> 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-118">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="55d1e-119">예제</span><span class="sxs-lookup"><span data-stu-id="55d1e-119">Example</span></span>

<span data-ttu-id="55d1e-120">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-120">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="55d1e-121">또한 `"test.xml"`에 `"creditcard"` 요소가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-121">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="55d1e-122">`test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-122">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
[!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55d1e-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="55d1e-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="55d1e-124">.NET Framework를 대상으로 하는 프로젝트에서에 대 한 참조를 포함 `System.Security.dll` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-124">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="55d1e-125">.NET Core 또는 .NET 5를 대상으로 하는 프로젝트에서 NuGet 패키지 [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-125">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>

- <span data-ttu-id="55d1e-126"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="55d1e-127">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="55d1e-127">.NET Security</span></span>

<span data-ttu-id="55d1e-128">이 예제에서 사용된 X.509 인증서는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-128">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="55d1e-129">응용 프로그램은 신뢰할 수 있는 인증 기관에서 생성 한 x.509 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55d1e-129">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d1e-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55d1e-130">See also</span></span>

- [<span data-ttu-id="55d1e-131">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="55d1e-131">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="55d1e-132">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="55d1e-132">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="55d1e-133">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="55d1e-133">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="55d1e-134">방법: X.509 인증서로 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="55d1e-134">How to: Encrypt XML Elements with X.509 Certificates</span></span>](how-to-encrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="55d1e-135">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="55d1e-135">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
