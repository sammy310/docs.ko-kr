---
title: DynamicResource 태그 확장
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: d07816718ebee2507f1888cffb70e6f8037bb996
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091410"
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="197b1-102">DynamicResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="197b1-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="197b1-103">에 대 한 값을 제공 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 해당 값이 정의 된 리소스에 대 한 참조가 되도록 지연 하 여 속성 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="197b1-104">해당 리소스에 대 한 조회 동작 런타임 조회와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="197b1-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="197b1-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="197b1-106">XAML 속성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="197b1-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="197b1-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="197b1-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="197b1-108">요청한 리소스의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-108">The key for the requested resource.</span></span> <span data-ttu-id="197b1-109">이 키가 처음에 할당 합니다 [X:key 지시문](../../xaml-services/x-key-directive.md) 리소스 태그에서 만든 또는 변수로 제공 된 경우를 `key` 매개 변수를 호출할 때 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 코드에서 리소스를 만든 경우.</span><span class="sxs-lookup"><span data-stu-id="197b1-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="197b1-110">설명</span><span class="sxs-lookup"><span data-stu-id="197b1-110">Remarks</span></span>  
 <span data-ttu-id="197b1-111">`DynamicResource` 초기 컴파일하는 동안 임시 식을 만들려면 되며 따라서 요청 된 리소스 값이 개체를 생성 하기 위해 실제로 필요할 때까지 리소스에 대 한 조회를 연기 합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="197b1-112">이 후 될 수 있습니다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="197b1-113">리소스 값 섹션은 현재 페이지 범위에서 시작 하는 모든 활성 리소스 사전에 대 한 키 검색 및 컴파일에서 자리 표시자 식에 대 한 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="197b1-114">종속성 속성 우선 순위를 기준으로 한 `DynamicResource` 식은 동적 리소스 참조가 적용 되는 위치와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="197b1-115">이전에 있던 속성에 대 한 로컬 값을 설정 하는 경우는 `DynamicResource` 식 로컬 값으로는 `DynamicResource` 완전히 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="197b1-116">자세한 내용은 [종속성 속성 값 우선 순위](dependency-property-value-precedence.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="197b1-116">For details, see [Dependency Property Value Precedence](dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="197b1-117">특정 리소스 액세스 시나리오에 특히 적합 `DynamicResource` 반대인를 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span> <span data-ttu-id="197b1-118">참조 [XAML 리소스](xaml-resources.md) 상대적인 장점 및 성능에 미치는 영향에 대 한 설명은 `DynamicResource` 고 `StaticResource`입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-118">See [XAML Resources](xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="197b1-119">지정 된 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 기존 리소스에 의해 결정에 대응 되어야 [X:key 지시문](../../xaml-services/x-key-directive.md) 페이지, 응용 프로그램을 사용할 수 있는 컨트롤 테마 및 외부 리소스 또는 시스템 리소스를 몇 가지 수준 및 리소스 조회 순서 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="197b1-120">정적 및 동적 리소스에 대 한 리소스 조회에 대 한 자세한 내용은 참조 하세요. [XAML 리소스](xaml-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="197b1-121">리소스 키에 정의 된 문자열일 수 있습니다 합니다 [XamlName 문법](../../xaml-services/xamlname-grammar.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-121">A resource key may be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="197b1-122">리소스 키 수도 다른 개체 형식 등을 <xref:System.Type>입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="197b1-123"><xref:System.Type> 테마 컨트롤은 방식의 기본 키가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="197b1-124">자세한 내용은 [컨트롤 제작 개요](../controls/control-authoring-overview.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="197b1-124">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <span data-ttu-id="197b1-125">리소스 값을 조회에 대 한 같은 <xref:System.Windows.FrameworkElement.FindResource%2A>에서 사용 되는 동일한 리소스 조회 논리에 따라 `DynamicResource`합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-125">for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="197b1-126">리소스를 참조 하는 대체 선언적 수단은는 [StaticResource 태그 확장](staticresource-markup-extension.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="197b1-127">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="197b1-128">`DynamicResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 확장 클래스의 <xref:System.Windows.DynamicResourceExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 `DynamicResource` <span data-ttu-id="197b1-129">개체 요소 구문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-129">can be used in object element syntax.</span></span> <span data-ttu-id="197b1-130">이 경우 값을 지정 하는 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 속성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 `DynamicResource` <span data-ttu-id="197b1-131">지정 하는 자세한 특성 사용 구문에 사용할 수는 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 속성으로 속성 = 값 쌍:</span><span class="sxs-lookup"><span data-stu-id="197b1-131">can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="197b1-132">자세한 정보 표시는 대개 설정 가능한 속성이 둘 이상이거나 일부 속성이 선택 사항인 확장의 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="197b1-133">
          `DynamicResource\`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="197b1-134">에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현에서이 태그 확장에 대 한 처리는 정의한는 <xref:System.Windows.DynamicResourceExtension> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 `DynamicResource` <span data-ttu-id="197b1-135">태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-135">is a markup extension.</span></span> <span data-ttu-id="197b1-136">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="197b1-137">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="197b1-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="197b1-138">자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="197b1-138">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="197b1-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="197b1-139">See also</span></span>

- [<span data-ttu-id="197b1-140">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="197b1-140">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="197b1-141">리소스 및 코드</span><span class="sxs-lookup"><span data-stu-id="197b1-141">Resources and Code</span></span>](resources-and-code.md)
- [<span data-ttu-id="197b1-142">x:Key 지시문</span><span class="sxs-lookup"><span data-stu-id="197b1-142">x:Key Directive</span></span>](../../xaml-services/x-key-directive.md)
- [<span data-ttu-id="197b1-143">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="197b1-143">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="197b1-144">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="197b1-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="197b1-145">StaticResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="197b1-145">StaticResource Markup Extension</span></span>](staticresource-markup-extension.md)
- [<span data-ttu-id="197b1-146">태그 확장명 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="197b1-146">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
