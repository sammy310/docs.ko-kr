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
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="81168-102">방법: DataGrid 컨트롤에 행 세부 정보 추가</span><span class="sxs-lookup"><span data-stu-id="81168-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="81168-103"><xref:System.Windows.Controls.DataGrid> 컨트롤을 사용 하는 경우 행 세부 정보 섹션을 추가 하 여 데이터 표시를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="81168-104">행 세부 정보 섹션을 추가 하는 필요에 따라 표시 또는 축소 하는 서식 파일의 일부 데이터를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="81168-105">예를 들어 <xref:System.Windows.Controls.DataGrid>의 각 행에 대 한 데이터 요약만 표시 하 고 사용자가 행을 선택할 때 더 많은 데이터 필드를 표시 하는 <xref:System.Windows.Controls.DataGrid>에 행 세부 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="81168-106"><xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성에서 행 세부 정보 섹션의 템플릿을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="81168-107">다음 그림에서는 행 세부 정보 섹션의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="81168-108">![행 세부 정보가 표시 된 DataGrid](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="81168-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="81168-109">리소스 또는 인라인으로 XAML로 행 세부 정보 템플릿을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="81168-110">다음 절차에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="81168-111">리소스로 추가 되는 데이터 템플릿은 다시 서식 파일을 만들지 않고 프로젝트 전체에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="81168-112">인라인 XAML 컨트롤에서 액세스할 수만 정의 된 대로 추가 되는 데이터 템플릿.</span><span class="sxs-lookup"><span data-stu-id="81168-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="81168-113">인라인 XAML을 사용 하 여 행 세부 정보를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="81168-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="81168-114">데이터 원본의 데이터를 표시 하는 <xref:System.Windows.Controls.DataGrid>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81168-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="81168-115"><xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="81168-116">행 세부 정보 섹션의 모양을 정의 하는 <xref:System.Windows.DataTemplate>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81168-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="81168-117">다음 XAML은 <xref:System.Windows.Controls.DataGrid> 및 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 인라인을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="81168-118"><xref:System.Windows.Controls.DataGrid>는 각 행에 3 개의 값을 표시 하 고 행을 선택 하면 3 개의 값을 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="81168-119">다음 코드는 <xref:System.Windows.Controls.DataGrid>에 표시 되는 데이터를 선택 하는 데 사용 되는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="81168-120">이 예제에서 쿼리는 고객 정보를 포함 하는 엔터티에서 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="81168-121">리소스를 사용 하 여 행 세부 정보를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="81168-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="81168-122">데이터 원본의 데이터를 표시 하는 <xref:System.Windows.Controls.DataGrid>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81168-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="81168-123"><xref:System.Windows.Window> 컨트롤 또는 <xref:System.Windows.Controls.Page> 컨트롤과 같은 루트 요소에 <xref:System.Windows.FrameworkElement.Resources%2A> 요소를 추가 하거나, 응용 프로그램 또는 응용 프로그램 .xaml 파일의 <xref:System.Windows.Application> 클래스에 <xref:System.Windows.Application.Resources%2A> 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="81168-124">Resources 요소에서 행 세부 정보 섹션의 모양을 정의 하는 <xref:System.Windows.DataTemplate>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81168-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="81168-125">다음 XAML은 <xref:System.Windows.Application> 클래스에 정의 된 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="81168-126"><xref:System.Windows.DataTemplate>에서 [X:Key 지시어](../../../desktop-wpf/xaml-services/xkey-directive.md) 를 데이터 템플릿을 고유 하 게 식별 하는 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="81168-127"><xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 이전 단계에서 정의한 리소스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="81168-128">리소스를 정적 리소스로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="81168-129">다음 XAML에서는 이전 예제의 리소스로 설정 된 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81168-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="81168-130">행 세부 정보에 대 한 표시 여부를 설정 하 고 가로 스크롤을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="81168-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="81168-131">필요한 경우 <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> 속성을 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="81168-132">기본적으로 이 값은 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="81168-133">모든 행 또는 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>에 대 한 세부 정보를 표시 하는 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> 설정 하 여 모든 행에 대 한 세부 정보를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81168-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="81168-134">필요한 경우 <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> 속성을 `true`으로 설정 하 여 행 세부 정보 섹션의 가로 스크롤을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="81168-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
