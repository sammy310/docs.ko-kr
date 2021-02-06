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
# <a name="viewing-data-in-a-datatable"></a>DataTable에서 데이터 보기

<xref:System.Data.DataTable> **DataTable** 의 **Rows** 및 **Columns** 컬렉션을 사용 하 여의 내용에 액세스할 수 있습니다. 메서드를 사용 하 여 <xref:System.Data.DataTable.Select%2A> 검색 조건, 정렬 순서 및 행 상태를 포함 한 조건에 따라 **DataTable** 의 데이터 하위 집합을 반환할 수도 있습니다. 또한 <xref:System.Data.DataRowCollection.Find%2A> 기본 키 값을 사용 하 여 특정 행을 검색할 때 **DataRowCollection** 의 메서드를 사용할 수 있습니다.

**DataTable** 개체의 **Select** 메서드는 <xref:System.Data.DataRow> 지정 된 조건과 일치 하는 개체 집합을 반환 합니다. **Select** 는 필터 식, 정렬 식 및 **DataViewRowState** 의 선택적 인수를 사용 합니다. 필터 식은 **DataColumn** 값 (예:)을 기반으로 반환 되는 행을 식별 합니다 `LastName = 'Smith'` . 정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다. 식 작성에 대 한 규칙은 <xref:System.Data.DataColumn.Expression%2A> **DataColumn** 클래스의 속성을 참조 하세요.

> [!TIP]
> **Datatable** 의 **Select** 메서드에 대 한 호출을 여러 개 수행 하는 경우 먼저 <xref:System.Data.DataView> **datatable** 에 대해를 만들어 성능을 향상 시킬 수 있습니다. **DataView** 를 만들면 테이블의 행이 인덱싱합니다. 그런 다음 **Select** 메서드는 해당 인덱스를 사용 하 여 쿼리 결과를 생성 하는 시간을 크게 줄입니다. **DataTable** 에 대해 **DataView** 를 만드는 방법에 대 한 자세한 내용은 [dataviews](dataviews.md)를 참조 하세요.

**Select** 메서드는를 기준으로 보거나 조작할 행의 버전을 결정 합니다 <xref:System.Data.DataViewRowState> . 다음 표에서는 가능한 **DataViewRowState** 열거형 값에 대해 설명 합니다.

|DataViewRowState 값|설명|
|----------------------------|-----------------|
|**CurrentRows**|변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행|
|**삭제됨**|삭제된 행입니다.|
|**ModifiedCurrent**|원래 데이터가 수정된 현재 버전 **ModifiedOriginal** 를 참조 하세요.|
|**ModifiedOriginal**|수정된 모든 행의 원래 버전. **ModifiedCurrent** 를 사용 하 여 현재 버전을 사용할 수 있습니다.|
|**추가됨**|새 행입니다.|
|**없음**|없음|
|**OriginalRows**|변경되지 않거나 삭제된 행을 포함하는 원래 행|
|**변경 안 됨**|변경되지 않은 행입니다.|

다음 예에서는 **DataViewRowState** 이 **currentrows** 로 설정 된 행만 사용 하도록 **DataSet** 개체를 필터링 합니다.

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

**Select** 메서드는 서로 다른 **RowState** 값 또는 필드 값을 가진 행을 반환 하는 데 사용할 수 있습니다. 다음 예에서는 삭제 된 모든 행을 참조 하는 **datarow** 배열을 반환 하 고, **배열은 custlname** 를 기준으로 정렬 된 모든 행을 참조 하는 다른 **datarow** 배열을 반환 합니다. 여기서 **CustID** 열은 5 보다 큽니다. **삭제** 된 행의 정보를 보는 방법에 대 한 자세한 내용은 [행 상태 및 행 버전](row-states-and-row-versions.md)을 참조 하세요.

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

## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [DataTable에서 데이터 조작](manipulating-data-in-a-datatable.md)
- [행 상태 및 행 버전](row-states-and-row-versions.md)
- [ADO.NET 개요](../ado-net-overview.md)
