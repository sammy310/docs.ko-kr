---
title: ComboBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743838"
---
# <a name="combobox-control-overview-windows-forms"></a>ComboBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ComboBox> 컨트롤은 드롭다운 콤보 상자에 데이터를 표시 하는 데 사용 됩니다. 기본적으로 <xref:System.Windows.Forms.ComboBox> 컨트롤은 두 부분으로 표시 됩니다. 맨 위 부분은 사용자가 목록 항목을 입력할 수 있는 텍스트 상자입니다. 두 번째 부분은 사용자가 하나를 선택할 수 있는 항목 목록을 표시 하는 목록 상자입니다. 콤보 상자의 다른 스타일에 대 한 자세한 내용은 [ListBox 대신 Windows Forms ComboBox를 사용 하는 경우를](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)참조 하세요.  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 속성은 선택한 목록 항목에 해당 하는 정수 값을 반환 합니다. 코드에서 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값을 변경 하 여 프로그래밍 방식으로 선택한 항목을 변경할 수 있습니다. 목록에서 해당 항목은 콤보 상자의 텍스트 상자 부분에 표시 됩니다. 항목을 선택 하지 않으면 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값은-1입니다. 목록의 첫 번째 항목을 선택 하는 경우 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값은 0입니다. <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 속성은 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>와 비슷하지만 일반적으로 문자열 값으로 항목을 반환 합니다. <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> 속성은 목록에 있는 항목 수를 반영 하 고, <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>는 0부터 시작 하므로 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> 속성의 값은 항상 가장 큰 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 값 보다 하나 더 큽니다.  
  
 <xref:System.Windows.Forms.ComboBox> 컨트롤에서 항목을 추가 하거나 삭제 하려면 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> 또는 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> 메서드를 사용 합니다. 또는 디자이너에서 <xref:System.Windows.Forms.ComboBox.Items%2A> 속성을 사용 하 여 목록에 항목을 추가할 수 있습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ComboBox>
- [ListBox 컨트롤 개요](listbox-control-overview-windows-forms.md)
- [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](add-and-remove-items-from-a-wf-combobox.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기](create-a-lookup-table-for-a-wf-combobox-listbox.md)
