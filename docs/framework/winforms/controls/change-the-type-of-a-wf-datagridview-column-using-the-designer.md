---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 열의 형식 변경'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: f42bfe9b407e8f81c0eaf5a654d246f7b83567c9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208555"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="0d5bf-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 열의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="0d5bf-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="0d5bf-103">Windows Forms에 이미 추가 된 열의 형식을 변경 하는 경우가 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d5bf-104">예를 들어, 다음 유형의 데이터 원본에 컨트롤을 바인딩하는 경우 자동으로 생성 되는 열 중 일부를 수정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="0d5bf-105">표시할 테이블에 열이 관련된 테이블의 행에 외래 키가 포함 된 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="0d5bf-106">이 경우 다음 관련된 테이블에서 보다 의미 있는 값을 표시 하는 콤보 상자 열을 사용 하 여 이러한 외래 키는 표시 되는 텍스트 상자 열을 대체 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="0d5bf-107">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0d5bf-108">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d5bf-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0d5bf-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0d5bf-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="0d5bf-112">디자이너를 사용 하 여 열 유형을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="0d5bf-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="0d5bf-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="0d5bf-114">열을 선택 합니다 **선택한 열** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="0d5bf-115">에 **열 속성** 표에서 설정 합니다 `ColumnType` 속성을 새 열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d5bf-116">`ColumnType` 속성은 열 형식을 나타내는 클래스를 나타내는 디자인 타임 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="0d5bf-117">열 클래스에서 정의 하는 실제 속성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0d5bf-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5bf-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0d5bf-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="0d5bf-119">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0d5bf-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="0d5bf-120">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="0d5bf-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
