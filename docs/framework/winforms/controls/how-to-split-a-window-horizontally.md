---
title: '방법: 가로로 창 분할'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 7ef3fe1210ae42c52a4fd7f23633d6566bc102a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956066"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="5f3d8-102">방법: 가로로 창 분할</span><span class="sxs-lookup"><span data-stu-id="5f3d8-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="5f3d8-103">다음 코드 예제에서는 컨트롤을 <xref:System.Windows.Forms.SplitContainer> 가로로 나누는 분할자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f3d8-104">컨트롤의 속성은 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 컨트롤이 아니라 분할자의 방향을 결정 합니다. <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="5f3d8-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="5f3d8-105">창을 가로로 분할 하려면</span><span class="sxs-lookup"><span data-stu-id="5f3d8-105">To split a window horizontally</span></span>  
  
1. <span data-ttu-id="5f3d8-106">프로시저 내에서 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> <xref:System.Windows.Forms.SplitContainer> 컨트롤의 속성을로 <xref:System.Windows.Forms.Orientation.Horizontal>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3d8-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5f3d8-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f3d8-107">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="5f3d8-108">SplitContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5f3d8-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
