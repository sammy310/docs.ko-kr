---
title: '방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: b9b78020a567d05ea000be97bb116b4f8353d56c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709460"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0e2a5-102">방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기</span><span class="sxs-lookup"><span data-stu-id="0e2a5-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0e2a5-103">표시할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView> 열 머리글이 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="0e2a5-104">에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성 값은 열 머리글 표시 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="0e2a5-105">열 머리글을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="0e2a5-105">To hide the column headers</span></span>  
  
-   <span data-ttu-id="0e2a5-106"><xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> 속성을 `false`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e2a5-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="0e2a5-107">Compiling the Code</span></span>  
 <span data-ttu-id="0e2a5-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-108">This example requires:</span></span>  
  
-   <span data-ttu-id="0e2a5-109">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0e2a5-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="0e2a5-110">
  <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="0e2a5-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2a5-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e2a5-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0e2a5-112">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="0e2a5-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
