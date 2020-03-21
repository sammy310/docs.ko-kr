---
title: ContextMenu 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: 4d2d8db0f614b5240705146dbe91432b96b46dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185908"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="0dd0d-102">ContextMenu 개요</span><span class="sxs-lookup"><span data-stu-id="0dd0d-102">ContextMenu Overview</span></span>
<span data-ttu-id="0dd0d-103">클래스는 <xref:System.Windows.Controls.ContextMenu> 컨텍스트별 <xref:System.Windows.Controls.Menu>을 사용하여 기능을 노출하는 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="0dd0d-104">일반적으로 사용자는 마우스 버튼을 <xref:System.Windows.Controls.ContextMenu> 마우스 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 오른쪽 단추를 클릭하여 에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="0dd0d-105">이 항목에서는 <xref:System.Windows.Controls.ContextMenu> 요소를 소개하고 요소 및 코드 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="0dd0d-106">ContextMenu 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0dd0d-106">ContextMenu Control</span></span>  
 <span data-ttu-id="0dd0d-107">A는 <xref:System.Windows.Controls.ContextMenu> 특정 컨트롤에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="0dd0d-108">이 <xref:System.Windows.Controls.ContextMenu> 요소를 사용하면 특정 컨트롤과 연결된 명령이나 옵션(예: <xref:System.Windows.Controls.Button>을)을 지정하는 항목 목록을 사용자에게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="0dd0d-109">사용자가 컨트롤을 마우스 오른쪽 단추로 클릭하면 메뉴가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="0dd0d-110">일반적으로 를 <xref:System.Windows.Controls.MenuItem> 클릭하면 하위 메뉴가 열리거나 응용 프로그램이 명령을 수행하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="0dd0d-111">ContextMenu 만들기</span><span class="sxs-lookup"><span data-stu-id="0dd0d-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="0dd0d-112">다음 예제는 하위 메뉴를 <xref:System.Windows.Controls.ContextMenu> 사용하여 를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="0dd0d-113">컨트롤은 <xref:System.Windows.Controls.ContextMenu> 단추 컨트롤에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="0dd0d-114">ContextMenu에 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="0dd0d-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="0dd0d-115">컨트롤을 <xref:System.Windows.Style>사용하면 사용자 지정 컨트롤을 작성하지 않고도 <xref:System.Windows.Controls.ContextMenu> a의 모양과 동작을 크게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="0dd0d-116">시각적 속성을 설정하는 것 외에 컨트롤의 파트에 스타일을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="0dd0d-117">예를 들어 속성을 사용하여 컨트롤 부품의 동작을 변경하거나 <xref:System.Windows.Controls.ContextMenu>에 대한 부품을 추가하거나 의 레이아웃을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0dd0d-118">다음 예제는 컨트롤에 스타일을 추가하는 <xref:System.Windows.Controls.ContextMenu> 몇 가지 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="0dd0d-119">첫 번째 예제는 스타일에서 현재 시스템 설정을 사용하는 방법을 보여 주는 `SimpleSysResources`라는 스타일을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="0dd0d-120">이 예제는 <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> <xref:System.Windows.Controls.Control.Background%2A> 색상을 색으로 <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> <xref:System.Windows.Controls.Control.Foreground%2A> 지정하고 <xref:System.Windows.Controls.ContextMenu>을 의 색으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="0dd0d-121">다음 예제에서는 <xref:System.Windows.Trigger> 요소를 사용하여 <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.ContextMenu>에서 발생되는 이벤트에 대한 응답으로 a의 모양을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0dd0d-122">사용자가 메뉴 위로 마우스를 이동하면 항목의 <xref:System.Windows.Controls.ContextMenu> 모양이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dd0d-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dd0d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dd0d-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="0dd0d-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0dd0d-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="0dd0d-125">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0dd0d-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- <span data-ttu-id="0dd0d-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)(WPF 컨트롤 갤러리 샘플)</span><span class="sxs-lookup"><span data-stu-id="0dd0d-126">[WPF Controls Gallery Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)</span></span>
