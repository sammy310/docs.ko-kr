---
title: 디자이너를 사용 하 여 DataGridView 컨트롤에서 열 다시 정렬 사용
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 823c0064b2710ab5dfd0f67edf95374590d4490b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745846"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="b34b2-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="b34b2-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="b34b2-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시 되는 데이터를 볼 때 사용자는 특정 열의 값을 비교 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="b34b2-104">이는 열이 컨트롤에서 광범위 하 게 분리 된 경우에 불편할 수 있습니다. 특히 사용자가 관심 있는 모든 열을 표시 하기 위해 앞뒤로 가로 방향으로 스크롤해야 하는 경우에는 불편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="b34b2-105">사용자가 열을 다시 정렬할 수 있도록 하 여 열 값을 보다 쉽게 비교 하는 태스크를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="b34b2-106">열 다시 정렬을 사용 하도록 설정 하면 사용자가 열 머리글을 마우스로 끌어 열을 새 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="b34b2-107">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b34b2-108">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b34b2-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="b34b2-109">열 다시 정렬을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b34b2-109">To enable column reordering</span></span>

- <span data-ttu-id="b34b2-110"><xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 클릭 한 다음 열 다시 **정렬 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b34b2-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b34b2-111">참조</span><span class="sxs-lookup"><span data-stu-id="b34b2-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b34b2-112">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="b34b2-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="b34b2-113">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="b34b2-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="b34b2-114">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="b34b2-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
