---
title: 컨트롤의 레이아웃
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: ed8603e997e7d0c1ed7a2ebda6dc960726d32f45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745243"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="d13f6-102">Windows Forms 컨트롤의 레이아웃</span><span class="sxs-lookup"><span data-stu-id="d13f6-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="d13f6-103">폼의 정확한 컨트롤 배치는 많은 애플리케이션에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="d13f6-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스는이를 위해 다양 한 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d13f6-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d13f6-105">In This Section</span></span>

<span data-ttu-id="d13f6-106">[AutoSize 속성 개요](autosize-property-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d13f6-106">[AutoSize Property Overview](autosize-property-overview.md)</span></span>\
<span data-ttu-id="d13f6-107">레이아웃의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 해당 역할에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="d13f6-108">[Windows Forms 컨트롤의 여백 및 안쪽 여백](margin-and-padding-in-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="d13f6-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)</span></span>\
<span data-ttu-id="d13f6-109">레이아웃의 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성과 해당 역할에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="d13f6-110">[방법: 컨트롤을 폼의 가장자리에 맞춤](how-to-align-a-control-to-the-edges-of-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d13f6-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)</span></span>\
<span data-ttu-id="d13f6-111"><xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용 하 여 컨트롤을 사용 하는 폼의 가장자리에 맞추는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="d13f6-112">[방법: 안쪽 여백을 사용 하 여 Windows Forms 컨트롤 주위에 테두리 만들기](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span><span class="sxs-lookup"><span data-stu-id="d13f6-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)</span></span>\
<span data-ttu-id="d13f6-113"><xref:System.Windows.Forms.Control.Padding%2A> 속성을 사용 하 여 컨트롤의 윤곽선을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="d13f6-114">[방법: 사용자 지정 레이아웃 엔진 구현](how-to-implement-a-custom-layout-engine.md)</span><span class="sxs-lookup"><span data-stu-id="d13f6-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)</span></span>\
<span data-ttu-id="d13f6-115">Windows Forms 컨트롤을 정렬 하는 <xref:System.Windows.Forms.Layout.LayoutEngine>을 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="d13f6-116">참조</span><span class="sxs-lookup"><span data-stu-id="d13f6-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="d13f6-117"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="d13f6-118"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d13f6-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="d13f6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d13f6-119">See also</span></span>

- [<span data-ttu-id="d13f6-120">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="d13f6-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="d13f6-121">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="d13f6-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d13f6-122">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="d13f6-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="d13f6-123">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d13f6-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
