---
description: '자세한 정보: AcceptChanges 및 RejectChanges'
title: AcceptChanges 및 RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: e21952063bf27f4f969669eb76b964fc7537b59a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725261"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges 및 RejectChanges

의 데이터 변경 내용에 대 한 정확성을 확인 한 후에는 <xref:System.Data.DataTable> , 또는의 메서드를 사용 하 여 변경 내용을 적용할 수 있습니다 <xref:System.Data.DataRow.AcceptChanges%2A> .이 메서드는 <xref:System.Data.DataRow> <xref:System.Data.DataTable> <xref:System.Data.DataSet> **현재** 행 값을 **원래** 값으로 설정 하 고 **RowState** 속성을 **변경 되지 않은 상태로** 설정 합니다. 변경 내용 수락 또는 거부는 모든 **RowError** 정보를 지우고 **haserrors** 속성을 **false** 로 설정 합니다. 또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다. 자세한 내용은 [Dataadapter 사용 하 여 데이터 원본 업데이트](../updating-data-sources-with-dataadapters.md)합니다.  
  
 **DataTable** 에 foreign key 제약 조건이 있는 경우 **AcceptChanges** 및 **RejectChanges** 를 사용 하 여 적용 되거나 거부 된 변경 내용은 **ForeignKeyConstraint** 에 따라 **DataRow** 의 자식 행으로 전파 됩니다. 자세한 내용은 [DataTable 제약 조건](datatable-constraints.md)을 참조 하세요.  
  
 다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다. 해결 된 오류의 경우 **RowError** 값을 빈 문자열로 다시 설정 하 여 **haserrors** 속성을 **false** 로 설정 합니다. 오류가 발생 한 모든 행이 해결 되거나 거부 된 경우에는 **AcceptChanges** 를 호출 하 여 전체 **DataTable** 의 모든 변경 내용을 적용 합니다.  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [DataTable에서 데이터 조작](manipulating-data-in-a-datatable.md)
- [ADO.NET 개요](../ado-net-overview.md)
