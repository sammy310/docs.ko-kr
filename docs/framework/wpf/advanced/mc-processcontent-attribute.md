---
title: mc:ProcessContent 특성
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 865b1a3ccc30ff5efab4b08956bf7ba2bba4769c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017899"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="3f616-102">mc:ProcessContent 특성</span><span class="sxs-lookup"><span data-stu-id="3f616-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="3f616-103">지정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 직계 부모 요소에서 무시 될 수 있습니다 하는 경우에 요소에서는 관련 부모 요소에 의해 처리 되는 콘텐츠를 아직 해야를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 지정으로 인해 프로세서 [mc: Ignorable 특성](mc-ignorable-attribute.md) .</span><span class="sxs-lookup"><span data-stu-id="3f616-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="3f616-104">합니다 `mc:ProcessContent` 특성에 대 한 및 사용자 지정 네임 스페이스 매핑에 대 한 태그 호환성 지원 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 버전 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="3f616-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="3f616-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="3f616-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="3f616-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f616-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="3f616-107">*ignorablePrefix*</span></span>|<span data-ttu-id="3f616-108">XML 1.0 사양에 따라 모든 유효한 접두사 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="3f616-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="3f616-109">*ignorableUri*</span></span>|<span data-ttu-id="3f616-110">XML 1.0 사양에 따라 네임 스페이스를 지정 하는 것에 대 한 모든 유효한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="3f616-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="3f616-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="3f616-112">무시할 수 있는 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 내부 형식을 확인할 수 없는 경우 프로세서 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="3f616-113">*[content]*</span><span class="sxs-lookup"><span data-stu-id="3f616-113">*[content]*</span></span>|<span data-ttu-id="3f616-114">*ThisElementCanBeIgnored* 무시할 수 있는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="3f616-115">프로세서에서 해당 요소를 무시 하면 *[콘텐츠]* 에서 처리 되 *개체*합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f616-116">설명</span><span class="sxs-lookup"><span data-stu-id="3f616-116">Remarks</span></span>  
 <span data-ttu-id="3f616-117">기본적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 무시 된 요소 내에서 콘텐츠를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="3f616-118">특정 요소를 지정할 수 있습니다 `mc:ProcessContent`, 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 무시 요소 내에서 콘텐츠를 처리 하는 데 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="3f616-119">이 콘텐츠는 하나 이상의 무시할 수 있는 하나 이상의 무시할 수 있는 몇 가지 태그 안에 중첩 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="3f616-120">예를 들어는 공백 구분 기호로 사용 하 여 특성에 여러 개의 접두사를 지정할 수 있습니다: `mc:ProcessContent="ignore:Element1 ignore:Element2"`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="3f616-121">합니다 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] 다른 요소와의이 영역 내에서 다루지 않는 특성을 정의 하는 네임 스페이스는 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="3f616-122">자세한 내용은 [XML 태그 호환성 사양](https://go.microsoft.com/fwlink/?LinkId=73824)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f616-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f616-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f616-123">See also</span></span>

- [<span data-ttu-id="3f616-124">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="3f616-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="3f616-125">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="3f616-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
