---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 80ede9b7bc5bf667e03dc0a745fbc0b5f6c2663a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343287"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="7fb2f-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="7fb2f-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="7fb2f-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤 데이터를 표시 하기 위해 열을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="7fb2f-104">수동으로 컨트롤을 채우는 하려는 경우에 직접 열을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="7fb2f-105">또는 생성 되 고 열을 자동으로 채워지도록 데이터 원본에 컨트롤을 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="7fb2f-106">데이터 원본에 표시 하려는 것 보다 많은 열이 있으면 필요 없는 열을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="7fb2f-107">다음 절차는 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="7fb2f-108">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fb2f-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7fb2f-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7fb2f-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="7fb2f-112">디자이너를 사용 하 여 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7fb2f-112">To add a column using the designer</span></span>  
  
1. <span data-ttu-id="7fb2f-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2. <span data-ttu-id="7fb2f-114">**열 추가** 대화 상자를 선택 합니다 **데이터 바인딩된 열** 옵션 및 데이터 원본에서 열을 선택 하거나 선택 합니다 **바인딩되지 않은 열** 옵션 및 해당 열을 정의 제공 된 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3. <span data-ttu-id="7fb2f-115">클릭 합니다 **추가** 기존 열이 컨트롤의 표시 영역에 아직 채워지지 않은 경우 디자이너에 표시 하는 열을 추가 하려면 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7fb2f-116">열 속성을 수정할 수 있습니다는 **열 편집** 대화 상자에서 컨트롤의 스마트 태그에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="7fb2f-117">디자이너를 사용 하 여 열을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7fb2f-117">To remove a column using the designer</span></span>  
  
1. <span data-ttu-id="7fb2f-118">선택할 **열 편집** 컨트롤의 스마트 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2. <span data-ttu-id="7fb2f-119">열을 선택 합니다 **선택한 열** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-119">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="7fb2f-120">클릭 합니다 **제거** 사라집니다 디자이너에서 열을 삭제 하려면 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb2f-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb2f-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="7fb2f-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="7fb2f-122">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7fb2f-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="7fb2f-123">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="7fb2f-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
