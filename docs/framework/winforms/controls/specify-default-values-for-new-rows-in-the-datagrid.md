---
title: DataGridView 컨트롤의 새 행에 대 한 기본값 지정
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
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742936"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="82a77-102">방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정</span><span class="sxs-lookup"><span data-stu-id="82a77-102">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="82a77-103">응용 프로그램이 새로 추가 된 행에 대 한 기본값을 채울 때 데이터 입력을 보다 편리 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-103">You can make data entry more convenient when the application fills in default values for newly added rows.</span></span> <span data-ttu-id="82a77-104"><xref:System.Windows.Forms.DataGridView> 클래스를 사용 하 여 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트로 기본값을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-104">With the <xref:System.Windows.Forms.DataGridView> class, you can fill in default values with the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span> <span data-ttu-id="82a77-105">이 이벤트는 사용자가 새 레코드에 대 한 행을 입력할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-105">This event is raised when the user enters the row for new records.</span></span> <span data-ttu-id="82a77-106">코드에서이 이벤트를 처리할 때 원하는 셀을 선택한 값으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-106">When your code handles this event, you can populate desired cells with values of your choosing.</span></span>  
  
 <span data-ttu-id="82a77-107">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트를 사용 하 여 새 행에 대 한 기본값을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-107">The following code example demonstrates how to specify default values for new rows using the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82a77-108">예제</span><span class="sxs-lookup"><span data-stu-id="82a77-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82a77-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="82a77-109">Compiling the Code</span></span>  
 <span data-ttu-id="82a77-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-110">This example requires:</span></span>  
  
- <span data-ttu-id="82a77-111"><xref:System.Windows.Forms.DataGridView>이라는 `dataGridView1` 컨트롤</span><span class="sxs-lookup"><span data-stu-id="82a77-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="82a77-112">고유한 `CustomerID` 값을 생성 하기 위한 `NewCustomerId` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="82a77-112">A `NewCustomerId` function for generating unique `CustomerID` values.</span></span>  
  
- <span data-ttu-id="82a77-113"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="82a77-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a77-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82a77-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [<span data-ttu-id="82a77-115">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="82a77-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="82a77-116">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="82a77-116">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
