---
title: DataGrid 컨트롤을 데이터 소스에 바인딩
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 2634a6bd8ace36bcf7a49120162474a8c04b2b83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746696"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="97680-102">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="97680-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="97680-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="97680-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="97680-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="97680-105">Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤은 데이터 원본의 정보를 표시 하도록 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="97680-106">런타임에 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출 하 여 컨트롤을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="97680-107">다양 한 데이터 원본의 데이터를 표시할 수 있지만 가장 일반적인 원본은 데이터 집합 및 데이터 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="97680-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="97680-108">프로그래밍 방식으로 DataGrid 컨트롤을 데이터 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="97680-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="97680-109">데이터 집합을 채우는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="97680-110">데이터 원본이 데이터 집합 또는 데이터 집합 테이블을 기반으로 하는 데이터 뷰 이면 폼에 코드를 추가 하 여 데이터 집합을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="97680-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="97680-111">사용 하는 정확한 코드는 데이터 집합이 데이터를 가져오는 위치에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="97680-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="97680-112">데이터베이스에서 데이터 집합을 직접 채우는 경우 일반적으로 다음 예제와 같이 데이터 어댑터의 `Fill` 메서드를 호출 하 여 `DsCategories1`라는 데이터 집합을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="97680-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="97680-113">XML Web services에서 데이터 집합을 채우는 경우 일반적으로 코드에서 서비스의 인스턴스를 만든 다음 해당 메서드 중 하나를 호출 하 여 데이터 집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="97680-114">그런 다음 XML Web services의 데이터 집합을 로컬 데이터 집합에 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="97680-115">다음 예제에서는 `CategoriesService`이라는 XML Web services의 인스턴스를 만들고 해당 `GetCategories` 메서드를 호출한 다음 결과 데이터 집합을 `DsCategories1`라는 로컬 데이터 집합에 병합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97680-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="97680-116"><xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 호출 하 여 데이터 소스 및 데이터 멤버를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="97680-117">데이터 멤버를 명시적으로 전달 하지 않아도 되는 경우 빈 문자열을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="97680-118">표를 처음 바인딩하는 경우 컨트롤의 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="97680-119">그러나 이러한 속성을 설정한 후에는 해당 속성을 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="97680-120">따라서 항상 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="97680-121">다음 예에서는 `DsCustomers1`이라는 데이터 집합에서 Customers 테이블에 프로그래밍 방식으로 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97680-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="97680-122">Customers 테이블이 데이터 집합의 유일한 테이블인 경우에는 다음과 같이 그리드를 바인딩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97680-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="97680-123">필드 적절 한 테이블 스타일과 열 스타일을 표에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="97680-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="97680-124">테이블 스타일이 없으면 테이블은 표시 되지만 최소 서식 지정 및 모든 열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97680-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97680-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97680-125">See also</span></span>

- [<span data-ttu-id="97680-126">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="97680-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="97680-127">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="97680-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="97680-128">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="97680-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="97680-129">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="97680-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
