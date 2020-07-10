---
title: ComboBox 및 ListBox
description: Windows Forms ComboBox 및 Windows Forms ListBox를 사용 하는 방법에 대해 알아보고 하나 또는 다른가 작업에 더 적합 한 경우를 확인 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174421"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="7e2eb-103">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="7e2eb-103">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="7e2eb-104"><xref:System.Windows.Forms.ComboBox>및 컨트롤은 <xref:System.Windows.Forms.ListBox> 유사한 동작을 포함 하며, 경우에 따라 상호 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-104">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="7e2eb-105">그러나 한 번은 작업에 더 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-105">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="7e2eb-106">일반적으로 콤보 상자는 제안 된 항목 목록이 있는 경우에 적합 하며 목록 상자는 입력을 목록에 있는 항목으로 제한 하려는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-106">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="7e2eb-107">콤보 상자에는 텍스트 상자 필드가 있으므로 목록에서 선택 하지 않은 항목은에서 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-107">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="7e2eb-108">속성이로 설정 된 경우는 예외입니다 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> .</span><span class="sxs-lookup"><span data-stu-id="7e2eb-108">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="7e2eb-109">이 경우 첫 번째 문자를 입력 하면 컨트롤에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-109">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="7e2eb-110">또한 콤보 상자는 폼의 공간을 절약 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-110">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="7e2eb-111">사용자가 아래쪽 화살표를 클릭할 때까지 전체 목록이 표시 되지 않기 때문에 콤보 상자는 목록 상자가 맞지 않는 작은 공간에 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-111">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="7e2eb-112">단 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> , 속성을로 설정 하면 <xref:System.Windows.Forms.ComboBoxStyle.Simple> 전체 목록이 표시 되 고 콤보 상자가 목록 상자 보다 더 많은 공간을 차지 하는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="7e2eb-112">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2eb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e2eb-113">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="7e2eb-114">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="7e2eb-114">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="7e2eb-115">방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬</span><span class="sxs-lookup"><span data-stu-id="7e2eb-115">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="7e2eb-116">옵션 목록 표시에 사용하는 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7e2eb-116">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
