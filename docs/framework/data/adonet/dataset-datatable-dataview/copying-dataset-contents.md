---
title: 데이터 세트 콘텐츠 복사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 1cadcacab6084bbf3caaf61d98b78fe3067d92f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202372"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="ad278-102">데이터 세트 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="ad278-102">Copying DataSet Contents</span></span>

<span data-ttu-id="ad278-103"><xref:System.Data.DataSet>원본 데이터에 영향을 주지 않고 데이터 작업을 수행 하거나 데이터 **집합**에서 데이터의 하위 집합을 사용 하 여 작업을 수행할 수 있도록의 복사본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="ad278-104">**데이터 집합**을 복사할 때 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="ad278-105">스키마, 데이터, 행 상태 정보 및 행 버전을 포함 하 여 **데이터 집합**의 정확한 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="ad278-106">기존 **데이터 집합**의 스키마를 포함 하지만 수정 된 행만 포함 하는 **데이터 집합** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="ad278-107">수정 된 모든 행을 반환 하거나 특정 **DataRowState**을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="ad278-108">행 상태에 대 한 자세한 내용은 [행 상태 및 행 버전](row-states-and-row-versions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad278-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="ad278-109">행을 복사 하지 않고 **데이터 집합** 의 스키마 또는 관계형 구조만 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="ad278-110"><xref:System.Data.DataTable>를 사용하여 행을 기존 <xref:System.Data.DataTable.ImportRow%2A>로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="ad278-111">스키마와 데이터를 모두 포함 하는 데이터 **집합** 의 정확한 복사본을 만들려면 <xref:System.Data.DataSet.Copy%2A> **데이터 집합**의 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad278-112">다음 코드 예제에서는 **데이터 집합**의 정확한 복사본을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="ad278-113">스키마를 포함 하 고 **추가**, **수정**또는 **삭제** 된 행을 나타내는 데이터만 포함 하는 데이터 **집합** 의 복사본을 만들려면 <xref:System.Data.DataSet.GetChanges%2A> **데이터 집합**의 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad278-114">**GetChanges** 를 사용 하 여 **GetChanges**를 호출할 때 **DataRowState** 값을 전달 하 여 지정 된 행 상태의 행만 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="ad278-115">다음 코드 예제에서는 **GetChanges**를 호출할 때 **DataRowState** 를 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="ad278-116">스키마만 포함 하는 **데이터 집합** 의 복사본을 만들려면 <xref:System.Data.DataSet.Clone%2A> **dataset**의 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad278-117">또한 **DataTable**의 **ImportRow** 메서드를 사용 하 여 복제 된 **데이터 집합** 에 기존 행을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="ad278-118">**ImportRow** 는 지정 된 테이블에 데이터, 행 상태 및 행 버전 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="ad278-119">열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="ad278-120">다음 코드 예에서는 **데이터 집합** 의 복제본을 만든 다음 원래 **데이터 집합** 의 행을 **CountryRegion** 열 값이 "독일" 인 고객에 대 한 **데이터 집합** 복제본의 **customers** 테이블에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad278-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad278-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad278-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ad278-122">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="ad278-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="ad278-123">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ad278-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
