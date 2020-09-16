---
title: x:Shared 특성
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557790"
---
# <a name="xshared-attribute"></a><span data-ttu-id="96a52-102">x:Shared 특성</span><span class="sxs-lookup"><span data-stu-id="96a52-102">x:Shared Attribute</span></span>

<span data-ttu-id="96a52-103">로 설정 `false` 된 경우 특성을 사용 하는 리소스에 대 한 요청이 모든 요청에 대해 동일한 인스턴스를 공유 하는 대신 각 요청에 대해 새 인스턴스를 만들도록 WPF 리소스 검색 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="96a52-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="96a52-104">XAML Attribute Usage</span></span>

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a><span data-ttu-id="96a52-105">설명</span><span class="sxs-lookup"><span data-stu-id="96a52-105">Remarks</span></span>

<span data-ttu-id="96a52-106">`x:Shared` 는 XAML 언어 XAML 네임 스페이스에 매핑되고 .NET XAML 서비스 및 해당 XAML 판독기에서 유효한 XAML 언어 요소로 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET XAML Services and its XAML readers.</span></span> <span data-ttu-id="96a52-107">그러나의 설명 된 기능은 `x:Shared` wpf 응용 프로그램 및 WPF XAML 파서에만 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="96a52-108">WPF에서 `x:Shared` 는 wpf 내에 있는 개체에 적용 되는 경우에만 특성으로 유용 <xref:System.Windows.ResourceDictionary> 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="96a52-109">다른 용도는 구문 분석 예외 나 기타 오류를 throw 하지 않지만 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>

<span data-ttu-id="96a52-110">의 의미는 `x:Shared` XAML 언어 사양에 지정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="96a52-111">.NET XAML 서비스를 기반으로 하는 것과 같은 다른 XAML 구현은 반드시 리소스 공유 지원을 제공 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-111">Other XAML implementations, such as those that build on .NET XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="96a52-112">이러한 XAML 구현은 지원 프레임 워크 에서도 값을 사용 하는 유사한 동작을 제공할 수 있습니다 `x:Shared` .</span><span class="sxs-lookup"><span data-stu-id="96a52-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>

<span data-ttu-id="96a52-113">WPF에서 `x:Shared` 리소스에 대 한 기본 조건은 `true` 입니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="96a52-114">이 조건은 지정 된 모든 리소스 요청이 항상 동일한 인스턴스를 반환 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-114">This condition means that any given resource request always returns the same instance.</span></span>

<span data-ttu-id="96a52-115">등의 리소스 API를 통해 반환 되는 개체를 수정 <xref:System.Windows.FrameworkElement.FindResource%2A> 하거나에서 직접 개체를 수정 <xref:System.Windows.ResourceDictionary> 하면 원래 리소스가 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="96a52-116">해당 리소스에 대 한 참조가 동적 리소스 참조 인 경우 해당 리소스의 소비자는 변경 된 리소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>

<span data-ttu-id="96a52-117">리소스에 대 한 참조가 정적 리소스 참조 인 경우 처리 시간 이후 리소스에 대 한 변경 내용이 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="96a52-118">정적 및 동적 리소스 참조에 대 한 자세한 내용은 [XAML 리소스](../fundamentals/xaml-resources-define.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96a52-118">For more information about static versus dynamic resource references, see [XAML Resources](../fundamentals/xaml-resources-define.md).</span></span>

<span data-ttu-id="96a52-119">가 이미 기본값 이기 때문에를 명시적으로 지정 하 `x:Shared="true"` 는 것은 거의 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="96a52-120">WPF 개체 모델에는에 해당 하는 직접 코드가 없습니다 `x:Shared` . XAML 사용에만 지정할 수 있으며, .NET XAML 서비스 및 해당 xaml 판독기를 사용 하 여 처리 하는 경우 로드 경로에서 기본 WPF 동작이 나 중간 XAML 노드 스트림에서 처리 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET XAML Services and its XAML readers.</span></span>

<span data-ttu-id="96a52-121">의 시나리오는 `x:Shared="false"` <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스를 리소스로 정의한 다음 요소 리소스를 콘텐츠 모델에 도입 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="96a52-122">`x:Shared="false"` 같은 컬렉션에서 요소 리소스를 여러 번 도입할 수 있도록 합니다 (예: <xref:System.Windows.Controls.UIElementCollection> ).</span><span class="sxs-lookup"><span data-stu-id="96a52-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="96a52-123">`x:Shared="false"`컬렉션은 내용에 고유성이 적용 되므로이는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="96a52-124">그러나이 `x:Shared="false"` 동작은 동일한 인스턴스를 반환 하는 대신 동일한 리소스의 다른 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>

<span data-ttu-id="96a52-125">의 또 다른 시나리오 `x:Shared="false"` 는 <xref:System.Windows.Freezable> 애니메이션 값에 리소스를 사용 하지만 애니메이션 별로 리소스를 수정 하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>

<span data-ttu-id="96a52-126">의 문자열 처리는 `false` 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-126">The string handling of `false` is not case sensitive.</span></span>

<span data-ttu-id="96a52-127">WPF에서 `x:Shared` 는 다음 조건 에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>

- <span data-ttu-id="96a52-128"><xref:System.Windows.ResourceDictionary>를 포함 하는 항목이 포함 된를 `x:Shared` 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="96a52-129">는 <xref:System.Windows.ResourceDictionary> 느슨한 XAML 내에 있거나 테마에 사용 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96a52-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>

- <span data-ttu-id="96a52-130"><xref:System.Windows.ResourceDictionary>항목을 포함 하는가 다른에 중첩 되지 않아야 합니다 <xref:System.Windows.ResourceDictionary> .</span><span class="sxs-lookup"><span data-stu-id="96a52-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="96a52-131">예를 들어 `x:Shared` <xref:System.Windows.ResourceDictionary> 이미 항목인 내에 있는 항목에는를 사용할 수 없습니다 <xref:System.Windows.Style> <xref:System.Windows.ResourceDictionary> .</span><span class="sxs-lookup"><span data-stu-id="96a52-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>

## <a name="see-also"></a><span data-ttu-id="96a52-132">참조</span><span class="sxs-lookup"><span data-stu-id="96a52-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="96a52-133">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="96a52-133">XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="96a52-134">기본 요소</span><span class="sxs-lookup"><span data-stu-id="96a52-134">Base Elements</span></span>](/dotnet/desktop/wpf/advanced/base-elements)
