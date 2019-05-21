---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 대한 대체 행 스타일 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fea160e62939a27521592201cd47615975b7733f
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959406"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="79f02-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 대한 대체 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="79f02-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="79f02-103">테이블 형식 데이터는 종종 교대로 반복 되는 행의 배경색은 여기서 장부와 비슷한 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="79f02-104">이 형식을 사용하면 특히 많은 열을 포함하는 넓은 테이블에서 사용자가 각 행에 있는 셀을 쉽게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="79f02-105"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 교대로 반복되는 행에 대한 전체 스타일 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="79f02-106">교대로 반복 되는 행을 구분할 수 전경색 및 배경색 외에도 글꼴과 같은 스타일 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="79f02-107">자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="79f02-108">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="79f02-109">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="79f02-110">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="79f02-111">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="79f02-112">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79f02-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="79f02-113">교대로 반복 되는 행에 대 한 스타일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-113">Define styles for alternating rows</span></span>

1. <span data-ttu-id="79f02-114">선택 된 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-114">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="79f02-115">에 **속성** 창에서 줄임표 단추를 클릭 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 옆에 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-115">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="79f02-116">에 **CellStyle 작성기** 대화 상자에서 속성을 설정 하 여 스타일 정의 및 사용 합니다 **미리 보기** 선택 사항을 확인 하는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-116">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="79f02-117">지정한 스타일 번째부터 컨트롤에서 표시 하는 다른 모든 행에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-117">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="79f02-118">나머지 행에 대 한 스타일을 정의 하려면 사용 하 여 2-3 단계를 반복 하 여 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-118">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="79f02-119">셀이 여러 속성에서 상속 하는 스타일을 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-119">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="79f02-120">스타일 상속에 대 한 자세한 내용은 참조 하세요. [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79f02-120">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79f02-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="79f02-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="79f02-122">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="79f02-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79f02-123">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="79f02-123">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79f02-124">Windows Forms DataGridView 컨트롤에 디자이너 사용</span><span class="sxs-lookup"><span data-stu-id="79f02-124">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="79f02-125">방법: Windows Forms 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="79f02-125">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="79f02-126">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="79f02-126">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
