---
title: '방법: X.509 인증서로 XML 요소 암호화'
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: c978bea7336e64d6622aca4d21c7ef3317d73957
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555723"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="f9d6d-102">방법: X.509 인증서로 XML 요소 암호화</span><span class="sxs-lookup"><span data-stu-id="f9d6d-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="f9d6d-103"><xref:System.Security.Cryptography.Xml> 네임스페이스의 클래스를 사용하여 XML 문서 내의 요소를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="f9d6d-104">XML 암호화는 데이터가 쉽게 읽혀질 염려 없이 암호화된 XML 데이터를 교환하거나 저장하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="f9d6d-105">XML 암호화 표준에 대 한 자세한 내용은에 있는 XML 암호화에 대 한 World Wide Web 컨소시엄 (W3C) 사양을 참조 하십시오 <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="f9d6d-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="f9d6d-106">XML 암호화를 사용하여 암호화된 XML 데이터가 포함된 <`EncryptedData`> 요소의 문서나 XML 요소를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="f9d6d-107"><`EncryptedData`> 요소는 암호화 중에 사용된 키와 프로세스에 대한 정보가 들어 있는 하위 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="f9d6d-108">XML 암호화를 사용하면 문서에 암호화된 여러 요소가 포함될 수 있고 한 요소가 여러 번 암호화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="f9d6d-109">이 절차의 코드 예제에서는 나중에 암호 해독 과정에서 사용할 수 있는 다른 여러 하위 요소와 함께 <`EncryptedData`> 요소를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
<span data-ttu-id="f9d6d-110">이 예제에서는 두 키를 사용하여 XML 요소를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="f9d6d-111">이 예제에서는 메서드를 사용 하 여 프로그래밍 방식으로 인증서를 검색 하 고이를 사용 하 여 XML 요소를 암호화 합니다 <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> .</span><span class="sxs-lookup"><span data-stu-id="f9d6d-111">The example programmatically retrieves a certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="f9d6d-112">내부적으로 <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> 메서드는 별도의 세션 키를 만들고 XML 문서를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-112">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="f9d6d-113">이 메서드는 세션 키를 암호화하고 이를 암호화된 XML과 함께 새 <`EncryptedData`> 요소 내부에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-113">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  

<span data-ttu-id="f9d6d-114">XML 요소의 암호를 해독 하려면 메서드를 호출 합니다 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> .이 메서드는 저장소에서 x.509 인증서를 자동으로 검색 하 고 필요한 암호 해독을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-114">To decrypt the XML element, call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="f9d6d-115">이 절차를 사용하여 암호화된 XML 요소를 암호 해독하는 방법에 대한 자세한 내용은 [방법: X.509 인증서로 XML 요소 암호 해독](how-to-decrypt-xml-elements-with-x-509-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-115">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
<span data-ttu-id="f9d6d-116">이 예제는 여러 애플리케이션이 암호화된 데이터를 공유해야 하거나 애플리케이션이 실행되는 시간 사이에 암호화된 데이터를 저장해야 경우에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-116">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="f9d6d-117">X.509 인증서로 XML 요소를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="f9d6d-117">To encrypt an XML element with an X.509 certificate</span></span>  

<span data-ttu-id="f9d6d-118">이 예제를 실행 하려면 테스트 인증서를 만들어 인증서 저장소에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-118">To run this example, you need to create a test certificate and save it in a certificate store.</span></span> <span data-ttu-id="f9d6d-119">해당 작업에 대 한 지침은 Windows [인증서 생성 도구 (Makecert.exe)](/windows/desktop/SecCrypto/makecert)에 대해서만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-119">Instructions for that task are provided only for the Windows [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span></span>

1. <span data-ttu-id="f9d6d-120">[Makecert.exe](/windows/desktop/SecCrypto/makecert) 를 사용 하 여 테스트 x.509 인증서를 생성 하 고 로컬 사용자 저장소에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-120">Use [Makecert.exe](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="f9d6d-121">교환 키를 생성해야 하며 키를 내보낼 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-121">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="f9d6d-122">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-122">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="f9d6d-123"><xref:System.Security.Cryptography.X509Certificates.X509Store> 개체를 만들고 초기화하여 현재 사용자 저장소를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-123">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="f9d6d-124">읽기 전용 모드로 저장소를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-124">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="f9d6d-125">저장소에 있는 모든 인증서를 사용하여 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection>을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-125">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="f9d6d-126">저장소에 있는 인증서를 열거하고 해당 이름을 가진 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-126">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="f9d6d-127">이 예제에서 인증서의 이름은 `"CN=XML_ENC_TEST_CERT"`입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-127">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="f9d6d-128">인증서를 찾은 후 저장소를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-128">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="f9d6d-129">디스크에서 XML 파일을 로드하여 <xref:System.Xml.XmlDocument> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-129">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="f9d6d-130"><xref:System.Xml.XmlDocument> 개체는 암호화할 XML 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-130">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="f9d6d-131"><xref:System.Xml.XmlDocument> 개체에서 지정된 요소를 찾고 암호화할 요소를 나타내는 <xref:System.Xml.XmlElement> 개체를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-131">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="f9d6d-132">이 예제에서는 `"creditcard"` 요소가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-132">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="f9d6d-133"><xref:System.Security.Cryptography.Xml.EncryptedXml> 클래스의 새 인스턴스를 만들고 X.509 인증서를 사용하여 지정된 요소를 암호화하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-133">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="f9d6d-134"><xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> 메서드는 암호화된 요소를 <xref:System.Security.Cryptography.Xml.EncryptedData> 개체로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-134">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="f9d6d-135">원본 <xref:System.Xml.XmlDocument> 개체의 요소를 <xref:System.Security.Cryptography.Xml.EncryptedData> 요소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-135">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="f9d6d-136"><xref:System.Xml.XmlDocument> 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-136">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="f9d6d-137">예제</span><span class="sxs-lookup"><span data-stu-id="f9d6d-137">Example</span></span>  
 <span data-ttu-id="f9d6d-138">이 예제에서는 `"test.xml"`이라는 파일이 컴파일된 프로그램과 동일한 디렉터리에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-138">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="f9d6d-139">또한 `"test.xml"`에 `"creditcard"` 요소가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-139">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="f9d6d-140">`test.xml`이라는 파일에 다음 XML을 배치하고 이 예제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-140">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9d6d-141">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f9d6d-141">Compiling the Code</span></span>  
  
- <span data-ttu-id="f9d6d-142">.NET Framework를 대상으로 하는 프로젝트에서에 대 한 참조를 포함 `System.Security.dll` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-142">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="f9d6d-143">.NET Core 또는 .NET 5를 대상으로 하는 프로젝트에서 NuGet 패키지 [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-143">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="f9d6d-144"><xref:System.Xml>, <xref:System.Security.Cryptography> 및 <xref:System.Security.Cryptography.Xml> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-144">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="f9d6d-145">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="f9d6d-145">.NET Security</span></span>
  
<span data-ttu-id="f9d6d-146">이 예제에서 사용된 X.509 인증서는 테스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-146">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="f9d6d-147">응용 프로그램은 신뢰할 수 있는 인증 기관에서 생성 한 x.509 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d6d-147">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d6d-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9d6d-148">See also</span></span>

- [<span data-ttu-id="f9d6d-149">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="f9d6d-149">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="f9d6d-150">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="f9d6d-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="f9d6d-151">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="f9d6d-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="f9d6d-152">방법: X.509 인증서로 XML 요소 해독</span><span class="sxs-lookup"><span data-stu-id="f9d6d-152">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="f9d6d-153">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="f9d6d-153">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
