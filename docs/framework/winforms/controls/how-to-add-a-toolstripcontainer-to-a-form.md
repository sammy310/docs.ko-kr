---
title: '방법: 양식에 ToolStripContainer 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582576"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="8fbc9-102">방법: 양식에 ToolStripContainer 추가</span><span class="sxs-lookup"><span data-stu-id="8fbc9-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="8fbc9-103">프로그래밍 방식으로 <xref:System.Windows.Forms.ToolStripContainer>를 Windows Form에 추가하고 컨트롤로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fbc9-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fbc9-104">예제</span><span class="sxs-lookup"><span data-stu-id="8fbc9-104">Example</span></span>  
 <span data-ttu-id="8fbc9-105">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripContainer> 및 <xref:System.Windows.Forms.ToolStrip>을 Windows Forms에 추가하는 방법, 항목을 <xref:System.Windows.Forms.ToolStrip>에 추가하는 방법, <xref:System.Windows.Forms.ToolStrip>을 <xref:System.Windows.Forms.ToolStripContainer>의 <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fbc9-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fbc9-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8fbc9-106">Compiling the Code</span></span>  
 <span data-ttu-id="8fbc9-107">이 코드 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8fbc9-107">This code example requires:</span></span>  
  
- <span data-ttu-id="8fbc9-108">System.Drawing, System.Text 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8fbc9-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fbc9-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="8fbc9-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="8fbc9-110">ToolStripContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8fbc9-110">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="8fbc9-111">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8fbc9-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
