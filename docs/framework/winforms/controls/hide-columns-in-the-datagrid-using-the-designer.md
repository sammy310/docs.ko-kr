---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: e0255cca5c614f07bbc4a7dfc9a908612e8867a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122384"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="70a0f-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 숨기기</span><span class="sxs-lookup"><span data-stu-id="70a0f-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="70a0f-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 열 중 일부만 표시하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="70a0f-104">직원을 표시 하려는 하는 예를 들어, 다른 사용자 로부터 숨기고 관리 자격 증명이 있는 사용자에 게 급여 열입니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="70a0f-105">또는 다음 중에서 일부만 표시 하려는 많은 열이 포함 된 데이터 원본에 컨트롤을 바인딩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="70a0f-106">이 경우 숨기기 보다는 표시 하는 데 관심이 없는 열은 일반적으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="70a0f-107">자세한 내용은 [방법: 추가 및 제거 열에는 Windows Forms DataGridView 컨트롤 디자이너를 사용 하 여](add-and-remove-columns-in-the-datagrid-using-the-designer.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="70a0f-108">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="70a0f-109">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70a0f-110">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="70a0f-111">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="70a0f-112">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70a0f-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="70a0f-113">디자이너를 사용 하 여 열을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="70a0f-113">To hide a column using the designer</span></span>  
  
1.  <span data-ttu-id="70a0f-114">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="70a0f-115">열을 선택 합니다 **선택한 열** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-115">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="70a0f-116">에 **열 속성** 표에서 설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="70a0f-116">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="70a0f-117">선택을 취소 하 여 추가 하는 경우 열을 숨길 수도 있습니다는 **Visible** 확인란 합니다 **열 추가** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="70a0f-117">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a0f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="70a0f-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="70a0f-119">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="70a0f-119">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="70a0f-120">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="70a0f-120">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="70a0f-121">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="70a0f-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
