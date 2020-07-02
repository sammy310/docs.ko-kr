---
ms.openlocfilehash: eafbdd2d42977381fb4d77748a3c9a2595ff2936
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620376"
---
### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="228ad-101">액세스할 수 있는 멤버를 액세스할 수 없는 멤버로 숨기는 형식을 직렬화하는 동안 XmlSerializer가 실패함</span><span class="sxs-lookup"><span data-stu-id="228ad-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

#### <a name="details"></a><span data-ttu-id="228ad-102">설명</span><span class="sxs-lookup"><span data-stu-id="228ad-102">Details</span></span>

<span data-ttu-id="228ad-103">파생된 형식을 직렬화할 때 형식에 액세스할 수 없는 필드 또는 ('new' 키워드를 통해) 필드를 숨기는 속성 또는 기본 유형에서 이전에 액세스할 수 있었던 같은 이름(예: public)의 속성이 포함된 경우 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228ad-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="228ad-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="228ad-104">Suggestion</span></span>

<span data-ttu-id="228ad-105">이 문제는 숨어 있는 멤버를 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>에 액세스할 수 있는 새로운 숨김 멤버를 만들어 해결할 수 있습니다(예: 공개로 표시). 또는 다음 구성 설정을 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> 동작으로 되돌리면 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="228ad-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> behavior, which will fix the problem:</span></span><pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="228ad-106">이름</span><span class="sxs-lookup"><span data-stu-id="228ad-106">Name</span></span>    | <span data-ttu-id="228ad-107">값</span><span class="sxs-lookup"><span data-stu-id="228ad-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="228ad-108">Scope</span><span class="sxs-lookup"><span data-stu-id="228ad-108">Scope</span></span>   |<span data-ttu-id="228ad-109">부</span><span class="sxs-lookup"><span data-stu-id="228ad-109">Minor</span></span>|
|<span data-ttu-id="228ad-110">버전</span><span class="sxs-lookup"><span data-stu-id="228ad-110">Version</span></span>|<span data-ttu-id="228ad-111">4.5</span><span class="sxs-lookup"><span data-stu-id="228ad-111">4.5</span></span>|
|<span data-ttu-id="228ad-112">형식</span><span class="sxs-lookup"><span data-stu-id="228ad-112">Type</span></span>|<span data-ttu-id="228ad-113">런타임</span><span class="sxs-lookup"><span data-stu-id="228ad-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="228ad-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="228ad-114">Affected APIs</span></span>

-<xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
