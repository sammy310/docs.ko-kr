---
title: ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우
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
ms.openlocfilehash: 5dc7778f43c01fd28a14489a7b4179dd851568b2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702999"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="da097-102">ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="da097-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="da097-103"><xref:System.Windows.Forms.ComboBox> 하며 <xref:System.Windows.Forms.ListBox> 컨트롤 유사 하 게 동작에 있으며 일부 경우 않을 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da097-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="da097-104">그러나 하나 또는 다른 작업에 더 적절 한 경우 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da097-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="da097-105">일반적으로 제안 된 선택 목록이 하 고 목록 상자는 목록에 새로운 기능에 대 한 입력을 제한 하려는 경우 적절 한 경우 콤보 상자 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="da097-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="da097-106">콤보 상자의 목록에 없는 항목에 입력할 수 있도록 텍스트 상자 필드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="da097-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="da097-107">경우는 예외를 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>합니다.</span><span class="sxs-lookup"><span data-stu-id="da097-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="da097-108">이 경우 컨트롤의 첫 번째 문자를 입력 하는 경우 항목을 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da097-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="da097-109">또한 콤보 상자 폼에서 공간을 절약 합니다.</span><span class="sxs-lookup"><span data-stu-id="da097-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="da097-110">아래쪽 화살표를 클릭할 때까지 전체 목록은 표시 되지 않으므로, 콤보 상자 목록 상자에 적합 하지는 작은 공간에 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da097-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="da097-111">경우는 예외입니다 합니다 <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.Simple>: 전체 목록이 표시 되 고 콤보 상자의 목록 상자 보다 더 많은 공간을 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="da097-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da097-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="da097-112">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="da097-113">방법: 추가 및 제거할 항목을 Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da097-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="da097-114">방법: Windows의 내용을 정렬할 Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da097-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="da097-115">옵션 목록 표시에 사용된 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="da097-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
