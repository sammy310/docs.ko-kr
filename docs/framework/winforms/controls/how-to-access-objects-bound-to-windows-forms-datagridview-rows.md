---
title: '방법: Windows Forms DataGridView 행에 바인딩된 개체 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 50882ab9a1a498bf8f76381e3f4aac53876abbb8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011283"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="1e959-102">방법: Windows Forms DataGridView 행에 바인딩된 개체 액세스</span><span class="sxs-lookup"><span data-stu-id="1e959-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="1e959-103">때로는 비즈니스 개체 컬렉션에 저장된 정보 테이블을 표시하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="1e959-104"><xref:System.Windows.Forms.DataGridView> 컨트롤을 이러한 컬렉션에 바인딩하면 속성이 <xref:System.ComponentModel.BrowsableAttribute>를 통해 검색 불가능으로 표시되지 않은 경우 각 공용 속성이 해당 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="1e959-105">예를 들어 `Customer` 개체 컬렉션에는 **이름** 및 **주소**와 같은 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="1e959-106">이러한 개체에 포함된 추가 정보 및 코드에 액세스하려는 경우 행 개체를 통해 접근할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="1e959-107">다음 코드 예제에서는 사용자가 여러 행을 선택하고 단추를 클릭하여 각 해당 고객에게 송장을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="1e959-108">행 바인딩된 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="1e959-108">To access row-bound objects</span></span>  
  
- <span data-ttu-id="1e959-109"><xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="1e959-110">예제</span><span class="sxs-lookup"><span data-stu-id="1e959-110">Example</span></span>  
 <span data-ttu-id="1e959-111">전체 코드 예제는 간단한 `Customer` 구현을 포함하며, 몇 개의 `Customer` 개체가 포함된 <xref:System.Collections.ArrayList>에 <xref:System.Windows.Forms.DataGridView>를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="1e959-112"><xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 이벤트 처리기 외부에서는 고객 컬렉션에 액세스할 수 없기 때문에 <xref:System.Windows.Forms.Button?displayProperty=nameWithType>의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기는 행을 통해 `Customer` 개체에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1e959-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1e959-113">Compiling the Code</span></span>  
 <span data-ttu-id="1e959-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-114">This example requires:</span></span>  
  
- <span data-ttu-id="1e959-115">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="1e959-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1e959-116">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1e959-117">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e959-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e959-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e959-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1e959-119">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="1e959-119">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1e959-120">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="1e959-120">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
