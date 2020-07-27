---
title: DataGrid
description: DataGrid 컨트롤을 사용 하 여 데이터베이스, LINQ 쿼리 또는 기타 바인딩 가능한 데이터 소스와 같은 여러 소스의 데이터를 표시 하 고 편집 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 3db49c12fcb363ef7f99e5c69beae09ab05addcf
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168320"
---
# <a name="datagrid"></a>DataGrid
<xref:System.Windows.Controls.DataGrid>컨트롤을 사용 하면 SQL 데이터베이스, LINQ 쿼리 또는 기타 바인딩 가능한 데이터 소스 등 다양 한 소스의 데이터를 표시 하 고 편집할 수 있습니다. 자세한 내용은 [바인딩 소스 개요](../data/binding-sources-overview.md)를 참조 하세요.  
  
 열에는 텍스트, 컨트롤, 예: <xref:System.Windows.Controls.ComboBox> 이미지, 단추 또는 템플릿에 포함 된 콘텐츠와 같은 기타 WPF 콘텐츠가 표시 될 수 있습니다. 를 사용 하 여 <xref:System.Windows.Controls.DataGridTemplateColumn> 템플릿에 정의 된 데이터를 표시할 수 있습니다. 다음 표에서는 기본적으로 제공 되는 열 유형을 나열 합니다.  
  
|생성 된 열 유형|데이터 형식|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>셀 글꼴, 색 및 크기와 같은 모양으로 사용자 지정할 수 있습니다. <xref:System.Windows.Controls.DataGrid>는 다른 WPF 컨트롤의 모든 스타일 및 템플릿 기능을 지원 합니다. <xref:System.Windows.Controls.DataGrid>또한에는 편집, 정렬 및 유효성 검사를 위한 기본 및 사용자 지정 가능 동작이 포함 되어 있습니다.  
  
 다음 표에서는에 대 한 몇 가지 일반적인 작업과이 <xref:System.Windows.Controls.DataGrid> 를 수행 하는 방법을 보여 줍니다. 관련 API를 확인 하 여 추가 정보 및 샘플 코드를 찾을 수 있습니다.  
  
|시나리오|접근 방식|  
|--------------|--------------|  
|교대로 반복 되는 배경색|속성을 <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> 2 이상으로 설정한 다음 <xref:System.Windows.Media.Brush> 및 속성에를 할당 <xref:System.Windows.Controls.DataGrid.RowBackground%2A> <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> 합니다.|  
|셀 및 행 선택 동작 정의|<xref:System.Windows.Controls.DataGrid.SelectionMode%2A> 및 <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> 속성을 설정합니다.|  
|머리글, 셀 및 행의 시각적 모양 사용자 지정|<xref:System.Windows.Style>,, 또는 속성에 새를 적용 <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.CellStyle%2A> <xref:System.Windows.Controls.DataGrid.RowStyle%2A> 합니다.|  
|크기 조정 옵션 설정|,, <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> ,, <xref:System.Windows.FrameworkElement.MinHeight%2A> 또는 속성을 설정 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A> 합니다. 자세한 내용은 [DataGrid 컨트롤의 크기 조정 옵션](sizing-options-in-the-datagrid-control.md)을 참조 하세요.|  
|선택한 항목 액세스|속성을 선택 하 여 선택한 셀을 가져오고 속성을 선택 하 여 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> 선택 된 행을 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> 가져옵니다. 자세한 내용은 <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>을 참조하세요.|  
|최종 사용자의 상호 작용 사용자 지정|,, <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> ,, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> 및 속성을 설정 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> 합니다.|  
|자동 생성 된 열 취소 또는 변경|이벤트를 처리 <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> 합니다.|  
|열 고정|속성을 <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> 1로 설정 하 고 속성을 0으로 설정 하 여 가장 왼쪽의 위치로 열을 이동 합니다 <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> .|  
|XML 데이터를 데이터 원본으로 사용|의를 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.DataGrid> 항목 컬렉션을 나타내는 XPath 쿼리에 바인딩합니다. 에서 각 열을 만듭니다 <xref:System.Windows.Controls.DataGrid> . 바인딩의 XPath를 항목 소스의 속성을 가져오는 쿼리에 설정 하 여 각 열을 바인딩합니다. 예제를 보려면 <xref:System.Windows.Controls.DataGridTextColumn>를 참조하세요.|  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|Description|  
|-----------|-----------------|  
|[연습: DataGrid 컨트롤에서 SQL Server 데이터베이스의 데이터 표시](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|새 WPF 프로젝트를 설정 하 고, Entity Framework 요소를 추가 하 고, 소스를 설정 하 고, 데이터를 표시 하는 방법을 설명 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|[방법: DataGrid 컨트롤에 행 세부 정보 추가](how-to-add-row-details-to-a-datagrid-control.md)|에 대 한 행 세부 정보를 만드는 방법을 설명 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|[방법: DataGrid 컨트롤을 사용하여 유효성 검사 구현](how-to-implement-validation-with-the-datagrid-control.md)|셀 및 행에서 값의 유효성을 검사 하 <xref:System.Windows.Controls.DataGrid> 고 유효성 검사 피드백을 표시 하는 방법을 설명 합니다.|  
|[DataGrid 컨트롤에서의 기본 키보드 및 마우스 동작](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>키보드와 마우스를 사용 하 여 컨트롤과 상호 작용 하는 방법을 설명 합니다.|  
|[방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|<xref:System.Windows.Controls.DataGrid>데이터를 그룹화, 정렬 및 필터링 하 여 다른 방법으로의 데이터를 보는 방법에 대해 설명 합니다.|  
|[DataGrid 컨트롤의 크기 조정 옵션](sizing-options-in-the-datagrid-control.md)|에서 절대 및 자동 크기 조정을 제어 하는 방법을 설명 합니다 <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.DataGrid>
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](../data/data-templating-overview.md)
- [컨트롤](index.md)
- [WPF 콘텐츠 모델](wpf-content-model.md)
