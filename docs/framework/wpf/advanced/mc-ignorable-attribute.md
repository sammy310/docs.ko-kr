---
title: mc:Ignorable 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: d8fdeec8784c9a44c9b272a0a5a8b9c56ace5230
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458822"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="3df44-102">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="3df44-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="3df44-103">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 태그 파일에 있는 네임 스페이스 접두사를 무시할 수 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="3df44-104">`mc:Ignorable` 특성은 사용자 지정 네임 스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리에 대 한 태그 호환성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="3df44-105">XAML 특성 사용 (단일 접두사)</span><span class="sxs-lookup"><span data-stu-id="3df44-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="3df44-106">XAML 특성 사용 (두 개의 접두사)</span><span class="sxs-lookup"><span data-stu-id="3df44-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3df44-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="3df44-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3df44-108">*ignorablePrefix, ignorablePrefix1 등*</span><span class="sxs-lookup"><span data-stu-id="3df44-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="3df44-109">XML 1.0 사양에 따라 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="3df44-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="3df44-110">*ignorableUri*</span></span>|<span data-ttu-id="3df44-111">XML 1.0 사양에 따라 네임 스페이스를 지정 하는 데 사용할 수 있는 모든 유효한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="3df44-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="3df44-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="3df44-113">기본 형식을 확인할 수 없는 경우 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 프로세서 구현에서 무시할 수 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3df44-114">주의</span><span class="sxs-lookup"><span data-stu-id="3df44-114">Remarks</span></span>  
 <span data-ttu-id="3df44-115">`mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스 접두사는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 호환성 네임 스페이스 `http://schemas.openxmlformats.org/markup-compatibility/2006`를 매핑할 때 사용 하는 권장 접두사 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="3df44-116">요소 이름의 접두사 부분이 `mc:Ignorable`으로 식별 되는 요소나 특성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 처리할 때 오류를 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="3df44-117">해당 특성을 기본 형식 또는 프로그래밍 구문으로 확인할 수 없으면 해당 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="3df44-118">그러나 무시 된 요소는 해당 요소가 처리 되지 않는 부작용 인 추가 요소 요구 사항에 대 한 추가 구문 분석 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="3df44-119">예를 들어, 특정 요소 콘텐츠 모델에는 정확히 하나의 자식 요소가 필요할 수 있지만 지정 된 자식 요소가 `mc:Ignorable` 접두사에 있고 지정 된 자식 요소가 형식으로 확인 되지 않은 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 오류를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="3df44-120">`mc:Ignorable`는 식별자 문자열에 대 한 네임 스페이스 매핑에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="3df44-121">CLR 네임 스페이스와 어셈블리를 지정 하는 어셈블리에는 네임 스페이스 매핑에 적용 되지 않습니다 .이 어셈블리는 CLR 네임 스페이스와 어셈블리를 지정 합니다 (또는 현재 실행 파일을 어셈블리로 기본 지정). `mc:Ignorable`</span><span class="sxs-lookup"><span data-stu-id="3df44-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="3df44-122">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서를 구현 하는 경우 프로세서 구현에서는 `mc:Ignorable`로 식별 된 접두사에 의해 정규화 된 요소나 특성에 대 한 형식 확인 시 구문 분석 또는 처리 오류를 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="3df44-123">그러나 프로세서 구현에서는 이전에 제공 된 단일 자식 요소 예제와 같이 로드 되지 않거나 처리 하지 못한 요소의 보조 결과인 예외를 여전히 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="3df44-124">기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 된 요소 내의 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="3df44-125">그러나 추가 특성인 [mc: ProcessContent 특성](mc-processcontent-attribute.md)을 지정 하 여 사용 가능한 다음 부모 요소에 의해 무시 된 요소 내에서 콘텐츠를 지속적으로 처리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="3df44-126">하나 이상의 공백 문자를 구분 기호로 사용 하 여 특성에 여러 접두사를 지정할 수 있습니다 (예: `mc:Ignorable="ignore1 ignore2"`).</span><span class="sxs-lookup"><span data-stu-id="3df44-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="3df44-127">`http://schemas.openxmlformats.org/markup-compatibility/2006` 네임 스페이스는 SDK의이 영역에 문서화 되지 않은 다른 요소와 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df44-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="3df44-128">자세한 내용은 [XML 태그 호환성 사양](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3df44-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df44-129">참조</span><span class="sxs-lookup"><span data-stu-id="3df44-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="3df44-130">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="3df44-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="3df44-131">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="3df44-131">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="3df44-132">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="3df44-132">Documents in WPF</span></span>](documents-in-wpf.md)
