---
title: PresentationOptions:Freeze 특성
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991422"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="a24a8-102">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="a24a8-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="a24a8-103"><xref:System.Windows.Freezable.IsFrozen%2A> 포함 `true` 하는 요소에 대 한 상태를로 설정 합니다. <xref:System.Windows.Freezable></span><span class="sxs-lookup"><span data-stu-id="a24a8-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="a24a8-104"><xref:System.Windows.Freezable> 특성이지정<xref:System.Windows.Freezable.IsFrozen%2A> 되지않은<xref:System.Windows.Freezable> 의 기본 동작은 로드 시 이며 런타임에 일반적인 동작에 따라 달라 집니다. `false` `PresentationOptions:Freeze`</span><span class="sxs-lookup"><span data-stu-id="a24a8-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a24a8-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="a24a8-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a24a8-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="a24a8-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="a24a8-107">Xml 1.0 사양에 따라 유효한 접두사 문자열일 수 있는 XML 네임 스페이스 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="a24a8-108">이 설명서 `PresentationOptions` 에서는 접두사가 식별 목적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="a24a8-109">의 <xref:System.Windows.Freezable>파생 클래스를 인스턴스화하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a24a8-110">설명</span><span class="sxs-lookup"><span data-stu-id="a24a8-110">Remarks</span></span>  
 <span data-ttu-id="a24a8-111">특성은 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임 스페이스에 정의 된 유일한 특성 또는 기타 프로그래밍 요소입니다. `Freeze`</span><span class="sxs-lookup"><span data-stu-id="a24a8-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="a24a8-112">특성 `Freeze` 은이 특수 네임 스페이스에 존재 하므로,이 특수 네임 스페이스는 [mc: ignorable 특성](mc-ignorable-attribute.md) 을 루트 요소 선언의 일부로 사용 하 여 무시할 수 있는 것으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="a24a8-113">무시할 수 `Freeze` 있어야 하는 이유는 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현이 로드 시을 <xref:System.Windows.Freezable> 중지할 수 없기 때문입니다 .이 기능은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="a24a8-114">`Freeze` 특성을 처리 하는 기능은 컴파일된 응용 프로그램을 처리 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 하 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 프로세서에 특히 내장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="a24a8-115">특성은 모든 클래스에서 지원 되지 않으며 특성 구문은 확장 또는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="a24a8-116">사용자 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고유의 프로세서를 구현 하는 경우 로드 시 요소에 대 <xref:System.Windows.Freezable> 한 특성을 `Freeze` 처리할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 때 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 고정 동작을 병렬로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="a24a8-117">(대/소문자 `Freeze` 구분 안 함 `true` ) 이외의 특성 값은 로드 시간 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="a24a8-118">`Freeze` 특성을로 `false` 지정 하는 것은 오류가 아니라 이미 기본값 이므로로 `false` 설정 해도 아무 작업도 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a24a8-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24a8-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="a24a8-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="a24a8-120">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="a24a8-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="a24a8-121">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="a24a8-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
