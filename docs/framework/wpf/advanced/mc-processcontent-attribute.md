---
title: mc:ProcessContent 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 619c3ffbc68c8c72ea9dd6545ab8da536380483b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206176"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="7bd0f-102">mc:ProcessContent 특성</span><span class="sxs-lookup"><span data-stu-id="7bd0f-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="7bd0f-103">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [Mc: Ignorable 특성](mc-ignorable-attribute.md)을 지정 하 여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 직계 부모 요소를 무시할 수 있는 경우에도 관련 부모 요소에 의해 처리 되는 콘텐츠를 계속 포함 해야 하는 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="7bd0f-104">특성 `mc:ProcessContent` 은 사용자 지정 네임 스페이스 매핑과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리에 대 한 태그 호환성을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7bd0f-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="7bd0f-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7bd0f-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="7bd0f-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7bd0f-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="7bd0f-107">*ignorablePrefix*</span></span>|<span data-ttu-id="7bd0f-108">XML 1.0 사양에 따라 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="7bd0f-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="7bd0f-109">*ignorableUri*</span></span>|<span data-ttu-id="7bd0f-110">XML 1.0 사양에 따라 네임 스페이스를 지정 하는 데 사용할 수 있는 모든 유효한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="7bd0f-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="7bd0f-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="7bd0f-112">내부 형식을 확인할 수 없는 경우 프로세서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 구현에서 무시할 수 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="7bd0f-113">*[content]*</span><span class="sxs-lookup"><span data-stu-id="7bd0f-113">*[content]*</span></span>|<span data-ttu-id="7bd0f-114">*ThisElementCanBeIgnored* 은 무시할 수 있는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="7bd0f-115">프로세서에서 해당 요소를 무시 하면 *[content]* 는 *개체*에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bd0f-116">설명</span><span class="sxs-lookup"><span data-stu-id="7bd0f-116">Remarks</span></span>  
 <span data-ttu-id="7bd0f-117">기본적으로 프로세서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 무시 된 요소 내의 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="7bd0f-118">를 기준 `mc:ProcessContent`으로 특정 요소를 지정할 수 있으며, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 무시 된 요소 내에서 콘텐츠를 계속 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="7bd0f-119">이는 일반적으로 콘텐츠가 여러 태그 내에 중첩 되어 있고, 하나 이상의 태그를 무시할 수 있으며,이 중 하나 이상이 무시할 수 없는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="7bd0f-120">공백 구분 기호를 사용 하 여 특성에 여러 접두사를 지정할 수 있습니다 (예 `mc:ProcessContent="ignore:Element1 ignore:Element2"`:).</span><span class="sxs-lookup"><span data-stu-id="7bd0f-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="7bd0f-121">네임 `http://schemas.openxmlformats.org/markup-compatibility/2006` 스페이스는 SDK의이 영역에 문서화 되지 않은 다른 요소 및 특성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="7bd0f-122">자세한 내용은 [XML 태그 호환성 사양](https://go.microsoft.com/fwlink/?LinkId=73824)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bd0f-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd0f-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="7bd0f-123">See also</span></span>

- [<span data-ttu-id="7bd0f-124">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="7bd0f-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="7bd0f-125">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="7bd0f-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
