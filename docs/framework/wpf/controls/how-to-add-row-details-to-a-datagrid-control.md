---
title: '방법: DataGrid 컨트롤에 행 세부 정보 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559679"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>방법: DataGrid 컨트롤에 행 세부 정보 추가
<xref:System.Windows.Controls.DataGrid> 컨트롤을 사용 하는 경우 행 세부 정보 섹션을 추가 하 여 데이터 표시를 사용자 지정할 수 있습니다. 행 세부 정보 섹션을 추가 하는 필요에 따라 표시 또는 축소 하는 서식 파일의 일부 데이터를 그룹화 할 수 있습니다. 예를 들어 <xref:System.Windows.Controls.DataGrid>의 각 행에 대 한 데이터 요약만 표시 하 고 사용자가 행을 선택할 때 더 많은 데이터 필드를 표시 하는 <xref:System.Windows.Controls.DataGrid>에 행 세부 정보를 추가할 수 있습니다. <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성에서 행 세부 정보 섹션의 템플릿을 정의 합니다. 다음 그림에서는 행 세부 정보 섹션의 예를 보여 줍니다.  
  
 ![행 세부 정보가 표시 된 DataGrid](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 리소스 또는 인라인으로 XAML로 행 세부 정보 템플릿을 정의 합니다. 다음 절차에서는 두 가지 방법을 모두 보여 줍니다. 리소스로 추가 되는 데이터 템플릿은 다시 서식 파일을 만들지 않고 프로젝트 전체에서 사용할 수 있습니다. 인라인 XAML 컨트롤에서 액세스할 수만 정의 된 대로 추가 되는 데이터 템플릿.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>인라인 XAML을 사용 하 여 행 세부 정보를 표시 하려면  
  
1. 데이터 원본의 데이터를 표시 하는 <xref:System.Windows.Controls.DataGrid>을 만듭니다.  
  
2. <xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 요소를 추가합니다.  
  
3. 행 세부 정보 섹션의 모양을 정의 하는 <xref:System.Windows.DataTemplate>을 만듭니다.  
  
     다음 XAML은 <xref:System.Windows.Controls.DataGrid> 및 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 인라인을 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.DataGrid>는 각 행에 3 개의 값을 표시 하 고 행을 선택 하면 3 개의 값을 더 합니다.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     다음 코드는 <xref:System.Windows.Controls.DataGrid>에 표시 되는 데이터를 선택 하는 데 사용 되는 쿼리를 보여 줍니다. 이 예제에서 쿼리는 고객 정보를 포함 하는 엔터티에서 데이터를 선택 합니다.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>리소스를 사용 하 여 행 세부 정보를 표시 하려면  
  
1. 데이터 원본의 데이터를 표시 하는 <xref:System.Windows.Controls.DataGrid>을 만듭니다.  
  
2. <xref:System.Windows.Window> 컨트롤 또는 <xref:System.Windows.Controls.Page> 컨트롤과 같은 루트 요소에 <xref:System.Windows.FrameworkElement.Resources%2A> 요소를 추가 하거나, 응용 프로그램 또는 응용 프로그램 .xaml 파일의 <xref:System.Windows.Application> 클래스에 <xref:System.Windows.Application.Resources%2A> 요소를 추가 합니다.  
  
3. Resources 요소에서 행 세부 정보 섹션의 모양을 정의 하는 <xref:System.Windows.DataTemplate>을 만듭니다.  
  
     다음 XAML은 <xref:System.Windows.Application> 클래스에 정의 된 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>를 보여 줍니다.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <xref:System.Windows.DataTemplate>에서 [X:Key 지시어](../../../desktop-wpf/xaml-services/xkey-directive.md) 를 데이터 템플릿을 고유 하 게 식별 하는 값으로 설정 합니다.  
  
5. <xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 이전 단계에서 정의한 리소스로 설정 합니다. 리소스를 정적 리소스로 할당 합니다.  
  
     다음 XAML에서는 이전 예제의 리소스로 설정 된 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 보여 줍니다.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>행 세부 정보에 대 한 표시 여부를 설정 하 고 가로 스크롤을 방지 하려면  
  
1. 필요한 경우 <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> 속성을 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> 값으로 설정 합니다.  
  
     기본적으로 이 값은 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>로 설정되어 있습니다. 모든 행 또는 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>에 대 한 세부 정보를 표시 하는 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> 설정 하 여 모든 행에 대 한 세부 정보를 숨길 수 있습니다.  
  
2. 필요한 경우 <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> 속성을 `true`으로 설정 하 여 행 세부 정보 섹션의 가로 스크롤을 방지 합니다.
