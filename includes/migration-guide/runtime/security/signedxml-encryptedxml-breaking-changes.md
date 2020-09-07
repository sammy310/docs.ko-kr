---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496996"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="24161-101">SignedXml 및 EncryptedXml 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="24161-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="24161-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="24161-102">Details</span></span>

<span data-ttu-id="24161-103">.NET Framework 4.6.2에서는 <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> 및 <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>의 보안 수정으로 인해 런타임 동작이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="24161-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="24161-104">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="24161-104">For example,</span></span><ul><li><span data-ttu-id="24161-105">문서에 동일한 <code>id</code> 특성을 가진 요소가 여러 개 있고 서명에서 해당 요소 중 하나를 서명 루트로 사용하는 경우, 이제는 문서가 잘못된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="24161-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="24161-106">참조에서 비표준 XPath 변환 알고리즘을 사용하는 문서는 현재 잘못된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="24161-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="24161-107">참조에서 비표준 XSLT 변환 알고리즘을 사용하는 문서는 현재 잘못된 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="24161-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="24161-108">외부 리소스 분리 서명을 사용하는 모든 프로그램은 그렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24161-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="24161-109">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="24161-109">Suggestion</span></span>

<span data-ttu-id="24161-110">개발자는 <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> 및 <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>과 <xref:System.Security.Cryptography.Xml.Transform>에서 파생된 형식의 사용을 검토해야 합니다. 문서 수신기가 이러한 사용을 처리하지 못할 수도 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="24161-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="24161-111">Name</span><span class="sxs-lookup"><span data-stu-id="24161-111">Name</span></span>    | <span data-ttu-id="24161-112">값</span><span class="sxs-lookup"><span data-stu-id="24161-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="24161-113">Scope</span><span class="sxs-lookup"><span data-stu-id="24161-113">Scope</span></span>   |<span data-ttu-id="24161-114">부</span><span class="sxs-lookup"><span data-stu-id="24161-114">Minor</span></span>|
|<span data-ttu-id="24161-115">버전</span><span class="sxs-lookup"><span data-stu-id="24161-115">Version</span></span>|<span data-ttu-id="24161-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="24161-116">4.6.2</span></span>|
|<span data-ttu-id="24161-117">형식</span><span class="sxs-lookup"><span data-stu-id="24161-117">Type</span></span>|<span data-ttu-id="24161-118">런타임</span><span class="sxs-lookup"><span data-stu-id="24161-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="24161-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="24161-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
