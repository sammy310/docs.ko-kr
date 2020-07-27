---
title: DataGrid 컨트롤의 크기 조정 옵션
description: Windows Presentation Foundation DataGrid 컨트롤의 개별 행과 열을 해당 내용 또는 특정 값으로 크기를 설정 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164746"
---
# <a name="sizing-options-in-the-datagrid-control"></a>DataGrid 컨트롤의 크기 조정 옵션
크기 자체의 크기를 제어 하는 데 다양 한 옵션을 사용할 수 있습니다 <xref:System.Windows.Controls.DataGrid> . 의 <xref:System.Windows.Controls.DataGrid> , 및 개별 행과 열은 <xref:System.Windows.Controls.DataGrid> 내용에 맞게 자동으로 크기를 설정 하거나 특정 값으로 설정할 수 있습니다. 기본적으로는 <xref:System.Windows.Controls.DataGrid> 내용의 크기에 맞게 확장 되 고 축소 됩니다.  
  
## <a name="sizing-the-datagrid"></a>DataGrid 크기 조정  
  
### <a name="cautions-when-using-automatic-sizing"></a>자동 크기 조정을 사용 하는 경우 주의 사항  
 기본적으로 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> 의 및 속성은 <xref:System.Windows.Controls.DataGrid> <xref:System.Double.NaN?displayProperty=nameWithType> (XAML의 경우)로 설정 되 `Auto` 고는 해당 <xref:System.Windows.Controls.DataGrid> 콘텐츠 크기에 맞게 조정 됩니다.  
  
 또는와 같은 자식 항목의 크기를 제한 하지 않는 컨테이너 내부에 배치 되 면 <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.StackPanel> 는 <xref:System.Windows.Controls.DataGrid> 컨테이너의 표시 범위를 벗어나 확장 되 고 스크롤 막대는 표시 되지 않습니다. 이 조건에는 유용성 및 성능에 영향을 미칩니다.  
  
 데이터 집합에 바인딩되는 경우 <xref:System.Windows.FrameworkElement.Height%2A> 의 <xref:System.Windows.Controls.DataGrid> 이 제한 되지 않은 경우 바인딩된 데이터 집합의 각 데이터 항목에 대 한 행이 계속 추가 됩니다. 이렇게 하면 행이 <xref:System.Windows.Controls.DataGrid> 추가 될 때이 응용 프로그램의 표시 범위를 벗어날 수 있습니다. 는 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.FrameworkElement.Height%2A> 새 행에 맞게 계속 증가 하므로이 경우에 스크롤 막대를 표시 하지 않습니다.  
  
 의 각 행에 대해 개체가 만들어집니다 <xref:System.Windows.Controls.DataGrid> . 큰 데이터 집합으로 작업 하 고가 자동으로 크기를 자동으로 조정 하도록 허용 하는 경우 <xref:System.Windows.Controls.DataGrid> 많은 수의 개체를 만들면 응용 프로그램의 성능에 영향을 줄 수 있습니다.  
  
 대량 데이터 집합으로 작업할 때 이러한 문제를 방지 하려면의를 구체적으로 설정 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.DataGrid> 하거나와 같이를 제한 하는 컨테이너에 저장 하는 것이 좋습니다 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.Grid> . <xref:System.Windows.FrameworkElement.Height%2A>이 제한 되 면는 <xref:System.Windows.Controls.DataGrid> 지정 된 내에 맞는 행만 만들며 <xref:System.Windows.FrameworkElement.Height%2A> 새 데이터를 표시 하기 위해 필요에 따라 해당 행을 재생 합니다.  
  
### <a name="setting-the-datagrid-size"></a>DataGrid 크기 설정  
 는 <xref:System.Windows.Controls.DataGrid> 지정 된 경계 내에서 자동으로 크기를 조정 하도록 설정 하거나 <xref:System.Windows.Controls.DataGrid> 특정 크기로 설정할 수 있습니다. 다음 표에서는 크기를 제어 하기 위해 설정할 수 있는 속성을 보여 줍니다 <xref:System.Windows.Controls.DataGrid> .  
  
|속성|Description|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|의 특정 높이를 설정 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|높이의 상한을 설정 합니다 <xref:System.Windows.Controls.DataGrid> . 가 <xref:System.Windows.Controls.DataGrid> 이 높이에 도달할 때까지 세로로 증가 합니다.|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|높이의 하 한을 설정 합니다 <xref:System.Windows.Controls.DataGrid> . 는 <xref:System.Windows.Controls.DataGrid> 이 높이에 도달할 때까지 세로로 축소 됩니다.|  
|<xref:System.Windows.FrameworkElement.Width%2A>|의 특정 너비를 설정 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|의 너비에 대 한 상한을 설정 합니다 <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>이 너비에 도달할 때까지가 가로로 증가 합니다.|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|의 너비에 대 한 하 한을 설정 합니다 <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Controls.DataGrid>이 너비에 도달할 때까지 가로 방향으로 축소 됩니다.|  
  
## <a name="sizing-rows-and-row-headers"></a>행 및 행 머리글 크기 조정  
  
### <a name="datagrid-rows"></a>DataGrid 행  
 기본적으로 <xref:System.Windows.Controls.DataGrid> 행의 <xref:System.Windows.FrameworkElement.Height%2A> 속성은 <xref:System.Double.NaN?displayProperty=nameWithType> ( `Auto` XAML에서는 "")로 설정 되 고 행 높이는 해당 내용의 크기로 확장 됩니다. 속성을 설정 하 여에 있는 모든 행의 높이를 <xref:System.Windows.Controls.DataGrid> 지정할 수 있습니다 <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> . 사용자는 행 머리글 구분선을 끌어 행 높이를 변경할 수 있습니다.  
  
### <a name="datagrid-row-headers"></a>DataGrid 행 머리글  
 행 머리글을 표시 하려면 <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 속성을 또는로 설정 해야 <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> 합니다 <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> . 기본적으로 행 머리글이 표시 되 고 내용에 맞게 자동으로 크기가 조정 됩니다. 속성을 설정 하 여 행 머리글에 특정 너비를 지정할 수 있습니다 <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> .  
  
## <a name="sizing-columns-and-column-headers"></a>열 및 열 머리글 크기 조정  
  
### <a name="datagrid-columns"></a>DataGrid 열  
 는 <xref:System.Windows.Controls.DataGrid> 및 구조체의 값을 사용 하 여 <xref:System.Windows.Controls.DataGridLength> <xref:System.Windows.Controls.DataGridLengthUnitType> 절대 또는 자동 크기 조정 모드를 지정 합니다.  
  
 다음 표에서는 구조체에서 제공 하는 값을 보여 줍니다 <xref:System.Windows.Controls.DataGridLengthUnitType> .  
  
|Name|Description|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|기본 자동 크기 조정 모드는 <xref:System.Windows.Controls.DataGrid> 셀과 열 머리글의 내용에 따라 열 크기를 조정 합니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|셀 기반 자동 크기 모드를 크기 조정 <xref:System.Windows.Controls.DataGrid> 열 머리글을 포함 하지 않고 열에서 셀의 내용에 기반 합니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|머리글 기반 자동 크기 모드를 크기 조정 <xref:System.Windows.Controls.DataGrid> 열만 열 머리글의 내용에 기반 합니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|픽셀 기반 크기 조정 모드는 <xref:System.Windows.Controls.DataGrid> 제공 된 숫자 값을 기준으로 열 크기를 조정 합니다.|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|별 크기 조정 모드는 사용 가능한 공간을 가중치가 적용 된 비율로 배포 하는 데 사용 됩니다.<br /><br /> XAML에서 별모양 값은 n *로 표현 됩니다. 여기서 n은 숫자 값을 나타냅니다. 1 \* 은와 동일 \* 합니다. 예를 들어의 두 열 <xref:System.Windows.Controls.DataGrid> 너비가 및 2 인 경우 \* \* 첫 번째 열은 사용 가능한 공간의 한 부분을 받고 두 번째 열은 사용 가능한 공간의 두 부분을 받습니다.|  
  
 <xref:System.Windows.Controls.DataGridLengthConverter>클래스를 사용 하 여 숫자 또는 문자열 값과 값 사이에 데이터를 변환할 수 있습니다 <xref:System.Windows.Controls.DataGridLength> .  
  
 기본적으로 속성은 <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> 로 설정 되 <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> 고 <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> 속성은로 설정 됩니다 <xref:System.Windows.Controls.DataGridLength.Auto%2A> . 크기 조정 모드를 또는로 설정 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 하면 <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> 열이 가장 넓은 표시 되는 콘텐츠의 너비로 늘어납니다. 스크롤할 때 현재 열 크기 보다 큰 내용이 표시 되 면 이러한 크기 조정 모드에서 열이 확장 됩니다. 콘텐츠 보기에서 스크롤 된 후에 열 축소 되지 않습니다.  
  
 의 열을 <xref:System.Windows.Controls.DataGrid> 지정 된 경계 내 에서만 자동 크기 조정으로 설정 하거나 열을 특정 크기로 설정할 수도 있습니다. 다음 표에서는 열 크기를 제어 하기 위해 설정할 수 있는 속성을 보여 줍니다.  
  
|속성|Description|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|의 모든 열에 대 한 상한을 설정 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|개별 열에 대 한 상한을 설정 합니다. <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>을 재정의합니다.|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|의 모든 열에 대 한 하 한을 설정 <xref:System.Windows.Controls.DataGrid> 합니다.|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|개별 열에 대 한 하 한을 설정 합니다. <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>을 재정의합니다.|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|의 모든 열에 대해 특정 너비를 설정 합니다 <xref:System.Windows.Controls.DataGrid> .|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|개별 열에 대 한 특정 너비를 설정 합니다. <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>을 재정의합니다.|  
  
### <a name="datagrid-column-headers"></a>DataGrid 열 머리글  
 기본적으로 <xref:System.Windows.Controls.DataGrid> 열 머리글이 표시 됩니다. 열 머리글을 숨기려면 속성을 <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 또는로 설정 해야 합니다 <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> . 기본적으로 열 머리글이 표시 되 면 해당 콘텐츠에 맞게 자동으로 크기가 조정 됩니다. 열 머리글에는 속성을 설정 하 여 특정 높이를 지정할 수 있습니다 <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> .  
  
### <a name="resizing-with-the-mouse"></a>마우스로 크기 조정  
 사용자는 <xref:System.Windows.Controls.DataGrid> 행 또는 열 머리글 구분선을 끌어 행과 열의 크기를 조정할 수 있습니다. 에서는 <xref:System.Windows.Controls.DataGrid> 행 또는 열 머리글 구분선을 두 번 클릭 하 여 행과 열의 자동 크기 조정을 지원 합니다. 사용자가 특정 열의 크기를 조정 하지 않도록 하려면 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> `false` 개별 열에 대해 속성을로 설정 합니다. 사용자가 모든 열의 크기를 조정 하지 못하게 하려면 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 속성을로 설정 `false` 합니다. 사용자가 모든 행의 크기를 조정 하지 못하게 하려면 <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> 속성을로 설정 `false` 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>
