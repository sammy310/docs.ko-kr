---
title: 데이터 바인딩된 DataGridView 컨트롤의 열 자동 생성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], autogenerating columns
- columns [Windows Forms], autogenerating
- DataGridView control [Windows Forms], data-bound columns
ms.assetid: 699f6f9e-6aa5-4811-902b-6a2c57dec7d6
ms.openlocfilehash: 860e640e095537358d2f8778c810aa577e9d7ff0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746238"
---
# <a name="how-to-autogenerate-columns-in-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="fc74c-102">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성</span><span class="sxs-lookup"><span data-stu-id="fc74c-102">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fc74c-103">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 바인딩된 데이터 소스의 열을 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-103">The following code example demonstrates how to display columns from a bound data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fc74c-104"><xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성 값이 `true` (기본값) 이면 데이터 원본 테이블의 각 열에 대해 <xref:System.Windows.Forms.DataGridViewColumn> 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-104">When the <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> property value is `true` (the default), a <xref:System.Windows.Forms.DataGridViewColumn> is created for each column in the data source table.</span></span>  
  
 <span data-ttu-id="fc74c-105"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 속성을 설정할 때 <xref:System.Windows.Forms.DataGridView> 컨트롤에 이미 열이 있는 경우 기존 바인딩된 열은 데이터 원본의 열과 비교 되며, 일치 하는 항목이 있을 때마다 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-105">If the <xref:System.Windows.Forms.DataGridView> control already has columns when you set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property, the existing bound columns are compared to the columns in the data source and preserved whenever there is a match.</span></span> <span data-ttu-id="fc74c-106">바인딩되지 않은 열은 항상 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-106">Unbound columns are always preserved.</span></span> <span data-ttu-id="fc74c-107">데이터 원본에 일치 하는 항목이 없는 바운드 열은 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-107">Bound columns for which there is no match in the data source are removed.</span></span> <span data-ttu-id="fc74c-108">컨트롤에 일치 하는 항목이 없는 데이터 원본의 열은 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션의 끝에 추가 되는 새 <xref:System.Windows.Forms.DataGridViewColumn> 개체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-108">Columns in the data source for which there is no match in the control generate new <xref:System.Windows.Forms.DataGridViewColumn> objects, which are added to the end of the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc74c-109">示例</span><span class="sxs-lookup"><span data-stu-id="fc74c-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#020)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#020](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#020)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc74c-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fc74c-110">Compiling the Code</span></span>  
 <span data-ttu-id="fc74c-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-111">This example requires:</span></span>  
  
- <span data-ttu-id="fc74c-112">`customersDataGridView`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fc74c-112">A <xref:System.Windows.Forms.DataGridView> control named `customersDataGridView`.</span></span>  
  
- <span data-ttu-id="fc74c-113">이름이 `Customers`인 테이블이 있는 `customersDataSet` 라는 <xref:System.Data.DataSet> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-113">A <xref:System.Data.DataSet> object named `customersDataSet` that has a table named `Customers`.</span></span>  
  
- <span data-ttu-id="fc74c-114"><xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> 및 <xref:System.Xml?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fc74c-114">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType>, and <xref:System.Xml?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc74c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc74c-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fc74c-116">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="fc74c-116">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fc74c-117">방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거</span><span class="sxs-lookup"><span data-stu-id="fc74c-117">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)
