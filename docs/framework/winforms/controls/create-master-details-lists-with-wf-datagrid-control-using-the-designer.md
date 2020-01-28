---
title: 디자이너를 사용 하 여 DataGrid 컨트롤을 사용 하 여 마스터-세부 목록 만들기
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0dea3dd88a8c6c2aceb894789ace8ef3b5c83632
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743391"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="61795-102">방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="61795-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="61795-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61795-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="61795-104">자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61795-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="61795-105"><xref:System.Data.DataSet>에 일련의 관련 테이블이 포함 되어 있는 경우 두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 사용 하 여 데이터를 마스터-세부 형식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61795-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="61795-106">한 <xref:System.Windows.Forms.DataGrid> 마스터 그리드로 지정 되 고 두 번째는 세부 정보 표로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61795-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="61795-107">마스터 목록에서 항목을 선택 하면 관련 된 모든 자식 항목이 세부 정보 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61795-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="61795-108">예를 들어 <xref:System.Data.DataSet>에 Customers 테이블과 관련 Orders 테이블이 포함 되어 있는 경우에는 Customers 테이블을 마스터 그리드로 지정 하 고 Orders 테이블을 세부 정보 표로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="61795-109">마스터 표에서 고객이 선택 된 경우 Orders 테이블에서 해당 고객과 연결 된 모든 주문이 세부 정보 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61795-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>

 <span data-ttu-id="61795-110">다음 절차를 수행 하려면 **Windows 응용 프로그램** 프로젝트 (**파일** > **새** > **프로젝트** >  **C# Visual** 또는 **Visual Basic** > **클래식 데스크톱** > **응용 프로그램**)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-110">The following procedure requires a **Windows Application** project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="61795-111">디자이너에서 마스터-세부 목록을 만들려면</span><span class="sxs-lookup"><span data-stu-id="61795-111">To create a master-details list in the designer</span></span>

1. <span data-ttu-id="61795-112">두 개의 <xref:System.Windows.Forms.DataGrid> 컨트롤을 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-112">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="61795-113">자세한 내용은 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61795-113">For more information, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="61795-114">Visual Studio 2005에서 <xref:System.Windows.Forms.DataGrid> 컨트롤은 기본적으로 **도구 상자** 에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61795-114">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="61795-115">자세한 내용은 [방법: 도구 상자에 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61795-115">For more information, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span>

    > [!NOTE]
    > <span data-ttu-id="61795-116">다음 단계는 디자인 타임 데이터 바인딩에 대해 **데이터 소스** 창을 사용 하는 Visual Studio 2005에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61795-116">The following steps are not applicable to Visual Studio 2005, which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="61795-117">자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 및 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61795-117">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).</span></span>

2. <span data-ttu-id="61795-118">**서버 탐색기** 에서 폼으로 두 개 이상의 테이블을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="61795-118">Drag two or more tables from **Server Explorer** to the form.</span></span>

3. <span data-ttu-id="61795-119">**데이터** 메뉴에서 데이터 **집합 생성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-119">From the **Data** menu, select **Generate DataSet**.</span></span>

4. <span data-ttu-id="61795-120">XML 디자이너를 사용 하 여 테이블 간의 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-120">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="61795-121">자세한 내용은 MSDN의 "방법: XML 스키마 및 데이터 집합에서 일 대 다 관계 만들기"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="61795-121">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>

5. <span data-ttu-id="61795-122">**파일** 메뉴에서 **모두 저장** 을 선택 하 여 관계를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-122">Save the relationships by selecting **Save All** from the **File** menu.</span></span>

6. <span data-ttu-id="61795-123">다음과 같이 마스터 그리드를 지정 하려는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-123">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>

    1. <span data-ttu-id="61795-124"><xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성의 드롭다운 목록에서 <xref:System.Data.DataSet>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-124">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="61795-125"><xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성의 드롭다운 목록에서 마스터 테이블 (예: "Customers")을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-125">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>

7. <span data-ttu-id="61795-126">다음과 같이 세부 정보 표를 지정 하려는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-126">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>

    1. <span data-ttu-id="61795-127"><xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성의 드롭다운 목록에서 <xref:System.Data.DataSet>을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-127">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="61795-128"><xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성의 드롭다운 목록에서 마스터 테이블과 세부 테이블 간의 관계 (예: "CustOrd")를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-128">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="61795-129">관계를 보려면 드롭다운 목록에서 마스터 테이블 옆에 있는 더하기 ( **+** ) 기호를 클릭 하 여 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="61795-129">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="61795-130">참조</span><span class="sxs-lookup"><span data-stu-id="61795-130">See also</span></span>

- [<span data-ttu-id="61795-131">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="61795-131">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="61795-132">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="61795-132">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="61795-133">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="61795-133">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [<span data-ttu-id="61795-134">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="61795-134">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
