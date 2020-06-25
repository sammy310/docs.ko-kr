---
title: DataGridView 컨트롤에 개체 바인딩
description: 각 개체가 개별 행으로 표시 되도록 개체 컬렉션을 Windows Forms DataGridView 컨트롤에 바인딩하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: add0047937b404dcec1ea12bac8053bb9bdfcf1c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325856"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="442fc-103">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="442fc-103">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="442fc-104">다음 코드 예제에서는 각 개체가 개별 행으로 표시되도록 개체 컬렉션을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="442fc-104">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="442fc-105">이 예제에서는 콤보 상자 드롭다운 목록에 열거형 값이 포함되도록 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>에서 열거형 형식을 가진 속성을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="442fc-105">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="442fc-106">예제</span><span class="sxs-lookup"><span data-stu-id="442fc-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="442fc-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="442fc-107">Compiling the Code</span></span>  
 <span data-ttu-id="442fc-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="442fc-108">This example requires:</span></span>  
  
- <span data-ttu-id="442fc-109">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="442fc-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="442fc-110">참조</span><span class="sxs-lookup"><span data-stu-id="442fc-110">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="442fc-111">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="442fc-111">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="442fc-112">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="442fc-112">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
