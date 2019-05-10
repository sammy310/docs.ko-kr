---
title: '방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경'
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
ms.openlocfilehash: cf2f332b17bf6ff5b6ffb7cbc2d5777649728ec6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650853"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="a7df0-102">방법: Windows Forms에서 ToolStrip 텍스트 및 이미지의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="a7df0-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="a7df0-103">텍스트 및 이미지에 표시 되는지 여부를 제어할 수 있습니다는 <xref:System.Windows.Forms.ToolStripItem> 서로 기준으로 정렬 되는 방법 및 및 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="a7df0-104">ToolStripItem의 표시 되는 항목을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="a7df0-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="a7df0-105">설정 된 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="a7df0-106">가능성은 `Image`, `ImageAndText`하십시오 `None`, 및 `Text`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="a7df0-107">기본값은 `ImageAndText`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="a7df0-108">ToolStripItem의 텍스트에 맞게</span><span class="sxs-lookup"><span data-stu-id="a7df0-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="a7df0-109">설정 된 <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="a7df0-110">가능성은 중간 위쪽과 아래쪽 왼쪽, 가운데, 오른쪽을 사용 하 여 조합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="a7df0-111">기본값은 `MiddleCenter`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="a7df0-112">ToolStripItem의 이미지에 맞게</span><span class="sxs-lookup"><span data-stu-id="a7df0-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="a7df0-113">설정 된 <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="a7df0-114">가능성은 중간 위쪽과 아래쪽 왼쪽, 가운데, 오른쪽을 사용 하 여 조합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="a7df0-115">기본값은 `MiddleLeft`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="a7df0-116">Toolstripitem을 가리키는 텍스트 및 이미지 서로 기준으로 표시 되는 방법을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="a7df0-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="a7df0-117">설정 된 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="a7df0-118">가능성은 `ImageAboveText`, `ImageBeforeText`를 `Overlay`합니다 `TextAboveImage`, 및 `TextBeforeImage`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="a7df0-119">기본값은 `ImageBeforeText`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7df0-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a7df0-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="a7df0-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="a7df0-121">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="a7df0-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="a7df0-122">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a7df0-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="a7df0-123">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="a7df0-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
