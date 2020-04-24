---
title: DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: cdf4bfff8182b62d55f56b823c7ff129de4f9f1c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646125"
---
# <a name="datagrid"></a>DataGrid
이 <xref:System.Windows.Controls.DataGrid> 컨트롤을 사용하면 SQL 데이터베이스, LINQ 쿼리 또는 기타 바인딩 가능한 데이터 원본과 같은 다양한 소스의 데이터를 표시하고 편집할 수 있습니다. 자세한 내용은 [바인딩 소스 개요](../data/binding-sources-overview.md)를 참조하세요.  
  
 열은 텍스트, 컨트롤(예: <xref:System.Windows.Controls.ComboBox>의 컨트롤) 또는 이미지, 단추 또는 템플릿에 포함된 모든 콘텐츠와 같은 기타 WPF 콘텐츠를 표시할 수 있습니다. 를 <xref:System.Windows.Controls.DataGridTemplateColumn> 사용하여 템플릿에 정의된 데이터를 표시할 수 있습니다. 다음 표에는 기본적으로 제공되는 열 유형이 나열되어 있습니다.  
  
|생성된 열 유형|데이터 형식|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>셀 글꼴, 색상 및 크기와 같은 모양으로 사용자 정의 할 수 있습니다. <xref:System.Windows.Controls.DataGrid>은 다른 WPF 컨트롤의 모든 스타일 지정 및 템플릿 기능을 지원합니다. <xref:System.Windows.Controls.DataGrid>또한 편집, 정렬 및 유효성 검사를 위한 기본 및 사용자 지정 가능한 동작도 포함됩니다.  
  
 다음 표에는 몇 가지 일반적인 <xref:System.Windows.Controls.DataGrid> 작업과 이를 수행하는 방법을 나열합니다. 관련 API를 확인하여 자세한 정보와 샘플 코드를 찾을 수 있습니다.  
  
|시나리오|접근 방식|  
|--------------|--------------|  
|배경 색 교대|<xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> 속성을 2 이상으로 설정한 다음 <xref:System.Windows.Controls.DataGrid.RowBackground%2A> 및 <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> 속성에 a를 <xref:System.Windows.Media.Brush> 할당합니다.|  
|셀 및 행 선택 동작 정의|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 및 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 속성을 설정합니다.|  
|헤더, 셀 및 행의 시각적 모양 사용자 지정|<xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>에 <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> <xref:System.Windows.Style> <xref:System.Windows.Controls.DataGrid.CellStyle%2A>새 를 적용 <xref:System.Windows.Controls.DataGrid.RowStyle%2A> 합니다.|  
|크기 조정 옵션 설정|<xref:System.Windows.FrameworkElement.Height%2A>을 <xref:System.Windows.FrameworkElement.MaxHeight%2A>설정합니다. <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A> 자세한 내용은 [데이터 그리드 제어의 크기 조정 옵션을](sizing-options-in-the-datagrid-control.md)참조하십시오.|  
|선택한 항목에 액세스|<xref:System.Windows.Controls.DataGrid.SelectedCells%2A> 선택한 셀과 선택한 행을 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> 얻으려면 속성을 확인합니다. 자세한 내용은 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>를 참조하세요.|  
|최종 사용자 상호 작용 사용자 지정|<xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>을 <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>설정합니다. <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A>|  
|자동 생성된 열 취소 또는 변경|이벤트를 <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> 처리합니다.|  
|열 고정|<xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> 속성을 1로 설정하고 <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> 속성을 0으로 설정하여 열을 가장 왼쪽 위치로 이동합니다.|  
|XML 데이터를 데이터 원본으로 사용|<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 항목 컬렉션을 <xref:System.Windows.Controls.DataGrid> 나타내는 XPath 쿼리에 에 바인딩합니다. <xref:System.Windows.Controls.DataGrid>에서 각 열을 만듭니다. 항목 원본에서 속성을 가져오는 쿼리에 바인딩에 XPath를 설정하여 각 열을 바인딩합니다. 예제를 보려면 <xref:System.Windows.Controls.DataGridTextColumn>를 참조하세요.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|Description|  
|-----------|-----------------|  
|[연습: DataGrid 컨트롤에서 SQL Server 데이터베이스의 데이터 표시](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|새 WPF 프로젝트를 설정하고, 엔터티 프레임워크 요소를 추가하고, 소스를 설정하고, <xref:System.Windows.Controls.DataGrid>에 데이터를 표시하는 방법을 설명합니다.|  
|[방법: DataGrid 컨트롤에 행 세부 정보 추가](how-to-add-row-details-to-a-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>에 대한 행 세부 정보를 만드는 방법에 대해 설명합니다.|  
|[방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현](how-to-implement-validation-with-the-datagrid-control.md)|셀 및 행의 <xref:System.Windows.Controls.DataGrid> 값 유효성을 검사하고 유효성 검사 피드백을 표시하는 방법을 설명합니다.|  
|[DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|키보드와 마우스를 <xref:System.Windows.Controls.DataGrid> 사용하여 컨트롤과 상호 작용하는 방법을 설명합니다.|  
|[방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|데이터를 그룹화, 정렬 <xref:System.Windows.Controls.DataGrid> 및 필터링하여 다양한 방법으로 데이터를 보는 방법을 설명합니다.|  
|[DataGrid 컨트롤의 크기 조정 옵션](sizing-options-in-the-datagrid-control.md)|에서 절대 및 자동 크기 조정을 <xref:System.Windows.Controls.DataGrid>제어하는 방법에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.DataGrid>
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [컨트롤](index.md)
- [WPF 콘텐츠 모델](wpf-content-model.md)
