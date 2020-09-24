---
title: DataRow 삭제
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153354"
---
# <a name="datarow-deletion"></a>DataRow 삭제

개체에서 개체를 삭제 하는 데 사용할 수 있는 두 가지 방법은 <xref:System.Data.DataRow> <xref:System.Data.DataTable> 개체의 **Remove** 메서드와 <xref:System.Data.DataRowCollection> <xref:System.Data.DataRow.Delete%2A> **DataRow** 개체의 메서드를 사용 하는 것입니다. <xref:System.Data.DataRowCollection.Remove%2A>메서드가 **DataRowCollection**에서 **DataRow** 를 삭제 하는 반면 메서드는 <xref:System.Data.DataRow.Delete%2A> 행을 삭제 하도록 표시 합니다. 실제 제거는 응용 프로그램이 **AcceptChanges** 메서드를 호출할 때 발생 합니다. <xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다. 삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.  
  
 <xref:System.Data.DataRow.Delete%2A> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRowCollection.Remove%2A> 또는 <xref:System.Data.DataRowCollection>가 호출되지 않아야 합니다. <xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>는 컬렉션의 상태를 수정하지 않습니다.  
  
 <xref:System.Data.DataSet> **DataAdapter** 및 관계형 데이터 원본과 함께 또는 **DataTable** 을 사용 하는 경우 **DataRow** 의 **Delete** 메서드를 사용 하 여 행을 제거 합니다. **Delete** 메서드는 **데이터 집합이** 나 **DataTable** 에서 행을 **삭제** 된 것으로 표시 하지만 제거 하지는 않습니다. 대신 **DataAdapter** 가 **Deleted**로 표시 된 행을 발견 하면 해당 **DeleteCommand** 메서드를 실행 하 여 데이터 소스에서 행을 삭제 합니다. 그런 다음 **AcceptChanges** 메서드를 사용 하 여 행을 영구적으로 제거할 수 있습니다. **제거** 를 사용 하 여 행을 삭제 하면 해당 행은 테이블에서 완전히 제거 되지만 **DataAdapter** 는 데이터 원본에서 행을 삭제 하지 않습니다.  
  
 **DataRowCollection** 의 **Remove** 메서드는 다음 예제와 같이 **DataRow** 를 인수로 사용 하 고 컬렉션에서 제거 합니다.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 반면, 다음 예제에서는 **DataRow** 에 대해 **Delete** 메서드를 호출 하 여 **RowState** 를 **deleted**로 변경 하는 방법을 보여 줍니다.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 행이 삭제 되도록 표시 되 고 **datatable** 개체의 **AcceptChanges** 메서드를 호출 하면 **datatable**에서 해당 행이 제거 됩니다. 반면 **RejectChanges**를 호출 하면 행의 **RowState** 가 **삭제**된 것으로 표시 되기 전의 상태로 돌아갑니다.  
  
> [!NOTE]
> **DataRow** 의 **RowState** 이 **추가**되 면 테이블에 추가 된 것을 의미 하 고 **삭제**된 것으로 표시 되 면 테이블에서 제거 됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [DataTable에서 데이터 조작](manipulating-data-in-a-datatable.md)
- [ADO.NET 개요](../ado-net-overview.md)
