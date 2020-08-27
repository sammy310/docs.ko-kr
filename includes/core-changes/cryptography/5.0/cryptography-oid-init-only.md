---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558008"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="478e9-101">System.Security.Cryptography.Oid는 기능상 초기화 전용임</span><span class="sxs-lookup"><span data-stu-id="478e9-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="478e9-102">ASN.1 개체 식별자 값과 “식별” 이름을 나타내는 데 사용되는 <xref:System.Security.Cryptography.Oid?displayProperty=fullName> 클래스가 이전에는 완전히 변경 가능했습니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="478e9-103">이 가변성은 간과되거나 예상치 못한 것으로 인식되는 경우가 많았습니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="478e9-104">이미 할당된 값을 변경하려고 하면 속성 setter가 이제 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="478e9-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="478e9-105">Change description</span></span>

<span data-ttu-id="478e9-106">이전 버전에서는 <xref:System.Security.Cryptography.Oid>의 속성 setter를 사용하여 <xref:System.Security.Cryptography.Oid.FriendlyName> 및 <xref:System.Security.Cryptography.Oid.Value> 속성의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="478e9-107">.NET 5.0 이상 버전에서는 속성 setter에서 값을 초기화하는 것만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="478e9-108">속성 setter에 대한 이전 호출이나 생성자를 통해 속성 값이 있는 경우에는 속성 setter에서 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="478e9-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="478e9-109">Reason for change</span></span>

<span data-ttu-id="478e9-110">이렇게 변경하면 퍼블릭 API에서 반환 값의 일부로 <xref:System.Security.Cryptography.Oid> 개체를 재사용하여 개체 할당 프로필을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="478e9-111"><xref:System.Security.Cryptography.Oid> 값을 입력으로 사용할 때 “방어적인” 임시 복사본을 만들지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="478e9-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="478e9-112">Version introduced</span></span>

<span data-ttu-id="478e9-113">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="478e9-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="478e9-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="478e9-114">Recommended action</span></span>

<span data-ttu-id="478e9-115">개체 초기화 이외의 다른 용도로 <xref:System.Security.Cryptography.Oid> 속성 setter를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="478e9-116">새 값을 나타내려면 기존 개체의 값을 변경하는 대신 새 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="478e9-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="478e9-117">범주</span><span class="sxs-lookup"><span data-stu-id="478e9-117">Category</span></span>

<span data-ttu-id="478e9-118">암호화</span><span class="sxs-lookup"><span data-stu-id="478e9-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="478e9-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="478e9-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
