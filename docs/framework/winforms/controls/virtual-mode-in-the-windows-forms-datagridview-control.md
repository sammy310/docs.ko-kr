---
title: DataGridView 컨트롤의 가상 모드
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 0d82f0fc9946e5b61ea171f2f5d2ab5690db0c71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745437"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 가상 모드
가상 모드를 사용 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤과 사용자 지정 데이터 캐시 간의 상호 작용을 관리할 수 있습니다. 가상 모드를 구현 하려면 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정 하 고이 항목에서 설명 하는 하나 이상의 이벤트를 처리 합니다. 일반적으로 하나 이상의 `CellValueNeeded` 이벤트를 처리 하 여 컨트롤에서 데이터 캐시의 값을 조회할 수 있도록 합니다.  
  
## <a name="bound-mode-and-virtual-mode"></a>바인딩된 모드 및 가상 모드  
 가상 모드는 바인딩된 모드를 보완 하거나 대체 해야 하는 경우에만 필요 합니다. 바인딩된 모드에서는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 설정 하 고, 컨트롤은 지정 된 소스에서 데이터를 자동으로 로드 하 고 사용자 변경 내용을 다시 전송 합니다. 표시 되는 바인딩된 열을 제어할 수 있으며, 데이터 소스 자체는 일반적으로 정렬과 같은 작업을 처리 합니다.  
  
## <a name="supplementing-bound-mode"></a>바인딩 모드 보완  
 바인딩된 열과 함께 바인딩되지 않은 열을 표시 하 여 바인딩된 모드를 보완할 수 있습니다. 이를 "혼합 모드" 라고도 하며 계산 된 값 또는 UI (사용자 인터페이스) 컨트롤과 같은 항목을 표시 하는 데 유용 합니다.  
  
 바인딩되지 않은 열은 데이터 소스 외부에 있으므로 데이터 원본의 정렬 작업에서 무시 됩니다. 따라서 혼합 모드에서 정렬을 사용 하도록 설정 하는 경우 로컬 캐시에서 바인딩되지 않은 데이터를 관리 하 고 <xref:System.Windows.Forms.DataGridView> 컨트롤이 상호 작용할 수 있도록 가상 모드를 구현 해야 합니다.  
  
 가상 모드를 사용 하 여 바인딩되지 않은 열의 값을 유지 하는 방법에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> 클래스 참조 항목의 예제를 참조 하세요.  
  
## <a name="replacing-bound-mode"></a>바인딩된 모드 바꾸기  
 바인딩된 모드가 성능 요구를 충족 하지 않는 경우 가상 모드 이벤트 처리기를 통해 사용자 지정 캐시의 모든 데이터를 관리할 수 있습니다. 예를 들어 가상 모드를 사용 하 여 최적의 성능을 위해 필요한 만큼 네트워크로 연결 된 데이터베이스에서 데이터만 검색 하는 just-in-time 데이터 로드 메커니즘을 구현할 수 있습니다. 이 시나리오는 느린 네트워크 연결을 통해 대량의 데이터를 사용 하거나 RAM 또는 저장소 공간이 제한 된 클라이언트 컴퓨터를 사용 하는 경우에 특히 유용 합니다.  
  
 Just-in-time 시나리오에서 가상 모드를 사용 하는 방법에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤에서 Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)을 참조 하세요.  
  
## <a name="virtual-mode-events"></a>가상 모드 이벤트  
 데이터가 읽기 전용 이면 처리 해야 하는 이벤트는 `CellValueNeeded` 이벤트 일 수 있습니다. 추가 가상 모드 이벤트를 사용 하 여 사용자 편집, 행 추가 및 삭제, 행 수준 트랜잭션과 같은 특정 기능을 사용할 수 있습니다.  
  
 사용자가 행을 추가 하거나 삭제할 때 발생 하는 이벤트, 사용자가 행을 추가 하거나 삭제할 때 발생 하는 이벤트, 셀 값 편집, 구문 분석, 유효성 검사 또는 형식이 지정 된 경우와 같은 일부 표준 <xref:System.Windows.Forms.DataGridView> 이벤트는 가상 모드 에서도 유용 합니다 일반적으로 바인딩된 데이터 원본에 저장 되지 않는 값 (예: 셀 도구 설명 텍스트, 셀 및 행 오류 텍스트, 셀 및 행 바로 가기 메뉴 데이터 및 행 높이 데이터)을 유지 관리할 수 있는 이벤트를 처리할 수도 있습니다.  
  
 행 수준 커밋 범위를 사용 하 여 읽기/쓰기 데이터를 관리 하는 가상 모드를 구현 하는 방법에 대 한 자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)을 참조 하세요.  
  
 셀 수준 커밋 범위를 사용 하 여 가상 모드를 구현 하는 예제는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 참조 항목을 참조 하세요.  
  
 다음 이벤트는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`로 설정 된 경우에만 발생 합니다.  
  
|Event|설명|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|컨트롤에서 표시할 데이터 캐시의 셀 값을 검색 하는 데 사용 됩니다. 이 이벤트는 바인딩되지 않은 열의 셀에 대해서만 발생 합니다.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|컨트롤에서 데이터 캐시에 대 한 사용자 입력을 커밋하는 데 사용 됩니다. 이 이벤트는 바인딩되지 않은 열의 셀에 대해서만 발생 합니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기 외부에서 캐시 된 값을 변경할 때 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 메서드를 호출 하 여 현재 값이 컨트롤에 표시 되는지 확인 하 고 현재 적용 되는 자동 크기 조정 모드를 적용 합니다.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|컨트롤에서 데이터 캐시에 새 행이 필요한 지 여부를 나타내는 데 사용 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|컨트롤에서 행에 커밋되지 않은 변경 내용이 있는지 여부를 확인 하는 데 사용 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|컨트롤에서 행을 캐시 된 값으로 되돌려야 함을 나타내는 데 사용 됩니다.|  
  
 다음 이벤트는 가상 모드에서 유용 하지만 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 설정에 관계 없이 사용할 수 있습니다.  
  
|이벤트|설명|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|컨트롤에서 행을 삭제 하거나 추가 하는 시간을 표시 하는 데 사용 되므로 데이터 캐시를 적절 하 게 업데이트할 수 있습니다.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|컨트롤에서 표시 하기 위해 셀 값의 서식을 지정 하 고 사용자 입력을 구문 분석 하 고 유효성을 검사 하는 데 사용 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|<xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정 되거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`될 때 컨트롤에서 셀 도구 설명 텍스트를 검색 하는 데 사용 됩니다.<br /><br /> <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> 속성 값이 `true`되는 경우에만 셀 도구 설명이 표시 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|<xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정 되거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`될 때 컨트롤에서 셀 또는 행 오류 텍스트를 검색 하는 데 사용 됩니다.<br /><br /> 셀 또는 행 오류 텍스트를 변경 하 여 현재 값이 컨트롤에 표시 되도록 하려면 <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> 메서드나 <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> 메서드를 호출 합니다.<br /><br /> 셀 및 행 오류 문자 모양은 <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> 및 <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> 속성 값이 `true`될 때 표시 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|컨트롤 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정 되거나 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성이 `true`때 컨트롤이 셀 또는 행 <xref:System.Windows.Forms.ContextMenuStrip>를 검색 하는 데 사용 됩니다.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|컨트롤에서 데이터 캐시의 행 높이 정보를 검색 하거나 저장 하는 데 사용 됩니다. <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> 이벤트 처리기 외부에서 캐시 된 행 높이 정보를 변경할 때 <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> 메서드를 호출 하 여 현재 값이 컨트롤 표시에 사용 되는지 확인 합니다.|  
  
## <a name="best-practices-in-virtual-mode"></a>가상 모드의 모범 사례  
 많은 양의 데이터를 효율적으로 사용 하기 위해 가상 모드를 구현 하는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤 자체를 효율적으로 사용 하 고 있는지도 확인 해야 합니다. 셀 스타일, 자동 크기 조정, 선택 항목 및 행 공유를 효율적으로 사용 하는 방법에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤 크기 조정에 대 한 모범 사례](best-practices-for-scaling-the-windows-forms-datagridview-control.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Windows Forms DataGridView 컨트롤의 성능 조정](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
