---
description: '자세한 정보: DataAdapter DataTable 및 DataColumn 매핑'
title: DataAdapter DataTable 및 DataColumn 매핑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 25007925afa57dd0cb6e75f808444f1bfaeea9b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739736"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="01175-103">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="01175-103">DataAdapter DataTable and DataColumn Mappings</span></span>

<span data-ttu-id="01175-104">**DataAdapter** 의 <xref:System.Data.Common.DataTableMapping> **TableMappings** 속성에는 0 개 이상의 개체 컬렉션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-104">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="01175-105">**DataTableMapping** 는 데이터 원본에 대 한 쿼리에서 반환 되는 데이터와에 대 한 마스터 매핑을 제공 <xref:System.Data.DataTable> 합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-105">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="01175-106">**DataTableMapping** 이름은 **DataTable** 이름 대신 **DataAdapter** 의 **Fill** 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-106">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="01175-107">다음 예제에서는 **Authors** 테이블에 대해 **AuthorsMapping** 이라는 **DataTableMapping** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01175-107">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="01175-108">**DataTableMapping** 을 통해 데이터베이스의 열 이름과 다른 **DataTable** 의 열 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-108">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="01175-109">**DataAdapter** 는 테이블이 업데이트될 때 매핑을 통해 열을 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="01175-109">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="01175-110">**DataAdapter** 의 **Fill** 또는 **Update** 메서드를 호출할 때 **TableName** 또는 **DataTableMapping** 이름을 지정하지 않으면 **DataAdapter** 가 “Table”이라는 **DataTableMapping** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-110">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="01175-111">해당 **DataTableMapping** 없는 경우 **DataTable** 의 **TableName** 은 "Table"입니다.</span><span class="sxs-lookup"><span data-stu-id="01175-111">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="01175-112">“Table”이라는 이름의 **DataTableMapping** 을 만들어 기본 **DataTableMapping** 을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-112">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="01175-113">다음 코드 예제에서는 <xref:System.Data.Common> 네임스페이스에서 **DataTableMapping** 을 만들고, 이름을 “Table”로 하여 지정된 **DataAdapter** 의 기본 매핑으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-113">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="01175-114">그런 다음, 쿼리 결과의 첫 번째 테이블(**Northwind** 데이터베이스의 **Customers** 테이블)에 있는 열을 <xref:System.Data.DataSet>의 **Northwind Customers** 테이블에 있는, 사용자에게 더 친숙한 이름 세트로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-114">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01175-115">매핑되지 않는 열의 경우 데이터 소스의 열 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-115">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="01175-116">나중에 동일한 **DataAdapter** 에서 다른 매핑을 사용하는 다른 테이블의 로드를 지원하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-116">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="01175-117">이렇게 하려면 추가 **DataTableMapping** 개체를 추가 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-117">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="01175-118">**Fill** 메서드에 **DataSet** 의 인스턴스와 **DataTableMapping** 이름이 전달될 때 해당 이름의 매핑이 있으면 그 매핑이 사용되고, 없으면 해당 이름의 **DataTable** 이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-118">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="01175-119">다음 예제에서는 **Customers** 라는 이름의 **DataTableMapping** 과 **BizTalkSchema** 라는 이름의 **DataTable** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01175-119">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="01175-120">그런 다음, SELECT 문에서 반환하는 행을 **BizTalkSchema** **DataTable** 에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-120">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="01175-121">열 매핑에 소스 열 이름을 제공하지 않거나 테이블 매핑에 소스 테이블 이름을 제공하지 않으면 기본 이름이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-121">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="01175-122">열 매핑에 대해 원본 열이 제공 되지 않은 경우 열 매핑에는 **SourceColumn1** 로 시작 하는 **SourceColumn** *N* 의 증분 기본 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-122">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="01175-123">테이블 매핑에 대해 제공 된 원본 테이블 이름이 없으면 테이블 매핑에 **SourceTable1** 로 시작 하는 **SourceTable** *N* 의 증분 기본 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-123">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01175-124">사용자가 제공하는 이름이 **ColumnMappingCollection** 에 있는 기존의 기본 열 매핑 이름이나 **DataTableMappingCollection** 에 있는 테이블 매핑 이름과 충돌할 수 있으므로, 열 매핑에 **SourceColumn** *N* 을 제공하거나 테이블 매핑에 **SourceTable** *N* 을 제공하는 명명 규칙은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-124">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="01175-125">이미 있는 이름을 제공하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="01175-125">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="01175-126">여러 개의 결과 집합 처리</span><span class="sxs-lookup"><span data-stu-id="01175-126">Handling Multiple Result Sets</span></span>  

 <span data-ttu-id="01175-127">**SelectCommand** 가 여러 개의 테이블을 반환하면 **Fill** 은 **DataSet** 의 테이블에 대해 지정된 테이블 이름으로 시작하여 **TableName** *N*(**TableName1** 로 시작) 형식으로 계속되는 증분 값을 갖는 테이블 이름을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-127">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="01175-128">테이블 매핑을 사용하여 자동 생성된 테이블 이름을 **DataSet** 의 테이블에 대해 지정하려는 이름으로 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-128">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="01175-129">예를 들어, **Customers** 와 **Orders** 라는 두 테이블을 반환하는 **SelectCommand** 의 경우 **Fill** 에 대해 다음과 같이 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-129">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="01175-130">두 테이블은 **DataSet**: **Customers** 와 **Customers1** 에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="01175-130">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="01175-131">테이블 매핑을 사용하면 두 번째 테이블이 **Customers1** 대신 **Orders** 로 명명되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01175-131">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="01175-132">이를 수행하려면 다음 예제와 같이 **Customers1** 의 원본 테이블을 **DataSet** 테이블 **Orders** 로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="01175-132">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="01175-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01175-133">See also</span></span>

- [<span data-ttu-id="01175-134">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="01175-134">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="01175-135">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="01175-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="01175-136">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="01175-136">ADO.NET Overview</span></span>](ado-net-overview.md)
