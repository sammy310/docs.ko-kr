---
title: Windows Forms DataGridView 컨트롤의 열 정렬 모드
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: b8f6048946d367dd79b1ce0d23d84446ffdb1115
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106668"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 열 정렬 모드
<xref:System.Windows.Forms.DataGridView> 열의 경우 세 가지 정렬 모드 각 열에 대 한 정렬 모드를 통해 지정 됩니다 합니다 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 다음 중 하나로 설정할 수 있는 열의 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형 값입니다.  
  
|`DataGridViewColumnSortMode` 값|설명|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|텍스트 상자 열에 대 한 기본값입니다. 열 머리글 선택으로 사용 되므로 하지 않으면 자동으로 열 머리글을 클릭 하면 정렬는 <xref:System.Windows.Forms.DataGridView> 이 열에서 정렬 순서를 나타내는 문자 모양을 표시 합니다.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|텍스트 상자가 아닌 열의 기본값입니다. 프로그래밍 방식으로이 열을 정렬할 수 있습니다. 그러나 것은 아닙니다 정렬에 대 한 정렬 문자에 대 한 공간이 없으면 예약 되어 있도록 합니다.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|프로그래밍 방식으로이 열을 정렬할 수 있습니다 하 고 정렬 문자를 위한 공간이 예약 됩니다.|  
  
 기본적으로 열 정렬 모드를 변경 하려는 <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 의미에 따라 정렬할 수 있는 값이 포함 된 경우. 예를 들어에서 항목 상태를 나타내는 번호가 포함 된 데이터베이스 열에 있는 경우에 데이터베이스 열은 이미지 열에 바인딩하여 해당 아이콘으로 이러한 숫자를 표시할 수 있습니다. 에 대 한 처리기에서 이미지 표시 값으로 숫자 셀 값을 변경할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 이벤트입니다. 이 경우에 설정 된 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> 열을 정렬할 수 있도록 합니다. 자동 정렬 상태 번호에 해당 하는 자연 스러운 순서 없는 경우에 동일한 상태에 있는 항목을 그룹화 하 여 사용자 사용 하도록 설정 됩니다. 확인란 열은 자동 정렬을 동일한 상태에서 항목을 그룹화 하는 데 유용한 또 다른 예입니다.  
  
 정렬할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 프로그래밍 방식으로 또는 여러 열에 관계 없이 모든 열에서 값으로는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 설정 합니다. 정렬에 대 한 고유한 사용자 인터페이스 (UI)를 제공 하려는 경우 또는 사용자 지정 정렬을 구현 하려는 경우 프로그래밍 방식으로 정렬 하는 것은 유용 합니다. 를 고유한 정렬 UI가 도움이 제공 예를 들어, 설정한 경우는 <xref:System.Windows.Forms.DataGridView> 열 머리글 선택 영역을 사용 하도록 설정 하려면 선택 모드입니다. 이 경우 정렬에 대 한 열 헤더를 사용할 수 있지만 여전히 원하는 헤더를 설정할 수 있도록 적절 한 정렬 문자를 표시 합니다 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>입니다.  
  
 프로그래밍 방식으로 정렬 모드 설정 열에 정렬 문자를 자동으로 표시 되지 않습니다. 이러한 열에 대 한 직접 표시 해야 문자 모양을 설정 하 여는 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> 속성입니다. 이 사용자 지정 정렬에 유연성을 원하는 경우 필요 합니다. 예를 들어, 정렬 하는 경우는 <xref:System.Windows.Forms.DataGridView> 여러 정렬 문자 또는 정렬 문자 모양은 표시 하려는 여러 열을 기준으로 합니다.  
  
 프로그래밍 방식으로 정렬할 수 있습니다 하지만 <xref:System.Windows.Forms.DataGridView> 열순으로 단추 열과 같은 일부 열 의미에 따라 정렬할 수 있는 값 없을 수도 있습니다. 이 열에 대해서는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 의 속성 설정을 <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 정렬 문자에 대 한 헤더에 공간을 예약 하지 않아도 되므로 하 고 정렬에 사용 되지 것입니다 나타냅니다.  
  
 경우는 <xref:System.Windows.Forms.DataGridView> 는 정렬 확인할 수 있습니다 정렬 열 및 정렬 순서 값을 확인 하 여 합니다 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성입니다. 사용자 지정 정렬 작업을 수행한 후에 이러한 값은 의미가 없습니다. 사용자 지정 정렬 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 사용자 지정 정렬 섹션을 참조 합니다.  
  
 경우는 <xref:System.Windows.Forms.DataGridView> 바인딩된 및 바인딩되지 않은 열이 포함 된 컨트롤은 정렬 된, 바인딩되지 않은 열에서 값을 자동으로 유지 될 수 없습니다. 이러한 값을 유지 하려면 설정 하 여 가상 모드 구현 해야 합니다는 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true` 하 고 처리를 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 및 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트. 자세한 내용은 [방법: Windows에서 가상 모드 구현 Forms DataGridView 컨트롤](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)합니다. 바인딩된 모드로 바인딩되지 않은 열을 기준으로 정렬 하는 것은 지원 되지 않습니다.  
  
## <a name="programmatic-sorting"></a>프로그래밍 방식 정렬  
 정렬할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 를 호출 하 여 프로그래밍 방식으로 해당 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드.  
  
 `Sort(DataGridViewColumn,ListSortDirection)` 오버 로드는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드를 <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.ComponentModel.ListSortDirection> 매개 변수로 열거형 값입니다. 이 오버 로드는 의미에 따라 정렬할 수, 하지만 자동 정렬에 대 한 구성 하지 않을 값을 사용 하 여 열을 기준으로 정렬할 때 유용 합니다. 이 오버 로드를 호출 하 고 열에 전달 하는 경우는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성 값 <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>의 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성 자동으로 설정 되 고 열 머리글에 적절 한 정렬 문자 모양이 표시 합니다.  
  
> [!NOTE]
>  경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 바인딩되는 외부 데이터 원본 설정 하 여는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성인은 `Sort(DataGridViewColumn,ListSortDirection)` 바인딩되지 않은 열에 대 한 메서드 오버 로드 작동 하지 않습니다. 또한, 합니다 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성은 `true`바인딩된 열에 대해서만이 오버 로드를 호출할 수 있습니다. 열 데이터 바인딩 인지를 확인 하려면 확인을 <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> 속성 값입니다. 바인딩된 모드로 바인딩되지 않은 열을 정렬 하는 것은 지원 되지 않습니다.  
  
## <a name="custom-sorting"></a>사용자 지정 정렬  
 사용자 지정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 를 사용 하 여 합니다 `Sort(IComparer)` 오버 로드는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드 또는 처리 하 여는 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트입니다.  
  
 합니다 `Sort(IComparer)` 구현 하는 클래스의 인스턴스를 사용 하는 메서드 오버 로드는 <xref:System.Collections.IComparer> 인터페이스를 매개 변수로 합니다. 사용자 지정 정렬을; 제공 하려는 경우이 오버 로드 유용 합니다. 예를 들어, 열의 값에 자연 정렬 순서가 없는 또는 자연 순서를 정렬 하는 경우 적합 하지 않습니다. 이 경우 자동 정렬을 사용할 수 없지만 사용자가 열 머리글을 클릭 하 여 정렬 하려면 않으려고 할 수 있습니다. 이 오버 로드에 대 한 처리기를 호출할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> 선택에 대 한 열 헤더를 사용 하지 않는 경우에 이벤트입니다.  
  
> [!NOTE]
>  `Sort(IComparer)` 메서드 오버 로드는 경우에만 작동 합니다 <xref:System.Windows.Forms.DataGridView> 외부 데이터 원본에 바인딩되어 있지 않은 하며 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 값이 `false`. 외부 데이터 원본에 바인딩된 열에 대 한 정렬 작업을 사용자 지정 하려면 데이터 원본에서 제공 하는 정렬 작업을 사용 해야 합니다. 가상 모드에 바인딩되지 않은 열에 대 한 고유한 정렬 작업을 제공 해야 합니다.  
  
 사용 하 여 `Sort(IComparer)` 메서드 오버 로드를 구현 하는 고유한 클래스를 만들어야 합니다를 <xref:System.Collections.IComparer> 인터페이스. 이 인터페이스를 구현할 클래스를 사용 하려면를 <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> 는 메서드를 <xref:System.Windows.Forms.DataGridView> 전달 <xref:System.Windows.Forms.DataGridViewRow> 개체를 입력 하는 경우는 `Sort(IComparer)` 메서드 오버 로드가 호출 됩니다. 이 사용 하 여 모든 열에 값을 기반으로 올바른 행 정렬 순서를 계산할 수 있습니다.  
  
 `Sort(IComparer)` 메서드 오버 로드를 설정 하지 않습니다는 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> 및 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 속성을 설정 해야 합니다 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> 정렬 문자를 표시 하는 속성입니다.  
  
 대 안으로 합니다 `Sort(IComparer)` 메서드 오버 로드에 대 한 처리기를 구현 하 여 사용자 지정 정렬을 제공할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트입니다. 이 이벤트는 사용자가 자동 정렬 또는 호출 하는 경우에 대해 구성 된 열의 머리글을 클릭할 때 발생 합니다 `Sort(DataGridViewColumn,ListSortDirection)` 오버 로드는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드. 올바른 순서를 계산할 수 있도록 컨트롤에서 행의 각 쌍에 대 한 이벤트가 발생 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.SortCompare> 이벤트가 발생 하지 않습니다 경우는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성이 설정 되어 때나 합니다 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성 값이 `true`.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Windows Forms DataGridView 컨트롤의 데이터 정렬](sorting-data-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 열 정렬 모드 설정](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
