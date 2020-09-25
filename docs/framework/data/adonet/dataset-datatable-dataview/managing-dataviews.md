---
title: 데이터 보기 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: c07f521b94f23b479281b0314d6b89a095ee9624
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181247"
---
# <a name="managing-dataviews"></a><span data-ttu-id="f0f27-102">데이터 보기 관리</span><span class="sxs-lookup"><span data-stu-id="f0f27-102">Managing DataViews</span></span>

<span data-ttu-id="f0f27-103"><xref:System.Data.DataViewManager>를 사용하여 <xref:System.Data.DataView>의 모든 테이블에 대한 뷰 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-103">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="f0f27-104">관계를 탐색 하는 표와 같이 여러 테이블에 바인딩하려는 컨트롤이 있는 경우에는 **DataViewManager** 이 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-104">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="f0f27-105">**DataViewManager** 에 <xref:System.Data.DataViewSetting> 는에 있는 테이블의 뷰 설정을 설정 하는 데 사용 되는 개체의 컬렉션이 포함 되어 있습니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="f0f27-105">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f0f27-106">에는 <xref:System.Data.DataViewSettingCollection> <xref:System.Data.DataViewSetting> **데이터 집합**의 각 테이블에 대 한 하나의 개체가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-106">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="f0f27-107">해당 **DataViewSetting**를 사용 하 여 참조 되는 테이블의 기본 **ApplyDefaultSort**, **Sort**, **RowFilter**및 **rowstatefilter** 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-107">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="f0f27-108">이름 또는 서 수 참조를 기준으로 특정 테이블에 대 한 **DataViewSetting** 를 참조 하거나 해당 특정 테이블 개체에 대 한 참조를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-108">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="f0f27-109">**DataViewSettings** 속성을 사용 하 여 **DataViewManager** 에서 **DataViewSetting** 개체의 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-109">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="f0f27-110">다음 코드 예제에서는 SQL Server **Northwind** 데이터베이스 테이블 **고객**, **주문**및 **주문 정보**를 사용 하 여 **데이터 집합** 을 채우고, 테이블 간의 관계를 만들고, **DataViewManager** 를 사용 하 여 기본 **DataView** 설정을 설정 하 고, **DataGrid** 를 **DataViewManager**에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-110">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="f0f27-111">이 예에서는 테이블의 기본 키를 기준으로 정렬 하도록 **데이터 집합** 의 모든 테이블에 대 한 기본 **DataView** 설정을 설정 (**ApplyDefaultSort**  =  **true**) 한 다음 **Customers** 테이블의 정렬 순서를 수정 하 여 **CompanyName**을 기준으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f27-111">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0f27-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0f27-112">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="f0f27-113">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="f0f27-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="f0f27-114">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f0f27-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
