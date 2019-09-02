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
ms.openlocfilehash: b68909d94ad8cc5bba75b2c520db82c5ccf1b922
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206183"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="b7bbc-102">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="b7bbc-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="b7bbc-103">태그 파일 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 에서 발생 하는 네임 스페이스 접두사를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 무시할 수 있는 것으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="b7bbc-104">특성 `mc:Ignorable` 은 사용자 지정 네임 스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리에 대 한 태그 호환성을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="b7bbc-105">XAML 특성 사용 (단일 접두사)</span><span class="sxs-lookup"><span data-stu-id="b7bbc-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="b7bbc-106">XAML 특성 사용 (두 개의 접두사)</span><span class="sxs-lookup"><span data-stu-id="b7bbc-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b7bbc-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="b7bbc-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7bbc-108">*ignorablePrefix, ignorablePrefix1, etc.*</span><span class="sxs-lookup"><span data-stu-id="b7bbc-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="b7bbc-109">XML 1.0 사양에 따라 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b7bbc-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="b7bbc-110">*ignorableUri*</span></span>|<span data-ttu-id="b7bbc-111">XML 1.0 사양에 따라 네임 스페이스를 지정 하는 데 사용할 수 있는 모든 유효한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="b7bbc-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="b7bbc-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="b7bbc-113">내부 형식을 확인할 수 없는 경우 프로세서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 구현에서 무시할 수 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7bbc-114">설명</span><span class="sxs-lookup"><span data-stu-id="b7bbc-114">Remarks</span></span>  
 <span data-ttu-id="b7bbc-115">네임 스페이스 접두사는 호환성 네임 스페이스 `http://schemas.openxmlformats.org/markup-compatibility/2006`를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 매핑할 때 사용 하는 권장 접두사 규칙입니다. `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bbc-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="b7bbc-116">요소 이름의 접두사 부분이로 `mc:Ignorable` 식별 된 요소 또는 특성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 처리할 때 오류를 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="b7bbc-117">해당 특성을 기본 형식 또는 프로그래밍 구문으로 확인할 수 없으면 해당 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="b7bbc-118">그러나 무시 된 요소는 해당 요소가 처리 되지 않는 부작용 인 추가 요소 요구 사항에 대 한 추가 구문 분석 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="b7bbc-119">예를 들어, 특정 요소 콘텐츠 모델에는 정확히 하나의 자식 요소가 필요할 수 있지만 지정 된 자식 요소가 `mc:Ignorable` 접두사에 있고 지정 된 자식 요소를 형식으로 확인할 수 없는 경우 프로세서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="b7bbc-120">`mc:Ignorable`식별자 문자열에 대 한 네임 스페이스 매핑에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="b7bbc-121">`mc:Ignorable`는 CLR 네임 스페이스 및 어셈블리를 지정 하는 어셈블리에 대 한 네임 스페이스 매핑과 적용 되지 않습니다. 또는 현재 실행 파일을 어셈블리로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="b7bbc-122">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서를 구현 하는 경우 프로세서 구현에서는로 `mc:Ignorable`식별 된 접두사에 의해 정규화 된 요소나 특성에 대 한 형식 확인의 구문 분석 또는 처리 오류를 발생 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="b7bbc-123">그러나 프로세서 구현에서는 이전에 제공 된 단일 자식 요소 예제와 같이 로드 되지 않거나 처리 하지 못한 요소의 보조 결과인 예외를 여전히 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="b7bbc-124">기본적으로 프로세서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 무시 된 요소 내의 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="b7bbc-125">그러나 추가 특성인 [mc: ProcessContent 특성](mc-processcontent-attribute.md)을 지정 하 여 사용 가능한 다음 부모 요소에 의해 무시 된 요소 내에서 콘텐츠를 지속적으로 처리 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="b7bbc-126">특성에서 하나 이상의 공백 문자를 구분 기호로 사용 하 여 여러 접두사를 지정할 수 있습니다 (예: `mc:Ignorable="ignore1 ignore2"`).</span><span class="sxs-lookup"><span data-stu-id="b7bbc-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="b7bbc-127">네임 `http://schemas.openxmlformats.org/markup-compatibility/2006` 스페이스는 SDK의이 영역에 문서화 되지 않은 다른 요소 및 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="b7bbc-128">자세한 내용은 [XML 태그 호환성 사양](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7bbc-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bbc-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7bbc-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="b7bbc-130">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="b7bbc-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="b7bbc-131">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="b7bbc-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="b7bbc-132">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="b7bbc-132">Documents in WPF</span></span>](documents-in-wpf.md)
