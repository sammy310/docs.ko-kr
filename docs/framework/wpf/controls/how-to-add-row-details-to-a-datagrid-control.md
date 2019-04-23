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
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768646"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="8fa4a-102">방법: DataGrid 컨트롤에 행 세부 정보 추가</span><span class="sxs-lookup"><span data-stu-id="8fa4a-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="8fa4a-103">사용 하는 경우는 <xref:System.Windows.Controls.DataGrid> 컨트롤을 사용자 지정할 수 있습니다 데이터 프레젠테이션 행 세부 정보 섹션을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="8fa4a-104">행 세부 정보 섹션을 추가 하는 필요에 따라 표시 또는 축소 하는 서식 파일의 일부 데이터를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="8fa4a-105">예를 들어, 행 세부 정보를 추가할 수 있습니다는 <xref:System.Windows.Controls.DataGrid> 의 각 행에 대 한 데이터의 요약만을 표시 하는 <xref:System.Windows.Controls.DataGrid>, 행을 선택 하면 더 많은 데이터 필드를 표시 하지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="8fa4a-106">행 세부 정보 섹션의 템플릿을 정의 합니다 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="8fa4a-107">다음 그림에서는 행 세부 정보 섹션의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="8fa4a-108">![행 세부 정보를 사용 하 여 표시 된 DataGrid](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="8fa4a-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="8fa4a-109">리소스 또는 인라인으로 XAML로 행 세부 정보 템플릿을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="8fa4a-110">두 방법 모두 다음 절차에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="8fa4a-111">리소스로 추가 되는 데이터 템플릿은 다시 서식 파일을 만들지 않고 프로젝트 전체에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="8fa4a-112">인라인 XAML 컨트롤에서 액세스할 수만 정의 된 대로 추가 되는 데이터 템플릿.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="8fa4a-113">인라인 XAML을 사용 하 여 행 정보를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="8fa4a-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="8fa4a-114">만들기는 <xref:System.Windows.Controls.DataGrid> 데이터 원본에서 데이터를 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="8fa4a-115"><xref:System.Windows.Controls.DataGrid> 요소에서 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="8fa4a-116">만들기는 <xref:System.Windows.DataTemplate> 행 세부 정보 섹션의 모양을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="8fa4a-117">다음 XAML은 <xref:System.Windows.Controls.DataGrid> 정의 하는 방법과 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 인라인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="8fa4a-118"><xref:System.Windows.Controls.DataGrid> 표시 3 값 3 각 행에 더 많은 값 행을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="8fa4a-119">다음 코드에 표시 되는 데이터를 선택 하는 데 사용 되는 쿼리를 보여 줍니다.는 <xref:System.Windows.Controls.DataGrid>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="8fa4a-120">이 예에서 쿼리는 고객 정보가 포함 된 엔터티에서 데이터를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="8fa4a-121">리소스를 사용 하 여 행 정보를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="8fa4a-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="8fa4a-122">만들기는 <xref:System.Windows.Controls.DataGrid> 데이터 원본에서 데이터를 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="8fa4a-123">추가 <xref:System.Windows.FrameworkElement.Resources%2A> 루트 요소에 요소와 같은 <xref:System.Windows.Window> 컨트롤 또는 <xref:System.Windows.Controls.Page> , 제어 하거나 추가 <xref:System.Windows.Application.Resources%2A> 요소를는 <xref:System.Windows.Application> App.xaml (또는 Application.xaml) 파일에서 클래스.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="8fa4a-124">리소스 요소를 만듭니다를 <xref:System.Windows.DataTemplate> 행 세부 정보 섹션의 모양을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="8fa4a-125">다음 XAML은 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 에 정의 된는 <xref:System.Windows.Application> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="8fa4a-126">에 <xref:System.Windows.DataTemplate>설정 합니다 [X:key 지시문](../../xaml-services/x-key-directive.md) 데이터 서식 파일을 고유 하 게 식별 하는 값을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="8fa4a-127">에 <xref:System.Windows.Controls.DataGrid> 요소를 설정 합니다 <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 이전 단계에서 정의한 리소스 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="8fa4a-128">정적 리소스와 리소스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="8fa4a-129">에서는 다음 XAML <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 앞의 예제에서 리소스에 설정 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="8fa4a-130">표시 유형을 설정 하 고 행 세부 정보에 대 한 가로 스크롤을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="8fa4a-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="8fa4a-131">필요한 경우 설정 합니다 <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> 속성을 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="8fa4a-132">기본적으로 값 설정할지 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="8fa4a-133">설정할 수 있습니다 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> 의 모든 행에 대 한 세부 정보를 표시 하거나 <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> 모든 행에 대 한 세부 정보를 숨기려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="8fa4a-134">필요한 경우 설정 합니다 <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> 속성을 `true` 행을 방지 하기 위해 가로로 스크롤할 섹션에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fa4a-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
