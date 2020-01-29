---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 열 숨기기
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738659"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a7a27-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기</span><span class="sxs-lookup"><span data-stu-id="a7a27-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="a7a27-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 열 중 일부만 표시하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a7a27-104">예를 들어 관리 자격 증명이 있는 사용자에 게 직원 급여 열을 표시 하 고 다른 사용자는 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="a7a27-105">또는 많은 열을 포함 하는 데이터 소스에 컨트롤을 바인딩할 수 있습니다. 이러한 열 중 일부만 표시 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="a7a27-106">이 경우 일반적으로 표시 되지 않는 열은 숨기는 대신 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="a7a27-107">자세한 내용은 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거](add-and-remove-columns-in-the-datagrid-using-the-designer.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7a27-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="a7a27-108">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a7a27-109">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7a27-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="a7a27-110">디자이너를 사용 하 여 열을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="a7a27-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="a7a27-111"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 **열 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="a7a27-112">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a7a27-113">**열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7a27-114">열 **추가** 대화 상자에서 **표시** 확인란의 선택을 취소 하 여 열을 추가할 때 열을 숨길 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a27-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7a27-115">참조</span><span class="sxs-lookup"><span data-stu-id="a7a27-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a7a27-116">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="a7a27-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="a7a27-117">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a7a27-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a7a27-118">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a7a27-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
