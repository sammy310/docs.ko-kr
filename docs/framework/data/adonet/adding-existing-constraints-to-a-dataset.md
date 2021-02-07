---
description: '자세히 알아보기: 데이터 집합에 기존 제약 조건 추가'
title: 데이터 세트에 기존 제약 조건 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: cad0dd1bd16747a5e76e10784d00c14cd9aa8c2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729574"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="5798b-103">데이터 세트에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="5798b-103">Adding Existing Constraints to a DataSet</span></span>

<span data-ttu-id="5798b-104">**DataAdapter** 의 **Fill** 메서드는 <xref:System.Data.DataSet> 데이터 원본의 테이블 열과 행만 사용 하 여를 채웁니다. 제약 조건은 일반적으로 데이터 원본에 의해 설정 되지만 **Fill** 메서드는 기본적으로이 스키마 정보를 데이터 **집합** 에 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-104">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="5798b-105">데이터 원본의 기존 기본 키 제약 조건 정보를 사용 하 여 데이터 **집합** 을 채우려면 **dataadapter** 의 **FillSchema** 메서드를 호출 하거나 **Fill** 을 호출 하기 전에 **dataadapter** 의 **MissingSchemaAction** 속성을 **AddWithKey** 로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-105">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="5798b-106">이렇게 하면 **DataSet** 의 기본 키 제약 조건이 데이터 원본의 해당 제약 조건을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-106">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="5798b-107">Foreign key 제약 조건 정보는 포함 되지 않으며 [DataTable 제약 조건](./dataset-datatable-dataview/datatable-constraints.md)에 표시 된 대로 명시적으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-107">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
<span data-ttu-id="5798b-108">**DataSet** 를 데이터로 채우기 전에 스키마 정보를 추가하면 기본 키 제약 조건이 <xref:System.Data.DataTable> 개체와 함께 **DataSet** 에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-108">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="5798b-109">결과적으로 **DataSet** 의 Fill에 대한 추가 호출이 있으면 기본 키 열 정보를 사용하여 데이터 원본의 새 행을 각 **DataTable** 의 현재 행과 일치시키고 해당 테이블의 현재 데이터를 데이터 원본의 데이터로 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-109">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="5798b-110">스키마 정보가 없으면 데이터 원본의 새 행이 **DataSet** 에 추가되어 결국 행이 중복됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-110">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5798b-111">데이터 원본의 열이 자동 증가, **FillSchema** 메서드 또는 **Fill** 메서드 ( **MissingSchemaAction** **AddWithKey**)로 식별 되 면 **AutoIncrement** 속성이로 설정 된 **DataColumn** 을 만듭니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="5798b-111">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="5798b-112">그러나 **AutoIncrementStep** 및 **AutoIncrementSeed** 값은 직접 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-112">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="5798b-113">자동 증분 열에 대 한 자세한 내용은 [AutoIncrement 열 만들기](./dataset-datatable-dataview/creating-autoincrement-columns.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5798b-113">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
<span data-ttu-id="5798b-114">**FillSchema** 를 사용하거나 **MissingSchemaAction** 을 **AddWithKey** 로 설정하려면 기본 키 열 정보를 확인하기 위해 데이터 원본에서 추가 처리를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-114">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="5798b-115">이러한 추가 처리로 인해 성능이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-115">This additional processing can hinder performance.</span></span> <span data-ttu-id="5798b-116">디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-116">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="5798b-117">테이블에 대 한 기본 키 정보를 명시적으로 설정 하는 방법에 대 한 자세한 내용은 [기본 키 정의](./dataset-datatable-dataview/defining-primary-keys.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5798b-117">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>
  
<span data-ttu-id="5798b-118">다음 코드 예제에서는 **FillSchema** 를 사용 하 여 **데이터 집합** 에 스키마 정보를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-118">The following code example shows how to add schema information to a **DataSet** using **FillSchema**:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
<span data-ttu-id="5798b-119">다음 코드 예제에서는 **Fill** 메서드의 **MissingSchemaAction. AddWithKey** 속성을 사용 하 여 **데이터 집합** 에 스키마 정보를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-119">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="5798b-120">다중 결과 집합 처리</span><span class="sxs-lookup"><span data-stu-id="5798b-120">Handling multiple result sets</span></span>  

<span data-ttu-id="5798b-121">**DataAdapter** 가 **SelectCommand** 에서 반환 된 여러 결과 집합을 발견 하는 경우 **데이터 집합** 에 여러 개의 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-121">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="5798b-122">테이블에는 0부터 시작하되 “Table0”이 아니라 **Table** 로 시작하는 증분 기본 이름 **Table** *N* 이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-122">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="5798b-123">테이블 이름이 **FillSchema** 메서드에 인수로 전달 되는 경우 테이블에는 0부터 시작 하는 증분 이름 (예를 들어, "TableName0  " 대신 **tablename** *으로 시작*)이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-123">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5798b-124">여러 결과 집합을 반환 하는 명령에 대해 **OleDbDataAdapter** 개체의 **FillSchema** 메서드를 호출 하면 첫 번째 결과 집합의 스키마 정보만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-124">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="5798b-125">**OleDbDataAdapter** 를 사용 하 여 여러 결과 집합에 대 한 스키마 정보를 반환 하는 경우 **MissingSchemaAction** 의 **AddWithKey** 를 지정 하 고 **Fill** 메서드를 호출할 때 스키마 정보를 가져오는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5798b-125">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5798b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5798b-126">See also</span></span>

- [<span data-ttu-id="5798b-127">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="5798b-127">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="5798b-128">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="5798b-128">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="5798b-129">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="5798b-129">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="5798b-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="5798b-130">ADO.NET Overview</span></span>](ado-net-overview.md)
