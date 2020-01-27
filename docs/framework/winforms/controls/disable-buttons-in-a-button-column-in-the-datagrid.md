---
title: DataGridView 컨트롤의 단추 열에서 단추 비활성화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 691781a43005d66e13029ab8110eb7f9daacc35f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745953"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="67ba8-102">방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화</span><span class="sxs-lookup"><span data-stu-id="67ba8-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="67ba8-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에는 단추처럼 UI(사용자 인터페이스)가 있는 셀을 표시하기 위한 <xref:System.Windows.Forms.DataGridViewButtonCell> 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="67ba8-104">그러나 <xref:System.Windows.Forms.DataGridViewButtonCell>은 셀에서 표시될 수 있는 단추의 모양을 비활성화하는 방법을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="67ba8-105">다음 코드 예제에서는 비활성화된 것으로 나타날 수 있는 단추를 표시하도록 <xref:System.Windows.Forms.DataGridViewButtonCell> 클래스를 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="67ba8-106">다음 예제에서는 <xref:System.Windows.Forms.DataGridViewButtonCell>에서 파생되는 새로운 셀 형식 `DataGridViewDisableButtonCell`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="67ba8-107">이 셀 형식은 셀에 비활성화된 단추를 그리기 위해 `false`로 설정할 수 있는 새로운 `Enabled` 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="67ba8-108">예제에서는 `DataGridViewDisableButtonCell` 개체를 표시하는 새로운 열 형식 `DataGridViewDisableButtonColumn`도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="67ba8-109">이 새로운 셀 및 열 형식을 보여 주기 위해 부모 <xref:System.Windows.Forms.DataGridView>에 있는 각 <xref:System.Windows.Forms.DataGridViewCheckBoxCell>의 현재 값에 따라 동일한 행의 `DataGridViewDisableButtonCell`에 대한 `Enabled` 속성이 `true` 또는 `false`인지가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67ba8-110"><xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="67ba8-111">또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67ba8-112">예</span><span class="sxs-lookup"><span data-stu-id="67ba8-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="67ba8-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="67ba8-113">Compiling the Code</span></span>  
 <span data-ttu-id="67ba8-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="67ba8-114">This example requires:</span></span>  
  
- <span data-ttu-id="67ba8-115">System, System.Drawing, System.Windows.Forms 및 System.Windows.Forms.VisualStyles 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="67ba8-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ba8-116">참조</span><span class="sxs-lookup"><span data-stu-id="67ba8-116">See also</span></span>

- [<span data-ttu-id="67ba8-117">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="67ba8-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="67ba8-118">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="67ba8-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="67ba8-119">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="67ba8-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
