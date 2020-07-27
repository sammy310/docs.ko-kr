---
title: '방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링'
description: 뷰에서 데이터 그룹화, 정렬 및 필터링을 지 원하는 CollectionView에 Windows Presentation Foundation DataGrid 컨트롤을 바인딩하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 072e5a104a91faa40bb54f2a3fc4ed6188e1112e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167665"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>방법: DataGrid 컨트롤에서 데이터 그룹화, 정렬 및 필터링

<xref:System.Windows.Controls.DataGrid>데이터를 그룹화, 정렬 및 필터링 하 여 다양 한 방법으로의 데이터를 보는 것이 유용한 경우가 많습니다. 에서 데이터를 그룹화, 정렬 및 필터링 하려면 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Data.CollectionView> 이러한 함수를 지 원하는에 바인딩합니다. 그런 다음 <xref:System.Windows.Data.CollectionView> 기본 원본 데이터에 영향을 주지 않고의 데이터를 사용할 수 있습니다. 컬렉션 뷰의 변경 내용은 <xref:System.Windows.Controls.DataGrid> UI (사용자 인터페이스)에 반영 됩니다.

<xref:System.Windows.Data.CollectionView>클래스는 인터페이스를 구현 하는 데이터 소스에 대 한 그룹화 및 정렬 기능을 제공 합니다 <xref:System.Collections.IEnumerable> . <xref:System.Windows.Data.CollectionViewSource>클래스를 사용 하면 XAML에서의 속성을 설정할 수 있습니다 <xref:System.Windows.Data.CollectionView> .

이 예제에서는 개체의 컬렉션을에 `Task` 바인딩합니다 <xref:System.Windows.Data.CollectionViewSource> . 는의 <xref:System.Windows.Data.CollectionViewSource> 로 사용 됩니다 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.DataGrid> . 그룹화, 정렬 및 필터링은에서 수행 되며 <xref:System.Windows.Data.CollectionViewSource> UI에 표시 됩니다 <xref:System.Windows.Controls.DataGrid> .

![DataGrid의 그룹화 된 데이터](././media/wpf-datagridgroups.png "WPF_DataGridGroups") DataGrid의 그룹화 된 데이터

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>System.windows.controls.itemscontrol.itemssource로 CollectionViewSource 사용

컨트롤에서 데이터를 그룹화, 정렬 및 필터링 하려면 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Data.CollectionView> 이러한 함수를 지 원하는에 바인딩합니다. 이 예제에서는 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Data.CollectionViewSource> 개체의에 대해 이러한 함수를 제공 하는에 <xref:System.Collections.Generic.List%601> 바인딩됩니다 `Task` .

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>CollectionViewSource에 DataGrid를 바인딩하려면

1. 인터페이스를 구현 하는 데이터 컬렉션을 만듭니다 <xref:System.Collections.IEnumerable> .

    <xref:System.Collections.Generic.List%601>를 사용 하 여 컬렉션을 만드는 경우의 인스턴스를 인스턴스화하는 대신에서 상속 하는 새 클래스를 만들어야 합니다 <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.List%601> . 이렇게 하면 XAML에서 컬렉션에 데이터 바인딩할 수 있습니다.

    > [!NOTE]
    > 컬렉션의 개체는 <xref:System.ComponentModel.INotifyPropertyChanged> <xref:System.ComponentModel.IEditableObject> 가 <xref:System.Windows.Controls.DataGrid> 속성 변경 및 편집에 올바르게 응답 하기 위해 변경 된 인터페이스와 인터페이스를 구현 해야 합니다. 자세한 내용은 [속성 변경 알림 구현](../data/how-to-implement-property-change-notification.md)을 참조하세요.

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. XAML에서 컬렉션 클래스의 인스턴스를 만들고 [X:Key 지시어](../../../desktop-wpf/xaml-services/xkey-directive.md)를 설정 합니다.

3. XAML에서 클래스의 인스턴스를 만들고, <xref:System.Windows.Data.CollectionViewSource> [x:Key 지시문](../../../desktop-wpf/xaml-services/xkey-directive.md)을 설정 하 고, 컬렉션 클래스의 인스턴스를로 설정 <xref:System.Windows.Data.CollectionViewSource.Source%2A> 합니다.

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. 클래스의 인스턴스를 만들고 <xref:System.Windows.Controls.DataGrid> 속성을로 설정 합니다 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Data.CollectionViewSource> .

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. 코드에서에 액세스 하려면 메서드를 사용 하 여에 대 한 <xref:System.Windows.Data.CollectionViewSource> <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 참조를 가져옵니다 <xref:System.Windows.Data.CollectionViewSource> .

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>DataGrid에서 항목 그룹화

에서 항목을 그룹화 하는 방법을 지정 하려면 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Data.PropertyGroupDescription> 형식을 사용 하 여 원본 뷰의 항목을 그룹화 합니다.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>XAML을 사용 하 여 DataGrid에서 항목을 그룹화 하려면

1. <xref:System.Windows.Data.PropertyGroupDescription>그룹화 할 속성을 지정 하는을 만듭니다. XAML 또는 코드에서 속성을 지정할 수 있습니다.

   1. XAML에서을 <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> 그룹화 할 속성의 이름으로 설정 합니다.

   2. 코드에서 그룹화 할 속성의 이름을 생성자에 전달 합니다.

2. 를 <xref:System.Windows.Data.PropertyGroupDescription> 컬렉션에 추가 합니다 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> .

3. 컬렉션에의 추가 인스턴스 <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> 를 추가 하 여 그룹화 수준을 더 추가 합니다.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. 그룹을 제거 하려면 <xref:System.Windows.Data.PropertyGroupDescription> 컬렉션에서을 제거 합니다 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> .

5. 모든 그룹을 제거 하려면 <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> 컬렉션의 메서드를 호출 합니다 <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> .

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

에서 항목이 그룹화 되 면 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Controls.GroupStyle> 각 그룹의 모양을 지정 하는를 정의할 수 있습니다. 를 <xref:System.Windows.Controls.GroupStyle> DataGrid의 컬렉션에 추가 하 여 적용 합니다 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> . 그룹화 수준이 여러 개인 경우 각 그룹 수준에 다른 스타일을 적용할 수 있습니다. 스타일은 정의 된 순서 대로 적용 됩니다. 예를 들어 두 스타일을 정의 하는 경우 첫 번째이 최상위 행 그룹에 적용 됩니다. 두 번째 스타일은 두 번째 수준 이하의 모든 행 그룹에 적용 됩니다. <xref:System.Windows.FrameworkElement.DataContext%2A>의는 <xref:System.Windows.Controls.GroupStyle> <xref:System.Windows.Data.CollectionViewGroup> 그룹이 나타내는입니다.

### <a name="to-change-the-appearance-of-row-group-headers"></a>행 그룹 머리글의 모양을 변경 하려면

1. <xref:System.Windows.Controls.GroupStyle>행 그룹의 모양을 정의 하는을 만듭니다.

2. 태그 안에를 추가 합니다 <xref:System.Windows.Controls.GroupStyle> `<DataGrid.GroupStyle>` .

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>DataGrid에서 항목 정렬

에서 항목을 정렬 하는 방법을 지정 하려면 <xref:System.Windows.Controls.DataGrid> 형식을 사용 하 여 <xref:System.ComponentModel.SortDescription> 소스 뷰의 항목을 정렬 합니다.

### <a name="to-sort-items-in-a-datagrid"></a>DataGrid에서 항목을 정렬 하려면

1. <xref:System.ComponentModel.SortDescription>정렬할 속성을 지정 하는을 만듭니다. XAML 또는 코드에서 속성을 지정할 수 있습니다.

    1. XAML에서을 <xref:System.ComponentModel.SortDescription.PropertyName%2A> 정렬할 속성의 이름으로 설정 합니다.

    2. 코드에서 정렬할 속성의 이름을 및 <xref:System.ComponentModel.ListSortDirection> 생성자에 전달 합니다.

2. 를 <xref:System.ComponentModel.SortDescription> 컬렉션에 추가 합니다 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> .

3. 추가 속성을 기준으로 정렬 하려면의 인스턴스를 <xref:System.ComponentModel.SortDescription> 컬렉션에 추가 <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> 합니다.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>DataGrid에서 항목 필터링

을 사용 하 여에서 항목을 필터링 하려면 <xref:System.Windows.Controls.DataGrid> <xref:System.Windows.Data.CollectionViewSource> 이벤트에 대 한 처리기에서 필터링 논리를 제공 합니다 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> .

### <a name="to-filter-items-in-a-datagrid"></a>DataGrid에서 항목을 필터링 하려면

1. 이벤트에 대 한 처리기를 추가 <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> 합니다.

2. <xref:System.Windows.Data.CollectionViewSource.Filter>이벤트 처리기에서 필터링 논리를 정의 합니다.

    뷰를 새로 고칠 때마다 필터가 적용 됩니다.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

또는 <xref:System.Windows.Controls.DataGrid> 필터링 논리를 제공 하는 메서드를 만들고 <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> 필터를 적용 하도록 속성을 설정 하 여에서 항목을 필터링 할 수 있습니다. 이 메서드의 예를 보려면 [뷰에서 데이터 필터링](../data/how-to-filter-data-in-a-view.md)을 참조 하세요.

## <a name="example"></a>예제

다음 예에서는에서 데이터를 그룹화, 정렬 및 필터링 `Task` <xref:System.Windows.Data.CollectionViewSource> 하 고에서 그룹화, 정렬 및 필터링 된 데이터를 표시 하는 방법을 보여 줍니다 `Task` <xref:System.Windows.Controls.DataGrid> . 는의 <xref:System.Windows.Data.CollectionViewSource> 로 사용 됩니다 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.DataGrid> . 그룹화, 정렬 및 필터링은에서 수행 되며 <xref:System.Windows.Data.CollectionViewSource> UI에 표시 됩니다 <xref:System.Windows.Controls.DataGrid> .

이 예를 테스트 하려면 프로젝트 이름과 일치 하도록 DGGroupSortFilterExample 이름을 조정 해야 합니다. Visual Basic를 사용 하는 경우 클래스 이름을 다음과 같이 변경 해야 <xref:System.Windows.Window> 합니다.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>참고 항목

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [System.collections.objectmodel.observablecollection 만들기 및 바인딩](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [뷰에서 데이터 필터링](../data/how-to-filter-data-in-a-view.md)
- [뷰의 데이터 정렬](../data/how-to-sort-data-in-a-view.md)
- [XAML에서 뷰를 사용 하 여 데이터 정렬 및 그룹화](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
