---
title: '방법: 도구 스트립 항목의 간격 및 정렬 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182237"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="1c0f8-102">방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경</span><span class="sxs-lookup"><span data-stu-id="1c0f8-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="1c0f8-103">컨트롤은 <xref:System.Windows.Forms.ToolStrip> 크기 조정, 서로에 대한 <xref:System.Windows.Forms.ToolStripItem> 컨트롤의 간격, <xref:System.Windows.Forms.ToolStrip>에 대한 컨트롤의 배열 및 <xref:System.Windows.Forms.ToolStrip>에 대한 컨트롤의 간격과 같은 레이아웃 기능을 완벽하게 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="1c0f8-104"><xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성의 기본값은 `true`에서 속성을 설정하지 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 않으면 컨트롤의 크기가 자동으로 조정됩니다. `false`</span><span class="sxs-lookup"><span data-stu-id="1c0f8-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="1c0f8-105">수동으로 도구 스트립 항목의 크기를 조정하려면</span><span class="sxs-lookup"><span data-stu-id="1c0f8-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="1c0f8-106">연결된 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> `false` 컨트롤에 대한 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="1c0f8-107">연결된 <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStripItem.Size%2A> 에 대해 원하는 방식으로 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="1c0f8-108">도구스트립항목의 간격을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1c0f8-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="1c0f8-109">원하는 값을 픽셀 단위로 연관된 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 컨트롤의 속성에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="1c0f8-110"><xref:System.Windows.Forms.ToolStripItem.Margin%2A> 속성값은 항목과 인접 항목 사이의 간격을 왼쪽, 위쪽, 오른쪽 및 아래쪽 순서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="1c0f8-111">도구 스트립의 오른쪽에 ToolStrip항목을 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="1c0f8-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="1c0f8-112">연결된 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 컨트롤에 대한 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="1c0f8-113">기본적으로 은의 왼쪽에 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Left> <xref:System.Windows.Forms.ToolStrip>컨트롤을 정렬하는 로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="1c0f8-114">도구 스트립에서 도구 스트립 항목을 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="1c0f8-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="1c0f8-115"><xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성을 원하는 값으로 <xref:System.Windows.Forms.ToolStripLayoutStyle> 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0f8-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c0f8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c0f8-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="1c0f8-117">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1c0f8-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="1c0f8-118">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="1c0f8-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="1c0f8-119">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="1c0f8-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
