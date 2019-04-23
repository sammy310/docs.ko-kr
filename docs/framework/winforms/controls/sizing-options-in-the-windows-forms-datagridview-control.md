---
title: Windows Forms DataGridView 컨트롤의 크기 조정 옵션
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sizing
- data grids [Windows Forms], column sizing
- DataGridView control [Windows Forms], column sizing
- DataGridView control [Windows Forms], sizing options
- data grids [Windows Forms], row sizing
- data grids [Windows Forms], sizing options
ms.assetid: a5620a9c-0d06-41e3-8934-c25ddb16c9e6
ms.openlocfilehash: 2f76bbca3d4b6e642c0eec2129c4a2abee752655
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197843"
---
# <a name="sizing-options-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 크기 조정 옵션
<xref:System.Windows.Forms.DataGridView> 행, 열 및 헤더는 여러 가지 동작의 결과로 크기를 변경할 수 있습니다. 다음 표에서 이러한 상황을 보여 줍니다.  
  
|발생|설명|  
|----------------|-----------------|  
|사용자 크기 조정|사용자가 끌거나 행, 열 또는 머리글 구분선을 두 번 클릭 하 여 크기를 조정할 수 있습니다.|  
|컨트롤 크기 조정|열 채우기 모드에서 열 너비 변경 컨트롤 너비 바뀌면; 예를 들어, 해당 부모 폼을 사용자 컨트롤이 도킹 되는 경우 폼 크기가 조정 됩니다.|  
|셀 값 변경|콘텐츠 기반 자동 크기 조정 모드로 크기 새 표시 값에 맞게 변경 합니다.|  
|메서드 호출|프로그래밍 방식으로 콘텐츠 기반 크기 조정 메서드 호출 시 셀 값에 따라 편의적 크기를 조정할 수 있습니다.|  
|속성 설정|또한 특정 높이 및 너비 값을 설정할 수 있습니다.|  
  
 기본적으로 사용자가 크기를 조정할 자동 크기 조정, 사용 하지 않도록 설정 하 고 열 보다 큰 되는 셀 값은 잘립니다.  
  
 다음 표에서 기본 동작을 조정 하거나 특정 크기 조정 옵션을 사용 하 여 특정 효과를 얻기 위해 사용할 수 있는 시나리오를 보여 줍니다.  
  
|시나리오|구현|  
|--------------|--------------------|  
|비슷한 크기의 비교적 적은 수의 가로 스크롤 막대를 표시 하지 않고 컨트롤의 전체 너비를 차지 하는 열에는 데이터를 표시 하기 위한 열 채우기 모드를 사용 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다.|  
|사용 하 여 열 채우기 모드를 사용 하 여 다양 한 크기의 값을 표시 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다. 열을 설정 하 여 상대 열 너비를 초기화할 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 또는 컨트롤을 호출 하 여 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 컨트롤을 데이터로 채운 후 메서드.|  
|다양 한 중요도 값을 사용 하 여 열 채우기 모드를 사용 합니다.|<xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>으로 설정합니다. 큰 설정 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 항상 해당 데이터의 일부를 표시 하거나 아닌 다른 크기 조정 옵션을 사용 해야 하는 열 채우기 모드 열의 특정 값입니다.|  
|컨트롤 배경에 표시 하지 않으려면 열 채우기 모드를 사용 합니다.|설정 합니다 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 마지막 열의 속성 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill> 하 고 다른 열에 대 한 다른 크기 조정 옵션을 사용 합니다. 다른 열을 너무 많이 사용 가능한 공간을 사용 하는 경우 설정의 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> 마지막 열 속성입니다.|  
|ID 열 또는 아이콘 같은 고정 폭 열을 표시 합니다.|설정 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 하 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None> 하 고 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> 에 <xref:System.Windows.Forms.DataGridViewTriState.False> 열에 대 한 합니다. 너비를 설정 하 여 초기화 된 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> 속성 또는 컨트롤을 호출 하 여 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A> 컨트롤을 데이터로 채운 후 메서드.|  
|셀 내용이 잘리는 것을 방지 하는 데 공간 사용을 최적화 변경 될 때마다 자동으로 크기를 조정 합니다.|콘텐츠 기반 크기 조정 모드를 나타내는 값으로 자동 크기 조정 속성을 설정 합니다. 많은 양의 데이터를 작업할 때 성능 저하를 방지 하려면 계산 하는 크기 조정 모드를 사용 하 여 행만 표시 됩니다.|  
|행의 수를 사용 하 여 작업할 때 성능 저하를 방지 하려면 표시 된 행의 값에 맞게 크기를 조정 합니다.|자동 또는 프로그래밍 방식으로 크기 조정을 사용 하 여 적절 한 크기 조정 모드 열거형 값을 사용 합니다. 스크롤 하는 동안 새로 표시 된 행의 값에 맞게 크기를 조정 하려면 크기 조정 메서드를 호출을 <xref:System.Windows.Forms.DataGridView.Scroll> 이벤트 처리기입니다. 사용자를 두 번 클릭에 맞게 크기 조정 값만 표시 된 행의 새 크기를 확인할 수 있도록 크기 조정의 메서드를 호출을 <xref:System.Windows.Forms.DataGridView.RowDividerDoubleClick> 또는 <xref:System.Windows.Forms.DataGridView.ColumnDividerDoubleClick> 이벤트 처리기입니다.|  
|특정 시간 성능 저하를 방지 하거나 사용자가 크기 조정 설정에 셀 내용에 맞게 크기를 조정 합니다.|이벤트 처리기에서 콘텐츠 기반 크기 조정 메서드를 호출 합니다. 사용 예를 들어 합니다 <xref:System.Windows.Forms.DataGridView.DataBindingComplete> 바인딩 후 크기를 초기화 하 고 처리 하는 이벤트를 <xref:System.Windows.Forms.DataGridView.CellValidated> 또는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 사용자 편집 내용 또는 변경에 대 한 보정을 위해 크기를 조정 하는 이벤트 바인딩된 데이터 소스에서 합니다.|  
|여러 줄 셀 내용에 대 한 행 높이 조정 합니다.|열 너비 텍스트 단락을 표시 하는 것에 대 한 적절 한지 확인 하 고 높이를 조정 콘텐츠 기반 자동 또는 프로그래밍 방식으로 행 크기를 사용 합니다. 또한 사용 하 여 여러 줄로 콘텐츠를 사용 하 여 셀은 표시를 확인 한 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 셀의 스타일 값 <xref:System.Windows.Forms.DataGridViewTriState.True>합니다.<br /><br /> 일반적으로 열 너비를 유지 관리 또는 행 높이 조정 하기 전에 특정 너비를 설정 하려면 자동 열 크기 조정 모드를 사용 합니다.|  
  
## <a name="resizing-with-the-mouse"></a>마우스를 사용 하 여 크기 조정  
 사용자는 기본적으로 행, 열 및 셀 값에 따라 자동 크기 조정 모드를 사용 하지 않는 헤더를 조정할 수 있습니다. 열 채우기 모드와 같은 다른 모드를 사용 하 여 크기를 조정 하지 못하게 하려면 다음 중 하나 이상을 설정 <xref:System.Windows.Forms.DataGridView> 속성:  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
 설정 하 여 개별 행 이나 열 크기 조정에서 사용자를 방지할 수도 있습니다는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성입니다. 기본적으로 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값은 기반으로 합니다 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A> 열에 대 한 속성 값 및 <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A> 행에 대 한 속성 값입니다. 명시적으로 설정 하면 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 하 <xref:System.Windows.Forms.DataGridViewTriState.True> 또는 <xref:System.Windows.Forms.DataGridViewTriState.False>그러나 컨트롤 값이 해당 행 또는 열에 대해 지정 된 값이 재정의 합니다. 설정 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 에 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 상속을 복원 합니다.  
  
 때문에 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 값 상속을 복원 합니다 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성을 반환 하지 것입니다를 <xref:System.Windows.Forms.DataGridViewTriState.NotSet> 행 또는 열에 추가 되지 않는에 값을 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 확인 해야 할 경우 여부를 합니다 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 행 또는 열 속성 값이 상속, 검사 해당 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성입니다. 경우는 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 값에 포함 됩니다 합니다 <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet> 플래그를는 <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A> 속성 값 상속 되지 않습니다.  
  
## <a name="automatic-sizing"></a>자동 크기 조정  
 두 가지 종류의 자동 크기 조정의는 <xref:System.Windows.Forms.DataGridView> 컨트롤: 열 채우기 모드 및 콘텐츠 기반 자동 크기 조정 합니다.  
  
 열 채우기 모드 컨트롤의 표시 영역 너비에 맞게 컨트롤에 표시 되는 열의 발생 합니다. 이 모드에 대 한 자세한 내용은 참조 하세요. [Windows Forms DataGridView 컨트롤의 열 채우기 모드](column-fill-mode-in-the-windows-forms-datagridview-control.md)합니다.  
  
 행, 열 및 머리글 셀 내용에 맞게 크기를 자동으로 조정 하도록 구성할 수 있습니다. 이 경우 크기 조정 셀 내용이 변경 될 때마다 발생 합니다.  
  
> [!NOTE]
>  가상 모드를 사용 하 여 사용자 지정 데이터 캐시에 셀 값을 유지 하는 경우 자동 크기 조정 경우 사용자가 셀 값을 편집 하지만 외부에서 캐시 된 값을 변경할 때 발생 하지 않습니다는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트 처리기입니다. 이 경우 호출 된 <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> 셀 표시 내용을 업데이트 하 여 현재 자동 크기 조정 모드를 적용 하는 컨트롤을 강제 적용 하는 방법입니다.  
  
 콘텐츠 기반 자동 크기 조정 중 한 방향 으로만 사용할 수 있는 경우-즉, 열 또는 열을이 아니라 행에 대 한 있지만 행 하지-및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 사용 하도록 설정, 크기 조정에도 다른 차원을 변경 될 때마다 발생 이기도 합니다. 예를 들어, 자동 크기 조정에 대 한 열이 아니라 행 구성 된 경우 및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 는 사용자 수 열 구분선을 끌어 열의 너비를 변경 하려면 사용 하 고 셀 내용을 완벽 하 게 표시 되도록 행 높이 자동으로 조정 됩니다.  
  
 행과 콘텐츠 기반 자동 크기 조정에 대 한 열을 구성 하는 경우 및 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 을 사용 하는 <xref:System.Windows.Forms.DataGridView> 셀 내용을 변경 하 고 새 크기를 계산 하는 경우는 이상적인 셀 높이 너비의 비율을 사용 하는 때마다 컨트롤 크기 조정 됩니다.  
  
 컨트롤 값을 재정의 하지 않는 열 및 머리글 및 행에 대 한 크기 조정 모드를 구성 하려면 다음 중 하나 이상을 설정 <xref:System.Windows.Forms.DataGridView> 속성:  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A>  
  
 개별 열에 대 한 컨트롤의 열 크기 조정 모드를 재정의 하려면 해당 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 이외의 값으로 속성 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>합니다. 열에 대 한 크기 조정 모드에 따른 실제로 해당 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성입니다. 이 속성의 값은 열에 기반 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> 속성 값이 아닌 값 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.NotSet>있으며이 경우 컨트롤의 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A> 값은 상속 됩니다.  
  
 콘텐츠 기반 자동 크기 조정 주의 해 서 많은 양의 데이터를 작업할 때 사용 합니다. 성능 저하를 방지 하려면 컨트롤의 모든 행을 분석 하는 것이 아니라 표시 된 행에 따라서만 크기를 계산 하는 자동 크기 조정 모드를 사용 합니다. 최상의 성능을 위해 사용 하 여 프로그래밍 방식으로 크기 조정 대신 새 데이터 직후와 같은 특정 시간에 조정할 수 있습니다 있도록 로드 됩니다.  
  
 콘텐츠 기반 자동 크기 조정 모드에는 행 이나 열, 행 또는 열을 설정 하 여 숨겨진 헤더 주지 <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성 또는 컨트롤 <xref:System.Windows.Forms.DataGridView.RowHeadersVisible%2A> 또는 <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> 속성을 `false`입니다. 예를 들어 큰 셀 값에 맞게 크기가 자동으로 열을 숨기면, 숨겨진된 열 변경 되지 않습니다 크기가 큰 셀 값이 포함 된 행을 삭제 하는 경우. 표시 유형 변경 되 면 자동 크기 조정 수행 하므로 열을 변경 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 다시 `true` 현재 내용에 따라 크기를 계산 하도록 강제 하지 것입니다.  
  
 프로그래밍 방식으로 콘텐츠 기반 크기 조정 행, 열 및 머리글의 가시성에 관계 없이 영향을 줍니다.  
  
## <a name="programmatic-resizing"></a>프로그래밍 방식의 크기 조정  
 자동 크기 조정을 비활성화 되 면 정확한 너비 또는 높이 행, 열 또는 다음 속성을 통해 헤더의 프로그래밍 방식으로 설정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
  
 또한 프로그래밍 방식으로 행, 열 및 헤더는 다음 메서드를 사용 하 여 해당 내용에 맞게 조정할 수 있습니다.  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A>  
  
-   <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A>  
  
 이러한 메서드는 행, 열 또는 헤더를 한 번 구성 하지 않고 연속 크기 조정에 대 한 크기가 조정 됩니다. 새 크기 클리핑 없이 모든 셀 내용을 표시 하도록 자동으로 계산 됩니다. 그러나이 있는 열을 프로그래밍 방식으로 조정 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.Fill>를 내용에 따라 계산된 된 너비 열 크기를 비례적으로 조정 되는 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> 속성 값 및 실제 열 너비 그런 다음 모든 열에서 사용 가능한 표시 영역의 컨트롤을 채울 수 있도록 이러한 새 비율에 따라 계산 합니다.  
  
 프로그래밍 방식의 크기 조정 하는 것은 지속적인 크기 조정을 통한 성능 저하를 방지 하는 데 유용 합니다. 사용자-크기를 조정할 행, 열 및 헤더와 열 채우기 모드에 대 한 초기 크기를 제공 하는 것이 유용 합니다.  
  
 일반적으로 특정 시간에 프로그래밍 방식으로 크기 조정 메서드를 호출 합니다. 예를 들어, 데이터를 로드 한 직후 모든 열을 프로그래밍 방식으로 조정 될 수 있습니다 또는 특정 셀 값을 수정한 후 특정 행을 프로그래밍 방식으로 조정 될 수 있습니다.  
  
## <a name="customizing-content-based-sizing-behavior"></a>콘텐츠 기반 크기 조정 동작을 사용자 지정  
 파생을 사용 하는 경우 크기 조정 동작을 사용자 지정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 재정의 하 여 셀, 행 및 열 형식 합니다 <xref:System.Windows.Forms.DataGridViewCell.GetPreferredSize%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridViewRow.GetPreferredHeight%2A?displayProperty=nameWithType>, 또는 <xref:System.Windows.Forms.DataGridViewColumn.GetPreferredWidth%2A?displayProperty=nameWithType> 메서드를 호출 하 여 파생에서 크기 조정 메서드 오버 로드를 보호 하거나 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다. 보호 된 크기 조정 메서드 오버 로드는 지나치게 가로 또는 세로 셀을 방지 하는 이상적인 셀 높이 너비 비율을 달성 하기 위해 쌍에서 작동 하도록 설계 되었습니다. 예를 들어, 호출 하는 경우는 `AutoResizeRows(DataGridViewAutoSizeRowsMode,Boolean)` 오버 로드 된 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A> 메서드 및 값을 전달 `false` 에 대 한는 <xref:System.Boolean> 매개 변수를 이상적인 높이 너비는 행의 셀에 대 한 오버 로드를 계산 하지만 행 높이가 조정 됩니다 만 합니다. 다음 호출 해야 합니다는 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> 계산 이상적인 열 너비를 조정 하는 방법입니다.  
  
## <a name="content-based-sizing-options"></a>콘텐츠 기반 크기 조정 옵션  
 콘텐츠 기반 크기 조정에 대 한 유사한 값을 포함 하는 방법 및 크기 조정 속성에서 사용 하는 열거형입니다. 이러한 값을 사용 하 여 기본 설정된 크기를 계산 하는 셀이 사용 됩니다 제한할 수 있습니다. 모든 크기 조정 열거형에 대 한 이름이 표시 된 셀을 참조 하는 값이 있는 표시 된 행의 셀에는 계산을 제한 합니다. 행은 제외 하는 것은 대용량 행의를 사용 하 여 작업할 때 성능 저하를 방지 하는 데 유용 합니다. 또한 계산 헤더 또는 머리글이 아닌 셀에 셀 값을 제한할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AllowUserToResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.Resizable%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.Height%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 열 채우기 모드](column-fill-mode-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)
