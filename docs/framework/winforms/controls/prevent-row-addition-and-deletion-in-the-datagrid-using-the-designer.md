---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 행 추가 및 삭제 방지
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628893"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="30d61-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="30d61-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="30d61-103">때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="30d61-104">새 행은 컨트롤의 맨 아래에 있는 새 레코드의 특수 행에 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="30d61-105">행 추가를 사용 하지 않도록 설정 하면 새 레코드의 행이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="30d61-106">그런 다음 행 삭제 및 셀 편집을 사용 하지 않도록 설정 하 여 컨트롤을 완전히 읽기 전용으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="30d61-107">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="30d61-108">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="30d61-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="30d61-109">행 추가 및 삭제를 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="30d61-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="30d61-110"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 디자이너 작업 문자 모양 (![작은 검은색 화살표](./media/designer-actions-glyph.gif))을 클릭 한 다음 **추가 사용** 및 **삭제 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30d61-111">컨트롤을 완전히 읽기 전용으로 설정 하려면 **편집 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d61-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="30d61-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30d61-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="30d61-113">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="30d61-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="30d61-114">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="30d61-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
