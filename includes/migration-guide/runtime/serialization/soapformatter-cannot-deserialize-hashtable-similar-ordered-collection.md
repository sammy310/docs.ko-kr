---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620379"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="4ba5a-101">SoapFormatter는 해시 테이블과 순서가 지정된 유사 컬렉션 개체를 역직렬화할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="4ba5a-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="4ba5a-102">설명</span><span class="sxs-lookup"><span data-stu-id="4ba5a-102">Details</span></span>

<span data-ttu-id="4ba5a-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName>은 하나의 .NET Framework 버전에서 직렬화된 개체가 다른 버전에서 성공적으로 역직렬화하는 것을 보장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba5a-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="4ba5a-104">특히, 일부 순서가 지정된 컬렉션(예: <xref:System.Collections.Hashtable?displayProperty=fullName>)은 4.0 및 4.5 간에 멤버가 추가되었으며 이러한 형식의 개체가 .NET Framework 4.5로 직렬화된 경우 .NET Framework 4.0으로 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba5a-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="4ba5a-105">직렬화된 데이터가 같은 .NET Framework 버전으로 직렬화 및 역직렬화되면 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba5a-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4ba5a-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4ba5a-106">Suggestion</span></span>

<span data-ttu-id="4ba5a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> 직렬화는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> 직렬화 또는 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>으로 대체되어야 .NET Framework 변경 시 복원이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba5a-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="4ba5a-108">이름</span><span class="sxs-lookup"><span data-stu-id="4ba5a-108">Name</span></span>    | <span data-ttu-id="4ba5a-109">값</span><span class="sxs-lookup"><span data-stu-id="4ba5a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4ba5a-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4ba5a-110">Scope</span></span>   |<span data-ttu-id="4ba5a-111">부</span><span class="sxs-lookup"><span data-stu-id="4ba5a-111">Minor</span></span>|
|<span data-ttu-id="4ba5a-112">버전</span><span class="sxs-lookup"><span data-stu-id="4ba5a-112">Version</span></span>|<span data-ttu-id="4ba5a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4ba5a-113">4.5</span></span>|
|<span data-ttu-id="4ba5a-114">형식</span><span class="sxs-lookup"><span data-stu-id="4ba5a-114">Type</span></span>|<span data-ttu-id="4ba5a-115">런타임</span><span class="sxs-lookup"><span data-stu-id="4ba5a-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4ba5a-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4ba5a-116">Affected APIs</span></span>

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
