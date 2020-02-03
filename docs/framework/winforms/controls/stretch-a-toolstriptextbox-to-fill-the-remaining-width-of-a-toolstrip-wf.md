---
title: '방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742847"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="0b7b3-102">방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0b7b3-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="0b7b3-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성을 `true`로 설정 하는 경우 컨트롤은 해당 컨테이너를 끝에서 끝까지 채우고 컨테이너의 크기가 조정 될 때 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="0b7b3-104">이 구성에서는 <xref:System.Windows.Forms.ToolStripTextBox>와 같은 컨트롤의 항목을 확장 하 여 사용 가능한 공간을 채우고 컨트롤의 크기를 조정할 때 크기를 조정 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="0b7b3-105">예를 들어이 확장은 Microsoft® Internet Explorer의 주소 표시줄과 비슷한 모양 및 동작을 수행 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b7b3-106">예제</span><span class="sxs-lookup"><span data-stu-id="0b7b3-106">Example</span></span>  
 <span data-ttu-id="0b7b3-107">다음 코드 예제에서는 `ToolStripSpringTextBox`이라는 <xref:System.Windows.Forms.ToolStripTextBox>에서 파생 된 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="0b7b3-108">이 클래스는 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 메서드를 재정의 하 여 다른 모든 항목의 전체 너비를 뺀 후의 부모 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 사용 가능한 너비를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="0b7b3-109">이 코드 예제에서는 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스를 제공 하 여 새 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b7b3-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0b7b3-110">Compiling the Code</span></span>  
 <span data-ttu-id="0b7b3-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7b3-111">This example requires:</span></span>  
  
- <span data-ttu-id="0b7b3-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="0b7b3-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b7b3-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0b7b3-114">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0b7b3-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="0b7b3-115">방법: StatusStrip에서 대화형으로 Spring 속성 사용</span><span class="sxs-lookup"><span data-stu-id="0b7b3-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
