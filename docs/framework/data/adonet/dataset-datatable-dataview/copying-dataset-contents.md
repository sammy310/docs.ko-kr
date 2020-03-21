---
title: 데이터 세트 콘텐츠 복사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151366"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="8476b-102">데이터 세트 콘텐츠 복사</span><span class="sxs-lookup"><span data-stu-id="8476b-102">Copying DataSet Contents</span></span>
<span data-ttu-id="8476b-103">원본 데이터에 영향을 주지 <xref:System.Data.DataSet> 않고 데이터로 작업하거나 **DataSet에서**데이터의 하위 집합으로 작업할 수 있도록 a의 복사본을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="8476b-104">**데이터 집합을**복사할 때 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="8476b-105">스키마, 데이터, 행 상태 정보 및 행 버전을 포함하여 **DataSet의**정확한 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="8476b-106">기존 **DataSet의** 스키마를 포함하지만 수정된 행만 포함하는 **DataSet을**만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="8476b-107">수정된 모든 행을 반환하거나 특정 **DataRowState**를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="8476b-108">행 상태에 대한 자세한 내용은 [행 상태 및 행 버전을](row-states-and-row-versions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8476b-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="8476b-109">행을 복사하지 않고 **DataSet의** 스키마 또는 관계형 구조만 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="8476b-110"><xref:System.Data.DataTable>를 사용하여 행을 기존 <xref:System.Data.DataTable.ImportRow%2A>로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="8476b-111">스키마와 데이터를 모두 포함하는 **DataSet의** 정확한 복사본을 만들려면 <xref:System.Data.DataSet.Copy%2A> **DataSet**의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="8476b-112">다음 코드 예제에서는 **DataSet**의 정확한 복사본을 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="8476b-113">스키마를 포함하는 **DataSet의** 복사본을 만들고 **추가됨,** **수정됨**또는 **삭제된** 행을 나타내는 데이터만 만들려면 <xref:System.Data.DataSet.GetChanges%2A> **DataSet**의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="8476b-114">GetChanges를 사용하여 **GetChanges** 를 호출할 때 **DataRowState** 값을 전달하여 지정된 행 상태의 행만 반환할 수도 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8476b-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="8476b-115">다음 코드 예제에서는 **GetChanges**를 호출할 때 **DataRowState를** 전달하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="8476b-116">스키마만 포함하는 **DataSet의** 복사본을 만들려면 <xref:System.Data.DataSet.Clone%2A> **DataSet**의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="8476b-117">DataTable 의 **ImportRow** 메서드를 사용하여 복제된 **DataSet에** 기존 행을 추가할 수도 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8476b-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="8476b-118">**ImportRow** 는 지정된 테이블에 데이터, 행 상태 및 행 버전 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="8476b-119">열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="8476b-120">다음 코드 예제에서는 **DataSet의** 복제본을 만들고 원래 **DataSet의** 행을 **DataSet** 복제의 **고객** 테이블에 추가하여 **CountryRegion** 열에 "독일" 값이 있는 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8476b-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8476b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8476b-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="8476b-122">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="8476b-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8476b-123">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="8476b-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
