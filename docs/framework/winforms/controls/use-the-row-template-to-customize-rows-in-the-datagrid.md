---
title: '방법: 행 템플릿을 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 3cd1e9af32cb47f5d81abfc92423ea30e2e599cf
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707575"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="20a5e-102">방법: 행 템플릿을 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="20a5e-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="20a5e-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 바인딩을 통해 또는 호출 하는 경우 컨트롤에 추가 하는 모든 행에 대 한 기준으로 행 템플릿을 사용 합니다 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 메서드를 사용 하 여 기존 행을 지정 하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="20a5e-104">행 템플릿을 큰 세부적으로 제어할 모양 및 동작 행 보다는 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="20a5e-105">행 템플릿을 사용 하 여 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridViewRow> 속성을 포함 하 여 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="20a5e-106">특정 효과 달성 하기 위해 행 템플릿을 사용 해야 하는 몇 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="20a5e-107">예를 들어에 행 높이 정보를 저장할 수 없습니다는 <xref:System.Windows.Forms.DataGridViewCellStyle>이므로 모든 행에서 사용 하는 기본 높이 변경 하려면 행 템플릿을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="20a5e-108">행 템플릿을 유용에서 파생 된 고유한 클래스를 만들 때 <xref:System.Windows.Forms.DataGridViewRow> 하려는 컨트롤에 새 행을 추가할 때 사용 되는 사용자 지정 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20a5e-109">행 템플릿은 행을 추가 하는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="20a5e-110">행 템플릿을 변경 하 여 기존 행을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="20a5e-111">행 템플릿을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="20a5e-111">To use the row template</span></span>  
  
-   <span data-ttu-id="20a5e-112">검색 된 개체의 속성을 설정 합니다 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20a5e-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="20a5e-113">Compiling the Code</span></span>  
 <span data-ttu-id="20a5e-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="20a5e-114">This example requires:</span></span>  
  
-   <span data-ttu-id="20a5e-115">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="20a5e-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="20a5e-116">
  <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="20a5e-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a5e-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="20a5e-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="20a5e-118">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="20a5e-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="20a5e-119">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="20a5e-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
