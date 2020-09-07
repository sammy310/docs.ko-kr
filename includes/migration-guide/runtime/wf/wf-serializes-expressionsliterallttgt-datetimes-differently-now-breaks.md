---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496716"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="440a2-101">WF가 Expressions.Literal&lt;T&gt; DateTimes를 직렬화합니다(사용자 지정 XAML 파서 중단).</span><span class="sxs-lookup"><span data-stu-id="440a2-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="440a2-102">설명</span><span class="sxs-lookup"><span data-stu-id="440a2-102">Details</span></span>

<span data-ttu-id="440a2-103">연결된 <xref:System.Windows.Markup.ValueSerializer> 개체는 두 번째 및 <xref:System.DateTime.Millisecond?displayProperty=fullName> 구성 요소가 0이 아니고(<xref:System.DateTime?displayProperty=fullName> 값의 경우) <xref:System.DateTime.Kind> 속성이 지정되지 않은 <xref:System.DateTime?displayProperty=fullName> 또는 <xref:System.DateTimeOffset?displayProperty=fullName> 개체를 문자열 대신에 속성 요소 구문으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="440a2-104">이 변경은 <xref:System.DateTime?displayProperty=fullName> 및 <xref:System.DateTimeOffset?displayProperty=fullName> 값이 라운드트립되는 것을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="440a2-105">입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="440a2-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="440a2-106">Suggestion</span></span>

<span data-ttu-id="440a2-107">이 변경은 <xref:System.DateTime?displayProperty=fullName> 및 <xref:System.DateTimeOffset?displayProperty=fullName> 값이 라운드트립되는 것을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="440a2-108">입력 XAML이 특성 구문에 있다고 가정하는 사용자 지정 XAML 파서가 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="440a2-109">이름</span><span class="sxs-lookup"><span data-stu-id="440a2-109">Name</span></span>    | <span data-ttu-id="440a2-110">값</span><span class="sxs-lookup"><span data-stu-id="440a2-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="440a2-111">Scope</span><span class="sxs-lookup"><span data-stu-id="440a2-111">Scope</span></span>   |<span data-ttu-id="440a2-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="440a2-112">Edge</span></span>|
|<span data-ttu-id="440a2-113">버전</span><span class="sxs-lookup"><span data-stu-id="440a2-113">Version</span></span>|<span data-ttu-id="440a2-114">4.5</span><span class="sxs-lookup"><span data-stu-id="440a2-114">4.5</span></span>|
|<span data-ttu-id="440a2-115">형식</span><span class="sxs-lookup"><span data-stu-id="440a2-115">Type</span></span>|<span data-ttu-id="440a2-116">런타임</span><span class="sxs-lookup"><span data-stu-id="440a2-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="440a2-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="440a2-117">Affected APIs</span></span>

<span data-ttu-id="440a2-118">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="440a2-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
