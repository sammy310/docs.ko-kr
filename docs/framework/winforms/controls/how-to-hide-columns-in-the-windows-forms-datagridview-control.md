---
title: DataGridView 컨트롤에서 열 숨기기
description: DataGridViewColumn 속성을 false로 설정 하 여 Windows Forms DataGridView 컨트롤에서 프로그래밍 방식으로 열을 숨기는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], hiding columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
ms.assetid: 3f94143a-2ef0-49a5-a22a-b2e6f9289642
ms.openlocfilehash: 46d7faea76098406b8e0a91d22922bf9ca391e28
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325908"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6a209-103">방법: Windows Forms DataGridView 컨트롤에서 열 숨기기</span><span class="sxs-lookup"><span data-stu-id="6a209-103">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6a209-104">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 열 중 일부만 표시하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-104">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6a209-105">예를 들어 관리 자격 증명을 가진 사용자에게 직원 급여 열을 표시하고 다른 사용자로부터는 숨기려 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-105">For example, you might want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="6a209-106">또는 많은 열을 포함하지만 이 중에서 일부만 표시하려는 데이터 소스에 컨트롤을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-106">Alternately, you might want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="6a209-107">이 경우 일반적으로 표시하지 않으려는 열을 숨기는 대신 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-107">In this case, you will typically remove the columns you are not interested in displaying rather than hide them.</span></span>  
  
 <span data-ttu-id="6a209-108"><xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성 값은 해당 열이 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-108">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property value of a column determines whether that column is displayed.</span></span>  
  
 <span data-ttu-id="6a209-109">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="6a209-110">또한 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 숨기기를](hide-columns-in-the-datagrid-using-the-designer.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a209-110">Also see [How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer](hide-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-hide-a-column-programmatically"></a><span data-ttu-id="6a209-111">프로그래밍 방식으로 열을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="6a209-111">To hide a column programmatically</span></span>  
  
- <span data-ttu-id="6a209-112"><xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> 속성을 `false`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="6a209-113">데이터 바인딩 중에 자동으로 생성되는 `CustomerID` 열을 숨기려면 다음 코드 예제를 <xref:System.Windows.Forms.DataGridView.DataBindingComplete> 이벤트 처리기에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-113">To hide a `CustomerID` column that is automatically generated during data binding, place the following code example in a <xref:System.Windows.Forms.DataGridView.DataBindingComplete> event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#063)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#063](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#063)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a209-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6a209-114">Compiling the Code</span></span>  
 <span data-ttu-id="6a209-115">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a209-115">This example requires:</span></span>  
  
- <span data-ttu-id="6a209-116">이름이 `CustomerID`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6a209-116">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `CustomerID`.</span></span>  
  
- <span data-ttu-id="6a209-117"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="6a209-117">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a209-118">참조</span><span class="sxs-lookup"><span data-stu-id="6a209-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6a209-119">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="6a209-119">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="6a209-120">방법: Windows Forms DataGridView 컨트롤에서 자동으로 생성된 열 제거</span><span class="sxs-lookup"><span data-stu-id="6a209-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
- [<span data-ttu-id="6a209-121">방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="6a209-121">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)
