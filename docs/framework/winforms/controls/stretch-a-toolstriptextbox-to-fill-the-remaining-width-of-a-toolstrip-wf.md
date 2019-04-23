---
title: '방법: Toolstriptextbox를 늘려 ToolStrip (Windows Forms)의 나머지 너비 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: 707fd2e470a9be1d61d2878eeff845b3cad270db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223578"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="27c93-102">방법: Toolstriptextbox를 늘려 ToolStrip (Windows Forms)의 나머지 너비 채우기</span><span class="sxs-lookup"><span data-stu-id="27c93-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="27c93-103">설정한 경우를 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 의 속성을 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 `true`, 컨트롤이 해당 컨테이너 종단 간 채우고 해당 컨테이너의 크기를 조정 하는 경우 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="27c93-104">이 구성에서는 유용할 수 있습니다 것과 같은 컨트롤에서 항목을 확장 하는 <xref:System.Windows.Forms.ToolStripTextBox>, 사용 가능한 공간 및 크기를 조정 하는 경우 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="27c93-105">이 확장 유용 예를 들어, 모양 및 Microsoft® Internet Explorer의 주소 표시줄에 비슷한 동작을 수행 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="27c93-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27c93-106">예제</span><span class="sxs-lookup"><span data-stu-id="27c93-106">Example</span></span>  
 <span data-ttu-id="27c93-107">다음 코드 예제에서 파생 된 클래스를 제공 <xref:System.Windows.Forms.ToolStripTextBox> 호출 `ToolStripSpringTextBox`합니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="27c93-108">이 클래스에서 재정의 된 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 부모 사용 가능한 너비를 계산 하는 방법 <xref:System.Windows.Forms.ToolStrip> 다른 모든 항목의 결합 된 너비를 뺀 후 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="27c93-109">이 코드 예제에서는 한 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스의 새 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="27c93-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="27c93-110">Compiling the Code</span></span>  
 <span data-ttu-id="27c93-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="27c93-111">This example requires:</span></span>  
  
-   <span data-ttu-id="27c93-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="27c93-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c93-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="27c93-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [<span data-ttu-id="27c93-114">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="27c93-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="27c93-115">방법: StatusStrip에서 대화형으로 Spring 속성 사용</span><span class="sxs-lookup"><span data-stu-id="27c93-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
