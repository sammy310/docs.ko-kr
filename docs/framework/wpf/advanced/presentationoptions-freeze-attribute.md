---
title: PresentationOptions:Freeze 특성
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772842"
---
# <a name="presentationoptionsfreeze-attribute"></a><span data-ttu-id="2f1cf-102">PresentationOptions:Freeze 특성</span><span class="sxs-lookup"><span data-stu-id="2f1cf-102">PresentationOptions:Freeze Attribute</span></span>
<span data-ttu-id="2f1cf-103">집합의 <xref:System.Windows.Freezable.IsFrozen%2A> 상태 `true` 포함 하는에 <xref:System.Windows.Freezable> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-103">Sets the <xref:System.Windows.Freezable.IsFrozen%2A> state to `true` on the containing <xref:System.Windows.Freezable> element.</span></span> <span data-ttu-id="2f1cf-104">기본 동작에 대 한는 <xref:System.Windows.Freezable> 없이 `PresentationOptions:Freeze` 는 지정 된 특성 <xref:System.Windows.Freezable.IsFrozen%2A> 됩니다 `false` 로드 시간 및 일반에 의존 하는 <xref:System.Windows.Freezable> 런타임에 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-104">Default behavior for a <xref:System.Windows.Freezable> without the `PresentationOptions:Freeze` attribute specified is that <xref:System.Windows.Freezable.IsFrozen%2A> is `false` at load time, and dependent on general <xref:System.Windows.Freezable> behavior at runtime.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2f1cf-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="2f1cf-105">XAML Attribute Usage</span></span>  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="2f1cf-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="2f1cf-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`PresentationOptions`|<span data-ttu-id="2f1cf-107">XML 네임 스페이스 접두사를 XML 1.0 사양에 따라 유효한 접두사 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-107">An XML namespace prefix, which can be any valid prefix string, per the XML 1.0 specification.</span></span> <span data-ttu-id="2f1cf-108">접두사 `PresentationOptions` 이 설명서의 식별을 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-108">The prefix `PresentationOptions` is used for identification purposes in this documentation.</span></span>|  
|`freezableElement`|<span data-ttu-id="2f1cf-109">요소 하나를 인스턴스화하는 파생 클래스의 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-109">An element that instantiates any derived class of <xref:System.Windows.Freezable>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f1cf-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f1cf-110">Remarks</span></span>  
 <span data-ttu-id="2f1cf-111">합니다 `Freeze` 특성은 유일한 특성 또는 기타 프로그래밍 요소에 정의 된는 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-111">The `Freeze` attribute is the only attribute or other programming element defined in the `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML namespace.</span></span> <span data-ttu-id="2f1cf-112">합니다 `Freeze` 특성으로 무시할 수 있는 사용 하 여 지정 될 수 있도록 특별히이 특별 한 네임 스페이스에 존재 [mc: Ignorable 특성](mc-ignorable-attribute.md) 루트 요소 선언의 일부로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-112">The `Freeze` attribute exists in this special namespace specifically so that it can be designated as ignorable, using [mc:Ignorable Attribute](mc-ignorable-attribute.md) as part of the root element declarations.</span></span> <span data-ttu-id="2f1cf-113">이유는 `Freeze` 무시할 수 있어야 아닙니다 때문에 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 고정할 수 있는 프로세서 구현을 <xref:System.Windows.Freezable> 로드 시이 기능은 없습니다 부분을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사양.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-113">The reason that `Freeze` must be able to be ignorable is because not all [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementations are able to freeze a <xref:System.Windows.Freezable> at load time; this capability is not part of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specification.</span></span>  
  
 <span data-ttu-id="2f1cf-114">처리 하는 기능을 `Freeze` 특성은 특히에 내장 되어를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 프로세서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 컴파일된 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-114">The ability to process the `Freeze` attribute is specifically built in to the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor that processes [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for compiled applications.</span></span> <span data-ttu-id="2f1cf-115">특성이 모든 클래스에서 지원 되지 않습니다 및 특성 구문이 확장 하거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-115">The attribute is not supported by any class, and the attribute syntax is not extensible or modifiable.</span></span> <span data-ttu-id="2f1cf-116">구현 하는 경우 사용자 고유의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 병렬의 동작을 중단 하도록 선택할 수 있습니다 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리 하는 경우 프로세서는 `Freeze` 특성을 <xref:System.Windows.Freezable> 로드 시 요소.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-116">If you are implementing your own [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor you can choose to parallel the freezing behavior of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor when processing the `Freeze` attribute on <xref:System.Windows.Freezable> elements at load time.</span></span>  
  
 <span data-ttu-id="2f1cf-117">에 대 한 모든 값을 `Freeze` 이외의 특성 `true` (없습니다 대/소문자 구분)는 로드 시간 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f1cf-117">Any value for the `Freeze` attribute other than `true` (not case sensitive) generates a load time error.</span></span> <span data-ttu-id="2f1cf-118">(지정 하는 `Freeze` 특성은 `false` 오류가 되지 않지만 기본값을 설정 하므로 이미 `false` 아무 작업도 수행 하지).</span><span class="sxs-lookup"><span data-stu-id="2f1cf-118">(Specifying the `Freeze` attribute as `false` is not an error, but that is already the default, so setting to `false` does nothing).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f1cf-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f1cf-119">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="2f1cf-120">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="2f1cf-120">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="2f1cf-121">mc:Ignorable 특성</span><span class="sxs-lookup"><span data-stu-id="2f1cf-121">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
