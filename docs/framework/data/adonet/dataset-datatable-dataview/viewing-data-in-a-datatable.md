---
title: DataTable에서 데이터 보기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: fa8749550e10256ee0623714cc95e03a838655c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607033"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="05322-102">DataTable에서 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="05322-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="05322-103">내용에 액세스할 수 있습니다는 <xref:System.Data.DataTable> 를 사용 하 여는 **행** 및 **열** 컬렉션을 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="05322-104">사용할 수도 있습니다는 <xref:System.Data.DataTable.Select%2A> 에 있는 데이터의 하위 집합을 반환 하는 방법을 **DataTable** 기준 검색 조건을 포함 하 여 정렬 순서 및 행 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="05322-105">또한 사용할 수는 <xref:System.Data.DataRowCollection.Find%2A> 메서드를 **DataRowCollection** 기본 키 값을 사용 하 여 특정 행을 검색할 때.</span><span class="sxs-lookup"><span data-stu-id="05322-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="05322-106">합니다 **선택** 메서드를 **DataTable** 개체 집합을 반환 <xref:System.Data.DataRow> 지정된 된 조건과 일치 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="05322-107">**선택** 필터 식, 정렬 식의 선택적 인수를 사용 하 고 **DataViewRowState**합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="05322-108">필터 식에 따라 반환 하는 행 식별 **DataColumn** 와 같은 값 `LastName = 'Smith'`합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="05322-109">정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="05322-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="05322-110">식을 작성 하는 방법에 대 한 규칙을 참조 하세요. 합니다 <xref:System.Data.DataColumn.Expression%2A> 의 속성을 **DataColumn** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="05322-111">숫자에 대 한 호출을 수행 하는 경우는 **선택** 메서드를 **DataTable**, 처음 생성 하 여 성능을 향상 시킬 수 있습니다를 <xref:System.Data.DataView> 에 대 한를 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="05322-112">만들기는 **DataView** 테이블의 행 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="05322-113">합니다 **선택** 메서드는 쿼리 결과 생성 하는 시간을 크게 줄일 해당 인덱스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="05322-114">만들기에 대 한 자세한를 **DataView** 에 대 한를 **DataTable**를 참조 하십시오 [Dataview](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="05322-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>

<span data-ttu-id="05322-115">합니다 **선택** 메서드를 보거나 조작 하려는 행의 버전에 따라 결정을 <xref:System.Data.DataViewRowState>입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="05322-116">다음 표에서 가능한 **DataViewRowState** 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="05322-117">DataViewRowState 값</span><span class="sxs-lookup"><span data-stu-id="05322-117">DataViewRowState value</span></span>|<span data-ttu-id="05322-118">설명</span><span class="sxs-lookup"><span data-stu-id="05322-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="05322-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="05322-119">**CurrentRows**</span></span>|<span data-ttu-id="05322-120">변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행</span><span class="sxs-lookup"><span data-stu-id="05322-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="05322-121">**삭제**</span><span class="sxs-lookup"><span data-stu-id="05322-121">**Deleted**</span></span>|<span data-ttu-id="05322-122">삭제된 행</span><span class="sxs-lookup"><span data-stu-id="05322-122">A deleted row.</span></span>|
|<span data-ttu-id="05322-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="05322-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="05322-124">원래 데이터가 수정된 현재 버전</span><span class="sxs-lookup"><span data-stu-id="05322-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="05322-125">(참조 **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="05322-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="05322-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="05322-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="05322-127">수정된 모든 행의 원래 버전.</span><span class="sxs-lookup"><span data-stu-id="05322-127">The original version of all modified rows.</span></span> <span data-ttu-id="05322-128">현재 버전은 사용할 **ModifiedCurrent**합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="05322-129">**추가**</span><span class="sxs-lookup"><span data-stu-id="05322-129">**Added**</span></span>|<span data-ttu-id="05322-130">새 행</span><span class="sxs-lookup"><span data-stu-id="05322-130">A new row.</span></span>|
|<span data-ttu-id="05322-131">**없음**</span><span class="sxs-lookup"><span data-stu-id="05322-131">**None**</span></span>|<span data-ttu-id="05322-132">없음</span><span class="sxs-lookup"><span data-stu-id="05322-132">None.</span></span>|
|<span data-ttu-id="05322-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="05322-133">**OriginalRows**</span></span>|<span data-ttu-id="05322-134">변경되지 않거나 삭제된 행을 포함하는 원래 행</span><span class="sxs-lookup"><span data-stu-id="05322-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="05322-135">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="05322-135">**Unchanged**</span></span>|<span data-ttu-id="05322-136">변경되지 않은 행</span><span class="sxs-lookup"><span data-stu-id="05322-136">An unchanged row.</span></span>|

<span data-ttu-id="05322-137">다음 예제에서는 **데이터 집합** 개체 에서만 사용 하는 행 인 하도록 필터링 됩니다 **DataViewRowState** 로 설정 되어 **CurrentRows**합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

<span data-ttu-id="05322-138">합니다 **선택** 메서드를 사용 하 여 다른 행을 반환할 수 있습니다 **RowState** 값 또는 필드 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05322-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="05322-139">다음 예는 **DataRow** 삭제 되었거나 다른 반환 하는 모든 행을 참조 하는 배열 **DataRow** 배열의 모든 행을 참조 하는 기준으로 정렬 된 **에서는**여기서는 **CustID** 열이 5 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="05322-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="05322-140">정보를 보는 방법에 대 한 자세한 합니다 **Deleted** 행을 참조 하세요 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05322-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a><span data-ttu-id="05322-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="05322-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="05322-142">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="05322-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="05322-143">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="05322-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="05322-144">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="05322-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
