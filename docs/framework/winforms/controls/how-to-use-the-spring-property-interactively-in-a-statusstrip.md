---
title: '방법: StatusStrip에서 대화형으로 Spring 속성 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589644"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="c510c-102">방법: StatusStrip에서 대화형으로 Spring 속성 사용</span><span class="sxs-lookup"><span data-stu-id="c510c-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="c510c-103"><xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성을 사용하여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="c510c-104"><xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성은 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤이 <xref:System.Windows.Forms.StatusStrip> 컨트롤에서 사용 가능한 공간을 자동으로 채울지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c510c-105">예제</span><span class="sxs-lookup"><span data-stu-id="c510c-105">Example</span></span>  
 <span data-ttu-id="c510c-106">다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성을 사용하여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 배치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="c510c-107"><xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기는 XOR(배타적 OR) 연산을 수행하여 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성의 값을 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="c510c-108">이 코드 예제를 사용 하려면 컴파일하고 응용 프로그램을 실행 한 다음 클릭 **중간 (Spring)** 에 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 값을 전환 합니다 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c510c-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c510c-109">Compiling the Code</span></span>  
 <span data-ttu-id="c510c-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c510c-110">This example requires:</span></span>  
  
- <span data-ttu-id="c510c-111">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c510c-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c510c-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c510c-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="c510c-113">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c510c-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
