---
title: ComboBox 및 ListBox
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
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739934"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우
<xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.ListBox> 컨트롤은 유사한 동작을 포함 하며, 경우에 따라 상호 교환할 수 있습니다. 그러나 한 번은 작업에 더 적합할 수 있습니다.  
  
 일반적으로 콤보 상자는 제안 된 항목 목록이 있는 경우에 적합 하며 목록 상자는 입력을 목록에 있는 항목으로 제한 하려는 경우에 적합 합니다. 콤보 상자에는 텍스트 상자 필드가 있으므로 목록에서 선택 하지 않은 항목은에서 입력할 수 있습니다. <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>로 설정 된 경우는 예외입니다. 이 경우 첫 번째 문자를 입력 하면 컨트롤에서 항목을 선택 합니다.  
  
 또한 콤보 상자는 폼의 공간을 절약 합니다. 사용자가 아래쪽 화살표를 클릭할 때까지 전체 목록이 표시 되지 않기 때문에 콤보 상자는 목록 상자가 맞지 않는 작은 공간에 쉽게 맞출 수 있습니다. 단, <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> 속성이 <xref:System.Windows.Forms.ComboBoxStyle.Simple>로 설정 된 경우, 전체 목록이 표시 되 고 콤보 상자가 목록 상자 보다 더 많은 공간을 차지 하는 경우는 예외입니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](add-and-remove-items-from-a-wf-combobox.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
