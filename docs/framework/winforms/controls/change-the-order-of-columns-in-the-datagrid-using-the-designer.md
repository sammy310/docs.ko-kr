---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 열 순서 변경
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628750"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="faa94-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="faa94-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="faa94-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 원본에 바인딩하는 경우 자동으로 생성 되는 열의 표시 순서는 데이터 원본에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="faa94-104">이 순서가 원하는 항목이 아닌 경우 디자이너를 사용 하 여 열의 순서를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="faa94-105">컨트롤에 바인딩되지 않은 열을 추가 하 고 표시 순서를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="faa94-106">프로그래밍 방식으로 열 순서를 변경 하는 방법에 대 한 자세한 내용은 [방법: DataGridView 컨트롤 Windows Forms에서 열 순서 변경](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa94-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="faa94-107">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="faa94-108">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="faa94-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="faa94-109">디자이너를 사용 하 여 열 순서를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="faa94-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="faa94-110"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 디자이너 작업 문자 모양 (![작은 검은색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **열 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="faa94-111">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="faa94-112">선택한 열이 원하는 위치에 있을 때까지 **선택한 열** 목록 오른쪽에 있는 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa94-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="faa94-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faa94-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="faa94-114">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="faa94-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="faa94-115">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="faa94-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="faa94-116">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="faa94-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
