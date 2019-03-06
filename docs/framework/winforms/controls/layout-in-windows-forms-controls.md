---
title: Windows Forms 컨트롤의 레이아웃
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: a184eea8fd6804848cf7dfa324ef1430746ff7e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503296"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="74b00-102">Windows Forms 컨트롤의 레이아웃</span><span class="sxs-lookup"><span data-stu-id="74b00-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="74b00-103">폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="74b00-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스 이렇게 하려면 여러 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="74b00-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="74b00-105">In This Section</span></span>

<span data-ttu-id="74b00-106">[AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)\\</span><span class="sxs-lookup"><span data-stu-id="74b00-106">[AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md)\\</span></span>
<span data-ttu-id="74b00-107">에 대해 설명 합니다 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 레이아웃에서 해당 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="74b00-108">[여백 및 안쪽 여백 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)\\</span><span class="sxs-lookup"><span data-stu-id="74b00-108">[Margin and Padding in Windows Forms Controls](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)\\</span></span>
<span data-ttu-id="74b00-109">에 대해 설명 합니다 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성 및 레이아웃에서 해당 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="74b00-110">[방법: 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="74b00-110">[How to: Align a Control to the Edges of Forms](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)\\</span></span>
<span data-ttu-id="74b00-111">사용 하는 방법에 설명 합니다 <xref:System.Windows.Forms.Control.Dock%2A> 컨트롤을 폼의 가장자리에 맞게 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="74b00-112">[방법: Windows Forms 주위에 테두리 만들기 패딩을 사용 하 여 제어 합니다.](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span><span class="sxs-lookup"><span data-stu-id="74b00-112">[How to: Create a Border Around a Windows Forms Control Using Padding](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span></span>
<span data-ttu-id="74b00-113">사용 하는 방법에 설명 합니다 <xref:System.Windows.Forms.Control.Padding%2A> 속성 컨트롤을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="74b00-114">[방법: 사용자 지정 레이아웃 엔진 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)\\</span><span class="sxs-lookup"><span data-stu-id="74b00-114">[How to: Implement a Custom Layout Engine](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)\\</span></span>
<span data-ttu-id="74b00-115">구현 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Layout.LayoutEngine> Windows Forms 컨트롤 정렬에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="74b00-116">참조</span><span class="sxs-lookup"><span data-stu-id="74b00-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="74b00-117"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="74b00-118"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="74b00-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="74b00-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="74b00-119">See also</span></span>

- [<span data-ttu-id="74b00-120">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="74b00-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="74b00-121">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="74b00-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="74b00-122">방법: 지역화에 효과적으로 대응 하는 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="74b00-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="74b00-123">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="74b00-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
