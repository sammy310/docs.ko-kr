---
title: DataGridViewComboBoxCell의 개체 액세스 드롭다운 목록
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746319"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>방법: Windows Forms DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스
<xref:System.Windows.Forms.ComboBox> 컨트롤과 마찬가지로 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 및 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 형식을 사용 하면 임의의 개체를 드롭다운 목록에 추가할 수 있습니다. 이 기능을 사용 하면 해당 개체를 별도의 컬렉션에 저장 하지 않고도 드롭다운 목록에서 복합 상태를 나타낼 수 있습니다.  
  
 <xref:System.Windows.Forms.ComboBox> 컨트롤과 달리 <xref:System.Windows.Forms.DataGridView> 형식에는 현재 선택 된 개체를 검색 하기 위한 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 속성이 없습니다. 대신 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> 속성을 비즈니스 개체의 속성 이름으로 설정 해야 합니다. 사용자가 선택 하면 비즈니스 개체의 표시 된 속성이 셀 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성을 설정 합니다.  
  
 셀 값을 통해 비즈니스 개체를 검색 하려면 `ValueMember` 속성이 비즈니스 개체 자체에 대 한 참조를 반환 하는 속성을 나타내야 합니다. 따라서 비즈니스 개체의 형식이 사용자의 제어를 받지 않는 경우 상속을 통해 형식을 확장 하 여 이러한 속성을 추가 해야 합니다.  
  
 다음 절차에서는 비즈니스 개체를 사용 하 여 드롭다운 목록을 채우고 셀 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성을 통해 개체를 검색 하는 방법을 보여 줍니다.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>드롭다운 목록에 비즈니스 개체를 추가 하려면  
  
1. 새 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>을 만들고 해당 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 컬렉션을 채웁니다. 또는 열 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 속성을 비즈니스 개체 컬렉션으로 설정할 수 있습니다. 그러나이 경우에는 컬렉션에서 해당 비즈니스 개체를 만들지 않고 드롭다운 목록에 "할당 되지 않음"을 추가할 수 없습니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성을 설정합니다. 드롭다운 목록에 표시할 비즈니스 개체의 속성을 나타내는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>입니다. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>은 비즈니스 개체에 대 한 참조를 반환 하는 속성을 나타냅니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. 현재 인스턴스에 대 한 참조를 반환 하는 속성이 비즈니스 개체 형식에 포함 되어 있는지 확인 합니다. 이전 단계에서 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>에 할당 된 값으로이 속성의 이름을 지정 해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>현재 선택 된 비즈니스 개체를 검색 하려면  
  
- 셀 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성을 가져와 비즈니스 개체 형식으로 캐스팅 합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>예제  
 전체 예제에서는 드롭다운 목록에서 비즈니스 개체를 사용 하는 방법을 보여 줍니다. 예제에서 <xref:System.Windows.Forms.DataGridView> 컨트롤은 `Task` 개체의 컬렉션에 바인딩됩니다. 각 `Task` 개체에는 해당 작업에 현재 할당 된 `Employee` 개체를 나타내는 `AssignedTo` 속성이 있습니다. `Assigned To` 열에는 할당 된 각 직원의 `Name` 속성 값이 표시 되거나 `Task.AssignedTo` 속성 값이 `null`인 경우 "할당 되지 않음"이 표시 됩니다.  
  
 이 예제의 동작을 보려면 다음 단계를 수행 합니다.  
  
1. 드롭다운 목록에서 다른 값을 선택 하거나 콤보 상자 셀에서 CTRL + 0을 눌러 `Assigned To` 열의 할당을 변경 합니다.  
  
2. 현재 할당을 표시 하려면 `Generate Report`를 클릭 합니다. 이는 `Assigned To` 열이 변경 되어 `tasks` 컬렉션을 자동으로 업데이트 하는 것을 보여 줍니다.  
  
3. `Request Status` 단추를 클릭 하 여 해당 행에 대 한 현재 `Employee` 개체의 `RequestStatus` 메서드를 호출 합니다. 이는 선택한 개체가 성공적으로 검색 되었음을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System 및 System.Windows.Forms 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Windows Forms DataGridView 컨트롤에서 데이터 표시](displaying-data-in-the-windows-forms-datagridview-control.md)
