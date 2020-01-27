---
title: DataGridView 컨트롤에서 새 레코드에 행 사용
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728342"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤에서 새 레코드에 대한 행 사용
응용 프로그램에서 데이터를 편집 하는 데 <xref:System.Windows.Forms.DataGridView>를 사용 하는 경우 데이터 저장소에 새 데이터 행을 추가할 수 있는 기능을 사용자에 게 제공 하는 경우가 많습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤은 항상 마지막 행으로 표시 되는 새 레코드에 대 한 행을 제공 하 여이 기능을 지원 합니다. 행 머리글에 별표 (*) 기호로 표시 됩니다. 다음 섹션에서는 새 레코드를 사용할 수 있도록 행으로 프로그래밍할 때 고려해 야 할 몇 가지 사항에 대해 설명 합니다.  
  
## <a name="displaying-the-row-for-new-records"></a>새 레코드에 대 한 행 표시  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 사용 하 여 새 레코드에 대 한 행이 표시 되는지 여부를 나타냅니다. 이 속성의 기본값은 `true`입니다.  
  
 데이터 바인딩된 경우에는 새 레코드에 대 한 행이 표시 됩니다 .이는 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성과 데이터 원본의 <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> 속성이 모두 `true`경우에 표시 됩니다. `false` 경우에는 해당 행이 표시 되지 않습니다.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>기본 데이터를 사용 하 여 새 레코드에 대 한 행 채우기  
 사용자가 새 레코드에 대 한 행을 현재 행으로 선택 하면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트를 발생 시킵니다.  
  
 이 이벤트는 새 <xref:System.Windows.Forms.DataGridViewRow>에 대 한 액세스를 제공 하 고 새 행을 기본 데이터로 채울 수 있도록 합니다. 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 새 행에 대 한 기본값 지정을](specify-default-values-for-new-rows-in-the-datagrid.md) 참조 하세요.  
  
## <a name="the-rows-collection"></a>Rows 컬렉션  
 새 레코드에 대 한 행은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에 포함 되지만 다음과 같은 두 가지 측면에서 다르게 동작 합니다.  
  
- <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에서 프로그래밍 방식으로 새 레코드의 행을 제거할 수 없습니다. 이를 시도 하면 <xref:System.InvalidOperationException>이 throw 됩니다. 또한 사용자는 새 레코드에 대 한 행을 삭제할 수 없습니다. <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> 메서드는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션에서이 행을 제거 하지 않습니다.  
  
- 새 레코드의 행 뒤에는 행을 추가할 수 없습니다. 이를 시도 하면 <xref:System.InvalidOperationException> 발생 합니다. 따라서 새 레코드의 행은 항상 <xref:System.Windows.Forms.DataGridView> 컨트롤의 마지막 행입니다. 행을 추가 하는 <xref:System.Windows.Forms.DataGridViewRowCollection>에 대 한 메서드 (<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>및 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>)는 새 레코드에 대 한 행이 있는 경우 내부적으로 삽입 메서드를 호출 합니다.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>새 레코드에 대 한 행의 시각적 사용자 지정  
 새 레코드에 대 한 행을 만들 때이 행은 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성에 지정 된 행을 기반으로 합니다. 이 행에 지정 되지 않은 모든 셀 스타일은 다른 속성에서 상속 됩니다. 셀 스타일 상속에 대 한 자세한 내용은 참조 하세요. [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)합니다.  
  
 새 레코드에 대 한 행의 셀에 표시 되는 초기 값은 각 셀의 <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> 속성에서 검색 됩니다. <xref:System.Windows.Forms.DataGridViewImageCell>형식의 셀의 경우이 속성은 자리 표시자 이미지를 반환 합니다. 그렇지 않은 경우 `null`을 반환합니다. 사용자 지정 값을 반환 하도록이 속성을 재정의할 수 있습니다. 그러나 이러한 초기 값은 포커스를 새 레코드의 행에 입력할 때 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트 처리기로 대체 될 수 있습니다.  
  
 이 행 머리글에 대 한 표준 아이콘 (화살표 또는 별표)은 공개적으로 노출 되지 않습니다. 아이콘을 사용자 지정 하려면 사용자 지정 <xref:System.Windows.Forms.DataGridViewRowHeaderCell> 클래스를 만들어야 합니다.  
  
 표준 아이콘은 행 머리글 셀에 사용 되는 <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 속성을 사용 합니다. 표준 아이콘은 완전히 표시 하는 데 충분 한 공간이 없는 경우에는 렌더링 되지 않습니다.  
  
 행 머리글 셀에 문자열 값이 설정 되어 있고 텍스트와 아이콘의 공간이 충분 하지 않은 경우 아이콘이 먼저 삭제 됩니다.  
  
## <a name="sorting"></a>정렬  
 바인딩되지 않은 모드에서는 사용자가 <xref:System.Windows.Forms.DataGridView>콘텐츠를 정렬 했더라도 새 레코드가 항상 <xref:System.Windows.Forms.DataGridView> 끝에 추가 됩니다. 사용자는 행을 올바른 위치로 정렬 하기 위해 정렬을 다시 적용 해야 합니다. 이 동작은 <xref:System.Windows.Forms.ListView> 컨트롤과 비슷합니다.  
  
 데이터 바인딩 및 가상 모드에서 정렬이 적용 될 때 삽입 동작은 데이터 모델의 구현에 따라 달라 집니다. ADO.NET의 경우 행이 올바른 위치로 즉시 정렬 됩니다.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>새 레코드의 행에 대 한 기타 참고 사항  
 이 행의 <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> 속성을 `false`로 설정할 수 없습니다. 이를 시도 하면 <xref:System.InvalidOperationException> 발생 합니다.  
  
 새 레코드에 대 한 행은 항상 선택 되지 않은 상태로 만들어집니다.  
  
## <a name="virtual-mode"></a>가상 모드  
 가상 모드를 구현 하는 경우 데이터 모델에 새 레코드의 행이 필요한 시기와 행 추가를 롤백하는 시기를 추적 해야 합니다. 이 기능의 정확한 구현은 커밋 범위가 셀 또는 행 수준에 있는지 여부와 같은 데이터 모델 및 해당 트랜잭션 의미 체계의 구현에 따라 달라 집니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 가상 모드](virtual-mode-in-the-windows-forms-datagridview-control.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 데이터 입력](data-entry-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정](specify-default-values-for-new-rows-in-the-datagrid.md)
