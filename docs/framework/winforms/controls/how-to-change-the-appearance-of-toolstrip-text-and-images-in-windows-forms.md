---
title: '방법: ToolStrip 텍스트 및 이미지의 모양 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746600"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="6ad0e-102">방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="6ad0e-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="6ad0e-103">텍스트 및 이미지가 <xref:System.Windows.Forms.ToolStripItem>에 표시 되는지 여부와 서로 상대적 <xref:System.Windows.Forms.ToolStrip>으로 정렬 되는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="6ad0e-104">ToolStripItem에 표시 되는 항목을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="6ad0e-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="6ad0e-105"><xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="6ad0e-106">이러한 가능성은 `Image`, `ImageAndText`, `None`및 `Text`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="6ad0e-107">기본값은 `ImageAndText`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="6ad0e-108">ToolStripItem에서 텍스트를 맞추려면</span><span class="sxs-lookup"><span data-stu-id="6ad0e-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="6ad0e-109"><xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="6ad0e-110">가능한 것은 왼쪽, 가운데 및 오른쪽의 위쪽, 가운데 및 아래쪽 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="6ad0e-111">기본값은 `MiddleCenter`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="6ad0e-112">ToolStripItem에서 이미지를 맞추려면</span><span class="sxs-lookup"><span data-stu-id="6ad0e-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="6ad0e-113"><xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="6ad0e-114">가능한 것은 왼쪽, 가운데 및 오른쪽의 위쪽, 가운데 및 아래쪽 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="6ad0e-115">기본값은 `MiddleLeft`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="6ad0e-116">ToolStripItem 텍스트 및 이미지가 서로를 기준으로 표시 되는 방법을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="6ad0e-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="6ad0e-117"><xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성을 원하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="6ad0e-118">가능성은 `ImageAboveText`, `ImageBeforeText`를 `Overlay`합니다 `TextAboveImage`, 및 `TextBeforeImage`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="6ad0e-119">기본값은 `ImageBeforeText`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad0e-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ad0e-120">참조</span><span class="sxs-lookup"><span data-stu-id="6ad0e-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="6ad0e-121">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6ad0e-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="6ad0e-122">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6ad0e-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="6ad0e-123">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="6ad0e-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
