---
title: '연습: 혼합 애플리케이션에서 데이터 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 99f0e621c7dd56c0a26b51b4725f9fb96ab3cbf9
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197909"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="a4c7d-102">연습: 혼합 애플리케이션에서 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="a4c7d-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="a4c7d-103">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하는지에 관계 없이 사용자에 게 기본 데이터에 대 한 액세스 권한을 제공 하려면 데이터 소스를 컨트롤에 바인딩하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="a4c7d-104">이 연습에서는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함 하는 혼합 응용 프로그램에서 데이터 바인딩을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="a4c7d-105">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a4c7d-106">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-106">Creating the project.</span></span>

- <span data-ttu-id="a4c7d-107">데이터 템플릿 정의</span><span class="sxs-lookup"><span data-stu-id="a4c7d-107">Defining the data template.</span></span>

- <span data-ttu-id="a4c7d-108">폼 레이아웃 지정</span><span class="sxs-lookup"><span data-stu-id="a4c7d-108">Specifying the form layout.</span></span>

- <span data-ttu-id="a4c7d-109">데이터 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="a4c7d-109">Specifying data bindings.</span></span>

- <span data-ttu-id="a4c7d-110">상호 운용성을 사용하여 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="a4c7d-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="a4c7d-111">프로젝트에 데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="a4c7d-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="a4c7d-112">데이터 소스에 바인딩</span><span class="sxs-lookup"><span data-stu-id="a4c7d-112">Binding to the data source.</span></span>

<span data-ttu-id="a4c7d-113">이 연습에서 설명 하는 작업의 전체 코드 목록은 [하이브리드 응용 프로그램의 데이터 바인딩 샘플](https://go.microsoft.com/fwlink/?LinkID=159983)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="a4c7d-114">작업을 완료하면 혼합 애플리케이션의 데이터 바인딩 기능을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4c7d-115">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a4c7d-115">Prerequisites</span></span>

<span data-ttu-id="a4c7d-116">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a4c7d-117">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-117">Visual Studio.</span></span>

- <span data-ttu-id="a4c7d-118">Microsoft SQL Server에서 실행 되는 Northwind 샘플 데이터베이스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a4c7d-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a4c7d-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="a4c7d-120">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-120">To create and set up the project</span></span>

1. <span data-ttu-id="a4c7d-121">`WPFWithWFAndDatabinding`이라는 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="a4c7d-122">솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="a4c7d-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a4c7d-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="a4c7d-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="a4c7d-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="a4c7d-125">[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에서 Mainwindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="a4c7d-126"><xref:System.Windows.Window> 요소에서 다음 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임 스페이스 매핑을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="a4c7d-127"><xref:System.Windows.FrameworkElement.Name%2A> 속성을 할당 하 여 `mainGrid` 기본 <xref:System.Windows.Controls.Grid> 요소 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="a4c7d-128">데이터 템플릿 정의</span><span class="sxs-lookup"><span data-stu-id="a4c7d-128">Defining the Data Template</span></span>

<span data-ttu-id="a4c7d-129">고객의 마스터 목록이 <xref:System.Windows.Controls.ListBox> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="a4c7d-130">다음 코드 예제에서는 <xref:System.Windows.Controls.ListBox> 컨트롤의 시각적 트리를 제어 하는 `ListItemsTemplate` 라는 <xref:System.Windows.DataTemplate> 개체를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="a4c7d-131">이 <xref:System.Windows.DataTemplate>은 <xref:System.Windows.Controls.ListBox> 컨트롤의 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="a4c7d-132">데이터 템플릿을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-132">To define the data template</span></span>

- <span data-ttu-id="a4c7d-133">다음 XAML을 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="a4c7d-134">폼 레이아웃 지정</span><span class="sxs-lookup"><span data-stu-id="a4c7d-134">Specifying the Form Layout</span></span>

<span data-ttu-id="a4c7d-135">폼의 레이아웃은 세 개의 행과 세 개의 열이 있는 그리드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="a4c7d-136">Customers 테이블의 각 열을 식별 하기 위해 <xref:System.Windows.Controls.Label> 컨트롤이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="a4c7d-137">그리드 레이아웃을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-137">To set up the Grid layout</span></span>

- <span data-ttu-id="a4c7d-138">다음 XAML을 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="a4c7d-139">레이블 컨트롤을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-139">To set up the Label controls</span></span>

- <span data-ttu-id="a4c7d-140">다음 XAML을 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="a4c7d-141">데이터 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="a4c7d-141">Specifying Data Bindings</span></span>

<span data-ttu-id="a4c7d-142">고객의 마스터 목록이 <xref:System.Windows.Controls.ListBox> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="a4c7d-143">연결 된 `ListItemsTemplate`는 <xref:System.Windows.Controls.TextBlock> 컨트롤을 데이터베이스의 `ContactName` 필드에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="a4c7d-144">각 고객 레코드의 세부 정보는 여러 <xref:System.Windows.Controls.TextBox> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="a4c7d-145">데이터 바인딩을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-145">To specify data bindings</span></span>

- <span data-ttu-id="a4c7d-146">다음 XAML을 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="a4c7d-147"><xref:System.Windows.Data.Binding> 클래스는 <xref:System.Windows.Controls.TextBox> 컨트롤을 데이터베이스의 적절 한 필드에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="a4c7d-148">상호 운용성을 사용하여 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="a4c7d-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="a4c7d-149">선택한 고객에 해당 하는 주문이 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> 컨트롤에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="a4c7d-150">`dataGridView1` 컨트롤은 코드 숨김이 있는 파일의 데이터 소스에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="a4c7d-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은이 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="a4c7d-152">DataGridView 컨트롤에 데이터를 표시하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="a4c7d-153">다음 XAML을 <xref:System.Windows.Controls.Grid> 요소의 선언에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="a4c7d-154">프로젝트에 데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="a4c7d-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="a4c7d-155">Visual Studio를 사용 하면 프로젝트에 데이터 소스를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="a4c7d-156">이 절차에서는 강력한 형식의 데이터 집합을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="a4c7d-157">선택한 각 테이블에 대한 테이블 어댑터 같은 여러 가지 다른 지원 클래스도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="a4c7d-158">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-158">To add the data source</span></span>

1. <span data-ttu-id="a4c7d-159">**데이터** 메뉴에서 **새 데이터 소스 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="a4c7d-160">**데이터 소스 구성 마법사**에서 데이터 집합을 사용 하 여 Northwind 데이터베이스에 대 한 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="a4c7d-161">자세한 내용은 [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="a4c7d-162">**데이터 소스 구성 마법사**에서 메시지가 표시 되 면 연결 문자열을 `NorthwindConnectionString`로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="a4c7d-163">데이터베이스 개체를 선택 하 라는 메시지가 표시 되 면 `Customers` 및 `Orders` 테이블을 선택 하 고 생성 된 데이터 집합의 이름을 `NorthwindDataSet`합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="a4c7d-164">데이터 소스에 바인딩</span><span class="sxs-lookup"><span data-stu-id="a4c7d-164">Binding to the Data Source</span></span>

<span data-ttu-id="a4c7d-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> 구성 요소는 응용 프로그램의 데이터 소스에 대 한 균일 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="a4c7d-166">데이터 소스에 바인딩은 코드 숨김 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="a4c7d-167">데이터 소스에 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="a4c7d-167">To bind to the data source</span></span>

1. <span data-ttu-id="a4c7d-168">MainWindow.xaml.vb 또는 MainWindow.xaml.cs라는 코드 숨김 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="a4c7d-169">`MainWindow` 클래스 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="a4c7d-170">이 코드는 데이터베이스에 연결 하는 <xref:System.Windows.Forms.BindingSource> 구성 요소 및 연결 된 도우미 클래스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="a4c7d-171">다음 코드를 생성자에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="a4c7d-172">이 코드는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 만들고 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="a4c7d-173">MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="a4c7d-174">디자인 뷰 또는 XAML 뷰에서 <xref:System.Windows.Window> 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="a4c7d-175">속성 창에서 **이벤트** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="a4c7d-176"><xref:System.Windows.FrameworkElement.Loaded> 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="a4c7d-177">다음 코드를 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="a4c7d-178">이 코드는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 컨텍스트로 할당 하 고 `Customers` 및 `Orders` 어댑터 개체를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="a4c7d-179">`MainWindow` 클래스 정의에 다음 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="a4c7d-180">이 메서드는 <xref:System.Windows.Data.CollectionView.CurrentChanged> 이벤트를 처리 하 고 데이터 바인딩의 현재 항목을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="a4c7d-181">F5 키를 눌러 애플리케이션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4c7d-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4c7d-182">참조</span><span class="sxs-lookup"><span data-stu-id="a4c7d-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a4c7d-183">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="a4c7d-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a4c7d-184">하이브리드 응용 프로그램의 데이터 바인딩 샘플</span><span class="sxs-lookup"><span data-stu-id="a4c7d-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="a4c7d-185">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="a4c7d-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a4c7d-186">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="a4c7d-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
