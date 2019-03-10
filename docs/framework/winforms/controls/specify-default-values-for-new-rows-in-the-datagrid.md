---
title: '방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값을 지정 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: cc854f0cdbef8373b74a16c7d5bc044cfee5aa84
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708030"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="08f82-102">방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="08f82-103">응용 프로그램 새로 추가 된 행에 대 한 값을 기본 차면 데이터 입력을 보다 편리 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="08f82-104">사용 하 여 합니다 <xref:System.Windows.Forms.DataGridView> 클래스를 채울 수 있습니다 기본 값을 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="08f82-105">이 이벤트는 사용자가 새 레코드에 대 한 행을 입력할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="08f82-106">코드에서이 이벤트를 처리 하는 경우에 원하는 값이 선택한 셀을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="08f82-107">다음 코드 예제를 사용 하 여 새 행에 대 한 기본값을 지정 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08f82-108">예제</span><span class="sxs-lookup"><span data-stu-id="08f82-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08f82-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="08f82-109">Compiling the Code</span></span>  
 <span data-ttu-id="08f82-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-110">This example requires:</span></span>  
  
-   <span data-ttu-id="08f82-111">
  `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="08f82-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="08f82-112">A `NewCustomerId` 고유 생성에 대 한 함수 `CustomerID` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08f82-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
-   <span data-ttu-id="08f82-113">
  <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="08f82-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f82-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="08f82-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="08f82-115">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="08f82-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="08f82-116">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="08f82-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
