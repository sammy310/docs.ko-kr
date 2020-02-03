---
title: 디자이너를 사용 하 여 DataGridView 열의 형식 변경
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737139"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="8aa3f-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="8aa3f-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="8aa3f-103">경우에 따라 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 이미 추가 된 열의 형식을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8aa3f-104">예를 들어 데이터 소스에 컨트롤을 바인딩할 때 자동으로 생성 되는 일부 열의 형식을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="8aa3f-105">이 기능은 표시 하는 테이블에 관련 테이블의 행에 대 한 외래 키가 포함 된 열이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="8aa3f-106">이 경우 이러한 외래 키를 표시 하는 입력란 열을 관련 테이블의 의미 있는 값을 표시 하는 콤보 상자 열로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="8aa3f-107">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8aa3f-108">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="8aa3f-109">디자이너를 사용 하 여 열의 형식을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="8aa3f-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="8aa3f-110"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 **열 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="8aa3f-111">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="8aa3f-112">**열 속성** 표에서 `ColumnType` 속성을 새 열 유형으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8aa3f-113">`ColumnType` 속성은 열 유형을 나타내는 클래스를 나타내는 디자인 타임 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="8aa3f-114">열 클래스에 정의 된 실제 속성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8aa3f-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="8aa3f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aa3f-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="8aa3f-116">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="8aa3f-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="8aa3f-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="8aa3f-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
