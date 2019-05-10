---
title: '방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: f60acbfa73ef363d58c57e1c01bdce8cf3337e48
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619660"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="16514-102">방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="16514-102">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="16514-103">와 상호 작용을 <xref:System.Windows.Forms.DataGridView> 를 프로그래밍 방식으로 검색 된 셀을 현재 활성 종종 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="16514-103">Interaction with the <xref:System.Windows.Forms.DataGridView> often requires that you programmatically discover which cell is currently active.</span></span> <span data-ttu-id="16514-104">현재 셀을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16514-104">You may also need to change the current cell.</span></span> <span data-ttu-id="16514-105">이러한 작업을 수행할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="16514-105">You can perform these tasks with the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16514-106">현재 셀의 행 이나 열에 설정할 수 없습니다 해당 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성이 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="16514-106">You cannot set the current cell in a row or column that has its <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> property set to `false`.</span></span>  
  
 <span data-ttu-id="16514-107">에 따라는 <xref:System.Windows.Forms.DataGridView> 현재 셀 변경 되는 컨트롤의 선택 모드 선택을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16514-107">Depending on the <xref:System.Windows.Forms.DataGridView> control's selection mode, changing the current cell can change the selection.</span></span> <span data-ttu-id="16514-108">자세한 내용은 [Windows Forms DataGridView 컨트롤의 선택 모드](selection-modes-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16514-108">For more information, see [Selection Modes in the Windows Forms DataGridView Control](selection-modes-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-get-the-current-cell-programmatically"></a><span data-ttu-id="16514-109">현재 셀을 프로그래밍 방식으로 가져오려면</span><span class="sxs-lookup"><span data-stu-id="16514-109">To get the current cell programmatically</span></span>  
  
- <span data-ttu-id="16514-110">사용 된 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="16514-110">Use the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a><span data-ttu-id="16514-111">현재 셀을 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="16514-111">To set the current cell programmatically</span></span>  
  
- <span data-ttu-id="16514-112">설정 합니다 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 의 속성을 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="16514-112">Set the <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> property of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="16514-113">다음 코드 예제에서 현재 셀의 행 0, 1 열에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16514-113">In the following code example, the current cell is set to row 0, column 1.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16514-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="16514-114">Compiling the Code</span></span>  
 <span data-ttu-id="16514-115">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="16514-115">This example requires:</span></span>  
  
- <span data-ttu-id="16514-116"><xref:System.Windows.Forms.Button> 명명 된 컨트롤 `getCurrentCellButton` 고 `setCurrentCellButton`입니다.</span><span class="sxs-lookup"><span data-stu-id="16514-116"><xref:System.Windows.Forms.Button> controls named `getCurrentCellButton` and `setCurrentCellButton`.</span></span> <span data-ttu-id="16514-117">시각적 개체의 C#에 연결 해야 합니다는 <xref:System.Windows.Forms.Control.Click> 예제 코드에 연결 된 이벤트 처리기에 각 단추에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="16514-117">In Visual C#, you must attach the <xref:System.Windows.Forms.Control.Click> events for each button to the associated event handler in the example code.</span></span>  
  
- <span data-ttu-id="16514-118">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="16514-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="16514-119"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="16514-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16514-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="16514-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [<span data-ttu-id="16514-121">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="16514-121">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="16514-122">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="16514-122">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)
