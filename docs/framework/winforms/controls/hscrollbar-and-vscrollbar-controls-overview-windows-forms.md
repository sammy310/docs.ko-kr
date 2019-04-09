---
title: HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: d4a7912a5781fc583357affa728f7d81059b5cf9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097319"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="9c52f-102">HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9c52f-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="9c52f-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> 컨트롤은 가로로 또는 세로로 응용 프로그램 또는 컨트롤 내에서 쉽게 탐색 긴 목록 항목 또는 많은 양의 정보를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="9c52f-104">스크롤 막대는 Windows 인터페이스의 공통 요소 이므로 <xref:System.Windows.Forms.ScrollBar> 컨트롤에서 파생 되지 않은 컨트롤을 사용 하 여 흔히는 <xref:System.Windows.Forms.ScrollableControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="9c52f-105">통합 하기 위해 많은 개발자 선택 마찬가지로 <xref:System.Windows.Forms.ScrollBar> 자체 사용자 정의 컨트롤을 작성 하는 경우를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="9c52f-106">합니다 <xref:System.Windows.Forms.HScrollBar> (수평) 및 <xref:System.Windows.Forms.VScrollBar> (세로) 컨트롤을 다른 컨트롤에서 독립적으로 작동할 수 있고 자체 이벤트, 속성 및 메서드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <xref:System.Windows.Forms.ScrollBar> <span data-ttu-id="9c52f-107">컨트롤은 텍스트 상자나 목록 상자, 콤보 상자, MDI 폼에 연결 되어 있는 기본 제공 스크롤 막대와 동일 하지 않습니다 (합니다 <xref:System.Windows.Forms.TextBox> 컨트롤에는 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 컨트롤에 연결 되어 있는 스크롤 막대 표시 또는 숨기기).</span><span class="sxs-lookup"><span data-stu-id="9c52f-107">controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="9c52f-108">합니다 <xref:System.Windows.Forms.ScrollBar> 사용을 제어 합니다 <xref:System.Windows.Forms.ScrollBar.Scroll> 스크롤 막대에 스크롤 상자 (엄지 단추 라고도 함)의 움직임을 모니터링 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="9c52f-109">사용 하는 <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 끄는 대로 스크롤 막대의 값에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="9c52f-110">값 속성</span><span class="sxs-lookup"><span data-stu-id="9c52f-110">Value Property</span></span>  
 <span data-ttu-id="9c52f-111">합니다 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성 (즉, 기본적으로 0)는는 `integer` 스크롤 막대의 스크롤 상자 위치에 해당 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="9c52f-112">스크롤 상자 위치를 최소 값인 경우의 가장 왼쪽 위치 (가로 스크롤 막대) 또는 세로 스크롤 막대를 위쪽 위치를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="9c52f-113">스크롤 상자의 경우 최 댓 값, 맨 오른쪽으로 스크롤 상자 이동 이나 아래쪽 위치.</span><span class="sxs-lookup"><span data-stu-id="9c52f-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="9c52f-114">마찬가지로, 중간 및 범위의 상한 값 스크롤 상자 중간 스크롤 막대의 선행 가장자리를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="9c52f-115">스크롤 막대의 값을 변경 하려면 마우스 클릭을 사용 하는 것 외에도 사용자 막대를 따라 모든 지점으로 사용 하는 스크롤 상자를 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="9c52f-116">결과 값의 스크롤 상자 위치에 따라 달라 지지만 범위 내 합니다 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 에 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 사용자가 설정 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="9c52f-117">LargeChange 및 SmallChange 속성</span><span class="sxs-lookup"><span data-stu-id="9c52f-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="9c52f-118">사용자가 PAGE UP 또는 PAGE DOWN 키를 누르거나 스크롤 상자 옆에 있는 스크롤 막대 트랙에서 클릭할 때 합니다 <xref:System.Windows.Forms.ScrollBar.Value%2A> 에 설정 된 값에 따라 속성 변경 내용을 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="9c52f-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="9c52f-119">키 또는 스크롤 막대 단추 중 하나를 클릭할 때 사용자가 누를 화살표 중 하나는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 에 설정 된 값에 따라 속성 변경 내용을 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9c52f-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c52f-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="9c52f-120">See also</span></span>

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [<span data-ttu-id="9c52f-121">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9c52f-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
