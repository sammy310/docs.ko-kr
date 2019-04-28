---
title: '방법: ToolStrip 컨트롤에서 도구 설명 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: ffaf859fafc87131de525f7bf2f52db421a208c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785751"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="71c33-102">방법: ToolStrip 컨트롤에서 도구 설명 사용</span><span class="sxs-lookup"><span data-stu-id="71c33-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="71c33-103">표시할 수 있습니다는 <xref:System.Windows.Forms.ToolTip> 에 대 한 합니다 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 설정 하 여 원하는 컨트롤 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="71c33-104">도구 설명이 표시</span><span class="sxs-lookup"><span data-stu-id="71c33-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="71c33-105">설정 된 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 컨트롤의 속성 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="71c33-106">기본값인 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 은 `true`, 및 기본값인 <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> 는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="71c33-107">도구 설명 텍스트를 ToolStripButton의 ToolTipText 속성을 사용 하도록</span><span class="sxs-lookup"><span data-stu-id="71c33-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="71c33-108">설정 된 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 하는 단추의 속성 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="71c33-109">설정 된 <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> 하는 단추의 속성 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="71c33-110">합니다 `AutoToolTip` 속성은 `true` 에 대해 기본적으로 <xref:System.Windows.Forms.ToolStripButton>를 <xref:System.Windows.Forms.ToolStripDropDownButton>, 및 <xref:System.Windows.Forms.ToolStripSplitButton>합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="71c33-111">A <xref:System.Windows.Forms.ToolStripButton> 사용 하 여 해당 `Text` 속성에 대 한는 <xref:System.Windows.Forms.ToolTip> 기본적으로는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="71c33-112">이 절차의 사용자 지정 텍스트를 표시 하는 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>합니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71c33-113">설정 하는 경우 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 하 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, 텍스트가 없는 단추를 나타나지만 도구 설명도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c33-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c33-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="71c33-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="71c33-115">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="71c33-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
