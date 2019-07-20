---
title: ComponentResourceKey 태그 확장
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 93735d12426042fd6517c10a55d1a9bd32f906bb
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363066"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="7092e-102">ComponentResourceKey 태그 확장</span><span class="sxs-lookup"><span data-stu-id="7092e-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="7092e-103">외부 어셈블리에서 로드 되는 리소스에 대 한 키를 정의 하 고 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="7092e-104">이렇게 하면 리소스 조회가 어셈블리 또는 클래스의 명시적 리소스 사전이 아닌 어셈블리의 대상 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="7092e-105">XAML 특성 사용 (설정 키, 압축)</span><span class="sxs-lookup"><span data-stu-id="7092e-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="7092e-106">XAML 특성 사용 (설정 키, 자세한 정보)</span><span class="sxs-lookup"><span data-stu-id="7092e-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="7092e-107">XAML 특성 사용 (리소스 요청, 압축)</span><span class="sxs-lookup"><span data-stu-id="7092e-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="7092e-108">XAML 특성 사용 (리소스 요청, 자세한 정보)</span><span class="sxs-lookup"><span data-stu-id="7092e-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7092e-109">XAML 값</span><span class="sxs-lookup"><span data-stu-id="7092e-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="7092e-110">리소스 어셈블리에 정의 된 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 공용 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-110">The name of the public [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="7092e-111">리소스의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-111">The key for the resource.</span></span> <span data-ttu-id="7092e-112">리소스가 조회 `targetID` 될 때는 리소스의 [x:Key 지시문](../../xaml-services/x-key-directive.md) 과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7092e-113">설명</span><span class="sxs-lookup"><span data-stu-id="7092e-113">Remarks</span></span>  
 <span data-ttu-id="7092e-114">위의 사용에서 볼 수 있듯이 {`ComponentResourceKey`} 태그 확장 사용은 다음 두 위치에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="7092e-115">컨트롤 작성자가 제공한 테마 리소스 사전 내에서 키의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="7092e-116">컨트롤을 다시 템플릿을 지정 컨트롤의 테마에서 제공 하는 리소스에서 제공 되는 속성 값을 사용 하려는 경우 어셈블리에서 테마 리소스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="7092e-117">테마에서 제공 되는 구성 요소 리소스를 참조 하는 경우 일반적으로 `{DynamicResource}` `{StaticResource}`대신를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="7092e-118">이는 사용법에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-118">This is shown in the usages.</span></span> <span data-ttu-id="7092e-119">`{DynamicResource}`사용자가 테마 자체를 변경할 수 있기 때문에를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="7092e-120">테마를 지원 하기 위한 컨트롤 작성자의 의도와 가장 일치 하는 구성 요소 리소스가 필요한 경우 구성 요소 리소스 참조를 동적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="7092e-121">는 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 리소스가 실제로 정의 된 대상 어셈블리에 있는 형식을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="7092e-122">는 가정의된<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 위치를 정확 하 게 파악 하는 것과 독립적으로 정의 하 고 사용할 수있지만결국에는참조된어셈블리를통해형식을확인해야합니다.`ComponentResourceKey`</span><span class="sxs-lookup"><span data-stu-id="7092e-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="7092e-123">의 <xref:System.Windows.ComponentResourceKey> 일반적인 용도는 클래스의 멤버로 노출 되는 키를 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="7092e-124">이러한 사용을 위해 태그 확장이 아니라 <xref:System.Windows.ComponentResourceKey> 클래스 생성자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="7092e-125">자세한 내용은 <xref:System.Windows.ComponentResourceKey> [컨트롤 제작 개요](../controls/control-authoring-overview.md)항목에서 또는 "테마 리소스의 키 정의 및 참조" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7092e-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="7092e-126">키를 설정 하 고 키가 지정 된 리소스를 참조 하는 경우 일반적 `ComponentResourceKey` 으로 특성 구문은 태그 확장에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="7092e-127">표시 되는 압축 구문은 태그 확장 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 의 생성자 시그니처와 위치 매개 변수 사용을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="7092e-128">`targetTypeName` 및`targetID` 가 제공 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="7092e-129">자세한 구문은 <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> 매개 변수가 없는 생성자를 사용 하 고 개체 요소의 진정한 특성 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 구문과 비슷한 방식으로 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="7092e-130">자세한 구문에서 속성이 설정 되는 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="7092e-131">이러한 두 가지 대안 (압축 및 자세한 정보)의 관계와 메커니즘은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)항목에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="7092e-132">기술적으로의 `targetID` 값은 임의의 개체 일 수 있으며, 문자열일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="7092e-133">그러나 WPF에서 가장 일반적으로 사용 되는 것은 문자열 `targetID` 형식으로 값을 정렬 하는 것입니다. 이러한 문자열은 [XamlName 문법](../../xaml-services/xamlname-grammar.md)에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="7092e-134">`ComponentResourceKey`개체 요소 구문에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="7092e-135">이 경우 확장을 제대로 초기화 하려면 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 및 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 속성의 값을 모두 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="7092e-136">판독기 구현에서이 태그 <xref:System.Windows.ComponentResourceKey> 확장에 대 한 처리는 클래스에 의해 정의 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7092e-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="7092e-137">`ComponentResourceKey`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="7092e-138">태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="7092e-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그 확장은 특성 구문에서 { 및 } 문자를 사용합니다. 이러한 문자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 태그 확장이 특성을 처리해야 함을 인식하는 데 사용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="7092e-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="7092e-140">자세한 내용은 [태그 확장 및 WPF XAML](markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7092e-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7092e-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="7092e-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7092e-142">컨트롤 제작 개요</span><span class="sxs-lookup"><span data-stu-id="7092e-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="7092e-143">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="7092e-143">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="7092e-144">태그 확장 및 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="7092e-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
