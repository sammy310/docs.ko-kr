---
title: DataAdapter DataTable 및 DataColumn 매핑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 54af7c2f449f8eb289841fb3eca357c6916404aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201210"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="5d78a-102">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="5d78a-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="5d78a-103">A **DataAdapter** 0 개 이상의 컬렉션을 포함 <xref:System.Data.Common.DataTableMapping> 개체에 해당 **TableMappings** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="5d78a-104">A **DataTableMapping** 데이터 원본에 대해 쿼리에서 반환 된 데이터 간의 마스터 매핑을 제공 및 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="5d78a-105">**DataTableMapping** 이름 자리에 전달 될 수 있습니다를 **DataTable** 이름를 **채우기** 메서드를 **DataAdapter**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="5d78a-106">다음 예에서는 **DataTableMapping** 라는 **AuthorsMapping** 에 대 한 합니다 **작성자** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="5d78a-107">**DataTableMapping** 의 열 이름을 사용할 수 있습니다는 **DataTable** 된 데이터베이스의 경우와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="5d78a-108">합니다 **DataAdapter** 매핑을 사용 하 여 테이블 업데이트 되 면 열과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="5d78a-109">지정 하지 않는 경우는 **TableName** 또는 **DataTableMapping** 호출 하는 경우 이름을 **채우기** 또는 **업데이트** 메서드는  **DataAdapter**서 **DataAdapter** 찾습니다는 **DataTableMapping** "Table" 이라는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="5d78a-110">있는지 **DataTableMapping** 존재 하지 않는 합니다 **TableName** 의 합니다 **DataTable** 은 "Table"입니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="5d78a-111">기본값을 지정할 수 있습니다 **DataTableMapping** 만들어를 **DataTableMapping** "Table"의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="5d78a-112">다음 코드 예제는 **DataTableMapping** (에서 <xref:System.Data.Common> 네임 스페이스) 지정 된 기본 매핑을 사용 하면 **DataAdapter** 이름을 지정 하 여 "Table".</span><span class="sxs-lookup"><span data-stu-id="5d78a-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="5d78a-113">예제는 다음 쿼리 결과의 첫 번째 테이블에서 열을 매핑합니다 (합니다 **고객** 목차를 **Northwind** 데이터베이스)의 더 친숙 한 이름 집합에는 **Northwind Customers**  테이블에 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5d78a-114">매핑되지 않는 열의 경우 데이터 소스의 열 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="5d78a-115">더 고급 시나리오에서는 결정할 수는 있습니다 동일 **DataAdapter** 다른 매핑 사용 하 여 다른 테이블의 로드를 지원 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="5d78a-116">이렇게 하려면 추가 하기만 하면 됩니다 **DataTableMapping** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="5d78a-117">경우는 **채우기** 메서드 인스턴스에 전달 되는 **데이터 집합** 및 **DataTableMapping** , 해당 이름의 매핑이 있으면 이름이 고, 그렇지 않으면 사용 되는  **DataTable** 된 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="5d78a-118">다음 예제에서는 **DataTableMapping** 라는 이름의 **고객** 와 **DataTable** 이름 **BizTalkSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="5d78a-119">이 예제에서는 SELECT 문으로 반환 되는 행 매핑합니다 합니다 **BizTalkSchema** **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="5d78a-120">열 매핑에 소스 열 이름을 제공하지 않거나 테이블 매핑에 소스 테이블 이름을 제공하지 않으면 기본 이름이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="5d78a-121">열 매핑이 증분 기본 이름인을 제공 하 고 열 매핑에 소스 열이 제공 되는 경우 **SourceColumn** *N* 부터는 **SourceColumn1**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="5d78a-122">테이블 매핑이 증분 기본 이름인을 제공 하 고 테이블 매핑에 소스 테이블 이름을 제공 하면 **SourceTable** *N*부터 **SourceTable1**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d78a-123">명명 규칙을 방지 하는 것이 좋습니다 **SourceColumn** *N* 열 매핑에, 또는 **SourceTable** *N* 테이블 제공한 이름에 있는 기존의 기본 열 매핑 이름과 충돌할 수 있습니다 때문에 매핑 합니다 **ColumnMappingCollection** 또는 테이블 매핑 이름 합니다 **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="5d78a-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="5d78a-124">이미 있는 이름을 제공하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="5d78a-125">여러 개의 결과 집합 처리</span><span class="sxs-lookup"><span data-stu-id="5d78a-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="5d78a-126">경우에 **SelectCommand** 여러 테이블을 반환 **채우기** 테이블에 대 한 증분 값을 사용 하 여 테이블 이름을 자동으로 생성 합니다 **데이터 집합**부터 시작 하 여는 테이블 이름 및 계속에 형식 지정 **TableName** *N*부터 **TableName1**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="5d78a-127">테이블 매핑을 사용 하 여 테이블에 대해 지정 하려는 이름으로 자동으로 생성 된 테이블 이름을 매핑하는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="5d78a-128">예를 **SelectCommand** 두 개의 테이블을 반환 하는 **고객** 및 **주문**, 다음 호출을 실행 하 **채우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="5d78a-129">만들어진 두 개의 테이블을 **데이터 집합**: **고객이** 하 고 **Customers1**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="5d78a-130">테이블 매핑을 사용 하 여 두 번째 테이블은 이름이 되도록 **주문을** of **Customers1**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="5d78a-131">이 작업을 수행 하려면 원본 테이블의를 매핑합니다 **Customers1** 에 **데이터 집합** 테이블 **주문**다음 예제에서와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d78a-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d78a-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d78a-132">See also</span></span>

- [<span data-ttu-id="5d78a-133">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="5d78a-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="5d78a-134">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="5d78a-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="5d78a-135">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5d78a-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
