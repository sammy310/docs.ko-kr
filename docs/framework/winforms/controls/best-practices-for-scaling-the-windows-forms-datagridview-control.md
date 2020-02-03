---
title: DataGridView 컨트롤 크기 조정에 대 한 모범 사례
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744129"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Windows Forms DataGridView 컨트롤의 크기 조정에 대한 모범 사례

<xref:System.Windows.Forms.DataGridView> 컨트롤은 최대 확장성을 제공 하도록 설계 되었습니다. 대량의 데이터를 표시 해야 하는 경우이 항목에 설명 된 지침에 따라 많은 양의 메모리를 사용 하거나 UI (사용자 인터페이스)의 응답성을 저하 하지 않아야 합니다. 이 항목에서는 다음 문제에 대해 설명 합니다.

- 효율적으로 셀 스타일 사용

- 효율적으로 바로 가기 메뉴 사용

- 효율적으로 자동 크기 조정 사용

- 선택한 셀, 행 및 열 컬렉션을 효율적으로 사용

- 공유 행 사용

- 행 공유가 해제 되지 않도록 방지

특별 한 성능 요구 사항이 있는 경우 가상 모드를 구현 하 고 고유한 데이터 관리 작업을 제공할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 컨트롤의 데이터 표시 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)를 참조 하세요.

## <a name="using-cell-styles-efficiently"></a>효율적으로 셀 스타일 사용

각 셀, 행 및 열에는 고유한 스타일 정보가 있을 수 있습니다. 스타일 정보는 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체에 저장 됩니다. 많은 개별 <xref:System.Windows.Forms.DataGridView> 요소에 대 한 셀 스타일 개체를 만드는 작업은 특히 많은 양의 데이터로 작업 하는 경우 비효율적입니다. 성능에 영향을 주지 않으려면 다음 지침을 따르십시오.

- 개별 <xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewRow> 개체에 대해 셀 스타일 속성을 설정 하지 마십시오. 여기에는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성으로 지정 된 행 개체가 포함 됩니다. 행 템플릿에서 복제 되는 각 새 행은 템플릿의 셀 스타일 개체에 대 한 자체 복사본을 받습니다. 확장성을 최대화 하려면 <xref:System.Windows.Forms.DataGridView> 수준에서 셀 스타일 속성을 설정 합니다. 예를 들어 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 속성 대신 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성을 설정 합니다.

- 일부 셀에 기본 서식 지정 이외의 서식 지정이 필요한 경우에는 셀, 행 또는 열 그룹에서 동일한 <xref:System.Windows.Forms.DataGridViewCellStyle> 인스턴스를 사용 합니다. 개별 셀, 행 및 열에 <xref:System.Windows.Forms.DataGridViewCellStyle> 형식의 속성을 직접 설정 하지 마십시오. 셀 스타일 공유의 예제는 [방법: DataGridView 컨트롤 Windows Forms에 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조 하세요. <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트 처리기를 처리 하 여 셀 스타일을 개별적으로 설정 하는 경우 성능 저하를 방지할 수도 있습니다. 예제는 [방법: DataGridView 컨트롤 Windows Forms에서 데이터 형식 사용자 지정](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조 하세요.

- 셀의 스타일을 결정 하는 경우 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> 속성 대신 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> 속성을 사용 합니다. 속성이 아직 사용 되지 않은 경우 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> 속성에 액세스 하면 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 새 인스턴스가 만들어집니다. 또한 일부 스타일이 행, 열 또는 컨트롤에서 상속 되는 경우이 개체에 셀에 대 한 전체 스타일 정보가 포함 되지 않을 수 있습니다. 셀 스타일 상속에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)을 참조 하세요.

## <a name="using-shortcut-menus-efficiently"></a>효율적으로 바로 가기 메뉴 사용

각 셀, 행 및 열에는 자체 바로 가기 메뉴가 있을 수 있습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤의 바로 가기 메뉴는 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤로 표시 됩니다. 셀 스타일 개체와 마찬가지로 개별 <xref:System.Windows.Forms.DataGridView> 요소에 대 한 바로 가기 메뉴를 만들면 성능에 부정적인 영향을 미칠 수 있습니다. 이러한 페널티를 방지 하려면 다음 지침을 따르십시오.

- 개별 셀 및 행에 대 한 바로 가기 메뉴를 만들지 마십시오. 여기에는 새 행이 컨트롤에 추가 될 때 바로 가기 메뉴와 함께 복제 되는 행 템플릿이 포함 됩니다. 확장성을 최대화 하려면 컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성만 사용 하 여 전체 컨트롤에 대 한 바로 가기 메뉴를 하나 지정 합니다.

- 여러 행 또는 셀에 대 한 여러 바로 가기 메뉴가 필요한 경우 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 또는 <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> 이벤트를 처리 합니다. 이러한 이벤트를 사용 하면 바로 가기 메뉴 개체를 직접 관리 하 여 성능을 조정할 수 있습니다.

## <a name="using-automatic-resizing-efficiently"></a>효율적으로 자동 크기 조정 사용

셀 내용이 잘리지 않고 전체 셀 내용이 표시 되도록 셀 내용이 변경 되 면 행, 열 및 머리글의 크기가 자동으로 조정 될 수 있습니다. 크기 조정 모드를 변경 하면 행, 열 및 머리글의 크기도 조정 될 수 있습니다. 올바른 크기를 확인 하기 위해 <xref:System.Windows.Forms.DataGridView> 컨트롤은 수용할 각 셀의 값을 검사 해야 합니다. 큰 데이터 집합으로 작업 하는 경우 자동 크기 조정이 발생 하면이 분석을 통해 컨트롤의 성능에 부정적인 영향을 줄 수 있습니다. 성능 저하를 방지 하려면 다음 지침을 따르십시오.

- 행 집합이 많은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 자동 크기 조정을 사용 하지 않도록 합니다. 자동 크기 조정을 사용 하는 경우 표시 된 행에 따라 크기를 조정 합니다. 가상 모드 에서도 표시 된 행만 사용 합니다.

  - 행 및 열의 경우 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>및 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> 열거형의 `DisplayedCells` 또는 `DisplayedCellsExceptHeaders` 필드를 사용 합니다.

  - 행 머리글의 경우 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> 열거의 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> 또는 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> 필드를 사용 합니다.

- 최대 확장성을 위해 자동 크기 조정을 끄고 프로그래밍 방식 크기 조정을 사용 합니다.

자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](sizing-options-in-the-windows-forms-datagridview-control.md)을 참조 하세요.

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>선택한 셀, 행 및 열 컬렉션을 효율적으로 사용

<xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션은 많은 항목을 선택 하 여 효율적으로 수행 되지 않습니다. 일반적인 <xref:System.Windows.Forms.DataGridView> 컨트롤의 셀 보다 많은 행이 있고 행 보다 많은 열이 더 적으므로 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 및 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션은 비효율적 일 수도 있습니다. 이러한 컬렉션으로 작업할 때 성능 저하를 방지 하려면 다음 지침을 따르십시오.

- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 컬렉션의 내용에 액세스 하기 전에 <xref:System.Windows.Forms.DataGridView>의 모든 셀을 선택 했는지 여부를 확인 하려면 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> 메서드의 반환 값을 확인 합니다. 그러나이 메서드는 행을 공유 하지 않을 수 있습니다. 자세한 내용은 다음 단원을 참조하세요.

- <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType>의 <xref:System.Collections.ICollection.Count%2A> 속성을 사용 하 여 선택한 셀 수를 결정 하지 않습니다. 대신 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> 메서드를 사용 하 여 <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> 값을 전달 합니다. 마찬가지로, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> 메서드를 사용 하 여 선택한 행 및 열 컬렉션에 액세스 하는 대신 선택 된 요소의 수를 확인 합니다.

- 셀 기반 선택 모드를 사용 하지 않습니다. 대신 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>로 설정 합니다.

## <a name="using-shared-rows"></a>공유 행 사용

효율적인 메모리 사용은 공유 행을 통해 <xref:System.Windows.Forms.DataGridView> 제어에서 수행 됩니다. 행은 <xref:System.Windows.Forms.DataGridViewRow> 클래스의 인스턴스를 공유 하 여 가능한 한 모양과 동작에 대 한 정보를 최대한 공유 합니다.

행 인스턴스를 공유 하는 경우 메모리를 절약 하지만 행을 쉽게 공유 하지 않을 수 있습니다. 예를 들어 사용자가 셀과 직접 상호 작용할 때마다 해당 행은 공유 되지 않습니다. 이 항목의 지침은 피할 수 없기 때문에이 항목의 지침은 매우 많은 양의 데이터로 작업 하는 경우와 사용자가 프로그램을 실행할 때마다 상대적으로 적은 데이터 부분과 상호 작용 하는 경우에만 유용 합니다.

셀에 값이 포함 되어 있으면 바인딩되지 않은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 행을 공유할 수 없습니다. <xref:System.Windows.Forms.DataGridView> 컨트롤이 외부 데이터 소스에 바인딩되어 있거나 가상 모드를 구현 하 고 고유한 데이터 소스를 제공 하는 경우 셀 값은 셀 개체가 아닌 컨트롤 외부에 저장 되어 행을 공유할 수 있습니다.

행의 상태와 해당 셀이 포함 된 열의 상태에서 모든 셀의 상태를 확인할 수 있는 경우에만 행 개체를 공유할 수 있습니다. 행과 열의 상태에서 더 이상 추론할 수 없도록 셀의 상태를 변경 하는 경우 행을 공유할 수 없습니다.

예를 들어 다음과 같은 경우에는 행을 공유할 수 없습니다.

- 선택한 열에 없는 단일 셀이 행에 포함 되어 있습니다.

- 행에 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> 속성이 설정 된 셀이 포함 되어 있습니다.

- 행에 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> 속성이 설정 된 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 포함 되어 있습니다.

바인딩된 모드 또는 가상 모드에서는 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 및 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> 이벤트를 처리 하 여 개별 셀에 대 한 도구 설명 및 바로 가기 메뉴를 제공할 수 있습니다.

<xref:System.Windows.Forms.DataGridView> 컨트롤은 행이 <xref:System.Windows.Forms.DataGridViewRowCollection>에 추가 될 때마다 공유 행을 자동으로 사용 하려고 시도 합니다. 다음 지침을 사용 하 여 행을 공유 하는지 확인 합니다.

- <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 `Add(Object[])` 오버 로드와 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드에 대 한 `Insert(Object[])` 오버 로드를 호출 하지 마십시오. 이러한 오버 로드는 공유 되지 않은 행을 자동으로 만듭니다.

- 다음과 같은 경우에는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 속성에 지정 된 행을 공유할 수 있어야 합니다.

  - `Add()`를 호출 하거나 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 오버 로드 또는 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 컬렉션의 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 메서드에 대 한 `Insert(Int32,Int32)` 오버 로드를 `Add(Int32)` 합니다.

  - <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> 속성 값을 늘릴 때입니다.

  - <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> 속성을 설정 하는 경우

- <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> 컬렉션의 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>및 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 메서드를 호출할 때 `indexSource` 매개 변수로 표시 되는 행을 공유할 수 있어야 합니다.

- <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 메서드의 `Add(DataGridViewRow)` 오버 로드, <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> 메서드, <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> 메서드의 `Insert(Int32,DataGridViewRow)` 오버 로드 및 <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> 컬렉션의 <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 메서드를 호출할 때 지정 된 행을 공유할 수 있어야 합니다.

행이 공유 되는지 여부를 확인 하려면 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 메서드를 사용 하 여 행 개체를 검색 한 다음 개체의 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성을 확인 합니다. 공유 행의 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> 속성 값은 항상-1입니다.

## <a name="preventing-rows-from-becoming-unshared"></a>행 공유가 해제 되지 않도록 방지

코드 또는 사용자 동작의 결과로 공유 행을 공유 하지 않을 수 있습니다. 성능에 영향을 주지 않으려면 행의 공유가 해제 되지 않도록 해야 합니다. 응용 프로그램을 개발 하는 동안 <xref:System.Windows.Forms.DataGridView.RowUnshared> 이벤트를 처리 하 여 행을 공유 하지 않을 시기를 결정할 수 있습니다. 이는 행 공유 문제를 디버깅할 때 유용 합니다.

행 공유가 해제 되지 않도록 하려면 다음 지침을 따르십시오.

- <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션을 인덱싱하거나 `foreach` 루프를 사용 하 여이를 반복 하지 마세요. 일반적으로는 행에 직접 액세스할 필요가 없습니다. 행에 대해 작동 하는 <xref:System.Windows.Forms.DataGridView> 메서드는 행 인스턴스가 아닌 행 인덱스 인수를 사용 합니다. 또한 행 관련 이벤트에 대 한 처리기는 항목을 공유 하지 않고 행을 조작 하는 데 사용할 수 있는 행 속성이 있는 이벤트 인수 개체를 받습니다.

- 행 개체에 액세스 해야 하는 경우 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 메서드를 사용 하 여 행의 실제 인덱스를 전달 합니다. 그러나이 메서드를 통해 검색 된 공유 행 개체를 수정 하면이 개체를 공유 하는 모든 행이 수정 됩니다. 그러나 새 레코드의 행은 다른 행과 공유 되지 않으므로 다른 행을 수정할 때 영향을 받지 않습니다. 또한 공유 행으로 표시 되는 여러 행에는 다른 바로 가기 메뉴가 있을 수 있습니다. 공유 행 인스턴스에서 올바른 바로 가기 메뉴를 검색 하려면 <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> 메서드를 사용 하 여 행의 실제 인덱스를 전달 합니다. 공유 행의 <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> 속성에 액세스 하는 경우 공유 행 인덱스-1을 사용 하 고 올바른 바로 가기 메뉴를 검색 하지 않습니다.

- <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> 컬렉션을 인덱싱하지 마세요. 셀에 직접 액세스 하면 부모 행이 공유 되지 않게 되어 새 <xref:System.Windows.Forms.DataGridViewRow>을 인스턴스화합니다. 셀 관련 이벤트에 대 한 처리기는 행이 공유 되지 않게 하지 않고 셀을 조작 하는 데 사용할 수 있는 셀 속성이 있는 이벤트 인수 개체를 받습니다. <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> 속성을 사용 하 여 셀에 직접 액세스 하지 않고 현재 셀의 행 및 열 인덱스를 검색할 수도 있습니다.

- 셀 기반 선택 모드를 사용 하지 않습니다. 이러한 모드를 수행 하면 행이 공유 되지 않게 됩니다. 대신 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>로 설정 합니다.

- <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> 이벤트를 처리 하지 않습니다. 이러한 이벤트로 인해 행이 공유 되지 않게 됩니다. 또한 이러한 이벤트를 발생 시키는 <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> 메서드를 호출 하지 마십시오.

- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성 값이 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>또는 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>인 경우 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> 컬렉션에 액세스 하지 마세요. 이렇게 하면 선택한 모든 행이 공유 되지 않게 됩니다.

- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> 메서드를 호출 하지 마십시오. 이 메서드는 행을 공유 하지 않을 수 있습니다.

- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> 속성 값이 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>경우 <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> 메서드를 호출 하지 마십시오. 이렇게 하면 모든 행이 공유 되지 않게 됩니다.

- 열의 해당 속성이 `true`로 설정 된 경우 셀의 <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> 또는 <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> 속성을 `false`로 설정 하지 마십시오. 이렇게 하면 모든 행이 공유 되지 않게 됩니다.

- <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> 속성에 액세스 하지 마십시오. 이렇게 하면 모든 행이 공유 되지 않게 됩니다.

- <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드의 `Sort(IComparer)` 오버 로드를 호출 하지 마십시오. 사용자 지정 비교자를 사용 하 여 정렬 하면 모든 행이 공유 되지 않게 됩니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DataGridView>
- [Windows Forms DataGridView 컨트롤의 성능 조정](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 가상 모드](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](sizing-options-in-the-windows-forms-datagridview-control.md)
