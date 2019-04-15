---
title: DataRow 삭제
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 57f51ada00bf24617ca3e295a010aae64f0aa849
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196140"
---
# <a name="datarow-deletion"></a>DataRow 삭제
두 가지 방법을 삭제 하는 데 사용할 수는 <xref:System.Data.DataRow> 에서 개체를 <xref:System.Data.DataTable> 개체:는 **제거** 메서드를 <xref:System.Data.DataRowCollection> 개체 및 <xref:System.Data.DataRow.Delete%2A> 메서드의 **DataRow**개체입니다. 반면 합니다 <xref:System.Data.DataRowCollection.Remove%2A> 메서드를 **DataRow** 에서 **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> 메서드는 삭제할 행을 표시만 합니다. 응용 프로그램 호출 때 실제 제거 합니다 **AcceptChanges** 메서드. <xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다. 삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.  
  
 <xref:System.Data.DataRow.Delete%2A> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRowCollection.Remove%2A> 또는 <xref:System.Data.DataRowCollection>가 호출되지 않아야 합니다. <xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A> 컬렉션의 상태를 수정 합니다.  
  
 사용 하는 경우는 <xref:System.Data.DataSet> 또는 **DataTable** 와 함께에서 **DataAdapter** 및 관계형 데이터 원본을 사용 하 여를 **삭제** 메서드를  **DataRow** 행을 제거 합니다. **삭제** 메서드는 해당 행을 표시 **Deleted** 에 **데이터 집합** 또는 **DataTable** 되지만 제거 되지는 않습니다. 대신, 합니다 **DataAdapter** 로 표시 된 행을 발견 하면 **삭제 됨**, 실행 해당 **DeleteCommand** 데이터 원본에서 행을 삭제 하는 방법. 행 후 영구적으로 제거할 수를 사용 하 여 **AcceptChanges** 메서드. 사용 하는 경우 **제거할** 행을 삭제 하려면 해당 행이 테이블에서 완전히 제거 되지만 **DataAdapter** 데이터 소스에서 행을 삭제 하지 것입니다.  
  
 **제거** 메서드를 **DataRowCollection** 사용을 **DataRow** 인수로 다음 예제에서와 같이 컬렉션에서 제거 합니다.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 반면, 다음 예제에서는 호출 하는 방법에 설명 합니다 **삭제** 메서드를를 **DataRow** 변경 하려면 해당 **RowState** 를 **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 행 삭제로 표시 되 고 호출 하는 경우는 **AcceptChanges** 메서드의 **DataTable** 개체에서 행이 제거 되는 **DataTable**합니다. 반대로, 호출 하는 경우 **RejectChanges**의 **RowState** 행의 되돌아갑니다로 표시 되기 전에 **Deleted**합니다.  
  
> [!NOTE]
>  경우는 **RowState** 의 **DataRow** 은 **Added**, 테이블에만 추가 되었습니다 의미 및 것으로 표시 됩니다 **Deleted**, 것 테이블에서 제거 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [DataTable에서 데이터 조작](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
