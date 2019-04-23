---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 966ffe131d10b97fe9632bb1ff23273b1dabd061
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194970"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="0ea92-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="0ea92-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="0ea92-103">Windows Forms에 표시 된 데이터를 볼 때 <xref:System.Windows.Forms.DataGridView> 컨트롤을 특정 열에 값을 비교할 사용자가 원하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="0ea92-104">이 불편할 수 있습니다 열 컨트롤에서 광범위 하 게 분리 되어 있으면 사용자가 관심 있는 모든 열을 표시 하려면 가로 앞뒤로 스크롤해야 하는 경우에 특히 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="0ea92-105">사용자가 열의 순서를 변경 하려면를 사용 하 여 열 값을 쉽게 비교 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="0ea92-106">열 다시 정렬을 사용 하도록 설정 하면 사용자는 마우스로 열 헤더를 끌어 열을 새 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>  
  
 <span data-ttu-id="0ea92-107">다음 절차를 수행 하려면을 **Windows 응용 프로그램** 포함 하는 양식을 사용 하 여 프로젝트를 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0ea92-108">이러한 프로젝트 설정에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트를 만듭니다](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 고 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ea92-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0ea92-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0ea92-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0ea92-111">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ea92-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-enable-column-reordering"></a><span data-ttu-id="0ea92-112">열 다시 정렬을 활성화 하려면</span><span class="sxs-lookup"><span data-stu-id="0ea92-112">To enable column reordering</span></span>  
  
-   <span data-ttu-id="0ea92-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택한 후 **열 다시 정렬 사용**.</span><span class="sxs-lookup"><span data-stu-id="0ea92-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea92-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0ea92-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0ea92-115">방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="0ea92-115">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="0ea92-116">방법: Windows Forms 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0ea92-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="0ea92-117">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="0ea92-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
