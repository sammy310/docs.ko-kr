---
title: '방법: TableLayoutPanel 컨트롤의 열과 행 편집'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 40129deed1f43480b7bde59ef8a67f4561af5d38
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724689"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="5673a-102">방법: TableLayoutPanel 컨트롤의 열과 행 편집</span><span class="sxs-lookup"><span data-stu-id="5673a-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="5673a-103">컬렉션 편집기를 사용할 수는 <xref:System.Windows.Forms.TableLayoutPanel> 호출을 **열 및 행 스타일** 대화 상자에서 행과 컨트롤의 열을 편집 하려면.</span><span class="sxs-lookup"><span data-stu-id="5673a-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5673a-104">여러 행 또는 열에 걸쳐 제어를 설정 합니다 `RowSpan` 및 `ColumnSpan` 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="5673a-105">자세한 내용은 [연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="5673a-106">셀 내에 있는 컨트롤을 정렬 하려는 셀 내에서 확장 하려는 경우를 사용 하 여 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="5673a-107">자세한 내용은 [연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="5673a-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5673a-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5673a-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5673a-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="5673a-111">행 및 열 편집</span><span class="sxs-lookup"><span data-stu-id="5673a-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="5673a-112"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="5673a-113">클릭 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 선택한 **행 및 열 편집** 열려는  **열 및 행 스타일** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="5673a-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="5673a-114">또한 마우스 오른쪽 단추로 클릭할 수에 합니다 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 선택 **행 및 열 편집** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="5673a-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="5673a-115">를 추가 하거나 열을 제거 하려면 선택 **열** 에서 합니다 **멤버 유형을** 드롭다운 목록 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="5673a-116">를 추가 하거나 행을 제거 하려면 선택 **행** 에서 합니다 **멤버 유형을** 드롭다운 목록 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="5673a-117">클릭 합니다 **추가** 끝에 행 또는 열을 추가 하려면 단추를 **멤버** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="5673a-118">클릭 합니다 **삽입** 목록의 행 또는 현재 선택한 항목 앞에 열을 추가 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="5673a-119">행 또는 열을 추가 하는 경우 선택 합니다 **크기 형식** 새 행 또는 열에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="5673a-120">자세한 내용은 <xref:System.Windows.Forms.SizeType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5673a-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="5673a-121">행 또는 열을 제거 하려면 클릭 합니다 **제거** 에서 현재 선택한 항목을 삭제 하려면 단추를 **멤버** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5673a-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5673a-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="5673a-122">See also</span></span>
- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="5673a-123">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5673a-123">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
