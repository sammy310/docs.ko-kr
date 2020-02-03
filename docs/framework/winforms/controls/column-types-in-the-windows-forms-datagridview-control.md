---
title: DataGridView 컨트롤의 열 형식
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743859"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 열 형식
<xref:System.Windows.Forms.DataGridView> 컨트롤에서는 여러 열 형식을 사용 하 여 해당 정보를 표시 하 고 사용자가 정보를 수정 하거나 추가할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 바인딩하고 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> 속성을 `true`로 설정 하면 바인딩된 데이터 원본에 포함 된 데이터 형식에 적합 한 기본 열 형식을 사용 하 여 열이 자동으로 생성 됩니다.  
  
 열 클래스의 인스턴스를 직접 만들고 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환 된 컬렉션에 추가할 수도 있습니다. 바인딩되지 않은 열로 사용 하기 위해 이러한 인스턴스를 만들거나 수동으로 바인딩할 수 있습니다. 수동으로 바인딩된 열은 예를 들어 한 형식의 자동으로 생성 된 열을 다른 형식의 열로 바꾸려는 경우 유용 합니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용할 수 있는 다양 한 열 클래스에 대해 설명 합니다.  
  
|클래스|Description|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|텍스트 기반 값에 사용 됩니다. 숫자 및 문자열에 바인딩할 때 자동으로 생성 됩니다.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|<xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값과 함께 사용 됩니다. 이러한 형식의 값에 바인딩하는 경우 자동으로 생성 됩니다.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|이미지를 표시 하는 데 사용 됩니다. 바이트 배열, <xref:System.Drawing.Image> 개체 또는 <xref:System.Drawing.Icon> 개체에 바인딩하는 경우 자동으로 생성 됩니다.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|셀에 단추를 표시 하는 데 사용 됩니다. 바인딩할 때 자동으로 생성 되지 않습니다. 일반적으로 바인딩되지 않은 열로 사용 됩니다.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|셀에 드롭다운 목록을 표시 하는 데 사용 됩니다. 바인딩할 때 자동으로 생성 되지 않습니다. 일반적으로 데이터 바인딩.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|셀에 링크를 표시 하는 데 사용 됩니다. 바인딩할 때 자동으로 생성 되지 않습니다. 일반적으로 데이터 바인딩.|  
|사용자 지정 열 형식|사용자 지정 모양, 동작 또는 호스트 된 컨트롤을 제공 하기 위해 <xref:System.Windows.Forms.DataGridViewColumn> 클래스 또는 해당 파생 클래스를 상속 하 여 고유한 열 클래스를 만들 수 있습니다. 자세한 내용은 [방법: 동작 및 모양을 확장 하 여 Windows Forms DataGridView 컨트롤에서 셀 및 열 사용자 지정을](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) 참조 하세요.|  
  
 이러한 열 형식은 다음 섹션에 자세히 설명 되어 있습니다.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>는 숫자 및 문자열과 같은 텍스트 기반 값에 사용할 수 있는 범용 열 유형입니다. 편집 모드에서는 사용자가 셀 값을 수정할 수 있도록 하는 <xref:System.Windows.Forms.TextBox> 컨트롤이 활성 셀에 표시 됩니다.  
  
 셀 값은 표시를 위해 자동으로 문자열로 변환 됩니다. 사용자가 입력 하거나 수정한 값은 자동으로 구문 분석 되어 해당 데이터 형식의 셀 값을 만듭니다. <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 및 <xref:System.Windows.Forms.DataGridView.CellParsing> 이벤트를 처리 하 여 이러한 변환을 사용자 지정할 수 있습니다.  
  
 열의 셀 값 데이터 형식은 열의 <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> 속성에서 지정 됩니다.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>는 <xref:System.Boolean> 및 <xref:System.Windows.Forms.CheckState> 값과 함께 사용 됩니다. <xref:System.Boolean> 값은 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성의 값에 따라 두 가지 상태 또는 세 가지 상태 확인란으로 표시 됩니다. 열이 <xref:System.Windows.Forms.CheckState> 값에 바인딩되면 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> 속성 값이 기본적으로 `true` 됩니다.  
  
 일반적으로 확인란 셀 값은 스토리지용이거나 다른 데이터와 같거나 대량 작업 수행용입니다. 사용자가 확인란 셀을 클릭할 때 즉시 응답 하려면 <xref:System.Windows.Forms.DataGridView.CellClick> 이벤트를 처리할 수 있지만이 이벤트는 셀 값이 업데이트 되기 전에 발생 합니다. 클릭 시 새 값을 해야 하는 경우 한 가지 방법은 될 예상 값을 계산 하려면 현재 값을 기반으로 합니다. 또 다른 방법은 변경 내용을 즉시 커밋하고 해당 이벤트에 응답 하는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트를 처리 하는 것입니다. 셀을 클릭 하면 변경 내용을 커밋하려면 <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> 이벤트를 처리 해야 합니다. 처리기에서 현재 셀이 확인란 셀 이면 <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> 메서드를 호출 하 고 <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> 값을 전달 합니다.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn>는 이미지를 표시 하는 데 사용 됩니다. 이미지 열은 데이터 원본에서 자동으로 채우거 나 바인딩되지 않은 열에 대해 수동으로 채우거 나 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트에 대 한 처리기에서 동적으로 채워질 수 있습니다.  
  
 데이터 원본에서 이미지 열의 자동 채우기는 <xref:System.Drawing.Image> 클래스에서 지원 되는 모든 형식과 Microsoft® Access 및 Northwind 샘플 데이터베이스에서 사용 하는 OLE 그림 형식을 포함 하 여 다양 한 이미지 형식으로 바이트 배열을 사용 하 여 작동 합니다.  
  
 수동으로 이미지 열을 채우면 사용자 지정 된 모양을 사용 하 여 <xref:System.Windows.Forms.DataGridViewButtonColumn>기능을 제공 하려는 경우에 유용 합니다. <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트를 처리 하 여 이미지 셀 내 클릭에 응답할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트에 대 한 처리기에서 이미지 열의 셀을 채우면 이미지 이외의 형식으로 계산 된 값 또는 값에 대 한 이미지를 제공 하려는 경우에 유용 합니다. 예를 들어 `"high"`, `"middle"`및 아이콘으로 표시할 `"low"`와 같은 문자열 값을 포함 하는 "위험" 열이 있을 수 있습니다. 또는 이미지의 이진 콘텐츠가 아닌 로드 해야 하는 이미지의 위치를 포함 하는 "Image" 열이 있을 수 있습니다.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>를 사용 하 여 단추를 포함 하는 셀의 열을 표시할 수 있습니다. 이 기능은 사용자가 주문을 배치 하거나 개별 창에 자식 레코드를 표시 하는 등 특정 레코드에 대 한 작업을 수행 하는 쉬운 방법을 제공 하려는 경우에 유용 합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 단추 열이 자동으로 생성 되지 않습니다. 단추 열을 사용 하려면 수동으로 만들고 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> 속성에서 반환 된 컬렉션에 추가 해야 합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 이벤트를 처리 하 여 단추 셀의 사용자 클릭에 응답할 수 있습니다.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>를 사용 하 여 드롭다운 목록 상자를 포함 하는 셀의 열을 표시할 수 있습니다. 이 기능은 Northwind 샘플 데이터베이스에 있는 Products 테이블의 Category 열과 같이 특정 값만 포함할 수 있는 필드의 데이터 입력에 유용 합니다.  
  
 <xref:System.Windows.Forms.ComboBox> 드롭다운 목록을 채우는 것과 같은 방식으로 모든 셀에 사용 되는 드롭다운 목록을 채울 수 있습니다 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 속성에서 반환 된 컬렉션을 통해 수동으로 또는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성을 통해 데이터 원본에 바인딩합니다. 자세한 내용은 [ComboBox 컨트롤](combobox-control-windows-forms.md)을 참조 하세요.  
  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>의 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> 속성을 설정 하 여 실제 셀 값을 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 사용 하는 데이터 소스에 바인딩할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 콤보 상자 열이 자동으로 생성 되지 않습니다. 콤보 상자 열을 사용 하려면 수동으로 만들고 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환 된 컬렉션에 추가 해야 합니다.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>를 사용 하면 하이퍼링크가 포함 된 셀의 열을 표시할 수 있습니다. 이 옵션은 데이터 원본의 URL 값 이나 자식 레코드를 사용 하 여 창을 여는 것과 같은 특수 동작에 대 한 단추 열에 대 한 대 안으로 유용 합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 바인딩할 때 링크 열이 자동으로 생성 되지 않습니다. 링크 열을 사용 하려면 해당 열을 수동으로 만들고 <xref:System.Windows.Forms.DataGridView.Columns%2A> 속성에서 반환 된 컬렉션에 추가 해야 합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellContentClick> 이벤트를 처리 하 여 링크에 대 한 사용자 클릭에 응답할 수 있습니다. 이 이벤트는 사용자가 셀의 아무 곳 이나 클릭할 때 발생 하는 <xref:System.Windows.Forms.DataGridView.CellClick> 및 <xref:System.Windows.Forms.DataGridView.CellMouseClick> 이벤트와는 별개입니다.  
  
 <xref:System.Windows.Forms.DataGridViewLinkColumn> 클래스는 이전, 도중 및 클릭 후에 링크 모양을 수정 하기 위한 여러 가지 속성을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [DataGridView 컨트롤](datagridview-control-windows-forms.md)
- [방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤 사용자 지정](customizing-the-windows-forms-datagridview-control.md)
