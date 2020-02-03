---
title: ListBox 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745186"
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListBox> 컨트롤은 사용자가 하나 이상의 항목을 선택할 수 있는 목록을 표시 합니다. 총 항목 수가 표시할 수 있는 수를 초과 하면 스크롤 막대가 <xref:System.Windows.Forms.ListBox> 컨트롤에 자동으로 추가 됩니다. <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `true`로 설정 된 경우 목록 상자에 여러 열의 항목이 표시 되 고 가로 스크롤 막대가 나타납니다. <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 속성이 `false`로 설정 된 경우 목록 상자에는 단일 열에 항목이 표시 되 고 세로 스크롤 막대가 나타납니다. <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A>을 `true`로 설정 하면 항목 수에 관계 없이 스크롤 막대가 표시 됩니다. <xref:System.Windows.Forms.ListBox.SelectionMode%2A> 속성은 한 번에 선택할 수 있는 목록 항목의 수를 결정 합니다.  
  
## <a name="ways-to-change-the-listbox-control"></a>ListBox 컨트롤을 변경 하는 방법  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 속성은 목록 상자에서 선택한 첫 번째 항목에 해당 하는 정수 값을 반환 합니다. 코드에서 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값을 변경 하 여 프로그래밍 방식으로 선택한 항목을 변경할 수 있습니다. 목록에서 해당 항목이 Windows Form에 강조 표시 됩니다. 항목을 선택 하지 않으면 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은-1입니다. 목록의 첫 번째 항목을 선택 하는 경우 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 0입니다. 여러 항목을 선택 하는 경우 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값은 목록에서 첫 번째로 표시 되는 선택 된 항목을 반영 합니다. <xref:System.Windows.Forms.ListBox.SelectedItem%2A> 속성은 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>와 비슷하지만 일반적으로 문자열 값으로 항목을 반환 합니다. <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성은 목록에 있는 항목 수를 반영 하 고, <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>는 0부터 시작 하므로 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 속성의 값은 항상 가장 큰 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 값 보다 하나 더 큽니다.  
  
 <xref:System.Windows.Forms.ListBox> 컨트롤에서 항목을 추가 하거나 삭제 하려면 <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A>, <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> 또는 <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> 메서드를 사용 합니다. 또는 디자인 타임에 <xref:System.Windows.Forms.ListBox.Items%2A> 속성을 사용 하 여 목록에 항목을 추가할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ListBox>
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거](add-and-remove-items-from-a-wf-combobox.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [방법: 데이터에 Windows Forms ComboBox 또는 ListBox 컨트롤 바인딩](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [ComboBox 컨트롤 개요](combobox-control-overview-windows-forms.md)
- [CheckedListBox 컨트롤 개요](checkedlistbox-control-overview-windows-forms.md)
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 조회 테이블 만들기](create-a-lookup-table-for-a-wf-combobox-listbox.md)
