---
title: 데이터 그리드 제어 형식 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182143"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="e2af9-102">방법: Windows Forms DataGrid 컨트롤 서식 지정</span><span class="sxs-lookup"><span data-stu-id="e2af9-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="e2af9-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e2af9-104">자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2af9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="e2af9-105"><xref:System.Windows.Forms.DataGrid> 컨트롤의 여러 부분에 서로 다른 색상을 적용하면 정보를 읽고 해석하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="e2af9-106">색상은 행과 열에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="e2af9-107">행과 열은 사용자의 재량에 따라 숨거나 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="e2af9-108">컨트롤 서식지정에는 세 <xref:System.Windows.Forms.DataGrid> 가지 기본 측면이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="e2af9-109">속성을 설정하여 데이터가 표시되는 기본 스타일을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="e2af9-110">그런 다음 해당 기반에서 특정 테이블이 런타임에 표시되는 방식을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="e2af9-111">마지막으로 데이터 그리드에 표시되는 열과 표시되는 색상 및 기타 서식을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="e2af9-112">데이터 그리드 서식을 지정하는 초기 단계로 <xref:System.Windows.Forms.DataGrid> 자체의 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="e2af9-113">이러한 색상 및 형식 선택 항목은 표시되는 데이터 테이블 및 열에 따라 변경할 수 있는 기반을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="e2af9-114">DataGrid 컨트롤에 대한 기본 스타일을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="e2af9-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="e2af9-115">다음 속성을 적절하게 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="e2af9-116">속성</span><span class="sxs-lookup"><span data-stu-id="e2af9-116">Property</span></span>|<span data-ttu-id="e2af9-117">Description</span><span class="sxs-lookup"><span data-stu-id="e2af9-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="e2af9-118">속성은 <xref:System.Windows.Forms.DataGrid.BackColor%2A> 표의 짝수 번호 행의 색상을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="e2af9-119"><xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 속성을 다른 색상으로 설정하면 다른 모든 행이 이 새 색상(행 1, 3, 5 등)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="e2af9-120">그리드의 짝수 번호 행의 배경 색(행 0, 2, 4, 6 등).</span><span class="sxs-lookup"><span data-stu-id="e2af9-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="e2af9-121">및 속성은 그리드의 행 색상을 결정하는 반면, <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 속성은 그리드가 아래로 스크롤될 때 또는 그리드에 몇 행만 포함된 경우에만 표시되는 nonrow 영역의 색상을 결정합니다. <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> <xref:System.Windows.Forms.DataGrid.BackColor%2A></span><span class="sxs-lookup"><span data-stu-id="e2af9-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="e2af9-122">표의 테두리 스타일( 열거형 <xref:System.Windows.Forms.BorderStyle> 값 중 하나)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="e2af9-123">그리드 바로 위에 나타나는 그리드 창 캡션의 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="e2af9-124">표 맨 위에 있는 캡션의 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="e2af9-125">그리드 창 캡션의 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="e2af9-126">그리드에 텍스트를 표시하는 데 사용되는 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="e2af9-127">데이터 그리드의 행에 있는 데이터에 의해 표시되는 글꼴의 색상입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="e2af9-128">데이터 그리드의 그리드 선의 색상입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="e2af9-129">열거값 중 하나인 그리드의 셀을 구분하는 <xref:System.Windows.Forms.DataGridLineStyle> 선의 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="e2af9-130">행 및 열 머리글의 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="e2af9-131">열 머리글에 사용되는 글꼴입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="e2af9-132">열 헤더 텍스트와 플러스/빼기 글리프를 포함한 그리드열 헤더의 전경 색상(여러 관련 테이블이 표시될 때 행을 확장함).</span><span class="sxs-lookup"><span data-stu-id="e2af9-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="e2af9-133">하위 테이블에 대한 링크, 관계 이름 등을 포함하여 데이터 그리드의 모든 링크의 텍스트 색상입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="e2af9-134">자식 테이블에서 부모 행의 배경 색입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="e2af9-135">자식 테이블에서 부모 행의 전경 색상입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="e2af9-136"><xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 열거형에 따라 테이블 및 열 이름들이 부모 행에 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="e2af9-137">데이터 표에서 열의 기본 너비(픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="e2af9-138">및 속성을 재설정하기 전에 이 속성을 설정하거나(메서드를 통해) <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 속성은 영향을 주지 않습니다. <xref:System.Windows.Forms.DataGrid.DataMember%2A> <xref:System.Windows.Forms.DataGrid.DataSource%2A></span><span class="sxs-lookup"><span data-stu-id="e2af9-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="e2af9-139">속성은 0보다 작은 값으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="e2af9-140">그리드의 행 높이(픽셀 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="e2af9-141">및 속성을 재설정하기 전에 이 속성을 설정하거나(메서드를 통해) <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 속성은 영향을 주지 않습니다. <xref:System.Windows.Forms.DataGrid.DataMember%2A> <xref:System.Windows.Forms.DataGrid.DataSource%2A></span><span class="sxs-lookup"><span data-stu-id="e2af9-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="e2af9-142">속성은 0보다 작은 값으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="e2af9-143">그리드의 행 머리글의 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="e2af9-144">행 또는 셀을 선택하면 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="e2af9-145">행 또는 셀을 선택하면 전경 색상입니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="e2af9-146">컨트롤의 색상을 사용자 지정할 때 색상 선택이 불량하여 컨트롤에 액세스할 수 없게 만들 수 있습니다(예: 빨간색 및 녹색).</span><span class="sxs-lookup"><span data-stu-id="e2af9-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="e2af9-147">이 문제를 방지하려면 **시스템 색상** 팔레트에서 사용할 수 있는 색상을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="e2af9-148">다음 절차에서 양식에 데이터 <xref:System.Windows.Forms.DataGrid> 테이블에 바인딩된 컨트롤이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="e2af9-149">자세한 내용은 [Windows Forms DataGrid 컨트롤을 데이터 원본에 바인딩합니다.](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)</span><span class="sxs-lookup"><span data-stu-id="e2af9-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="e2af9-150">데이터 테이블의 테이블 및 열 스타일을 프로그래밍 방식으로 설정하려면</span><span class="sxs-lookup"><span data-stu-id="e2af9-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="e2af9-151">새 테이블 스타일을 만들고 해당 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="e2af9-152">열 스타일을 만들고 해당 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="e2af9-153">테이블 스타일의 열 스타일 컬렉션에 열 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="e2af9-154">데이터 그리드의 테이블 스타일 컬렉션에 테이블 스타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="e2af9-155">아래 예제에서 새 <xref:System.Windows.Forms.DataGridTableStyle> 인스턴스를 만들고 해당 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="e2af9-156">**GridColumnStyle의** 새 인스턴스를 만들고 **매핑 이름(및** 기타 레이아웃 및 표시 속성)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="e2af9-157">만들려는 각 열 스타일에 대해 2~6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="e2af9-158">다음 예제에서는 이름을 <xref:System.Windows.Forms.DataGridTextBoxColumn> 열에 표시하기 때문에 a를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="e2af9-159">또한 테이블 스타일에 열 스타일을 <xref:System.Windows.Forms.GridColumnStylesCollection> 추가하고 테이블 스타일을 데이터 <xref:System.Windows.Forms.GridTableStylesCollection> 그리드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2af9-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName
       ' to the name of a DataColumn in the DataTable.
       ' Set the HeaderText and Width properties.
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to
       ' the GridTableStylesCollection.
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName
       // to the name of a DataColumn in the DataTable.
       // Set the HeaderText and Width properties.
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to
       // the GridTableStylesCollection.
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName
          // to the name of a DataColumn in the DataTable.
          // Set the HeaderText and Width properties.
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to
          // the GridTableStylesCollection.
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2af9-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2af9-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="e2af9-161">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="e2af9-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="e2af9-162">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e2af9-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
