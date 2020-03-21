---
title: GridView 개요
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181897"
---
# <a name="gridview-overview"></a>GridView 개요
<xref:System.Windows.Controls.GridView>뷰 모드는 <xref:System.Windows.Controls.ListView> 컨트롤의 뷰 모드 중 하나입니다. 클래스 <xref:System.Windows.Controls.GridView> 및 해당 지원 클래스를 사용하면 일반적으로 단추를 대화형 열 헤더로 사용하는 테이블에서 항목 컬렉션을 볼 수 있습니다. 이 항목에서는 <xref:System.Windows.Controls.GridView> 클래스를 소개하고 해당 클래스의 사용에 대해 간략하게 설명합니다.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>GridView 보기란?  
 뷰 <xref:System.Windows.Controls.GridView> 모드는 데이터 필드를 열에 바인딩하고 열 헤더를 표시하여 필드를 식별하여 데이터 항목 목록을 표시합니다. 기본 <xref:System.Windows.Controls.GridView> 스타일은 단추를 열 머리글로 구현합니다. 열 헤더에 단추를 사용하면 중요한 사용자 상호 작용 기능을 구현할 수 있습니다. 예를 들어 사용자는 열 헤더를 <xref:System.Windows.Controls.GridView> 클릭하여 특정 열의 내용에 따라 데이터를 정렬할 수 있습니다.  
  
> [!NOTE]
> 열 헤더에 <xref:System.Windows.Controls.GridView> 사용하는 단추 컨트롤은 에서 <xref:System.Windows.Controls.Primitives.ButtonBase>파생됩니다.  
  
 다음 그림에서는 <xref:System.Windows.Controls.GridView> 콘텐츠 <xref:System.Windows.Controls.ListView> 보기를 보여 주시겠습니다.  

 ![ListView 콘텐츠의 GridView 보기를 보여 주는 스크린샷입니다.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>열은 개체로 <xref:System.Windows.Controls.GridViewColumn> 표시되며, 이 항목은 해당 콘텐츠의 크기를 자동으로 조정할 수 있습니다. 선택적으로 특정 너비로 <xref:System.Windows.Controls.GridViewColumn> 명시적으로 설정할 수 있습니다. 열 헤더 사이에 위치 조정 막대를 끌어와 열의 크기를 조정할 수 있습니다. 이 기능이 에 기본 제공되므로 열을 동적으로 추가, 제거, <xref:System.Windows.Controls.GridView>바꾸기 및 순서를 다시 정렬할 수도 있습니다. 그러나 <xref:System.Windows.Controls.GridView> 표시되는 데이터를 직접 업데이트할 수는 없습니다.  
  
 다음 예제에서는 직원 데이터를 <xref:System.Windows.Controls.GridView> 표시하는 를 정의하는 방법을 보여 주며 있습니다. 이 예제에서는 <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>을 `EmployeeInfoDataSource` 으로 정의합니다. 콘텐츠를 데이터 범주에 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn> 바인딩하는 `EmployeeInfoDataSource` 속성 정의입니다.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림은 이전 예에서 만든 테이블을 보여줍니다. GridView 컨트롤은 ItemsSource 개체의 데이터를 표시합니다.

 ![GridView 출력이 있는 ListView를 보여 주는 스크린샷입니다.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>GridView 레이아웃 및 스타일  
 열 셀과 열 <xref:System.Windows.Controls.GridViewColumn> 머리글의 너비는 동일합니다. 기본적으로 각 열은 콘텐츠에 맞게 너비의 크기를 조정합니다. 선택적으로 열을 고정 너비로 설정할 수 있습니다.  
  
 관련 데이터 콘텐츠가 가로 행에 표시됩니다. 예를 들어, 이전 그림에서 각 직원의 성, 이름 및 ID 번호가 가로 행에 표시되므로 집합으로 표시됩니다.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>GridView에서 열 정의 및 스타일 지정  
 에 표시할 데이터 필드를 <xref:System.Windows.Controls.GridViewColumn>정의할 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>때 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>는 <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> " 또는 속성을 사용합니다. 속성은 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 템플릿 속성 중 하나보다 우선합니다.  
  
 열에서 콘텐츠의 맞춤을 지정 하는 <xref:System.Windows.Controls.GridView>, 정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>합니다. 사용 하지 마십시오는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성에 대 한 <xref:System.Windows.Controls.ListView> 사용 하 여 표시 되는 콘텐츠를 <xref:System.Windows.Controls.GridView>입니다.  
  
 열 머리글에 대한 템플릿 및 스타일 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn>속성을 <xref:System.Windows.Controls.GridViewColumnHeader> 지정하려면 에서 및 클래스를 사용합니다. 자세한 내용은 [GridView 열 헤더 스타일 및 템플릿 개요](gridview-column-header-styles-and-templates-overview.md)를 참조하세요.  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>GridView에 시각적 요소 추가  
 뷰 모드에 컨트롤과 <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.Button> 같은 시각적 요소를 추가하려면 템플릿 또는 스타일을 사용합니다. <xref:System.Windows.Controls.GridView>  
  
 시각적 요소를 데이터 항목으로 명시적으로 정의하는 경우 <xref:System.Windows.Controls.GridView>에 한 번만 나타날 수 있습니다. 요소에는 부모가 하나뿐일 수 있기 때문에 이 제한사항이 존재하고, 시각적 트리에 한 번만 표시될 수 있습니다.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>GridView의 행 스타일 지정  
 <xref:System.Windows.Controls.GridViewRowPresenter> 및 클래스를 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 사용하여 <xref:System.Windows.Controls.GridView>의 행의 서식을 지정하고 표시합니다. <xref:System.Windows.Controls.GridView> 뷰 모드에서 행에 스타일을 정하는 방법의 예는 [GridView를 구현하는 ListView에서 행 스타일 스타일을](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)참조하세요.  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>ItemContainerStyle을 사용할 때 맞춤 문제  
 열 머리글과 셀 간의 정렬 문제를 방지하려면 속성을 설정하거나 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>에서 항목의 너비에 영향을 주는 템플릿을 지정하지 마십시오. 예를 들어 속성을 설정하거나 <xref:System.Windows.FrameworkElement.Margin%2A> 컨트롤에 <xref:System.Windows.Controls.ControlTemplate> 정의된 <xref:System.Windows.Controls.CheckBox> a에 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> a를 추가하는 <xref:System.Windows.Controls.ListView> 지정을 하지 마십시오. 대신 뷰 모드를 정의하는 클래스에서 열 너비에 직접 <xref:System.Windows.Controls.GridView> 영향을 주는 속성 및 템플릿을 지정합니다.  
  
 예를 들어 뷰 <xref:System.Windows.Controls.CheckBox> 모드에서 행에 <xref:System.Windows.Controls.GridView> a를 추가하려면 <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.DataTemplate>에 를 추가한 다음 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 속성을 로 설정합니다. <xref:System.Windows.DataTemplate>  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>GridView와의 사용자 상호 작용  
 응용 프로그램에서 <xref:System.Windows.Controls.GridView> 를 사용하면 사용자가 에서 의 서식을 <xref:System.Windows.Controls.GridView>상호 작용하고 수정할 수 있습니다. 예를 들어, 열을 다시 정렬하고, 열의 크기를 조정하며, 테이블에서 항목을 선택하고, 콘텐츠를 스크롤할 수 있습니다. 사용자가 열 헤더 단추를 클릭하면 응답하는 이벤트 처리기도 정의할 수 있습니다. 이벤트 처리기는 열의 내용에 <xref:System.Windows.Controls.GridView> 따라 표시되는 데이터를 정렬하는 등의 작업을 수행할 수 있습니다.  
  
 다음 목록에서는 사용자 상호 작용에 <xref:System.Windows.Controls.GridView> 사용하는 기능에 대해 자세히 설명합니다.  
  
- **끌어서 놓기 메서드를 사용하여 열을 다시 정렬.**  
  
     사용자는 열 헤더 위에 <xref:System.Windows.Controls.GridView> 있는 동안 왼쪽 마우스 버튼을 누른 다음 해당 열을 새 위치로 드래그하여 열을 순서를 다시 정렬할 수 있습니다. 사용자가 열 헤더를 끌어오는 동안 헤더의 부동 버전과 함께 열을 삽입할 위치를 표시하는 검은 실선이 표시됩니다.  
  
     헤더의 부동 버전에 대한 기본 스타일을 <xref:System.Windows.Controls.ControlTemplate> 수정하려면 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성이 로 설정될 때 트리거되는 형식에 대한 a를 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>지정합니다. 자세한 내용은 [끌어 온 GridView 열 헤더의 스타일 만들기](how-to-create-a-style-for-a-dragged-gridview-column-header.md)를 참조하세요.  
  
- **콘텐츠에 맞게 열의 크기 조정.**  
  
     콘텐츠에 맞게 열의 크기를 조정하려면 열 헤더의 오른쪽에 있는 위치 조정 막대를 두 번 클릭할 수 있습니다.  
  
    > [!NOTE]
    > <xref:System.Windows.Controls.GridViewColumn.Width%2A> 동일한 효과를 생성하도록 `Double.NaN` 속성을 설정할 수 있습니다.  
  
- **행 항목 선택.**  
  
     사용자는 에서 하나 이상의 항목을 <xref:System.Windows.Controls.GridView>선택할 수 있습니다.  
  
     선택한 항목의 스타일을 <xref:System.Windows.Style> 변경하려면 ListView 에서 [선택한 항목의 스타일을 지정하기 위해 트리거 사용을](how-to-use-triggers-to-style-selected-items-in-a-listview.md)참조하세요.  
  
- **처음에 화면에 표시되지 않는 콘텐츠를 보려면 스크롤.**  
  
     의 <xref:System.Windows.Controls.GridView> 크기가 모든 항목을 표시할 만큼 크지 않은 경우 사용자는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤에서 제공하는 스크롤 막대를 사용하여 가로 또는 세로로 스크롤할 수 있습니다. 모든 <xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠가 특정 방향으로 표시되는 경우 A는 숨김됩니다. 열 표제는 세로 스크롤 막대로는 스크롤되지 않지만 가로로는 스크롤됩니다.  
  
- **열 표제 단추를 클릭하여 열과 상호 작용.**  
  
     열 헤더 단추를 클릭하면, 정렬 알고리즘을 제공한 경우 열에 표시되는 데이터를 정렬할 수 있습니다.  
  
     정렬 알고리즘과 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 같은 기능을 제공하기 위해 열 헤더 단추에 대한 이벤트를 처리할 수 있습니다. 단일 열 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 헤더에 대한 이벤트를 처리하려면 <xref:System.Windows.Controls.GridViewColumnHeader>에서 이벤트 처리기를 설정합니다. 모든 열 헤더에 대한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리하는 이벤트 처리기를 설정하려면 <xref:System.Windows.Controls.ListView> 컨트롤에서 처리기를 설정합니다.  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>다른 사용자 지정 보기 가져오기  
 추상 <xref:System.Windows.Controls.GridView> 클래스에서 파생된 클래스는 <xref:System.Windows.Controls.ListView> 클래스에 대해 가능한 뷰 모드 중 하나일 뿐입니다. <xref:System.Windows.Controls.ViewBase> 클래스에서 <xref:System.Windows.Controls.ListView> 파생하여 다른 사용자 지정 뷰를 <xref:System.Windows.Controls.ViewBase> 만들 수 있습니다. 사용자 지정 보기 모드의 예는 [ListView의 사용자 지정 뷰 모드 만들기](how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하세요.  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>GridView 지원 클래스  
 다음 클래스는 <xref:System.Windows.Controls.GridView> 보기 모드를 지원합니다.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [ListView 개요](listview-overview.md)
- [헤더를 클릭하면 GridView 열 정렬](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [방법 주제](listview-how-to-topics.md)
