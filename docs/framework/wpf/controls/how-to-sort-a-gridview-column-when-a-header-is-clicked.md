---
title: '방법: 머리글 클릭 시 GridView 열 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], GridView
- controls [WPF], ListView
- ListView controls [WPF], sorting GridView columns
- GridView controls [WPF], ListView control
ms.assetid: 4865d720-d147-40ed-83a7-af7587f8aad8
ms.openlocfilehash: 3438ab91045a144a7fa1d531e9d7d55ad30e89ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052029"
---
# <a name="how-to-sort-a-gridview-column-when-a-header-is-clicked"></a><span data-ttu-id="d0a70-102">방법: 머리글 클릭 시 GridView 열 정렬</span><span class="sxs-lookup"><span data-stu-id="d0a70-102">How to: Sort a GridView Column When a Header Is Clicked</span></span>

<span data-ttu-id="d0a70-103">만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ListView> 구현 하는 컨트롤을 <xref:System.Windows.Controls.GridView> 모드 및 사용자가 열 머리글을 클릭할 때 데이터 콘텐츠 정렬 보기.</span><span class="sxs-lookup"><span data-stu-id="d0a70-103">This example shows how to create a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView> view mode and sorts the data content when a user clicks a column header.</span></span>

## <a name="example"></a><span data-ttu-id="d0a70-104">예제</span><span class="sxs-lookup"><span data-stu-id="d0a70-104">Example</span></span>

<span data-ttu-id="d0a70-105">다음 예제에서는 정의 <xref:System.Windows.Controls.GridView> 바인딩되는 세 개의 열으로는 <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, 및 <xref:System.DateTime.Day%2A>의 속성을 <xref:System.DateTime> 구조.</span><span class="sxs-lookup"><span data-stu-id="d0a70-105">The following example defines a <xref:System.Windows.Controls.GridView> with three columns that bind to the <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, and <xref:System.DateTime.Day%2A>, properties of the <xref:System.DateTime> structure.</span></span>

```xaml
<GridView>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Year}"
                  Header="Year"
                  Width="100"/>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Month}"
                  Header="Month"
                  Width="100"/>
  <GridViewColumn DisplayMemberBinding="{Binding Path=Day}"
                  Header="Day"
                  Width="100"/>
</GridView>
```

<span data-ttu-id="d0a70-106">다음 예제에서는으로 정의 된 데이터 항목을 <xref:System.Collections.ArrayList> 의 <xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-106">The following example shows the data items that are defined as an <xref:System.Collections.ArrayList> of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="d0a70-107"><xref:System.Collections.ArrayList> 으로 정의 됩니다 합니다 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 에 대 한는 <xref:System.Windows.Controls.ListView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-107">The <xref:System.Collections.ArrayList> is defined as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> control.</span></span>

```xaml
<ListView.ItemsSource>
  <s:ArrayList>
    <p:DateTime>1993/1/1 12:22:02</p:DateTime>
    <p:DateTime>1993/1/2 13:2:01</p:DateTime>
    <p:DateTime>1997/1/3 2:1:6</p:DateTime>
    <p:DateTime>1997/1/4 13:6:55</p:DateTime>
    <p:DateTime>1999/2/1 12:22:02</p:DateTime>
    <p:DateTime>1998/2/2 13:2:01</p:DateTime>
    <p:DateTime>2000/2/3 2:1:6</p:DateTime>
    <p:DateTime>2002/2/4 13:6:55</p:DateTime>
    <p:DateTime>2001/3/1 12:22:02</p:DateTime>
    <p:DateTime>2006/3/2 13:2:01</p:DateTime>
    <p:DateTime>2004/3/3 2:1:6</p:DateTime>
    <p:DateTime>2004/3/4 13:6:55</p:DateTime>
  </s:ArrayList>
</ListView.ItemsSource>
```

<span data-ttu-id="d0a70-108">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그의 `s` 및 `p` 식별자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 메타데이터에 정의된 네임스페이스 매핑을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-108">The `s` and `p` identifiers in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] tags refer to namespace mappings that are defined in the metadata of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="d0a70-109">다음 예제에서는 이 메타데이터 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-109">The following example shows the metadata definition.</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="ListViewSort.Window1"
    xmlns:s="clr-namespace:System.Collections;assembly=mscorlib"
    xmlns:p="clr-namespace:System;assembly=mscorlib">
```

<span data-ttu-id="d0a70-110">예제에서는 열 콘텐츠에 따라 데이터를 정렬 하려면 처리할 이벤트 처리기를 정의 합니다 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 열 헤더 단추를 누를 때 발생 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-110">To sort the data according to the contents of a column, the example defines an event handler to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event that occurs when you press the column header button.</span></span> <span data-ttu-id="d0a70-111">다음 예제에 대 한 이벤트 처리기를 지정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.GridViewColumnHeader> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-111">The following example shows how to specify an event handler for the <xref:System.Windows.Controls.GridViewColumnHeader> control.</span></span>

```xaml
<ListView x:Name='lv' Height="150" HorizontalAlignment="Center"
  VerticalAlignment="Center"
  GridViewColumnHeader.Click="GridViewColumnHeaderClickedHandler"
 >
```

<span data-ttu-id="d0a70-112">다음 예제에서는 열 머리글 단추를 누를 때마다 정렬 방향을 오름차순과 내림차순으로 번갈아 변경하도록 이벤트 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-112">The example defines the event handler so that the sort direction changes between ascending order and descending order each time you press the column header button.</span></span> <span data-ttu-id="d0a70-113">다음 예제에서는 이벤트 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-113">The following example shows the event handler.</span></span>

```csharp
public partial class Window1 : Window
{
    public Window1()
    {
        InitializeComponent();
    }

    GridViewColumnHeader _lastHeaderClicked = null;
    ListSortDirection _lastDirection = ListSortDirection.Ascending;

    void GridViewColumnHeaderClickedHandler(object sender,
                                            RoutedEventArgs e)
    {
        var headerClicked = e.OriginalSource as GridViewColumnHeader;
        ListSortDirection direction;

        if (headerClicked != null)
        {
            if (headerClicked.Role != GridViewColumnHeaderRole.Padding)
            {
                if (headerClicked != _lastHeaderClicked)
                {
                    direction = ListSortDirection.Ascending;
                }
                else
                {
                    if (_lastDirection == ListSortDirection.Ascending)
                    {
                        direction = ListSortDirection.Descending;
                    }
                    else
                    {
                        direction = ListSortDirection.Ascending;
                    }
                }

                var columnBinding = headerClicked.Column.DisplayMemberBinding as Binding;
                var sortBy = columnBinding?.Path.Path ?? headerClicked.Column.Header as string;

                Sort(sortBy, direction);

                if (direction == ListSortDirection.Ascending)
                {
                    headerClicked.Column.HeaderTemplate =
                      Resources["HeaderTemplateArrowUp"] as DataTemplate;
                }
                else
                {
                    headerClicked.Column.HeaderTemplate =
                      Resources["HeaderTemplateArrowDown"] as DataTemplate;
                }

                // Remove arrow from previously sorted header
                if (_lastHeaderClicked != null && _lastHeaderClicked != headerClicked)
                {
                    _lastHeaderClicked.Column.HeaderTemplate = null;
                }

                _lastHeaderClicked = headerClicked;
                _lastDirection = direction;
            }
        }
    }
}
```

```vb
Partial Public Class Window1
    Inherits Window
    Public Sub New()
        InitializeComponent()
    End Sub

    Private _lastHeaderClicked As GridViewColumnHeader = Nothing
    Private _lastDirection As ListSortDirection = ListSortDirection.Ascending

    Private Sub GridViewColumnHeaderClickedHandler(ByVal sender As Object, ByVal e As RoutedEventArgs)
        Dim headerClicked = TryCast(e.OriginalSource, GridViewColumnHeader)
        Dim direction As ListSortDirection

        If headerClicked IsNot Nothing Then
            If headerClicked.Role <> GridViewColumnHeaderRole.Padding Then
                If headerClicked IsNot _lastHeaderClicked Then
                    direction = ListSortDirection.Ascending
                Else
                    If _lastDirection = ListSortDirection.Ascending Then
                        direction = ListSortDirection.Descending
                    Else
                        direction = ListSortDirection.Ascending
                    End If
                End If

                Dim columnBinding = TryCast(headerClicked.Column.DisplayMemberBinding, Binding)
                Dim sortBy = If(columnBinding?.Path.Path, TryCast(headerClicked.Column.Header, String))

                Sort(sortBy, direction)

                If direction = ListSortDirection.Ascending Then
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowUp"), DataTemplate)
                Else
                    headerClicked.Column.HeaderTemplate = TryCast(Resources("HeaderTemplateArrowDown"), DataTemplate)
                End If

                ' Remove arrow from previously sorted header
                If _lastHeaderClicked IsNot Nothing AndAlso _lastHeaderClicked IsNot headerClicked Then
                    _lastHeaderClicked.Column.HeaderTemplate = Nothing
                End If

                _lastHeaderClicked = headerClicked
                _lastDirection = direction
            End If
        End If
    End Sub
End Class
```

<span data-ttu-id="d0a70-114">다음 예제에서는 데이터를 정렬하기 위해 이벤트 처리기가 호출하는 정렬 알고리즘을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-114">The following example shows the sorting algorithm that is called by the event handler to sort the data.</span></span> <span data-ttu-id="d0a70-115">새 정렬을 수행 <xref:System.ComponentModel.SortDescription> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d0a70-115">The sort is performed by creating a new <xref:System.ComponentModel.SortDescription> structure.</span></span>

```csharp
private void Sort(string sortBy, ListSortDirection direction)
{
    ICollectionView dataView =
      CollectionViewSource.GetDefaultView(lv.ItemsSource);

    dataView.SortDescriptions.Clear();
    SortDescription sd = new SortDescription(sortBy, direction);
    dataView.SortDescriptions.Add(sd);
    dataView.Refresh();
}
```

```vb
Private Sub Sort(ByVal sortBy As String, ByVal direction As ListSortDirection)
    Dim dataView As ICollectionView = CollectionViewSource.GetDefaultView(lv.ItemsSource)

    dataView.SortDescriptions.Clear()
    Dim sd As New SortDescription(sortBy, direction)
    dataView.SortDescriptions.Add(sd)
    dataView.Refresh()
End Sub
```

## <a name="see-also"></a><span data-ttu-id="d0a70-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0a70-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="d0a70-117">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="d0a70-117">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="d0a70-118">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="d0a70-118">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="d0a70-119">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d0a70-119">How-to Topics</span></span>](listview-how-to-topics.md)
