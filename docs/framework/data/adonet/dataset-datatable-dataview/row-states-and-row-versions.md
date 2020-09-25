---
title: 행 상태 및 행 버전
ms.date: 07/19/2018
dev_langs:
- csharp
- vb
ms.assetid: 2e6642c9-bfc6-425c-b3a7-e4912ffa6c1f
ms.openlocfilehash: 1b80ae78fad22989f99fb1e992d4978a192e0c66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204530"
---
# <a name="row-states-and-row-versions"></a><span data-ttu-id="9dd11-102">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="9dd11-102">Row States and Row Versions</span></span>

<span data-ttu-id="9dd11-103">ADO.NET에서는 행 상태 및 버전을 사용하여 테이블의 행을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-103">ADO.NET manages rows in tables using row states and versions.</span></span> <span data-ttu-id="9dd11-104">행 상태는 행의 상태를 나타내며, 행 버전에서는 현재 값, 원래 값 및 기본값 등과 같이 수정될 때 행에 저장된 값을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-104">A row state indicates the status of a row; row versions maintain the values stored in a row as it is modified, including current, original, and default values.</span></span> <span data-ttu-id="9dd11-105">예를 들어, 행에서 열을 수정한 경우 이 행의 상태는 `Modified`가 되고 두 개의 행 버전이 존재하게 됩니다. 즉, `Current` 버전에는 현재의 행 값이 포함되고 `Original` 버전에는 열이 수정되기 전의 행 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-105">For example, after you have made a modification to a column in a row, the row will have a row state of `Modified`, and two row versions: `Current`, which contains the current row values, and `Original`, which contains the row values before the column was modified.</span></span>  
  
 <span data-ttu-id="9dd11-106">각 <xref:System.Data.DataRow> 개체에는 <xref:System.Data.DataRow.RowState%2A> 속성이 있어서 사용자는 이 속성을 검사하여 행의 현재 상태를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-106">Each <xref:System.Data.DataRow> object has a <xref:System.Data.DataRow.RowState%2A> property that you can examine to determine the current state of the row.</span></span> <span data-ttu-id="9dd11-107">다음 표에서는 각 `RowState` 열거형 값에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-107">The following table gives a brief description of each `RowState` enumeration value.</span></span>  
  
|<span data-ttu-id="9dd11-108">RowState 값</span><span class="sxs-lookup"><span data-stu-id="9dd11-108">RowState value</span></span>|<span data-ttu-id="9dd11-109">설명</span><span class="sxs-lookup"><span data-stu-id="9dd11-109">Description</span></span>|  
|--------------------|-----------------|  
|<xref:System.Data.DataRowState.Unchanged>|<span data-ttu-id="9dd11-110">`AcceptChanges`를 마지막으로 호출한 이후 또는 `DataAdapter.Fill`에 의해서 행이 만들어진 이후로 변경된 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-110">No changes have been made since the last call to `AcceptChanges` or since the row was created by `DataAdapter.Fill`.</span></span>|  
|<xref:System.Data.DataRowState.Added>|<span data-ttu-id="9dd11-111">테이블에 행이 추가되었지만 `AcceptChanges`가 호출되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-111">The row has been added to the table, but `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Modified>|<span data-ttu-id="9dd11-112">일부 행 요소가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-112">Some element of the row has been changed.</span></span>|  
|<xref:System.Data.DataRowState.Deleted>|<span data-ttu-id="9dd11-113">행이 테이블에서 삭제되었으며 `AcceptChanges`가 호출되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-113">The row has been deleted from a table, and `AcceptChanges` has not been called.</span></span>|  
|<xref:System.Data.DataRowState.Detached>|<span data-ttu-id="9dd11-114">행이 `DataRowCollection`의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-114">The row is not part of any `DataRowCollection`.</span></span> <span data-ttu-id="9dd11-115">새로 만든 행의 `RowState`가 `Detached`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-115">The `RowState` of a newly created row is set to `Detached`.</span></span> <span data-ttu-id="9dd11-116">`DataRow` 메서드를 호출하여 새 `DataRowCollection`를 `Add`에 추가한 후에는 `RowState` 속성 값이 `Added`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-116">After the new `DataRow` is added to the `DataRowCollection` by calling the `Add` method, the value of the `RowState` property is set to `Added`.</span></span><br /><br /> <span data-ttu-id="9dd11-117">`Detached` 메서드를 사용하거나 `DataRowCollection` 메서드를 사용한 후 `Remove` 메서드를 사용하여 `Delete`에서 제거된 행에 대해서도 이 속성이 `AcceptChanges`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-117">`Detached` is also set for a row that has been removed from a `DataRowCollection` using the `Remove` method, or by the `Delete` method followed by the `AcceptChanges` method.</span></span>|  
  
 <span data-ttu-id="9dd11-118">`AcceptChanges`, <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>에 대해 <xref:System.Data.DataRow>가 호출되는 경우 행 상태가 `Deleted`인 행은 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-118">When `AcceptChanges` is called on a <xref:System.Data.DataSet>, <xref:System.Data.DataTable> , or <xref:System.Data.DataRow>, all rows with a row state of `Deleted` are removed.</span></span> <span data-ttu-id="9dd11-119">나머지 행의 상태는 `Unchanged`로 지정되며 `Original` 행 버전의 값은 `Current` 행 버전의 값으로 덮어쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-119">The remaining rows are given a row state of `Unchanged`, and the values in the `Original` row version are overwritten with the `Current` row version values.</span></span> <span data-ttu-id="9dd11-120">`RejectChanges`가 호출되는 경우 행 상태가 `Added`인 행은 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-120">When `RejectChanges` is called, all rows with a row state of `Added` are removed.</span></span> <span data-ttu-id="9dd11-121">나머지 행의 상태는 `Unchanged`로 지정되며 `Current` 행 버전의 값은 `Original` 행 버전의 값으로 덮어쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-121">The remaining rows are given a row state of `Unchanged`, and the values in the `Current` row version are overwritten with the `Original` row version values.</span></span>  
  
 <span data-ttu-id="9dd11-122">다음 예제와 같이 열 참조와 함께 <xref:System.Data.DataRowVersion> 매개 변수를 전달하면 행의 다른 행 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-122">You can view the different row versions of a row by passing a <xref:System.Data.DataRowVersion> parameter with the column reference, as shown in the following example.</span></span>  
  
```vb  
Dim custRow As DataRow = custTable.Rows(0)  
Dim custID As String = custRow("CustomerID", DataRowVersion.Original).ToString()  
```  
  
```csharp  
DataRow custRow = custTable.Rows[0];  
string custID = custRow["CustomerID", DataRowVersion.Original].ToString();  
```  
  
 <span data-ttu-id="9dd11-123">다음 표에서는 각 `DataRowVersion` 열거형 값에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-123">The following table gives a brief description of each `DataRowVersion` enumeration value.</span></span>  
  
|<span data-ttu-id="9dd11-124">DataRowVersion 값</span><span class="sxs-lookup"><span data-stu-id="9dd11-124">DataRowVersion value</span></span>|<span data-ttu-id="9dd11-125">설명</span><span class="sxs-lookup"><span data-stu-id="9dd11-125">Description</span></span>|  
|--------------------------|-----------------|  
|<xref:System.Data.DataRowVersion.Current>|<span data-ttu-id="9dd11-126">행의 현재 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-126">The current values for the row.</span></span> <span data-ttu-id="9dd11-127">`RowState`가 `Deleted`인 행에는 이 행 버전이 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-127">This row version does not exist for rows with a `RowState` of `Deleted`.</span></span>|  
|<xref:System.Data.DataRowVersion.Default>|<span data-ttu-id="9dd11-128">특정 행에 대한 기본 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-128">The default row version for a particular row.</span></span> <span data-ttu-id="9dd11-129">`Added`, `Modified` 또는 `Deleted` 행의 기본 행 버전은 `Current`이고,</span><span class="sxs-lookup"><span data-stu-id="9dd11-129">The default row version for an `Added`, `Modified`, or `Deleted` row is `Current`.</span></span> <span data-ttu-id="9dd11-130">`Detached` 행의 기본 행 버전은 `Proposed`입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-130">The default row version for a `Detached` row is `Proposed`.</span></span>|  
|<xref:System.Data.DataRowVersion.Original>|<span data-ttu-id="9dd11-131">행의 원래 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-131">The original values for the row.</span></span> <span data-ttu-id="9dd11-132">`RowState`가 `Added`인 행에는 이 행 버전이 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-132">This row version does not exist for rows with a `RowState` of `Added`.</span></span>|  
|<xref:System.Data.DataRowVersion.Proposed>|<span data-ttu-id="9dd11-133">행에 제안된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-133">The proposed values for the row.</span></span> <span data-ttu-id="9dd11-134">이 행 버전은 행에서 편집 작업을 수행하는 동안 존재하거나 `DataRowCollection`의 일부가 아닌 행에 대해 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-134">This row version exists during an edit operation on a row, or for a row that is not part of a `DataRowCollection`.</span></span>|  
  
 <span data-ttu-id="9dd11-135">`DataRow`을 인수로 전달하여 <xref:System.Data.DataRow.HasVersion%2A> 메서드를 호출하면 `DataRowVersion`에 특정 행 버전이 있는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-135">You can test whether a `DataRow` has a particular row version by calling the <xref:System.Data.DataRow.HasVersion%2A> method and passing a `DataRowVersion` as an argument.</span></span> <span data-ttu-id="9dd11-136">예를 들어, `DataRow.HasVersion(DataRowVersion.Original)`은 `false`가 호출되기 전에 새로 추가된 행에 대해 `AcceptChanges`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-136">For example, `DataRow.HasVersion(DataRowVersion.Original)` will return `false` for newly added rows before `AcceptChanges` has been called.</span></span>  
  
 <span data-ttu-id="9dd11-137">다음 코드 예제에서는 테이블에서 삭제된 모든 행의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-137">The following code example displays the values in all the deleted rows of a table.</span></span> <span data-ttu-id="9dd11-138">`Deleted` 행에는 `Current` 행 버전이 없으므로 해당 열 값에 액세스할 때는 `DataRowVersion.Original`을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dd11-138">`Deleted` rows do not have a `Current` row version, so you must pass `DataRowVersion.Original` when accessing the column values.</span></span>  
  
```vb  
Dim catTable As DataTable = catDS.Tables("Categories")  
  
Dim delRows() As DataRow = catTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
Console.WriteLine("Deleted rows:" & vbCrLf)  
  
Dim catCol As DataColumn  
Dim delRow As DataRow  
  
For Each catCol In catTable.Columns  
  Console.Write(catCol.ColumnName & vbTab)  
Next  
Console.WriteLine()  
  
For Each delRow In delRows  
  For Each catCol In catTable.Columns  
    Console.Write(delRow(catCol, DataRowVersion.Original) & vbTab)  
  Next  
  Console.WriteLine()  
Next  
```  
  
```csharp  
DataTable catTable = catDS.Tables["Categories"];  
  
DataRow[] delRows = catTable.Select(null, null, DataViewRowState.Deleted);  
  
Console.WriteLine("Deleted rows:\n");  
  
foreach (DataColumn catCol in catTable.Columns)  
  Console.Write(catCol.ColumnName + "\t");  
Console.WriteLine();  
  
foreach (DataRow delRow in delRows)  
{  
  foreach (DataColumn catCol in catTable.Columns)  
    Console.Write(delRow[catCol, DataRowVersion.Original] + "\t");  
  Console.WriteLine();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9dd11-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dd11-139">See also</span></span>

- [<span data-ttu-id="9dd11-140">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="9dd11-140">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="9dd11-141">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="9dd11-141">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="9dd11-142">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="9dd11-142">DataAdapters and DataReaders</span></span>](../dataadapters-and-datareaders.md)
- [<span data-ttu-id="9dd11-143">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="9dd11-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
