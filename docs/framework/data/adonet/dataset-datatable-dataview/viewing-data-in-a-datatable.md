---
description: '자세한 정보: DataTable의 데이터 보기'
title: DataTable에서 데이터 보기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: ffaa8283da17c98fc58486af8dad741a61bbafc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651381"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="2d658-103">DataTable에서 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="2d658-103">Viewing Data in a DataTable</span></span>

<span data-ttu-id="2d658-104"><xref:System.Data.DataTable> **DataTable** 의 **Rows** 및 **Columns** 컬렉션을 사용 하 여의 내용에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-104">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="2d658-105">메서드를 사용 하 여 <xref:System.Data.DataTable.Select%2A> 검색 조건, 정렬 순서 및 행 상태를 포함 한 조건에 따라 **DataTable** 의 데이터 하위 집합을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-105">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="2d658-106">또한 <xref:System.Data.DataRowCollection.Find%2A> 기본 키 값을 사용 하 여 특정 행을 검색할 때 **DataRowCollection** 의 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-106">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="2d658-107">**DataTable** 개체의 **Select** 메서드는 <xref:System.Data.DataRow> 지정 된 조건과 일치 하는 개체 집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-107">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="2d658-108">**Select** 는 필터 식, 정렬 식 및 **DataViewRowState** 의 선택적 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-108">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="2d658-109">필터 식은 **DataColumn** 값 (예:)을 기반으로 반환 되는 행을 식별 합니다 `LastName = 'Smith'` .</span><span class="sxs-lookup"><span data-stu-id="2d658-109">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="2d658-110">정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-110">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="2d658-111">식 작성에 대 한 규칙은 <xref:System.Data.DataColumn.Expression%2A> **DataColumn** 클래스의 속성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d658-111">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="2d658-112">**Datatable** 의 **Select** 메서드에 대 한 호출을 여러 개 수행 하는 경우 먼저 <xref:System.Data.DataView> **datatable** 에 대해를 만들어 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-112">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="2d658-113">**DataView** 를 만들면 테이블의 행이 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-113">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="2d658-114">그런 다음 **Select** 메서드는 해당 인덱스를 사용 하 여 쿼리 결과를 생성 하는 시간을 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-114">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="2d658-115">**DataTable** 에 대해 **DataView** 를 만드는 방법에 대 한 자세한 내용은 [dataviews](dataviews.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d658-115">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="2d658-116">**Select** 메서드는를 기준으로 보거나 조작할 행의 버전을 결정 합니다 <xref:System.Data.DataViewRowState> .</span><span class="sxs-lookup"><span data-stu-id="2d658-116">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="2d658-117">다음 표에서는 가능한 **DataViewRowState** 열거형 값에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-117">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="2d658-118">DataViewRowState 값</span><span class="sxs-lookup"><span data-stu-id="2d658-118">DataViewRowState value</span></span>|<span data-ttu-id="2d658-119">설명</span><span class="sxs-lookup"><span data-stu-id="2d658-119">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="2d658-120">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="2d658-120">**CurrentRows**</span></span>|<span data-ttu-id="2d658-121">변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행</span><span class="sxs-lookup"><span data-stu-id="2d658-121">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="2d658-122">**삭제됨**</span><span class="sxs-lookup"><span data-stu-id="2d658-122">**Deleted**</span></span>|<span data-ttu-id="2d658-123">삭제된 행입니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-123">A deleted row.</span></span>|
|<span data-ttu-id="2d658-124">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="2d658-124">**ModifiedCurrent**</span></span>|<span data-ttu-id="2d658-125">원래 데이터가 수정된 현재 버전</span><span class="sxs-lookup"><span data-stu-id="2d658-125">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="2d658-126">**ModifiedOriginal** 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d658-126">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="2d658-127">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="2d658-127">**ModifiedOriginal**</span></span>|<span data-ttu-id="2d658-128">수정된 모든 행의 원래 버전.</span><span class="sxs-lookup"><span data-stu-id="2d658-128">The original version of all modified rows.</span></span> <span data-ttu-id="2d658-129">**ModifiedCurrent** 를 사용 하 여 현재 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-129">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="2d658-130">**추가됨**</span><span class="sxs-lookup"><span data-stu-id="2d658-130">**Added**</span></span>|<span data-ttu-id="2d658-131">새 행입니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-131">A new row.</span></span>|
|<span data-ttu-id="2d658-132">**없음**</span><span class="sxs-lookup"><span data-stu-id="2d658-132">**None**</span></span>|<span data-ttu-id="2d658-133">없음</span><span class="sxs-lookup"><span data-stu-id="2d658-133">None.</span></span>|
|<span data-ttu-id="2d658-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="2d658-134">**OriginalRows**</span></span>|<span data-ttu-id="2d658-135">변경되지 않거나 삭제된 행을 포함하는 원래 행</span><span class="sxs-lookup"><span data-stu-id="2d658-135">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="2d658-136">**변경 안 됨**</span><span class="sxs-lookup"><span data-stu-id="2d658-136">**Unchanged**</span></span>|<span data-ttu-id="2d658-137">변경되지 않은 행입니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-137">An unchanged row.</span></span>|

<span data-ttu-id="2d658-138">다음 예에서는 **DataViewRowState** 이 **currentrows** 로 설정 된 행만 사용 하도록 **DataSet** 개체를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-138">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="2d658-139">**Select** 메서드는 서로 다른 **RowState** 값 또는 필드 값을 가진 행을 반환 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-139">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="2d658-140">다음 예에서는 삭제 된 모든 행을 참조 하는 **datarow** 배열을 반환 하 고, **배열은 custlname** 를 기준으로 정렬 된 모든 행을 참조 하는 다른 **datarow** 배열을 반환 합니다. 여기서 **CustID** 열은 5 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="2d658-140">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="2d658-141">**삭제** 된 행의 정보를 보는 방법에 대 한 자세한 내용은 [행 상태 및 행 버전](row-states-and-row-versions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2d658-141">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2d658-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d658-142">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="2d658-143">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="2d658-143">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="2d658-144">행 상태 및 행 버전</span><span class="sxs-lookup"><span data-stu-id="2d658-144">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="2d658-145">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="2d658-145">ADO.NET Overview</span></span>](../ado-net-overview.md)
