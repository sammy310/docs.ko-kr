---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 82be9d31ff6bb3f2f5dd8a55b4426103d466bdd6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952101"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="2544f-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="2544f-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="2544f-103">기본적으로 사용자는 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시 되는 텍스트 및 숫자 데이터를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2544f-104">수정 하기에 적합 하지 않은 데이터를 표시 하려면 데이터를 포함 하는 열을 읽기 전용으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="2544f-105">컨트롤을 완전히 읽기 [전용으로 설정 하는 방법에 대 한 자세한 내용은 방법: 디자이너](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="2544f-106">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2544f-107">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="2544f-108">디자이너를 사용 하 여 열을 읽기 전용으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2544f-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="2544f-109"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 **열 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-109">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="2544f-110">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="2544f-111">**열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> 속성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2544f-112">**열 추가** 대화 상자에서 **읽기 전용** 확인란을 선택 하 여 열을 추가 하는 경우에도 열을 읽기 전용으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2544f-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="2544f-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="2544f-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2544f-114">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="2544f-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="2544f-115">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 방지</span><span class="sxs-lookup"><span data-stu-id="2544f-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="2544f-116">방법: Windows Forms 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2544f-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2544f-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="2544f-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
