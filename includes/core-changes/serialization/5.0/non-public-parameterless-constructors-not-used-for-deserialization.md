---
ms.openlocfilehash: 3692848a0cbd4bbbe3c7bb4d2c22a2b19de732e4
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050475"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="7d5a8-101">역직렬화에 사용되지 않는 비공용 매개 변수가 없는 생성자</span><span class="sxs-lookup"><span data-stu-id="7d5a8-101">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="7d5a8-102">지원되는 모든 TFM(대상 프레임워크 모니커) 간의 일관성을 위해 비공용 매개 변수가 없는 생성자는 기본적으로 <xref:System.Text.Json.JsonSerializer>를 사용한 역직렬화에 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-102">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7d5a8-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7d5a8-103">Change description</span></span>

<span data-ttu-id="7d5a8-104">.NET Standard 2.0 이상, 즉 버전 4.6.0-4.7.2를 지원하는 독립 실행형 [System.Text.Json NuGet 패키지](https://www.nuget.org/packages/System.Text.Json/)는 .NET Core 3.0 및 3.1의 기본 제공 동작과 일관되지 않게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-104">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="7d5a8-105">.NET Core 3.x에서는 내부 및 프라이빗 생성자를 역직렬화에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-105">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="7d5a8-106">독립형 패키지에서 비공용 생성자는 허용되지 않으며 비공용 매개 변수가 없는 생성자가 정의되지 않은 경우 <xref:System.MissingMethodException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-106">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="7d5a8-107">.NET 5.0 및 System.Text.Json NuGet 패키지 5.0.0부터 NuGet 패키지와 기본 제공 API 간에 동작이 일관됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-107">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="7d5a8-108">매개 변수가 없는 생성자를 비롯한 비공용 생성자는 기본적으로 직렬 변환기에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-108">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="7d5a8-109">직렬 변환기는 역직렬화를 위해 다음 생성자 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-109">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="7d5a8-110"><xref:System.Text.Json.Serialization.JsonConstructorAttribute> 주석이 달린 공용 생성자.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-110">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="7d5a8-111">공용 매개 변수가 없는 생성자.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-111">Public parameterless constructor.</span></span>
- <span data-ttu-id="7d5a8-112">공용 매개 변수가 있는 생성자(공용 생성자만 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="7d5a8-112">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="7d5a8-113">이러한 생성자를 사용할 수 없는 경우 유형을 역직렬화하려고 하면 <xref:System.NotSupportedException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-113">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7d5a8-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7d5a8-114">Version introduced</span></span>

<span data-ttu-id="7d5a8-115">5.0</span><span class="sxs-lookup"><span data-stu-id="7d5a8-115">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7d5a8-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7d5a8-116">Reason for change</span></span>

- <span data-ttu-id="7d5a8-117">.NET Core 3.0 이상 버전 및 .NET Standard 2.0에 대해 <xref:System.Text.Json?displayProperty=fullName>이 빌드하는 모든 TFM(대상 프레임워크 모니커) 간에 일관된 동작을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="7d5a8-117">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="7d5a8-118"><xref:System.Text.Json.JsonSerializer>는 생성자, 속성 또는 필드에 관계없이 유형의 비공용 노출 영역을 호출하지 않아야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-118">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7d5a8-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7d5a8-119">Recommended action</span></span>

- <span data-ttu-id="7d5a8-120">유형을 소유하고 있으며 적합한 경우 매개 변수가 없는 생성자를 공용으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-120">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="7d5a8-121">그렇지 않으면 형식에 대해 `JsonConverter<T>`를 구현하고 역직렬화 동작을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5a8-121">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="7d5a8-122">범주</span><span class="sxs-lookup"><span data-stu-id="7d5a8-122">Category</span></span>

<span data-ttu-id="7d5a8-123">Serialization</span><span class="sxs-lookup"><span data-stu-id="7d5a8-123">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7d5a8-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7d5a8-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
