---
title: DataTable에서 데이터 보기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: fa8749550e10256ee0623714cc95e03a838655c8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364491"
---
# <a name="viewing-data-in-a-datatable"></a>DataTable에서 데이터 보기

내용에 액세스할 수 있습니다는 <xref:System.Data.DataTable> 를 사용 하 여는 **행** 및 **열** 컬렉션을 **DataTable**합니다. 사용할 수도 있습니다는 <xref:System.Data.DataTable.Select%2A> 에 있는 데이터의 하위 집합을 반환 하는 방법을 **DataTable** 기준 검색 조건을 포함 하 여 정렬 순서 및 행 상태입니다. 또한 사용할 수는 <xref:System.Data.DataRowCollection.Find%2A> 메서드를 **DataRowCollection** 기본 키 값을 사용 하 여 특정 행을 검색할 때.

합니다 **선택** 메서드를 **DataTable** 개체 집합을 반환 <xref:System.Data.DataRow> 지정된 된 조건과 일치 하는 개체입니다. **선택** 필터 식, 정렬 식의 선택적 인수를 사용 하 고 **DataViewRowState**합니다. 필터 식에 따라 반환 하는 행 식별 **DataColumn** 와 같은 값 `LastName = 'Smith'`합니다. 정렬 식은 열 정렬에 표준 SQL 규칙을 사용하며, 이 식은 `LastName ASC, FirstName ASC`와 같이 표현됩니다. 식을 작성 하는 방법에 대 한 규칙을 참조 하세요. 합니다 <xref:System.Data.DataColumn.Expression%2A> 의 속성을 **DataColumn** 클래스입니다.

> [!TIP]
> 숫자에 대 한 호출을 수행 하는 경우는 **선택** 메서드를 **DataTable**, 처음 생성 하 여 성능을 향상 시킬 수 있습니다를 <xref:System.Data.DataView> 에 대 한를 **DataTable**합니다. 만들기는 **DataView** 테이블의 행 인덱스입니다. 합니다 **선택** 메서드는 쿼리 결과 생성 하는 시간을 크게 줄일 해당 인덱스를 사용 하 여 합니다. 만들기에 대 한 자세한를 **DataView** 에 대 한를 **DataTable**를 참조 하십시오 [Dataview](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).

합니다 **선택** 메서드를 보거나 조작 하려는 행의 버전에 따라 결정을 <xref:System.Data.DataViewRowState>입니다. 다음 표에서 가능한 **DataViewRowState** 열거형 값입니다.

|DataViewRowState 값|설명|
|----------------------------|-----------------|
|**CurrentRows**|변경되지 않거나 추가되거나 수정된 행을 포함하는 현재 행|
|**삭제**|삭제된 행|
|**ModifiedCurrent**|원래 데이터가 수정된 현재 버전 (참조 **ModifiedOriginal**.)|
|**ModifiedOriginal**|수정된 모든 행의 원래 버전. 현재 버전은 사용할 **ModifiedCurrent**합니다.|
|**추가**|새 행|
|**없음**|없음|
|**OriginalRows**|변경되지 않거나 삭제된 행을 포함하는 원래 행|
|**Unchanged**|변경되지 않은 행|

다음 예제에서는 **데이터 집합** 개체 에서만 사용 하는 행 인 하도록 필터링 됩니다 **DataViewRowState** 로 설정 되어 **CurrentRows**합니다.

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

합니다 **선택** 메서드를 사용 하 여 다른 행을 반환할 수 있습니다 **RowState** 값 또는 필드 값입니다. 다음 예는 **DataRow** 삭제 되었거나 다른 반환 하는 모든 행을 참조 하는 배열 **DataRow** 배열의 모든 행을 참조 하는 기준으로 정렬 된 **에서는**여기서는 **CustID** 열이 5 보다 큽니다. 정보를 보는 방법에 대 한 자세한 합니다 **Deleted** 행을 참조 하세요 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.

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

## <a name="see-also"></a>참고자료

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
