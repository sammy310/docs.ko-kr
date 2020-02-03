---
title: '방법: ToolStrip 오버플로 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736150"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="0be60-102">방법: Windows Forms의 ToolStrip 오버플로 관리</span><span class="sxs-lookup"><span data-stu-id="0be60-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="0be60-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤의 모든 항목이 할당 된 공간에 맞지 않는 경우 <xref:System.Windows.Forms.ToolStrip>에서 오버플로 기능을 사용 하도록 설정 하 고 특정 <xref:System.Windows.Forms.ToolStripItem>s의 오버플로 동작을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="0be60-104">양식의 현재 크기에 따라 <xref:System.Windows.Forms.ToolStrip>에 할당 된 것 보다 더 많은 공간이 필요한 <xref:System.Windows.Forms.ToolStripItem>을 추가 하면 <xref:System.Windows.Forms.ToolStrip>에 <xref:System.Windows.Forms.ToolStripOverflowButton> 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="0be60-105"><xref:System.Windows.Forms.ToolStripOverflowButton> 나타나고 오버플로 사용 항목이 드롭다운 오버플로 메뉴로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="0be60-106">이를 통해 <xref:System.Windows.Forms.ToolStrip> 항목이 다른 폼 크기로 적절히 조정 되는 방법을 사용자 지정 하 고 우선 순위를 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="0be60-107"><xref:System.Windows.Forms.ToolStripItem.Placement%2A> 및 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트를 사용 하 여 오버플로에 도달 하는 경우 항목의 모양을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="0be60-108">디자인 타임 또는 런타임에 폼을 확대 하는 경우 주 <xref:System.Windows.Forms.ToolStrip>에 더 많은 <xref:System.Windows.Forms.ToolStripItem>s를 표시할 수 있으며 폼의 크기를 줄일 때까지 <xref:System.Windows.Forms.ToolStripOverflowButton> 사라질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="0be60-109">ToolStrip 컨트롤에서 오버플로를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0be60-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="0be60-110"><xref:System.Windows.Forms.ToolStrip>에 대해 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 속성이 `false`로 설정 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="0be60-111">기본값은 `True`입니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-111">The default is `True`.</span></span>

     <span data-ttu-id="0be60-112"><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `True` (기본값) 이면 <xref:System.Windows.Forms.ToolStripItem>의 내용이 가로 <xref:System.Windows.Forms.ToolStrip>의 너비 또는 세로 <xref:System.Windows.Forms.ToolStrip>높이를 초과할 때 드롭다운 오버플로 메뉴로 <xref:System.Windows.Forms.ToolStripItem> 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="0be60-113">특정 ToolStripItem의 오버플로 동작을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="0be60-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="0be60-114"><xref:System.Windows.Forms.ToolStripItem>의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="0be60-115">가능성은 `Always`, `Never`및 `AsNeeded`입니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="0be60-116">기본값은 `AsNeeded`입니다.</span><span class="sxs-lookup"><span data-stu-id="0be60-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="0be60-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0be60-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="0be60-118">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0be60-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="0be60-119">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0be60-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="0be60-120">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="0be60-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
