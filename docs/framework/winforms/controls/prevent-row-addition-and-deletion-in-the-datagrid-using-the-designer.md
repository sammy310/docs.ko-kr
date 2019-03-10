---
title: '방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 52514c07313a60bac8e2c7142b66099dbcd779e5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714738"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="fb9b4-102">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="fb9b4-103">때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fb9b4-104">새 행은 컨트롤의 맨 아래에 새 레코드에 대 한 특수 한 행에 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="fb9b4-105">행 추가 해제 하면 새 레코드에 대 한 행이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="fb9b4-106">그런 다음 가능 컨트롤 완전히 읽기 전용 행을 삭제 하 고 셀 편집을 사용 하지 않도록 설정 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="fb9b4-107">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fb9b4-108">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb9b4-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fb9b4-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fb9b4-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="fb9b4-112">행 추가 및 삭제를 방지 하기 위해</span><span class="sxs-lookup"><span data-stu-id="fb9b4-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="fb9b4-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 다음 선택을 취소 합니다 **추가 사용** 및 **삭제 사용** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb9b4-114">완전히 읽기 전용 컨트롤을 하려면 선택을 취소 합니다 **편집 사용** 확인란도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9b4-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9b4-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb9b4-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fb9b4-116">방법: Windows Forms 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fb9b4-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="fb9b4-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="fb9b4-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
