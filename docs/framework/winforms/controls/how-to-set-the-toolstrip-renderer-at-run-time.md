---
title: '방법: 런타임에 ToolStrip 렌더러 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 90a80ba421698a108cd7a358f89b64810b06efc9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591621"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="4c064-102">방법: 런타임에 ToolStrip 렌더러 설정</span><span class="sxs-lookup"><span data-stu-id="4c064-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="4c064-103">사용자 지정 `ProfessionalColorTable` 클래스를 만들어 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c064-104">예제</span><span class="sxs-lookup"><span data-stu-id="4c064-104">Example</span></span>  
 <span data-ttu-id="4c064-105">다음 코드 예제에서는 사용자 지정 `ProfessionalColorTable` 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="4c064-106">이 클래스는 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대한 그라데이션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="4c064-107">이 코드 예제를 사용하려면 애플리케이션을 컴파일 및 실행한 다음 **색 변경**을 클릭하여 사용자 지정 `ProfessionalColorTable` 클래스에서 정의된 그라데이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="4c064-108">사용자 지정 ProfessionalColorTable 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="4c064-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="4c064-109">사용자 지정 그라데이션은 `CustomProfessionalColors` 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="4c064-110">사용자 지정 렌더러 할당</span><span class="sxs-lookup"><span data-stu-id="4c064-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="4c064-111">`CustomProfessionalColors` 클래스를 사용하여 새 `ToolStripProfessionalRenderer`를 만들고 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c064-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4c064-112">Compiling the Code</span></span>  
 <span data-ttu-id="4c064-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4c064-113">This example requires:</span></span>  
  
- <span data-ttu-id="4c064-114">System.Design, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="4c064-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c064-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4c064-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [<span data-ttu-id="4c064-116">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4c064-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
