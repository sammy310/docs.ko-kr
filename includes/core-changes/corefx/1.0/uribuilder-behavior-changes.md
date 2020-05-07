---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595686"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="3671e-101">UriBuilder 속성은 더 이상 앞에 선행 문자를 추가하지 않음</span><span class="sxs-lookup"><span data-stu-id="3671e-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="3671e-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType>는 더 이상 앞에 선행 `#` 문자를 추가하지 않으며 <xref:System.UriBuilder.Query?displayProperty=nameWithType>는 더 이상 앞에 선행 `?` 문자를 추가하지 않습니다(해당 문자가 이미 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="3671e-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3671e-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3671e-103">Change description</span></span>

<span data-ttu-id="3671e-104">.NET Framework에서 <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 및 <xref:System.UriBuilder.Query?displayProperty=nameWithType> 속성은 항상 저장되는 값 앞에 각각 `#` 또는 `?` 문자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="3671e-105">이 동작으로 인해 문자열에 이미 이 선행 문자 중 하나가 포함된 경우 저장된 값에 여러 `#` 또는 `?` 문자가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="3671e-106">예를 들어 <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> 값이 `##main`이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="3671e-107">.NET Core 1.0부터 이 속성은 더 이상 저장된 값 앞에 `#` 또는 `?` 문자를 추가하지 않습니다(해당 문자가 문자열의 시작 부분에 이미 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="3671e-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3671e-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3671e-108">Version introduced</span></span>

<span data-ttu-id="3671e-109">1.0</span><span class="sxs-lookup"><span data-stu-id="3671e-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3671e-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3671e-110">Recommended action</span></span>

<span data-ttu-id="3671e-111">속성 값을 설정할 때 더 이상 이 선행 문자를 명시적으로 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="3671e-112">더 이상 추가할 때마다 선행 `#` 또는 `?`를 제거할 필요가 없기 때문에 값을 추가할 경우 이 방법이 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="3671e-113">예를 들어 다음 코드 조각은 .NET Framework와 .NET Core의 동작 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="3671e-114">.NET Framework에서 출력은 `????one=1&two=2&three=3&four=4`입니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="3671e-115">.NET Core에서 출력은 `?one=1&two=2&three=3&four=4`입니다.</span><span class="sxs-lookup"><span data-stu-id="3671e-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="3671e-116">범주</span><span class="sxs-lookup"><span data-stu-id="3671e-116">Category</span></span>

<span data-ttu-id="3671e-117">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3671e-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3671e-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3671e-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
