---
title: '방법: TableLayoutPanel 컨트롤에서 열과 행 편집'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 4473b20eea57088104a51eb1b6c080219223d214
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628646"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="94679-102">방법: TableLayoutPanel 컨트롤에서 열과 행 편집</span><span class="sxs-lookup"><span data-stu-id="94679-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="94679-103">**열 및 행 스타일** 대화 상자 라고 하는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 컬렉션 편집기를 사용 하 여 컨트롤의 행과 열을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94679-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="94679-104">컨트롤이 여러 행 또는 열에 걸쳐 있도록 하려면 컨트롤의 `RowSpan` 및 `ColumnSpan` 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="94679-105">자세한 내용은 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94679-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="94679-106">셀 내에서 컨트롤을 정렬 하려는 경우 또는 셀 내에서 컨트롤을 확장 하려는 경우 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="94679-107">자세한 내용은 [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94679-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="94679-108">행 및 열을 편집 하려면</span><span class="sxs-lookup"><span data-stu-id="94679-108">To edit rows and columns</span></span>

1. <span data-ttu-id="94679-109"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="94679-109">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="94679-110"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 디자이너 작업 문자 모양 (![작은 검은색 화살표](./media/designer-actions-glyph.gif))을 클릭 하 고 **행 및 열 편집** 을 선택 하 여 **열 및 행 스타일** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94679-110">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="94679-111"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴에서 **행 및 열 편집** 을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94679-111">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="94679-112">열을 추가 하거나 제거 하려면 **멤버 유형** 드롭다운 목록 상자에서 **열** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-112">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="94679-113">행을 추가 하거나 제거 하려면 **멤버 유형** 드롭다운 목록 상자에서 **행** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-113">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="94679-114">**멤버** 목록의 끝에 행 또는 열을 추가 하려면 **추가** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-114">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="94679-115">**삽입** 단추를 클릭 하 여 목록에서 현재 선택한 항목 앞에 행 또는 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-115">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="94679-116">행 또는 열을 추가 하는 경우 새 행 또는 열의 **크기 유형을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-116">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="94679-117">자세한 내용은 <xref:System.Windows.Forms.SizeType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94679-117">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="94679-118">행 또는 열을 제거 하려면 **제거** 단추를 클릭 하 여 **멤버** 목록에서 현재 선택한 항목을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="94679-118">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="94679-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94679-119">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="94679-120">TableLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="94679-120">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
