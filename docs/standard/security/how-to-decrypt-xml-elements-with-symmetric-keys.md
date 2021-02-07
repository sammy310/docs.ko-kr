---
description: '자세히 알아보기: 방법: 대칭 키를 사용 하 여 XML 요소 암호 해독'
title: '방법: 대칭 키를 사용하여 XML 요소 해독'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.Aes class
- XML encryption
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
ms.openlocfilehash: 894b202143daf2af767fd9877266e2323e0057e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685181"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="46057-103">방법: 대칭 키를 사용하여 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="46057-103">How to: Decrypt XML Elements with Symmetric Keys</span></span>

<span data-ttu-id="46057-104"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46057-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="46057-105">XML 암호화를 사용하면 데이터가 쉽게 읽혀질 염려 없이 중요한 XML을 저장하거나 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46057-105">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="46057-106">이 코드 예제에서는 AES(Advanced Encryption Standard) (AES) 알고리즘을 사용 하 여 XML 요소의 암호를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-106">This code example decrypts an XML element using the Advanced Encryption Standard (AES) algorithm.</span></span>
  
 <span data-ttu-id="46057-107">이 절차를 사용 하 여 XML 요소를 암호화 하는 방법에 대 한 자세한 내용은 [방법: 대칭 키를 사용 하 여 Xml 요소 암호화](how-to-encrypt-xml-elements-with-symmetric-keys.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46057-107">For information about how to encrypt an XML element using this procedure, see [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="46057-108">AES와 같은 대칭 알고리즘을 사용하여 XML 데이터를 암호화하는 경우 동일한 키를 사용하여 XML 데이터를 암호화하고 암호 해독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-108">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="46057-109">이 절차의 예제에서는 동일한 키를 사용하여 암호화된 XML이 암호화되었으며 암호화 및 암호 해독하는 당사자가 알고리즘 및 사용할 키에 대해 동의한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-109">The example in this procedure assumes that the encrypted XML was encrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="46057-110">이 예제에서는 암호화된 XML 내의 AES 키를 저장하거나 암호화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46057-110">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="46057-111">이 예제는 단일 애플리케이션에서 메모리에 저장된 세션 키 또는 암호에서 파생된 강력한 암호화 키를 기반으로 하여 데이터를 암호화해야 하는 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-111">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="46057-112">둘 이상의 애플리케이션에서 암호화된 XML 데이터를 공유해야 하는 경우 비대칭 알고리즘 또는 X.509 인증서를 기반으로 하는 암호화 체계를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46057-112">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="46057-113">대칭 키를 사용하여 XML 요소를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="46057-113">To decrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="46057-114">[방법: 대칭 키를 사용 하 여 Xml 요소 암호화](how-to-encrypt-xml-elements-with-symmetric-keys.md)에 설명 된 기술을 사용 하 여 이전에 생성 된 키를 사용 하 여 xml 요소를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-114">Encrypt an XML element with the previously generated key using the techniques described in [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
2. <span data-ttu-id="46057-115">`EncryptedData`암호화 된 xml을 포함 하는 개체에서 <> 요소 (XML 암호화 표준에 의해 정의 됨)를 찾아 <xref:System.Xml.XmlDocument> <xref:System.Xml.XmlElement> 해당 요소를 나타내는 새 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46057-115">Find the <`EncryptedData`> element (defined by the XML Encryption standard) in an <xref:System.Xml.XmlDocument> object that contains the encrypted XML and create a new <xref:System.Xml.XmlElement> object to represent that element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. <span data-ttu-id="46057-116">이전에 만든 <xref:System.Xml.XmlElement> 개체에서 원시 XML 데이터를 로드하여 <xref:System.Security.Cryptography.Xml.EncryptedData> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46057-116">Create an <xref:System.Security.Cryptography.Xml.EncryptedData> object by loading the raw XML data from the previously created <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. <span data-ttu-id="46057-117">새 <xref:System.Security.Cryptography.Xml.EncryptedXml> 개체를 만들고 암호화에 사용된 것과 동일한 키로 XML 데이터를 암호 해독하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-117">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object and use it to decrypt the XML data using the same key that was used for encryption.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. <span data-ttu-id="46057-118">암호화된 요소를 XML 문서 내에서 새로 암호 해독된 일반 텍스트 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="46057-118">Replace the encrypted element with the newly decrypted plaintext element within the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="46057-119">예제</span><span class="sxs-lookup"><span data-stu-id="46057-119">Example</span></span>  

 <span data-ttu-id="46057-120">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-120">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="46057-121">또한 `"test.xml"`에 `"creditcard"` 요소가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-121">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="46057-122">`test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46057-122">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46057-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="46057-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="46057-124">.NET Framework를 대상으로 하는 프로젝트에서에 대 한 참조를 포함 `System.Security.dll` 합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-124">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="46057-125">.NET Core 또는 .NET 5를 대상으로 하는 프로젝트에서 NuGet 패키지 [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-125">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="46057-126"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="46057-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="46057-127">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="46057-127">.NET Security</span></span>
  
<span data-ttu-id="46057-128">암호화 키를 일반 텍스트로 저장하거나 컴퓨터 간에 일반 텍스트로 키를 전송하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="46057-128">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  
  
<span data-ttu-id="46057-129">대칭 암호화 키를 사용하여 작업이 완료되면 각 바이트를 0으로 설정하거나 관리되는 암호화 클래스의 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 메서드를 호출하여 메모리에서 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="46057-129">When you are done using a symmetric cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46057-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46057-130">See also</span></span>

- [<span data-ttu-id="46057-131">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="46057-131">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="46057-132">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="46057-132">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="46057-133">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="46057-133">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="46057-134">방법: 대칭 키를 사용하여 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="46057-134">How to: Encrypt XML Elements with Symmetric Keys</span></span>](how-to-encrypt-xml-elements-with-symmetric-keys.md)
- [<span data-ttu-id="46057-135">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="46057-135">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
